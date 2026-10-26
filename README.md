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
sbatch -p cuda13pr.120h --time=5-00:00:00 \
    --gpus=nvidia_rtx_pro_6000:1 --gres=gpumem:96g \
    --cpus-per-task=4 --mem-per-cpu=8G --tmp=100G \
    --job-name=agent-node --wrap="sleep infinity"
```

## Claude Code

- Memory and `CLAUDE.md` files: https://code.claude.com/docs/en/memory
