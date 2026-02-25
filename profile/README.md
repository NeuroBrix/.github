<p align="center">
  <img src="https://raw.githubusercontent.com/NeuroBrix/neurobrix/main/assets/logo.svg" alt="NeuroBrix Logo" width="200"/>
</p>

<h1 align="center">NeuroBrix</h1>

<p align="center">
  <strong>Universal AI Runtime — Run &amp; Train Any Model on Any Hardware</strong>
</p>

<p align="center">
  <a href="https://neurobrix.es">Website</a> ·
  <a href="https://github.com/NeuroBrix/neurobrix">Runtime</a> ·
  <a href="https://neurobrix.es/models">Model Hub</a> ·
  <a href="https://neurobrix.es/docs">Documentation</a>
</p>

<p align="center">
  <a href="https://pypi.org/project/neurobrix/"><img src="https://img.shields.io/pypi/v/neurobrix?include_prereleases&color=6366f1&label=PyPI" alt="PyPI"/></a>
  <a href="https://github.com/NeuroBrix/neurobrix/blob/main/LICENSE"><img src="https://img.shields.io/badge/License-Apache_2.0-green" alt="License"/></a>
  <a href="https://neurobrix.es/models"><img src="https://img.shields.io/badge/Models-NeuroBrix_Hub-orange" alt="Hub"/></a>
</p>

---

## The Problem

Today's AI ecosystem is fragmented. Every model requires its own framework, every GPU vendor demands its own toolchain, and deploying a model means navigating a maze of dependencies, conversions, and vendor lock-in.

**What if none of that mattered?**

## Our Mission

NeuroBrix is building the **universal runtime for artificial intelligence** — a single engine that executes and trains any AI model on any hardware, from any vendor.

A neural network is just a graph of mathematical operations. The runtime loads the graph. The hardware executes it. You get your result. **No framework lock-in. No vendor dependencies. No model-specific code.**

### Core Principles

| Principle | Description |
|---|---|
| **ZERO HARDCODE** | All values derived from the model container. Nothing hardcoded in the engine. |
| **ZERO FALLBACK** | The system crashes explicitly if data is missing. No silent defaults. |
| **ZERO SEMANTIC** | The runtime has no domain knowledge. Only tensors and execution plans. |

## What NeuroBrix Does

### Universal Inference *(Available Now — Public Beta)*
Execute any AI model architecture through a single, unified runtime:

- **Image Generation** — Diffusion Transformers (FLUX, PixArt-Sigma, Sana), VQ models (Janus-Pro)
- **Language Models** — Autoregressive LLMs with MoE support (DeepSeek, Qwen, Llama, Mistral)
- **Audio** — Speech recognition (Whisper)
- **Video** — Video generation (CogVideoX)

### Universal Training *(Roadmap)*
Train and fine-tune models using the same hardware-agnostic engine. One training loop, any architecture, any GPU.

### The `.nbx` Container Format
Models are packaged as `.nbx` containers — a **vendor-neutral, self-describing format** containing everything needed for execution: computation graph, weights, topology, metadata. Download from the [NeuroBrix Hub](https://neurobrix.es/models) and run instantly.

```
model.nbx
├── manifest.json       # Model metadata & shapes
├── topology.json       # Execution flow definition
├── components/         # Neural network layers as TensorDAGs
└── modules/            # Tokenizers, schedulers, processors
```

### Hardware-Agnostic Execution
The **Prism Solver** automatically analyzes your hardware and selects the optimal execution strategy — single GPU, pipeline parallelism, tensor parallelism, MoE expert distribution, or CPU offload. No manual configuration.

## Quick Start

```bash
pip install neurobrix

# Browse and download models
neurobrix hub
neurobrix import pixart/sigma-xl-1024

# Serve with automatic hardware optimization
neurobrix serve --model sigma-xl-1024 --hardware v100-32g

# Generate
neurobrix run --model sigma-xl-1024 --prompt "a sunset over mountains"
```

## Projects

| Repository | Description |
|---|---|
| [**neurobrix**](https://github.com/NeuroBrix/neurobrix) | Core runtime engine, CLI, Prism solver, Triton kernels |

## Hardware Integration Program

**GPU and accelerator manufacturers** — if you want your hardware natively supported by NeuroBrix, we want to hear from you. We are actively building backend support for hardware beyond NVIDIA and welcome partnerships with chip designers and hardware vendors of all sizes.

> 📧 **partners@neurobrix.es** — Hardware integration inquiries

## Model Registry Program

**AI labs and model publishers** — if you want your model available on the NeuroBrix Hub, reach out. We handle the conversion to `.nbx` format and ensure optimal execution across all supported hardware. Your model, instantly deployable everywhere.

> 📧 **models@neurobrix.es** — Model publishing inquiries

## Contributing

NeuroBrix is open source under Apache 2.0 and we welcome contributions from the community.

Whether you're a kernel engineer, a runtime developer, an ML researcher, or someone passionate about making AI more accessible — there's a place for you here.

- 🔧 **Runtime & Kernels** — Triton kernels, execution engine, memory optimization
- 🧩 **Model Support** — New architectures, topology definitions, component graphs
- 🔌 **Hardware Backends** — New GPU/accelerator support, driver integrations
- 📖 **Documentation** — Guides, tutorials, API reference
- 🧪 **Testing** — Validation, benchmarks, edge case coverage

**Get started:** Read the [contribution guide](https://github.com/NeuroBrix/neurobrix/blob/main/CONTRIBUTING.md) or jump straight into [open issues](https://github.com/NeuroBrix/neurobrix/issues).

## Support the Project

NeuroBrix is an independent, bootstrapped project. If you believe in a future where AI runs everywhere without vendor lock-in, consider supporting our work.

<p align="center">
  <a href="https://github.com/sponsors/NeuroBrix"><img src="https://img.shields.io/badge/GitHub_Sponsors-Support_NeuroBrix-ea4aaa?logo=github" alt="GitHub Sponsors"/></a>
  <a href="https://opencollective.com/neurobrix"><img src="https://img.shields.io/badge/Open_Collective-Contribute-7fadf2?logo=opencollective" alt="Open Collective"/></a>
</p>

**Enterprise sponsors** — we offer priority support, dedicated hardware integration, and co-development partnerships. Contact us at **sponsors@neurobrix.es**.

**Crypto donations** are accepted via Open Collective and dedicated wallet addresses listed on our [funding page](https://neurobrix.es/funding).

## About

NeuroBrix is developed and maintained by [**WizWorks OÜ**](https://wizworks.io), a property of [**Neural Networks Holding LTD**](https://neuralnetworkholding.com).

---

<p align="center">
  <sub>© 2025 – 2026 WizWorks OÜ · Apache 2.0 License</sub>
</p>
