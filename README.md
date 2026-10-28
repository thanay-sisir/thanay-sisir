# Thanay Sisir Anabathula

I'm doing my M.Eng. in Systems Engineering at the **University of Virginia** (graduating May 2027). Before that I did a B.Tech. in Computer Science with a minor in AI/ML at JNTU Hyderabad, India

Most of what I build is around **AI agents, evals, LLM inference, sandboxed execution, and model training**. I'm looking for **New Grad 2027** roles in that space, including AI research engineering and forward-deployed engineering, and I can start full-time in June 2027.

## What I'm working on

**Research Assistant, UVA Darden School of Business** (May 2026 to present)
I build data pipelines that turn messy, unstructured data into something faculty, deans and a Federal Reserve economist can actually do research on. That has meant pulling liability and joint-venture disclosures for 250+ BDCs out of SEC 10-K/10-Q filings, and fuzzy-matching hedge fund managers across 7 TB of voter registration data.

**Graduate Student Worker, UVA Engineering Link Lab** (Feb 2026 to May 2026)
Worked with Prof. B. Brian Park on EV fleet telematics, engineering battery-capacity features to classify degradation tiers. Partial-charge-based estimation turned out to be the strongest predictor.

## Projects

**[SentinelSRE](https://github.com/thanay-sisir/sentinelsre)**, an autonomous incident-response agent
A LangGraph agent with 21 typed tools that runs against a small multi-service FastAPI platform. 15 tools are read-only. The other 6 can change things, but only after a deterministic policy engine approves the step and issues a single-use HMAC token. It resolved an injected outage in about 90 seconds, traced end to end in LangSmith. Each run has hard budgets (15 model turns, 35 tool calls, timeouts on every LLM call). I also built a Harbor eval where an independent verifier grades the real outcome and penalizes cheating. It scored 1.0 in a LangSmith cloud sandbox and caught 2 failure modes my local tests had missed. 83 tests run in CI on Linux and Windows.

**[Synthetic Data Generator for a Coding LLM](https://github.com/thanay-sisir/Synthetic-data-generator-for-coding-LLM)**
An execution-verified data pipeline for Triton GPU kernels. Teacher-model workers write kernels, an AST check screens them, and an Apptainer GPU sandbox on A100s runs each one against a PyTorch reference. Only the 1,894 kernels that match are kept. I fine-tuned Qwen3.8-27B with LoRA on a single A100 through Slurm, which took the held-out pass rate on unseen operation families from 44.8% to 98.2%. Served with vLLM at 10.3 s p50 latency and 101.9 tokens/s. For comparison, a 0.5B LoRA model got 12.3% and a 29.5M Transformer trained from scratch got 0%.

**[Continuous Thought Machines](https://github.com/SakanaAI/continuous-thought-machines)** (SakanaAI, open source contribution)
Got a performance fix merged that vectorizes the maze-loss masking in PyTorch, replacing a per-example Python loop with batched tensor ops and cutting mask storage from B×R×T to B×R. Losses and gradients match the original exactly across 16 test configurations.

## Tech stack

**AI/ML:** LoRA/PEFT fine-tuning, GPU training, agentic workflows, tool calling, evals<br>
**Inference and infra:** vLLM, latency and throughput benchmarking, Docker, Apptainer (GPU sandboxing)<br>
**Libraries:** Python, PyTorch, LangChain, LangGraph, LangSmith, Harbor, FastAPI, Pydantic<br>
**Engineering:** Git, GitHub Actions CI, Azure, Cursor, Claude Code

## Find me

[Portfolio](https://thanaysisir.vercel.app/index.html) · [X](https://x.com/ThanaysisirA) · anabathula.thanaysisir@gmail.com

Outside of work, I like trying new AI tools as they launch, because they take care of the repetitive stuff and leave more time for the work that actually matters.
