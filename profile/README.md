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


---

### 🦾 AI Robot

A complete robotics compute platform for K3: SLAM, navigation, manipulation, and humanoid control — with all inference on-chip.

**What you can build today:**

- Visual SLAM and autonomous navigation
- Robot arm control with ACT and SmolVLA imitation-learning policies
- Humanoid whole-body control via RL inference
- MuJoCo simulation → real K3 hardware deployment

## AI Robot Software Package

<!-- 分层架构表格：外层 width=100% 撑满整行，各层右边线统一对齐；每个方框可点击跳转对应仓库 README -->

<table width="100%">
  <tr>
    <td align="center" valign="middle" width="120"><b>Solutions</b></td>
    <td>
      <table width="100%">
        <tr><td align="center" colspan="5"><b>集成应用（仿真 + 产品）</b></td></tr>
        <tr>
          <td align="center" width="20%"><a href="https://github.com/spacemit-robotics/ros2_nav2">AMR</a></td>
          <td align="center" width="20%"><a href="https://github.com/spacemit-robotics/uav">无人机</a></td>
          <td align="center" width="20%"><a href="https://github.com/spacemit-robotics/humanoid_unitree_go1">机器狗</a></td>
          <td align="center" width="20%"><a href="https://github.com/spacemit-robotics/ros2_arm">工业机器人</a></td>
          <td align="center" width="20%"><a href="https://github.com/spacemit-robotics/humanoid_common">人形机器人</a></td>
        </tr>
      </table>
      <table width="100%">
        <tr><td align="center" colspan="5"><b>学习套件</b></td></tr>
        <tr>
          <td align="center" width="20%"><a href="https://github.com/spacemit-com/model-zoo-asr">ASR</a>/<a href="https://github.com/spacemit-com/model-zoo-tts">TTS</a></td>
          <td align="center" width="20%"><a href="https://github.com/spacemit-com/model-zoo-vision">AI 视觉</a></td>
          <td align="center" width="20%"><a href="https://github.com/spacemit-com/model-zoo-llm">LLM</a></td>
          <td align="center" width="20%"><a href="https://github.com/spacemit-robotics/ros2_orbslam3_run">VSLAM</a></td>
          <td align="center" width="20%"><a href="https://github.com/spacemit-robotics">Demo Zoo</a></td>
        </tr>
      </table>
    </td>
  </tr>
  <tr>
    <td align="center" valign="middle" width="120"><b>Robot ROS2</b></td>
    <td>
      <table width="100%">
        <tr>
          <td align="center" width="25%"><a href="https://github.com/spacemit-robotics/control_base">ros2_control</a></td>
          <td align="center" width="25%">ros2_ethercat</td>
          <td align="center" width="25%"><a href="https://github.com/spacemit-robotics/ros2_simulation">ros_sim</a></td>
          <td align="center" width="25%"><a href="https://github.com/spacemit-com/brdk-doc">ros_brdk</a></td>
        </tr>
        <tr>
          <td align="center" width="25%"><a href="https://github.com/spacemit-robotics/ros2_base">ros_base</a></td>
          <td align="center" width="25%">ros_canopen</td>
          <td align="center" width="25%"><a href="https://github.com/eProsima/Fast-DDS">RT DDS*</a></td>
          <td align="center" width="25%"><a href="https://github.com/spacemit-com/v2d-test">2D ACC</a></td>
        </tr>
      </table>
    </td>
  </tr>
  <tr>
    <td align="center" valign="middle" width="120"><b>Robot OS</b></td>
    <td>
      <table width="100%">
        <tr>
          <td valign="top" width="34%">
            <table width="100%">
              <tr><td align="center"><b>Protocol</b></td></tr>
              <tr><td align="center" width="100%"><a href="https://github.com/CANopenNode/CANopenNode">CANOpen*</a></td></tr>
              <tr><td align="center" width="100%"><a href="https://gitlab.com/etherlab.org/ethercat">IGH EtherCAT master*</a></td></tr>
              <tr><td align="center" width="100%"><a href="https://github.com/open62541/open62541">OPC-UA pub/sub*</a></td></tr>
            </table>
          </td>
          <td valign="top">
            <table width="100%">
              <tr><td align="center"><b>AI Robot SDK</b></td></tr>
            </table>
            <table width="100%">
              <tr>
                <td align="center" width="33%"><a href="https://github.com/spacemit-com/model-zoo-vision">Model Zoo</a></td>
                <td align="center" width="33%"><a href="https://github.com/spacemit-robotics/audio_process">audio pipeline</a></td>
                <td align="center" width="34%">video pipeline</td>
              </tr>
            </table>
            <table width="100%">
              <tr>
                <td align="center" width="25%">SDK-Display</td>
                <td align="center" width="25%">SDK-G2D</td>
                <td align="center" width="25%">SDK-Frame</td>
                <td align="center" width="25%"><a href="https://github.com/spacemit-com/k1x-cam">SDK-CAM</a></td>
              </tr>
            </table>
            <table width="100%">
              <tr>
                <td align="center" width="33%"><a href="https://github.com/spacemit-com/ai-sdk">SDK-INF</a></td>
                <td align="center" width="33%"><a href="https://github.com/spacemit-com/k1x-jpu">SDK-Codec</a></td>
                <td align="center" width="34%"><a href="https://github.com/opencv/opencv">openCV*</a></td>
              </tr>
            </table>
            <table width="100%">
              <tr>
                <td align="center" width="33%"><a href="https://github.com/spacemit-com/onnxruntime">ONX runtime</a></td>
                <td align="center" width="33%"><a href="https://github.com/spacemit-com/mpp">MPP</a></td>
                <td align="center" width="34%"><a href="https://gitlab.com/libeigen/eigen">Eigen*</a></td>
              </tr>
            </table>
          </td>
        </tr>
      </table>
    </td>
  </tr>
  <tr>
    <td align="center" valign="middle" width="120"><b>Kernel space</b></td>
    <td>
      <table width="100%">
        <tr>
          <td valign="top" width="34%">
            <table width="100%">
              <tr>
                <td align="center" width="33%"><a href="https://github.com/spacemit-com/linux">RS485</a></td>
                <td align="center" width="33%"><a href="https://github.com/spacemit-com/linux">Modbus</a></td>
                <td align="center" width="34%"><a href="https://github.com/spacemit-com/linux">CAN-FD</a></td>
              </tr>
              <tr>
                <td align="center" colspan="3" width="100%">EtherCAT master device Driver</td>
              </tr>
            </table>
          </td>
          <td valign="top">
            <table width="100%">
              <tr>
                <td align="center" width="33%"><a href="https://github.com/spacemit-com/linux">Linux</a></td>
                <td align="center" width="33%"><a href="https://github.com/OpenAMP/open-amp">openAMP*</a></td>
                <td align="center" width="34%">RTOS</td>
              </tr>
              <tr>
                <td align="center" colspan="2" width="50%"><a href="https://github.com/spacemit-com/linux">Linux Driver</a></td>
                <td align="center" width="50%">RTOS Driver</td>
              </tr>
            </table>
          </td>
        </tr>
      </table>
    </td>
  </tr>
  <tr>
    <td align="center" valign="middle" width="120"><b>HW</b></td>
    <td>
      <table width="100%">
        <tr>
          <td align="center" width="17%"><a href="https://github.com/spacemit-com/docs-chip">TSN</a></td>
          <td align="center" width="17%"><a href="https://github.com/spacemit-com/docs-chip">EtherCAT</a></td>
          <td align="center" width="17%"><a href="https://github.com/spacemit-com/docs-chip">Modbus</a></td>
          <td align="center" width="17%"><a href="https://github.com/spacemit-com/docs-chip">CAN</a></td>
          <td align="center" width="16%"><a href="https://github.com/spacemit-com/docs-chip">RS485</a></td>
          <td align="center" width="16%"><a href="https://github.com/spacemit-com/docs-chip">Wi-Fi/BLE</a></td>
        </tr>
        <tr>
          <td align="center" colspan="3" width="50%"><a href="https://github.com/spacemit-com/docs-chip"><b>K1</b></a></td>
          <td align="center" colspan="3" width="50%"><a href="https://github.com/spacemit-com/docs-chip"><b>K3</b></a></td>
        </tr>
      </table>
    </td>
  </tr>
</table>

