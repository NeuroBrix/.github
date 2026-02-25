<p align="center">
  <img src="https://raw.githubusercontent.com/NeuroBrix/neurobrix/main/assets/logo.svg" alt="NeuroBrix Logo" width="120"/>
</p>

<h1 align="center">NeuroBrix</h1>

<p align="center">
  <strong>Universal AI Runtime — Execute Any Model on Any Hardware</strong>
</p>

<p align="center">
  <a href="https://neurobrix.es">Website</a> •
    <a href="https://github.com/NeuroBrix/neurobrix">Runtime</a> •
      <a href="https://neurobrix.es/docs">Documentation</a>
</p>

---

## What is NeuroBrix?

NeuroBrix is a **universal inference engine** that runs any AI model on any hardware — from cloud data centers to legacy GPUs.

Our philosophy is simple: **a neural network is just a graph of mathematical operations**. The runtime loads the graph, the GPU executes it, and you get your result. No framework lock-in. No vendor dependencies. Just pure execution.

## Why NeuroBrix?

| Challenge | NeuroBrix Solution |
|-----------|-------------------|
| Models tied to specific frameworks | **Model-agnostic** — runs any architecture |
| Hardware vendor lock-in | **Hardware-agnostic** — NVIDIA, AMD, Intel, Apple Silicon |
| Complex deployment pipelines | **Single `.nbx` file** — download and run |
| Performance varies by setup | **Optimized execution** — cloud clusters to older GPUs |

## The `.nbx` Format

Models are packaged as `.nbx` containers — a universal format containing everything needed for execution:

```
model.nbx
├── manifest.json      # Model metadata
├── topology.json      # Execution graph
├── components/        # Neural network layers
└── modules/           # Tokenizers, schedulers
```

Download models from the [NeuroBrix Models](https://neurobrix.es/models) and run them instantly.

## Supported Families

- **Image Generation** — Diffusion models (PixArt, Sana, Flux)
- **Language Models** — LLMs (DeepSeek, Llama, Mistral)
- **Audio** — Speech models (Whisper)
- **Video** — Video generation (CogVideoX)

## Quick Start

```bash
pip install neurobrix

# Run image generation
neurobrix run --model PixArt-Sigma-XL --prompt "A sunset over mountains"

# Run language model
neurobrix run --model deepseek-moe-16b --prompt "Explain quantum computing"
```

## Projects

| Repository | Description |
|------------|-------------|
| [neurobrix](https://github.com/NeuroBrix/neurobrix) | Core runtime and inference engine |

## A WizWorks OÜ Project

NeuroBrix is developed and maintained by [WizWorks OÜ](https://wizworks.io), a property of [Neural Networks Holding LTD](https://neuralnetworkholding.com).

---

<p align="center">
  <sub>© 2026 WizWorks OÜ • Apache 2.0 License</sub>
</p>
