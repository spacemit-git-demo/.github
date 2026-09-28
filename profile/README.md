<div align="center">

<img src="https://cdn-resource.spacemit.com/file/officialweb/assets/logo_white.svg" width="700" alt="SpacemiT logo" />

# SpacemiT



> Fast, open, and production-ready RISC-V silicon for AI edge computing.  
> K1 & K3 SoCs with **mainline Linux, GCC, LLVM, and Binutils** — no vendor lock-in.

[![Linux Mainline](https://img.shields.io/badge/Linux%20Kernel-Mainline-6aa82e?logo=linux&logoColor=white)](https://github.com/spacemit-com/linux/wiki)
[![GCC / LLVM Mainline](https://img.shields.io/badge/GCC%20%2F%20LLVM-Mainline-6aa82e)](https://github.com/spacemit-com/.github/blob/main/upstream-status/toolchain.md)
[![License Apache-2.0](https://img.shields.io/badge/License-Apache--2.0-AEDC3C)](https://www.apache.org/licenses/LICENSE-2.0)
[![RISC-V K1 K3](https://img.shields.io/badge/RISC--V-K1%20%7C%20K3-8DC63F?logo=riscv&logoColor=white)](https://www.spacemit.com)
[![Forum](https://img.shields.io/badge/Forum-spacemit.com-brightgreen)](https://forum.spacemit.com)

---
</div>

## Start Here

| Goal | Repository | Notes |
|---|---|---|
| **Flash Ubuntu onto K3** | [K3-Ubuntu-Images](https://github.com/spacemit-com/K3-Ubuntu-Images) | Prebuilt releases, fastboot & Titantools guide |
| **Run AI inference** | [ai-sdk](https://github.com/spacemit-com/ai-sdk) | Vision / ASR / TTS / VAD / LLM / VLM, C++ & Python |
| **Deploy a local LLM** | [model-zoo-llm](https://github.com/spacemit-com/model-zoo-llm) | Qwen, GLM, Deepseek in GGUF via llama.cpp |
| **Quantize an ONNX model** | [xslim](https://github.com/spacemit-com/xslim) | `pip install xslim` · INT8/FP16 PTQ · Apache-2.0 |
| **Use Triton on RISC-V** | [spine-triton](https://github.com/spacemit-com/spine-triton) | RVV 1.0, IME, AME · MIT · 35 contributors |
| **Build the Linux kernel** | [linux-6.6](https://github.com/spacemit-com/linux-6.6) (K1) · [linux-6.18](https://github.com/spacemit-com/linux-6.18) (K3) | Both mainlined upstream |
| **Get the toolchain** | [archive.spacemit.com](https://archive.spacemit.com/) | Prebuilt for x86_64 and aarch64 hosts |
| **Read chip docs** | [docs-chip](https://github.com/spacemit-com/docs-chip) · [spacemit.com/docs](https://www.spacemit.com/community/document) | Registers, peripherals, clocks |

---

## 📡 Upstream Status

K1 and K3 support is shipping in mainline open-source projects. No vendor branch required for the toolchain or kernel.

| Project | K1 | K3 | Updated | Details |
|---|---|---|---|---|
| **Linux kernel** | ✅ Mainline | ✅ Mainline | 2026-09-09 | [wiki](https://github.com/spacemit-com/linux/wiki) |
| **GCC** | ✅ Mainline | ✅ Mainline | 2026-09-01 | [details](https://github.com/spacemit-com/.github/blob/main/upstream-status/toolchain.md) |
| **LLVM** | ✅ Mainline | ✅ Mainline | 2026-07-01 | [details](https://github.com/spacemit-com/.github/blob/main/upstream-status/toolchain.md) |
| **Binutils** | ✅ Mainline | ✅ Mainline | 2026-09-01 | [details](https://github.com/spacemit-com/.github/blob/main/upstream-status/toolchain.md) |
| **OpenSBI** | ✅ Completed | 🔄 Planning | 2026-07-07 | [wiki](https://github.com/spacemit-com/opensbi-upstream/wiki) |
| **U-Boot** | 🔄 WIP | 🔄 Planning | 2026-09-07 | [wiki](https://github.com/spacemit-com/u-boot/wiki) |
| **llama.cpp** | 🔄 WIP | 🔄 WIP | 2026-06-05 | [wiki](https://github.com/spacemit-com/llama.cpp/wiki) |
| **FlagGems** | 🔄 WIP | 🔄 WIP | 2026-06-05 | [wiki](https://github.com/spacemit-com/spine-FlagGems/wiki) |

> Full patch links and per-module details: [upstream-status/toolchain.md](https://github.com/spacemit-com/.github/blob/main/upstream-status/toolchain.md)

---

## 🧠 AI Agent Computer Projects

SpacemiT K1 and K3 are built for agentic AI workloads — long-horizon reasoning, multi-modal perception, and real-time decision loops — running fully on the edge with no cloud dependency.

```
┌──────────────────────────────────────────────────────────┐
│                 AI Agent Application                     │
│         (vision + speech + LLM + action planning)        │
└───────────────────┬──────────────────────────────────────┘
                    │
┌───────────────────▼──────────────────────────────────────┐
│                      ai-sdk                              │
│    vision · asr · tts · vad · llm · vlm  (C++/Python)   │
└─────┬──────────────┬────────────────┬────────────────────┘
      │              │                │
onnxruntime     llama.cpp       spine-triton
SpacemiT EP     GGUF models     Triton/RVV/IME/AME
      │
   xslim  ←  INT8 / FP16 post-training quantization
```

| Repository | What it does | Status |
|---|---|---|
| [ai-sdk](https://github.com/spacemit-com/ai-sdk) | Unified AI SDK: vision, ASR, TTS, VAD, LLM, VLM. C++ & Python via git submodules. | Active |
| [xslim](https://github.com/spacemit-com/xslim) | Post-training INT8/FP16 quantization for ONNX. `pip install xslim`. 11 releases. Apache-2.0. | **Stable** |
| [spine-triton](https://github.com/spacemit-com/spine-triton) | Triton CPU backend for RISC-V RVV 1.0, IME, AME via MLIR pipeline. MIT. | Active — 35 contributors |
| [onnxruntime](https://github.com/spacemit-com/onnxruntime) | ONNX Runtime with SpacemiT Execution Provider (NPU). Python, C, C++ APIs. | WIP |
| [llama.cpp](https://github.com/spacemit-com/llama.cpp) | LLM inference for K1/K3. Qwen2.5, Qwen3, GLM, Deepseek in GGUF. | WIP upstream |
| [model-zoo-llm](https://github.com/spacemit-com/model-zoo-llm) | LLM examples with GGUF downloads. Sync/async/stream, Tool Calling, OpenAI-compatible. | Active |
| [spine-FlagGems](https://github.com/spacemit-com/spine-FlagGems) | GPU-free operator library for RISC-V. Upstream contribution in progress. | WIP |
| [spine-mlir](https://github.com/spacemit-com/spine-mlir) | MLIR dialect and lowering passes for K1/K3 vector and matrix extensions. | Active |
| [docs-ai](https://github.com/spacemit-com/docs-ai) | AI SDK and inference documentation. | Active |

---

## 🦾 AI Robotics Projects

Complete robotics stacks built on K3 — SLAM, navigation, manipulation, and humanoid control — with all AI inference running locally on-device.

> Robotics repositories live in the [spacemit-robotics](https://github.com/spacemit-robotics) organization and share the same K3 hardware and `ai-sdk` stack.

| Project | Description | Status |
|---|---|---|
| [Reachy Mini](https://github.com/spacemit-robotics/reachy_mini) | Desktop companion robot — vision follow, voice interaction, dance choreography on K3 | Demo Ready · Docs WIP |
| [Linksee](https://github.com/spacemit-robotics/linksee) | Wheeled mobile robot — SLAM, autonomous navigation, obstacle avoidance on K3 | Demo Ready · Docs WIP |
| [LeRobot App](https://github.com/spacemit-robotics/lerobot_app) | SO101 robot arm — ACT and SmolVLA imitation-learning policies, local inference on K3 | Demo Ready · Sim Ready |
| [Humanoid](https://github.com/spacemit-robotics/humanoid_unitree_g1) | Humanoid control — MuJoCo simulation, RL policy inference on K3 | Validation |

---

## 🗂 Repository Map

<details>
<summary>⚙️ System Software — Kernel, Bootloader, Firmware</summary>

| Repository | Description | Upstream |
|---|---|---|
| [linux-6.6](https://github.com/spacemit-com/linux-6.6) | Linux 6.6 LTS for K1 · branch `k1-bl-v2.2.y` | ✅ Mainline |
| [linux-6.18](https://github.com/spacemit-com/linux-6.18) | Linux 6.18 for K3 · branch `k3-br-v1.0.y` | ✅ Mainline |
| [opensbi](https://github.com/spacemit-com/opensbi) | OpenSBI RISC-V firmware for K1/K3 | ✅ Active |
| [uboot-2022.10](https://github.com/spacemit-com/uboot-2022.10) | U-Boot bootloader for K1/K3 | 🔄 WIP upstream |
| [edk2](https://github.com/spacemit-com/edk2) | EDK2 UEFI firmware for K3 (K3-Ubuntu boot chain) | Active |
| [esos](https://github.com/spacemit-com/esos) | ESOS — power management & real-time task core (K3) | Active |

</details>

<details>
<summary>💿 OS Images & BSP</summary>

| Repository | Description |
|---|---|
| [K3-Ubuntu-Images](https://github.com/spacemit-com/K3-Ubuntu-Images) | Build & flash Ubuntu for K3 Pico-ITX — prebuilt releases, fastboot & Titantools guide |
| [K1-Ubuntu-Images](https://github.com/spacemit-com/K1-Ubuntu-Images) | Ubuntu images for K1 boards |
| [buildroot](https://github.com/spacemit-com/buildroot) | Buildroot for K1/K3 |
| [archlinux-spacemit](https://github.com/spacemit-com/archlinux-spacemit) | Arch Linux community port for K1/K3 |

</details>

<details>
<summary>🎥 Graphics & Multimedia</summary>

| Repository | Description |
|---|---|
| [mpp](https://github.com/spacemit-com/mpp) | Media Process Platform — hardware video encode/decode |
| [mesa-pvr](https://github.com/spacemit-com/mesa-pvr) | Mesa with PowerVR GPU support (K3) |
| [multimedia-demo](https://github.com/spacemit-com/multimedia-demo) | Camera, VPU, and display examples |

</details>

<details>
<summary>📚 Documentation</summary>

| Repository | Covers | Status |
|---|---|---|
| [docs-chip](https://github.com/spacemit-com/docs-chip) | K1/K3 chip reference: registers, peripherals, clocks | Active |
| [docs-ai](https://github.com/spacemit-com/docs-ai) | AI SDK, model deployment, inference guides | Active |
| [docs-product](https://github.com/spacemit-com/docs-product) | Product-level datasheets and overviews | Active |
| [docs-openharmony](https://github.com/spacemit-com/docs-openharmony) | OpenHarmony on K1/K3 | Active |
| [bianbu-docs](https://github.com/spacemit-com/bianbu-docs) | Bianbu OS — English and Chinese | Archive |

</details>

---

## 🤝 Contributing

- **Report a bug** — Open an issue in the relevant repo. Include chip (K1/K3), OS version, kernel (`uname -a`), and `dmesg` output.
- **Fix documentation** — All `docs-*` repos accept PRs. Fix a command, improve a translation, add an example.
- **Contribute code** — Look for open issues. Each repo's README has build instructions and code style notes.
- **Discuss an idea** — Post on the [forum](https://forum.spacemit.com) before a large PR to align on approach first.
- **Security issues** — Email [developer@spacemit.com](mailto:developer@spacemit.com) privately. Do not open a public issue for vulnerabilities.

---

## 📬 Contact & Community

| Channel | Link |
|---|---|
| Forum | [forum.spacemit.com](https://forum.spacemit.com) |
| X / Twitter | [@spacemit_riscv](https://x.com/spacemit_riscv) |
| Reddit | [r/spacemit_riscv](https://www.reddit.com/r/spacemit_riscv/) |
| WeChat groups | [Join info](https://forum.spacemit.com/t/topic/942/5) |
| Developer | [developer@spacemit.com](mailto:developer@spacemit.com) |
| Business | [business@spacemit.com](mailto:business@spacemit.com) |
| Downloads | [archive.spacemit.com](https://archive.spacemit.com/) |
| Documentation | [spacemit.com/community/document](https://www.spacemit.com/community/document) |

---

*Upstream status updated monthly. Last update: 2026-09-09.*

