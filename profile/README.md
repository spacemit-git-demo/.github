<div align="center">

<img src="https://files.seeusercontent.com/2026/09/28/7aSv/logosquare1.png" width="200" alt="SpacemiT logo" title="logo.square1.png">

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

## AI Robot SDK

<!-- HTML 表格还原分层框架：每个白色方框可点击跳转到对应仓库 README -->
<!-- 分层配色：Solutions=绿 / Robot ROS2、Robot OS、Kernel=蓝 / HW=浅蓝 -->

<table>
  <tr>
    <td align="center" valign="middle" width="90"><b>Solutions</b></td>
    <td>
      <table width="100%">
        <tr>
          <td align="center" bgcolor="#7CB88D">
            <b>Application（Product + Simulation）</b>
            <table width="100%">
              <tr>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-robotics/ros2_nav2">AMR</a></td>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-robotics/uav">UAV</a></td>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-robotics/humanoid_unitree_go1">Robot Dog</a></td>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-robotics/ros2_arm">Industrial Robot</a></td>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-robotics/humanoid_common">Humanoid Robot</a></td>
              </tr>
            </table>
          </td>
        </tr>
        <tr>
          <td align="center" bgcolor="#5B9BD5">
            <b>Development Kit</b>
            <table width="100%">
              <tr>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-com/model-zoo-asr">ASR</a>/<a href="https://github.com/spacemit-com/model-zoo-tts">TTS</a></td>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-com/model-zoo-vision">AI Vision</a></td>
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
    <td align="center" valign="middle" width="90"><b>Robot<br/>ROS2</b></td>
    <td>
      <table width="100%">
        <tr>
          <td align="center" bgcolor="#5B9BD5">
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
    <td align="center" valign="middle" width="90"><b>Robot OS</b></td>
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
            <b>Robot SDK</b>
            <table width="100%">
              <tr>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-com/model-zoo-vision">Model Zoo</a></td>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-robotics/audio_process">audio pipeline</a></td>
                <td align="center" bgcolor="#FFFFFF">video pipeline</td>
              </tr>
              <tr>
                <td align="center" bgcolor="#FFFFFF">SDK-Display</td>
                <td align="center" bgcolor="#FFFFFF">SDK-G2D</td>
                <td align="center" bgcolor="#FFFFFF">SDK-Frame</td>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-com/k1x-cam">SDK-CAM</a></td>
              </tr>
              <tr>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-com/ai-sdk">SDK-INF</a></td>
                <td align="center" bgcolor="#FFFFFF"><a href="https://github.com/spacemit-com/k1x-jpu">SDK-Codec</a></td>
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
          <td align="center" bgcolor="#BDD7EE" colspan="3"><a href="https://github.com/spacemit-com/docs-chip"><b>K3</b></a></td>
        </tr>
      </table>
    </td>
  </tr>
</table>


