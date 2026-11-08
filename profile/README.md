<p align="center">
  <img src="https://raw.githubusercontent.com/NeuroBrix/neurobrix/main/assets/logo_NeuroBrix.png" alt="NeuroBrix" width="220"/>
</p>

<h1 align="center">NeuroBrix</h1>

<p align="center">
  <strong>An open AI ecosystem, built from the tensor up.</strong><br/>
  One engine. One container format. Every modality. Your hardware: Linux, Windows and macOS.
</p>

<p align="center">
  <a href="https://neurobrix.es">Website</a> ·
  <a href="https://neurobrix.es/models">Model Hub</a> ·
  <a href="https://github.com/NeuroBrix/neurobrix">Engine</a> ·
  <a href="https://github.com/NeuroBrix/nbxtensor">nbxtensor</a> ·
  <a href="https://github.com/NeuroBrix/neurobrix-studio">Studio</a> ·
  <a href="https://github.com/NeuroBrix/triton-ext">Triton for Apple GPUs</a>
</p>

<p align="center">
  <a href="https://pypi.org/project/neurobrix/"><img src="https://img.shields.io/pypi/v/neurobrix?color=6366f1&label=neurobrix" alt="neurobrix on PyPI"/></a>
  <a href="https://pypi.org/project/nbxtensor/"><img src="https://img.shields.io/pypi/v/nbxtensor?color=0ea5e9&label=nbxtensor" alt="nbxtensor on PyPI"/></a>
  <a href="https://github.com/NeuroBrix/neurobrix/blob/main/LICENSE"><img src="https://img.shields.io/badge/license-Apache_2.0-22c55e" alt="Apache 2.0"/></a>
  <a href="https://github.com/NeuroBrix/neurobrix/stargazers"><img src="https://img.shields.io/github/stars/NeuroBrix/neurobrix?style=social" alt="Stars"/></a>
</p>

---

## Why NeuroBrix exists

Running AI on your own machine today means stacking layers you did not choose: a framework of several gigabytes, a different runtime for each kind of model, glue code between them, and a different recipe for every vendor's GPU.

NeuroBrix removes the layers. A model becomes **one `.nbx` container**: its graph, its weights and everything needed to run it. **One engine** reads that container and runs it, whatever the model is (a chat model, a speech recogniser, a voice, an image or a video generator) and whatever the hardware is. No per-model code, no glue, no hidden dependency.

What we believe:

- **AI belongs on your own hardware.** Local, private, under your control: a workstation, a laptop, a server in a closet.
- **Simple to use.** `pip install neurobrix`, import a model, run it. One command line for every modality.
- **Light.** The engine does not drag a multi-gigabyte framework behind it. Our own tensor library replaces it.
- **Open standards.** One container format and one execution model for every model family, documented and open.
- **Hardware-neutral.** Linux, Windows and macOS. Your GPU is described by a profile of facts, not by special cases in the code. NVIDIA, AMD, Intel and Apple are first-class targets.
- **Measured, never assumed.** Kernel settings are certified on real hardware, and every release is validated model by model through the real entry point, with the output looked at.

## The ecosystem

| Project | What it is | Status |
|---|---|---|
| [**NeuroBrix Engine**](https://github.com/NeuroBrix/neurobrix) | The inference engine and its CLI. It reads `.nbx` containers and runs them with two engines: a **Triton engine** built on nbxtensor, without PyTorch, and an optional PyTorch engine. Prism plans memory and placement across your GPUs; tiling splits what does not fit. | **Stable, 0.6.2** · `pip install neurobrix` |
| [**nbxtensor**](https://github.com/NeuroBrix/nbxtensor) | The torch-free tensor library behind the Triton engine: tensors, Triton kernels, planned memory and certified tuning. Runs wherever Triton runs: NVIDIA, AMD, Intel and Apple GPUs. Reactivates the tensor cores of the V100. | **Published** · `pip install nbxtensor` |
| [**NeuroBrix Studio**](https://github.com/NeuroBrix/neurobrix-studio) | The desktop application for everyone who does not live in a terminal, on Linux, Windows and macOS. A client of the engine, never a second way to run models. | In development |
| [**triton-ext (NeuroBrix build)**](https://github.com/NeuroBrix/triton-ext) | NeuroBrix's own build of Triton for Apple GPUs (Metal), tested, fixed and packaged by NeuroBrix from the upstream backend proposal ([triton-ext#126](https://github.com/triton-lang/triton-ext/pull/126)). Ships the `nbx-triton-apple` wheels, so Triton runs on Apple Silicon today. | macOS arm64 wheels |
| [**Model Hub**](https://neurobrix.es/models) | The catalogue of ready-to-run `.nbx` containers, each under its own licence, accepted once at import. | 49 models |

## Get started

```bash
pip install neurobrix                         # the light install: Triton engine, no PyTorch
neurobrix import <model>                      # from the hub at neurobrix.es/models
neurobrix run --model <model> --prompt "..."
```

On a Mac with Apple Silicon, add the Metal build of Triton once:

```bash
python -m nbxtensor install-metal
```

Want the PyTorch engine as well? `pip install "neurobrix[pytorch]"`.

## What runs today

**49 models in nine families, one engine, one command line:**

- **Language and code:** Qwen3-30B-A3B, Qwen3-Coder-30B-A3B, DeepSeek-Coder-V2-Lite, DeepSeek-MoE-16B, Granite 3.1, TinyLlama
- **Vision-language and omni:** Qwen3-Omni, Qwen3-VL, MiniCPM-o 4.5, Ming-Lite-Omni, GLM-4.1V, Janus-Pro: models that read, see, hear, speak and draw
- **Speech recognition and audio understanding:** Whisper Large, Whisper v3 Turbo, Parakeet, Canary-Qwen, Granite Speech, Voxtral
- **Speech synthesis:** Kokoro, VibeVoice, Orpheus, OpenAudio S1, Chatterbox
- **Image generation:** Sana (1K and 4K), PixArt-Σ, PixArt-α, Flex.1
- **Video generation:** Wan 2.1 and 2.2 (text, image and VACE), CogVideoX, Allegro, Open-Sora 2, SANA-Video, Mochi
- **Upscaling:** Real-ESRGAN, HAT, SwinIR, Swin2SR

Every model is validated on every release through the real entry point, on both engines, with its output looked at.

## Where we are going

NeuroBrix started as an inference engine. It will not stop there: the goal is a complete, open AI stack that you own end to end.

- **Faster than the frameworks.** Our Triton engine already beats PyTorch on many models. Next come kernel fusion, graph-level simplification (operations that cancel out are never computed) and per-model tuning until it leads everywhere.
- **Every processor.** AMD and Intel GPUs through Triton, many-core CPUs used to their last core, ARM64 laptops and phones, and accelerators beyond GPUs. Multi-GPU across NVLink, PCIe and network links, chosen from the hardware profile.
- **Community-certified hardware.** Every GPU class certified once by its owners, shared through a pull request, and never tuned again by anyone.
- **Training.** nbxtensor grows from inference into training and fine-tuning: the same library, the same certified kernels.
- **Agents.** Local agents built on the engine: coding, tools, multimodal assistants that see, hear and speak, all running on your machine.
- **Serving and integration.** A local server for your applications, a JSON interface for every command, a terminal UI, and NeuroBrix as an engine inside other tools.
- **Studio for everyone.** One installer that brings the engine, the models and a real interface to people who will never open a terminal.
- **nbxtensor 2.0 in Rust.** The tensor library rewritten in Rust for speed and safety, with the same API.
- **An open model standard.** `.nbx` as a common container for any model, any family and any hardware: one format the whole ecosystem can read.

## Contribute

Everything here is Apache 2.0 and open to contributions.

- **Certify your GPU and share it.** Run `neurobrix autotune certify` on your card and open a pull request with the `certificate` template. Every class you certify is a class nobody autotunes again. See the [engine README](https://github.com/NeuroBrix/neurobrix#certify-your-gpu-and-share-it).
- **Report what breaks** on your hardware, and **request a model** through the [engine's issues](https://github.com/NeuroBrix/neurobrix/issues/new/choose).
- **Code:** read the [contributing guide](https://github.com/NeuroBrix/neurobrix/blob/main/CONTRIBUTING.md).

Built on open source and giving back to it: [Triton](https://github.com/triton-lang/triton), [triton-ext](https://github.com/triton-lang/triton-ext), and the authors of every model on the hub. We send our fixes upstream.

---

<p align="center">
  <sub>© 2025–2026 Hocine Benkelaya. NeuroBrix engine released under the Apache License 2.0.<br>Developed by <a href="https://www.linkedin.com/in/hocine-benkelaya/">Hocine Benkelaya</a> · Supported and funded by <a href="https://neuralnetworkholding.com">Neural Network Holding Ltd</a> · Commercial distribution by <a href="https://wizworks.io">WizWorks OÜ</a></sub>
</p>
