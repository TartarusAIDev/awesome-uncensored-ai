# Awesome Uncensored AI [![Awesome](https://awesome.re/badge-flat2.svg)](https://awesome.re)

> A curated list of uncensored and locally-runnable AI: coding agents, model
> runners, uncensoring techniques, and the tooling around them.

Mainstream assistants refuse a large and growing share of legitimate technical
requests: security research, red-teaming, low-level systems code, scraping,
content other people find distasteful. This list collects the tools that do not.

Everything here is open source or self-hostable unless marked **hosted**.

## Contents

- [Coding agents](#coding-agents)
- [Model runners](#model-runners)
- [Uncensoring techniques](#uncensoring-techniques)
- [Finding models](#finding-models)
- [Self-hosting and hardware](#self-hosting-and-hardware)
- [Reading](#reading)
- [Contributing](#contributing)

## Coding agents

Terminal- and editor-based agents that read, write and run code.

- **[Tartarus](https://tartarusai.dev)** **(hosted)** — Uncensored coding agent.
  CLI (`pip install tartarus-console`) plus an OpenAI-compatible API on a hosted
  model. Ships code instead of refusals; crypto-only billing, no KYC.
- [Aider](https://github.com/Aider-AI/aider) — Pair-programming in your terminal;
  bring your own model (local or hosted).
- [OpenHands](https://github.com/All-Hands-AI/OpenHands) — Autonomous software
  agent; runs any OpenAI-compatible backend.
- [Cline](https://github.com/cline/cline) — Agentic coding inside VS Code; works
  with local and self-hosted endpoints.
- [Continue](https://github.com/continuedev/continue) — Open-source IDE
  autocomplete and chat; point it at any model.

## Model runners

Run models locally, or serve them behind an OpenAI-compatible endpoint.

- [llama.cpp](https://github.com/ggml-org/llama.cpp) — The reference CPU/GPU
  inference engine; `llama-server` exposes an OpenAI-compatible API.
- [Ollama](https://github.com/ollama/ollama) — One-command local models.
- [vLLM](https://github.com/vllm-project/vllm) — High-throughput GPU serving.
- [LM Studio](https://lmstudio.ai) — Desktop app with a local server.
- [text-generation-webui](https://github.com/oobabooga/text-generation-webui) —
  Batteries-included local UI and API.
- [KoboldCpp](https://github.com/LostRuins/koboldcpp) — Single-binary llama.cpp
  wrapper with a built-in API.

## Uncensoring techniques

How refusal behaviour is removed or bypassed, for research.

- **Abliteration** — Refusal in instruction-tuned models is largely mediated by
  a single direction in activation space; zeroing it out suppresses refusals
  without retraining (Arditi et al., 2024). Community "abliterated" variants of
  popular open models apply this.
- **Fine-tuning / DPO** — Preference tuning on compliant responses to override
  safety alignment.
- **System-prompt and decoding steering** — Weaker, prompt-level methods that do
  not touch weights.

## Finding models

- [Hugging Face: "abliterated"](https://huggingface.co/models?search=abliterated)
  — community-uncensored variants of open models.
- [Hugging Face: "uncensored"](https://huggingface.co/models?search=uncensored)
  — fine-tuned uncensored models.
- Prefer GGUF quantizations (Q4_K_M and up) for llama.cpp / Ollama.

## Self-hosting and hardware

- A 30B mixture-of-experts model at Q4 fits in ~18-20 GB of VRAM; two 24 GB
  consumer GPUs run it comfortably with long context.
- Memory bandwidth, not FLOPs, is the usual bottleneck for single-user
  inference; size your GPU by VRAM and bandwidth first.
- Rent by the hour (vast.ai, RunPod, Lambda) before buying.

## Reading

- "Refusal in Language Models Is Mediated by a Single Direction" — Arditi et al.,
  2024. The paper behind abliteration.
- llama.cpp [server docs](https://github.com/ggml-org/llama.cpp/blob/master/tools/server/README.md)
  — OpenAI-compatible endpoint reference.

## Contributing

PRs welcome. One entry per line, alphabetical within a section, a one-line
description, and a working link. See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](LICENSE)

To the extent possible under law, the contributors have waived all copyright and
related rights to this work.
