<p align="center">
  <img src="https://raw.githubusercontent.com/NeuroBrix/neurobrix/main/assets/logo.svg" alt="NeuroBrix Logo" width="240"/>
</p>

<h1 align="center">NeuroBrix</h1>

<p align="center">
  <strong>The Universal AI Runtime</strong><br/>
  Run any model. Any modality. Any hardware. One engine.
</p>

<p align="center">
  <a href="https://neurobrix.es">Website</a> &nbsp;|&nbsp;
  <a href="https://github.com/NeuroBrix/neurobrix">GitHub</a> &nbsp;|&nbsp;
  <a href="https://neurobrix.es/models">Model Hub</a> &nbsp;|&nbsp;
  <a href="https://pypi.org/project/neurobrix/">PyPI</a> &nbsp;|&nbsp;
  <a href="https://github.com/NeuroBrix/neurobrix/blob/main/ROADMAP.md">Roadmap</a>
</p>

<p align="center">
  <a href="https://pypi.org/project/neurobrix/"><img src="https://img.shields.io/pypi/v/neurobrix?include_prereleases&color=6366f1&label=PyPI" alt="PyPI"/></a>
  <a href="https://github.com/NeuroBrix/neurobrix/blob/main/LICENSE"><img src="https://img.shields.io/badge/License-Apache_2.0-green" alt="License"/></a>
  <a href="https://github.com/NeuroBrix/neurobrix/stargazers"><img src="https://img.shields.io/github/stars/NeuroBrix/neurobrix?style=social" alt="Stars"/></a>
</p>

---

## Why NeuroBrix Exists

The AI ecosystem is fragmented. Want to run a diffusion model? Learn ComfyUI. Need an LLM? Choose between Ollama, vLLM, or llama.cpp. Audio model? Another tool. Video? Yet another. Every modality lives in its own silo with its own stack.

**NeuroBrix unifies all of it.**

One runtime that executes **any** AI model — image generation, language models, audio, video, vision-language, upscalers, embeddings — through a single CLI, a single container format, and a single hardware allocation engine.

| | Ollama | ComfyUI | vLLM | llama.cpp | **NeuroBrix** |
|---|:---:|:---:|:---:|:---:|:---:|
| LLMs | Yes | -- | Yes | Yes | **Yes** |
| Image Generation | -- | Yes | -- | -- | **Yes** |
| Video | -- | Partial | -- | -- | **Yes** |
| Audio / TTS / STT | -- | -- | -- | Yes | **Yes** |
| Vision-Language | -- | -- | Partial | Partial | **Yes** |
| Multi-GPU Auto-Allocation | -- | -- | Yes | -- | **Yes** |
| Universal Model Format | -- | -- | -- | GGUF (LLM) | **NBX (any)** |
| Framework-Independent | -- | -- | -- | Yes | **Yes** |
| Zero Model-Specific Code | -- | -- | -- | -- | **Yes** |

## How It Works

```bash
pip install neurobrix

neurobrix import sana/1600m-1024          # Download from NeuroBrix Hub
neurobrix serve --model 1600m-1024 \      # Load once, keep warm
               --hardware v100-32g
neurobrix run --prompt "A sunset"         # Instant inference
neurobrix stop                            # Free VRAM
```

Models are packaged as `.nbx` containers — self-contained archives with the full computation graph, weights, topology, and runtime configuration. The **Prism solver** reads your hardware profile and automatically selects the optimal execution strategy (single GPU, pipeline parallel, tensor parallel, MoE distribution, CPU offload).

The runtime has **zero domain knowledge**. It doesn't know what an "image" or "token" is. It sees tensors, operations, and execution plans. This is what makes it truly universal.

## Available Now

**Image Generation**: PixArt-Sigma, Sana 1600M, FLUX.2-dev, Flex.1-alpha, Janus-Pro-7B
**Language Models**: DeepSeek-MoE-16B, Qwen3-30B-A3B-Thinking
**Coming Soon**: Video (Wan2.2, LTX-Video), Audio (Whisper, TTS), VLMs, Upscalers, Apple Silicon, Desktop GUI

Browse the full catalog: **[neurobrix.es/models](https://neurobrix.es/models)**

## Projects

| Repository | Description | Status |
|---|---|---|
| [**neurobrix**](https://github.com/NeuroBrix/neurobrix) | Core runtime, CLI, Prism solver, kernel library | Public Beta |
| **NeuroBrix Studio** | Desktop GUI (Tauri + Vue.js) | Coming Q4 2026 |

## Programs

### Hardware Integration
GPU manufacturers and accelerator vendors — get your hardware natively supported. We're building backends for NVIDIA, Apple Silicon (MLX), AMD ROCm, Intel, and Chinese AI accelerators.

> **partners@neurobrix.es** — Hardware partnership inquiries

### Model Registry
AI labs and model publishers — make your model available as a `.nbx` container on the NeuroBrix Hub. We handle conversion and ensure optimal execution across all supported hardware.

> **models@neurobrix.es** — Model publishing inquiries

## Contributing

NeuroBrix is open source under **Apache 2.0**. We welcome contributions in runtime development, kernel engineering, hardware backends, documentation, and testing.

Read the [Contributing Guide](https://github.com/NeuroBrix/neurobrix/blob/main/CONTRIBUTING.md) or browse [open issues](https://github.com/NeuroBrix/neurobrix/issues).

## About

NeuroBrix is developed by [**WizWorks OÜ**](https://wizworks.io), a property of [**Neural Networks Holding LTD**](https://neuralnetworkholding.com).

---

<p align="center">
  <sub>Apache 2.0 License &middot; &copy; 2025–2026 Neural Networks Holding LTD</sub>
</p>
