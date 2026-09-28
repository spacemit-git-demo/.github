<div align="center">

<img src="https://cdn-resource.spacemit.com/file/officialweb/assets/logo_white.svg" width="700" alt="SpacemiT logo" />

# SpacemiT

**RISC-V chips for AI at the edge.**

K1 · K3 · and the K-series to come.

[![Linux Mainline](https://img.shields.io/badge/Linux%20Kernel-Mainline-8DC63F?logo=linux&logoColor=white)](https://github.com/spacemit-com/linux/wiki)
[![Toolchain Mainline](https://img.shields.io/badge/GCC%20%2F%20LLVM-Mainline-8DC63F)](https://github.com/spacemit-com/.github/blob/main/upstream-status/toolchain.md)
[![Apache 2.0](https://img.shields.io/badge/License-Apache--2.0-AEDC3C)](https://www.apache.org/licenses/LICENSE-2.0)
[![Forum](https://img.shields.io/badge/Community-forum.spacemit.com-6aa82e)](https://forum.spacemit.com)
[![RISC-V K1 K3](https://img.shields.io/badge/RISC--V-K1%20%7C%20K3-8DC63F?logo=riscv&logoColor=white)](https://www.spacemit.com)


</div>

---

SpacemiT makes RISC-V SoCs for two applications: **AI Agent Computers** and **AI Robots**. Both run entirely on-device — no cloud required. This organization hosts the chips' open-source software stack, from the Linux kernel through to application-level AI inference and robotics frameworks.

We contribute upstream. K1 and K3 are fully supported in mainline Linux, GCC, LLVM, and Binutils. The standard toolchain from your distro works.

---

## Two applications

### 🧠 AI Agent Computer

An always-local intelligence layer for the edge: vision, speech, LLM reasoning, and tool use, running on-device at conversation speed.

Think of it as a Raspberry Pi-class board that runs LLMs and vision models natively — your product's brain, without a cloud bill or latency penalty.

**What you can build today:**

- Local LLM chat and function calling (Qwen, Llama, Deepseek, GLM)
- Real-time vision: detection, tracking, segmentation, pose estimation
- Voice pipelines: wake word → ASR → LLM → TTS with VAD
- Agentic loops with tool use via OpenAI-compatible API
- Multi-modal applications combining all of the above

**Start building →**

```sh
# Flash Ubuntu, then:
git clone --recurse-submodules https://github.com/spacemit-com/ai-sdk
cd ai-sdk && source build/envsetup.sh && m
```

---

### 🦾 AI Robot

A complete robotics compute platform for K3: SLAM, navigation, manipulation, and humanoid control — with all inference on-chip.

**What you can build today:**

- Visual SLAM and autonomous navigation
- Robot arm control with ACT and SmolVLA imitation-learning policies
- Humanoid whole-body control via RL inference
- MuJoCo simulation → real K3 hardware deployment

**Explore demos →** [spacemit-robotics](https://github.com/spacemit-robotics)





> Source code lives in the [spacemit-robotics](https://github.com/spacemit-robotics) organization. All projects run on K3 and use the `ai-sdk` stack.

| Project | What it does | Status |
|---|---|---|
| [Reachy Mini](https://github.com/spacemit-robotics/reachy_mini) | Desktop companion robot — vision follow, voice interaction, dance choreography | Demo ready |
| [Linksee](https://github.com/spacemit-robotics/linksee) | Wheeled mobile robot — SLAM, autonomous navigation, obstacle avoidance | Demo ready |
| [LeRobot App](https://github.com/spacemit-robotics/lerobot_app) | SO101 arm — ACT / SmolVLA policies, local inference on K3, simulation-ready | Demo + sim ready |
| [Humanoid](https://github.com/spacemit-robotics/humanoid_unitree_g1) | Humanoid control — MuJoCo, RL policy inference on K3 | Validation |


---

## Start here

| Goal | Chip | Repository |
|---|---|---|
| **Flash Ubuntu** | K1 | [K1-Ubuntu-Images](https://github.com/spacemit-com/K1-Ubuntu-Images) |
| **Flash Ubuntu** | K3 | [K3-Ubuntu-Images](https://github.com/spacemit-com/K3-Ubuntu-Images) — prebuilt releases, full flashing guide |
| **AI SDK** (vision / ASR / TTS / LLM / VLM) | K1, K3 | [ai-sdk](https://github.com/spacemit-com/ai-sdk) |
| **Deploy a local LLM** | K1, K3 | [model-zoo-llm](https://github.com/spacemit-com/model-zoo-llm) — Qwen, GLM, Deepseek in GGUF |
| **Quantize an ONNX model** | K1, K3 | [xslim](https://github.com/spacemit-com/xslim) — `pip install xslim` · INT8/FP16 · Apache-2.0 |
| **Write Triton kernels for RVV** | K1, K3 | [spine-triton](https://github.com/spacemit-com/spine-triton) — 35 contributors · MIT |
| **Build the kernel** | K1 | [linux-6.6](https://github.com/spacemit-com/linux-6.6) |
| **Build the kernel** | K3 | [linux-6.18](https://github.com/spacemit-com/linux-6.18) |
| **Robotics demos** | K3 | [spacemit-robotics](https://github.com/spacemit-robotics) org |
| **Toolchain download** | K1, K3 | [archive.spacemit.com](https://archive.spacemit.com/) — prebuilt for x86_64 and aarch64 |
| **Read the docs** | K1, K3 | [spacemit.com/community/document](https://www.spacemit.com/community/document) |

---

## AI software stack

```
┌──────────────────────────────────────────────────────────────┐
│                Your application (agent / robot)              │
└───────────────────────┬──────────────────────────────────────┘
                        │
┌───────────────────────▼──────────────────────────────────────┐
│                          ai-sdk                              │
│     vision · asr · tts · vad · llm · vlm   (C++ & Python)   │
└───────┬───────────────┬──────────────────┬───────────────────┘
        │               │                  │
  onnxruntime      llama.cpp         spine-triton
  SpacemiT EP      GGUF / K1,K3      Triton→RVV/IME/AME
        │
      xslim  ──  INT8 / FP16 post-training quantization
```

| Repository | What it does | Status |
|---|---|---|
| [ai-sdk](https://github.com/spacemit-com/ai-sdk) | Unified AI SDK: vision, ASR, TTS, VAD, LLM, VLM — C++ and Python APIs | Active |
| [xslim](https://github.com/spacemit-com/xslim) | PTQ quantization for ONNX models. `pip install xslim`. 11 releases. Apache-2.0. | **Stable** |
| [spine-triton](https://github.com/spacemit-com/spine-triton) | Triton CPU backend for RVV 1.0, IME, AME via MLIR. MIT. 35 contributors. | Active |
| [onnxruntime](https://github.com/spacemit-com/onnxruntime) | ONNX Runtime with SpacemiT Execution Provider (NPU). Python, C, C++. | WIP |
| [llama.cpp](https://github.com/spacemit-com/llama.cpp) | LLM inference optimized for K-series. GGUF. Upstream contribution ongoing. | WIP |
| [model-zoo-llm](https://github.com/spacemit-com/model-zoo-llm) | LLM examples and model downloads. Sync/async/stream, Tool Calling, OpenAI-compatible. | Active |
| [spine-FlagGems](https://github.com/spacemit-com/spine-FlagGems) | GPU-free operator library for RISC-V. Upstream contribution in progress. | WIP |
| [spine-mlir](https://github.com/spacemit-com/spine-mlir) | MLIR dialect and lowering passes for K-series vector and matrix extensions. | Active |

---


## Upstream status

> No vendor branch required. Use your distro's standard toolchain.

| Project | K1 | K3 | Updated |
|---|---|---|---|
| Linux kernel | ✅ Mainline | ✅ Mainline | 2026-09-09 |
| GCC | ✅ Mainline | ✅ Mainline | 2026-09-01 |
| LLVM | ✅ Mainline | ✅ Mainline | 2026-07-01 |
| Binutils | ✅ Mainline | ✅ Mainline | 2026-09-01 |
| OpenSBI | ✅ Completed | 🔄 Planning | 2026-07-07 |
| U-Boot | 🔄 WIP | 🔄 Planning | 2026-09-07 |
| llama.cpp | 🔄 WIP | 🔄 WIP | 2026-06-05 |
| FlagGems | 🔄 WIP | 🔄 WIP | 2026-06-05 |

Full patch links and per-module details: [upstream-status/toolchain.md](https://github.com/spacemit-com/.github/blob/main/upstream-status/toolchain.md)

---

## All repositories

<details>
<summary>⚙️ System software — kernel, bootloader, firmware</summary>

| Repository | Description | Upstream |
|---|---|---|
| [linux-6.6](https://github.com/spacemit-com/linux-6.6) | Linux 6.6 LTS for K1 — branch `k1-bl-v2.2.y` | ✅ Mainline |
| [linux-6.18](https://github.com/spacemit-com/linux-6.18) | Linux 6.18 for K3 — branch `k3-br-v1.0.y` | ✅ Mainline |
| [opensbi](https://github.com/spacemit-com/opensbi) | OpenSBI RISC-V firmware for K-series | ✅ Active |
| [uboot-2022.10](https://github.com/spacemit-com/uboot-2022.10) | U-Boot bootloader for K-series | 🔄 WIP upstream |
| [edk2](https://github.com/spacemit-com/edk2) | EDK2 UEFI firmware for K3 (K3-Ubuntu boot chain) | Active |
| [esos](https://github.com/spacemit-com/esos) | ESOS — power management and real-time task core (K3) | Active |

</details>

<details>
<summary>💿 OS images and BSP</summary>

| Repository | Description |
|---|---|
| [K3-Ubuntu-Images](https://github.com/spacemit-com/K3-Ubuntu-Images) | Build or flash Ubuntu for K3 Pico-ITX — prebuilt releases, fastboot and Titantools guide |
| [K1-Ubuntu-Images](https://github.com/spacemit-com/K1-Ubuntu-Images) | Ubuntu for K1 boards |
| [buildroot](https://github.com/spacemit-com/buildroot) | Buildroot for K-series |
| [archlinux-spacemit](https://github.com/spacemit-com/archlinux-spacemit) | Arch Linux community port |

</details>

<details>
<summary>🎥 Graphics and multimedia</summary>

| Repository | Description |
|---|---|
| [mpp](https://github.com/spacemit-com/mpp) | Media Process Platform — hardware video encode/decode |
| [mesa-pvr](https://github.com/spacemit-com/mesa-pvr) | Mesa with PowerVR GPU support (K3) |
| [multimedia-demo](https://github.com/spacemit-com/multimedia-demo) | Camera, VPU, and display examples |

</details>

<details>
<summary>📚 Documentation</summary>

| Repository | Covers |
|---|---|
| [docs-chip](https://github.com/spacemit-com/docs-chip) | K-series chip reference: registers, peripherals, clocks |
| [docs-ai](https://github.com/spacemit-com/docs-ai) | AI SDK and inference documentation |
| [docs-product](https://github.com/spacemit-com/docs-product) | Product datasheets and overviews |
| [docs-openharmony](https://github.com/spacemit-com/docs-openharmony) | OpenHarmony on K-series |
| [bianbu-docs](https://github.com/spacemit-com/bianbu-docs) | Bianbu OS — EN and ZH |

</details>

---

## Contributing

- **Report a bug** — include chip (K1/K3), OS, kernel version (`uname -a`), and `dmesg` output. Each repo has its own issue tracker.
- **Fix the docs** — all `docs-*` repos accept PRs directly.
- **Contribute code** — check open issues first; build instructions are in each repo's README.
- **Propose a large change** — open a thread on the [forum](https://forum.spacemit.com) before writing code, so we can agree on the approach.
- **Security issues** — email [developer@spacemit.com](mailto:developer@spacemit.com) privately. Please don't open a public issue for vulnerabilities.

---

## Community

| | |
|---|---|
| Forum | [forum.spacemit.com](https://forum.spacemit.com) |
| X | [@spacemit_riscv](https://x.com/spacemit_riscv) |
| Reddit | [r/spacemit_riscv](https://www.reddit.com/r/spacemit_riscv/) |
| WeChat | [Join info](https://forum.spacemit.com/t/topic/942/5) |
| Developer | [developer@spacemit.com](mailto:developer@spacemit.com) |
| Business | [business@spacemit.com](mailto:business@spacemit.com) |
| Downloads | [archive.spacemit.com](https://archive.spacemit.com/) |

---

<div align="center">

*Upstream status updated monthly. Last update: 2026-09-09.*

</div>
