# SpacemiT Git Demo
[![Website](https://img.shields.io/badge/spacemit-www.spacemit.com-blue)](https://www.spacemit.com)
[![Developer Portal](https://img.shields.io/badge/dev-portal-orange)](https://developer.spacemit.com)

> SpacemiT (进迭时空) builds high-performance RISC-V AI CPU for Agent Computer and Robot Computer.
> 进迭时空，自研高性能RISC-V AI CPU，面向下一代 **Agent Computer 智能体计算机** 与 **Robot Computer 机器人计算机**。

## Overview
This organization repo hosts a collection of open-source demo projects for SpacemiT KeyStone K1 / K3 RISC-V AI CPU.
These projects demonstrate the full software stack, from kernel BSP, high-performance networking, LLM inference, hardware specification to embodied agent runtime.
All samples help developers, hardware OEM and system integrators quickly evaluate and build products based on SpacemiT chips.

本组织仓库集合进迭时空 KeyStone K1/K3 RISC-V AI CPU 的开源示例工程。
覆盖从底层板级驱动、高性能网络、大模型推理、硬件规范到具身智能运行时的完整软件栈，帮助开发者、整机厂商、系统集成商快速评估、开发基于进迭芯片的产品。

## Target Markets
- **Agent Computer**: On-device local reasoning, LLM planning, local knowledge base and tool-calling agent
- **Robot Computer**: On-board autonomous decision, multi-modal perception, robot motion & task orchestration
> 智能体计算机：端侧本地推理、大模型规划、本地知识库、工具调用智能体
> 机器人计算机：机载自主决策、多模态感知、机器人运动与任务编排

## Repositories
| Repository | Brief Description |
| :--- | :--- |
| [spacemit-k3-llm-infer](https://github.com/spacemit-git-demo/spacemit-k3-llm-infer) | Optimized LLM inference runtime for K3, for Agent & Robot Computer |
| [spacemit-hpn-stack](https://github.com/spacemit-git-demo/spacemit-hpn-stack) | High-Performance Networking / RDMA stack for RISC-V cluster deployment |
| [spacemit-accel-specs](https://github.com/spacemit-git-demo/spacemit-accel-specs) | AI accelerator and server hardware standard specifications |
| [spacemit-riscv-bsp](https://github.com/spacemit-git-demo/spacemit-riscv-bsp) | Linux kernel & board support package for K1 / K3 |
| [spacemit-agent-runtime](https://github.com/spacemit-git-demo/spacemit-agent-runtime) | Embodied agent demo: LLM planner, vision perception and robot control |

## Resources
- Official Website: https://www.spacemit.com
- Developer Portal: https://developer.spacemit.com
- Chip: KeyStone K1 / KeyStone K3 RISC-V AI CPU

## Get Started
1. Clone any demo repo from the table above
2. Follow each repository's `README.md` to build and run
3. Visit developer portal for datasheets, SDK and technical documents

## Community & Contribution
We welcome issues, feature requests and pull requests, especially use-case feedback for Agent Computer and Robot Computer.
Please follow the contribution guide in each sub repository.

## License
Each sub-project uses its own license. Refer to LICENSE file inside each repository.
