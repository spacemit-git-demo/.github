<div align="center">

<img src="https://cdn-resource.spacemit.com/file/officialweb/assets/logo_white.svg" width="300" alt="SpacemiT logo" />


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

## Bianbu Robot SDK 分层架构

<!-- HTML 表格还原分层框架：每个白色方框可点击跳转到对应仓库 README -->
<!-- 分层配色：Solutions=绿 / Bianbu ROS2、Bianbu OS、Kernel=蓝 / HW=浅蓝 -->

<table>
  <tr>
    <td align="center" valign="middle" width="90"><b>Solutions</b></td>
    <td>
      <table width="100%">
        <tr>
          <td align="center" bgcolor="#7CB88D">
            <b>集成应用（仿真 + 产品）</b>
            <table width="100%">
              <tr>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-robotics/ros2_nav2">AMR</a></td>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-robotics/uav">无人机</a></td>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-robotics/humanoid_unitree_go1">机器狗</a></td>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-robotics/ros2_arm">工业机器人</a></td>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-robotics/humanoid_common">人形机器人</a></td>
              </tr>
            </table>
          </td>
        </tr>
        <tr>
          <td align="center" bgcolor="#5B9BD5">
            <b>学习套件</b>
            <table width="100%">
              <tr>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-com/model-zoo-asr">ASR</a>/<a href="https://github.com/spacemit-com/model-zoo-tts">TTS</a></td>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-com/model-zoo-vision">AI 视觉</a></td>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-com/model-zoo-llm">LLM</a></td>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-robotics/ros2_orbslam3_run">VSLAM</a></td>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-robotics">Demo Zoo</a></td>
              </tr>
            </table>
          </td>
        </tr>
      </table>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <table width="100%">
        <tr>
          <td align="center" bgcolor="#5B9BD5">
            <b>Bianbu ROS2</b>
            <table width="100%">
              <tr>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-robotics/control_base">ros2_control</a></td>
                <td align="center" bgcolor="#FFFFFF">ros2_ethercat</td>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-robotics/ros2_simulation">ros_sim</a></td>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-com/brdk-doc">ros_brdk</a></td>
              </tr>
              <tr>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-robotics/ros2_base">ros_base</a></td>
                <td align="center" bgcolor="#FFFFFF">ros_canopen</td>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/eProsima/Fast-DDS">RT DDS*</a></td>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-com/v2d-test">2D ACC</a></td>
              </tr>
            </table>
          </td>
        </tr>
      </table>
    </td>
  </tr>
  <tr>
    <td align="center" valign="middle" width="90"><b>Bianbu OS</b></td>
    <td>
      <table width="100%">
        <tr>
          <td align="center" valign="top" width="34%" bgcolor="#5B9BD5">
            <b>Protocol</b>
            <table width="100%">
              <tr><td align="center" bgcolor="#FFFFFF"><a href="https://github.com/CANopenNode/CANopenNode">CANOpen*</a></td></tr>
              <tr><td align="center" bgcolor="#FFFFFF"><a href="https://gitlab.com/etherlab.org/ethercat">IGH EtherCAT master*</a></td></tr>
              <tr><td align="center" bgcolor="#FFFFFF"><a href="https://github.com/open62541/open62541">OPC-UA pub/sub*</a></td></tr>
            </table>
          </td>
          <td align="center" valign="top" bgcolor="#5B9BD5">
            <b>Bianbu JDK</b>
            <table width="100%">
              <tr>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-com/model-zoo-vision">Model Zoo</a></td>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-robotics/audio_process">audio pipeline</a></td>
                <td align="center" bgcolor="#FFFFFF">video pipeline</td>
              </tr>
              <tr>
                <td align="center" bgcolor="#FFFFFF">JDK-Display</td>
                <td align="center" bgcolor="#FFFFFF">JDK-G2D</td>
                <td align="center" bgcolor="#FFFFFF">JDK-Frame</td>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-com/k1x-cam">JDK-CAM</a></td>
              </tr>
              <tr>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-com/ai-sdk">JDK-INF</a></td>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-com/k1x-jpu">JDK-Codec</a></td>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/opencv/opencv">openCV*</a></td>
              </tr>
              <tr>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-com/onnxruntime">ONX runtime</a></td>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-com/mpp">MPP</a></td>
                <td align="center" bgcolor="#FFFFFF"><a href="https://gitlab.com/libeigen/eigen">Eigen*</a></td>
              </tr>
            </table>
          </td>
        </tr>
      </table>
    </td>
  </tr>
  <tr>
    <td align="center" valign="middle" width="90"><b>Kernel<br/>space</b></td>
    <td>
      <table width="100%">
        <tr>
          <td align="center" valign="top" width="34%" bgcolor="#5B9BD5">
            <table width="100%">
              <tr>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-com/linux">RS485</a></td>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-com/linux">Modbus</a></td>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-com/linux">CAN-FD</a></td>
              </tr>
              <tr>
                <td align="center" bgcolor="#FFFFFF" colspan="3">EtherCAT master device Driver</td>
              </tr>
            </table>
          </td>
          <td align="center" valign="top" bgcolor="#5B9BD5">
            <table width="100%">
              <tr>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-com/linux">Linux</a></td>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/OpenAMP/open-amp">openAMP*</a></td>
                <td align="center" bgcolor="#FFFFFF">RTOS</td>
              </tr>
              <tr>
                <td align="center" bgcolor="#FFFFFF" colspan="2"><a href="https://github.com/spacemit-com/linux">Linux Driver</a></td>
                <td align="center" bgcolor="#FFFFFF">RTOS Driver</td>
              </tr>
            </table>
          </td>
        </tr>
      </table>
    </td>
  </tr>
  <tr>
    <td align="center" valign="middle" width="90"><b>HW</b></td>
    <td>
      <table width="100%">
        <tr>
          <td align="center" bgcolor="#BDD7EE"><a href="https://github.com/spacemit-com/docs-chip">TSN</a></td>
          <td align="center" bgcolor="#BDD7EE"><a href="https://github.com/spacemit-com/docs-chip">EtherCAT</a></td>
          <td align="center" bgcolor="#BDD7EE"><a href="https://github.com/spacemit-com/docs-chip">Modbus</a></td>
          <td align="center" bgcolor="#BDD7EE"><a href="https://github.com/spacemit-com/docs-chip">CAN</a></td>
          <td align="center" bgcolor="#BDD7EE"><a href="https://github.com/spacemit-com/docs-chip">RS485</a></td>
          <td align="center" bgcolor="#BDD7EE"><a href="https://github.com/spacemit-com/docs-chip">Wi-Fi/BLE</a></td>
        </tr>
        <tr>
          <td align="center" bgcolor="#BDD7EE" colspan="3"><a href="https://github.com/spacemit-com/docs-chip"><b>K1</b></a></td>
          <td align="center" bgcolor="#BDD7EE" colspan="3"><a href="https://github.com/spacemit-com/docs-chip"><b>K2</b></a></td>
        </tr>
      </table>
    </td>
  </tr>
</table>

<sub>带 * 的为上游社区链接占位（CANopenNode / EtherLab IGH / open62541 / Fast-DDS / OpenCV / Eigen / OpenAMP），内部仓库就绪后替换为对应 spacemit-com / spacemit-robotics 仓库地址。</sub>

<sub>待补充内部仓库链接的方框：ros2_ethercat、ros_canopen、video pipeline、JDK-Display、JDK-G2D、JDK-Frame、EtherCAT master device Driver、RTOS、RTOS Driver。</sub>






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


