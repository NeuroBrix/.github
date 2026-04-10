<p align="center">
  <img src="https://raw.githubusercontent.com/NeuroBrix/neurobrix/main/assets/logo_NeuroBrix.png" alt="NeuroBrix Logo" width="240"/>
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
  <a href="https://pypi.org/project/neurobrix/">PyPI</a>
</p>

<p align="center">
  <a href="https://pypi.org/project/neurobrix/"><img src="https://img.shields.io/pypi/v/neurobrix?include_prereleases&color=6366f1&label=PyPI" alt="PyPI"/></a>
  <a href="https://github.com/NeuroBrix/neurobrix/blob/main/LICENSE"><img src="https://img.shields.io/badge/License-Apache_2.0-green" alt="License"/></a>
  <a href="https://github.com/NeuroBrix/neurobrix/stargazers"><img src="https://img.shields.io/github/stars/NeuroBrix/neurobrix?style=social" alt="Stars"/></a>
</p>

---

## What Is NeuroBrix

One runtime that executes **any** AI model — image generation, language models, audio, video, vision-language — through a single CLI, a single container format (`.nbx`), and automatic hardware allocation.

```bash
pip install neurobrix
neurobrix import sana/1600m-1024 --no-keep
neurobrix run --model Sana_1600M_1024px_MultiLing --prompt "A sunset over mountains"
```

**Runs on Linux, Windows, and macOS.** Auto-detects your GPU.

| | Ollama | ComfyUI | vLLM | **NeuroBrix** |
|---|:---:|:---:|:---:|:---:|
| LLMs | Yes | -- | Yes | **Yes** |
| Image Generation | -- | Yes | -- | **Yes** |
| Video Generation | -- | -- | -- | **Yes** |
| Audio (STT + TTS) | -- | -- | -- | **Yes** |
| Multi-GPU Auto-Allocation | -- | -- | Yes | **Yes** |
| Universal Model Format | -- | -- | -- | **NBX (any)** |
| Cross-Platform | Yes | -- | -- | **Yes** |

## Supported Models (30+)

**Image:** Sana (1K/4K), PixArt-Alpha, PixArt-Sigma, Flex.1-alpha, Janus-Pro-7B
**Video:** SANA-Video 720p
**Audio:** Whisper, Whisper V3 Turbo, Parakeet, Canary-Qwen, Granite Speech, Voxtral, Orpheus, Kokoro, VibeVoice, OpenAudio S1, Chatterbox
**LLM:** DeepSeek-MoE-16B, Qwen3-30B-A3B, TinyLlama

Browse: **[neurobrix.es/models](https://neurobrix.es/models)**

## Projects

| Repository | Description | Status |
|---|---|---|
| [**neurobrix**](https://github.com/NeuroBrix/neurobrix) | Core runtime, CLI, Prism solver, NBX format | Public Alpha |
| **NeuroBrix Studio** | Desktop GUI | Planned |

## Contributing

Apache 2.0 — contributions welcome. See the [Contributing Guide](https://github.com/NeuroBrix/neurobrix/blob/main/CONTRIBUTING.md).

---

<p align="center">
  <sub>&copy; 2025-2026 Neural Networks Holding LTD &middot; Developed by <a href="https://wizworks.io">WizWorks OÜ</a></sub>
</p>
