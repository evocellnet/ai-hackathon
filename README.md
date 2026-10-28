# ai-hackathon

A week-long hackathon run by the Beltrao lab (ETH Zürich), Colm Ryan lab (UCD), Emanuel Gonçalves lab (IST) and Christophe Dessimoz lab (UNIL) to assess the bioinformatics capabilities of agentic AI. Each project gives Claude (Opus 5.5, delegating to Opus/Sonnet subagents) a "predict X" problem and lets it build, benchmark and write up a method with minimal human intervention. Humans then verify the methodology and benchmarking. Projects run on Euler, each in its own sub-folder of the shared project space, with common large datasets (e.g. AlphaFold DB, PDB) stored once in a read-only location.

## Projects

- Cancer essentiality prediction: [ai-hackathon-cancer_essentiality](https://github.com/QuantitativeBiology/ai-hackathon-cancer_essentiality) — predicting CRISPR-Cas9 gene essentiality in cancer cell lines from molecular profiles (DepMap 26Q3)
- Cancer genome-scale metabolic model: [Cancer metabolic model](https://github.com/QuantitativeBiology/ai-hackathon-humangem) — Predicting cancer context specific the human genome-scale metabolic models
- Co-complex membership from Coessentiality: ([Coessentiality](https://github.com/cancergenetics/ai-hackathon-Coessentiality)  — Predicting human co-complex membership from co-essentiality
- Trans-transcriptomic consequences of CNV: ([DepMapTR](https://github.com/cancergenetics/ai-hackathon-DepMapRegulation/)  — Predicting trans-transcriptomic consequences of copy-number change
- Pocket prediction: [burrow](https://github.com/zoidpuff/pocket-detect-agents) — BURROW, fast protein ligand-binding pocket detection and ranking
- Ligand docking: [ADock](https://github.com/juliabuhmann/adock) — ADock is a protein–ligand docking engine for GPU 
- Pocket similarity: [pocketcompare](https://github.com/zoidpuff/pocketcompare-agents) — pocketcompare creates fast, ligand-free fingerprints as descriptors of protein binding pockets.
- Kinase targets: [agentKinaseSubPred](https://github.com/JulianvanGerwen/agentKinaseSubPred) — Predicting human kinase targets 
- Kinase activity
- Protein stability [physDDG](https://github.com/DennisGankin/physDDG) — physDDG - physics-inspired protein mutation stability predictor
- Coloc analysis
- Orthology prediction: [Ancestra](https://github.com/evocellnet/hackathon-p10-orthology-prediction) — Ancestra infers hierarchical orthologous groups (HOGs) from a set of proteomes
- MS analysis

## AI disclosure header

Each project repository and report starts with a human-written disclosure:

> (Human-written text starts)
>
> This is an exercise in assessing the bioinformatics capabilities of agentic AI. It is part of a hackathon run by the Beltrao lab at ETH Zurich, where we used Claude to run bioinformatics projects (https://github.com/evocellnet/ai-hackathon/). All results in this project were generated entirely by AI with minimal human intervention. This is not intended to be viewed as a traditional publication and bioinformatics tool.
>
> [Project-specific text, e.g.] The goal of this specific project was to create a predictive model for substrates of human protein kinases. It was executed by Claude Opus 5.5 with delegation to Opus 5.5/Sonnet 5.5 subagents, and finished within 24 hours on a computational cluster with XXX resources [optional, e.g. 128 GB RAM and 4 RTX4090 GPUs].
>
> Currently none of the results have been verified by a human. We plan to verify the agent's methodology and benchmarking, and we will update this section accordingly.
>
> The rest of this repository is entirely AI generated. It includes code for implementation of the predictive model and an AI-written report in the style of a journal article, detailing the final method, the path followed to reach it, and benchmarking against other methods.
>
> (Human-written text ends)

For Euler setup notes, see [EULER.md](EULER.md).
