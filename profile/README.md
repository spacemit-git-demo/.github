<div align="center">

<img src="https://cdn-resource.spacemit.com/file/officialweb/assets/logo_white.svg" width="300" alt="SpacemiT logo" />

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


| Repository | Covers |
|---|---|
| [docs-chip](https://github.com/spacemit-com/docs-chip) | K-series chip reference: registers, peripherals, clocks |
| [docs-ai](https://github.com/spacemit-com/docs-ai) | AI SDK and inference documentation |
| [docs-product](https://github.com/spacemit-com/docs-product) | Product datasheets and overviews |
| [docs-openharmony](https://github.com/spacemit-com/docs-openharmony) | OpenHarmony on K-series |
| [bianbu-docs](https://github.com/spacemit-com/bianbu-docs) | Bianbu OS — EN and ZH |

</details>


