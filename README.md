# ai-hackathon

## Setting up Euler

- Set up passwordless SSH login: https://docs.hpc.ethz.ch/connections/ssh/
- Use `euler-tunnel` to connect directly to batch nodes: https://docs.hpc.ethz.ch/connections/euler-tunnel/
- Set up GitHub access with a personal access token: https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens

## Shared data

The directory `/cluster/work/beltrao/shared` on Euler contains:

| Directory | Contents | Status |
|---|---|---|
| `alphafold/` | Copy of the AlphaFold database | Finished |
| `rsyncPDB/` | Copy of the PDB | Still running |

## Requesting a GPU node

Request a powerful node early, because it takes some time for the scheduler to allocate it:

```bash
sbatch --account=es_biol --time=5-00:00:00 \
    --gpus=nvidia_rtx_pro_6000:1 --gres=gpumem:96g \
    --cpus-per-task=4 --mem-per-cpu=8G --tmp=100G \
    --job-name=agent-node --wrap="sleep infinity"
```

Always pass `--account=es_biol` explicitly. The default account only has access to a very limited number of GPUs, so jobs without it can wait a long time.

Euler has many more RTX 3090 (32 nodes) and RTX 4090 (80 nodes) than RTX PRO 6000 (10 nodes), so a job requesting one of those is usually allocated sooner. They have 24 GB of GPU memory instead of 96 GB. To get whichever is free first, replace the `--gpus` line with `--gpus=rtx_3090,rtx_4090:1` and drop `--gres=gpumem:96g`. For all GPU types, see https://docs.hpc.ethz.ch/hardware/gpu_nodes/

Euler's Slurm batch settings (partitions, GPU types, resource options): https://docs.hpc.ethz.ch/batchsystem/slurm/

## Claude Code

- Memory and `CLAUDE.md` files: https://code.claude.com/docs/en/memory

### Sandboxed Claude Code on Euler

Three options for running Claude Code inside a Singularity/Apptainer container on a compute node, so it can run without permission prompts:

- [euler-vibe](https://github.com/jurgjn/euler-vibe/): `euler-claude` starts Claude in a container, in a tmux session per project directory
- [vibe-tunnel](https://github.com/DennisGankin/vibe-tunnel): VS Code + Claude Code in a container, opened from your laptop with one command; shared lab installation at `/cluster/project/beltrao/software/vibe-tunnel`
- [euler_agents](https://github.com/juliabuhmann/euler_agents): `euler-agent-run` with explicit read-write and read-only mounts; optionally hand off the session to claude.ai/code or the mobile app
