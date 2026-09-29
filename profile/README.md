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

# AI Robot Software Package

## System Architecture

<table>
  <tr>
    <th width="120">Layer</th>
    <th>Components</th>
  </tr>
  
  <!-- Solutions Layer -->
  <tr>
    <td align="center"><strong>Solutions</strong></td>
    <td>
      <table width="100%">
        <tr>
          <td colspan="5" align="center"><strong>Integrated Applications (Simulation + Products)</strong></td>
        </tr>
        <tr>
          <td width="20%" align="center"><a href="https://github.com/spacemit-robotics/ros2_nav2">AMR</a></td>
          <td width="20%" align="center"><a href="https://github.com/spacemit-robotics/uav">UAV</a></td>
          <td width="20%" align="center"><a href="https://github.com/spacemit-robotics/humanoid_unitree_go1">Robot Dog</a></td>
          <td width="20%" align="center"><a href="https://github.com/spacemit-robotics/ros2_arm">Industrial Robot</a></td>
          <td width="20%" align="center"><a href="https://github.com/spacemit-robotics/humanoid_common">Humanoid</a></td>
        </tr>
        <tr>
          <td colspan="5" align="center"><strong>Learning Kits</strong></td>
        </tr>
        <tr>
          <td width="20%" align="center"><a href="https://github.com/spacemit-com/model-zoo-asr">ASR</a> / <a href="https://github.com/spacemit-com/model-zoo-tts">TTS</a></td>
          <td width="20%" align="center"><a href="https://github.com/spacemit-com/model-zoo-vision">AI Vision</a></td>
          <td width="20%" align="center"><a href="https://github.com/spacemit-com/model-zoo-llm">LLM</a></td>
          <td width="20%" align="center"><a href="https://github.com/spacemit-robotics/ros2_orbslam3_run">VSLAM</a></td>
          <td width="20%" align="center"><a href="https://github.com/spacemit-robotics">Demo Zoo</a></td>
        </tr>
      </table>
    </td>
  </tr>
  
  <!-- Robot ROS2 Layer -->
  <tr>
    <td align="center"><strong>Robot ROS2</strong></td>
    <td>
      <table width="100%">
        <tr>
          <td width="25%" align="center"><a href="https://github.com/spacemit-robotics/control_base">ros2_control</a></td>
          <td width="25%" align="center">ros2_ethercat</td>
          <td width="25%" align="center"><a href="https://github.com/spacemit-robotics/ros2_simulation">ros_sim</a></td>
          <td width="25%" align="center"><a href="https://github.com/spacemit-com/brdk-doc">ros_brdk</a></td>
        </tr>
        <tr>
          <td width="25%" align="center"><a href="https://github.com/spacemit-robotics/ros2_base">ros_base</a></td>
          <td width="25%" align="center">ros_canopen</td>
          <td width="25%" align="center"><a href="https://github.com/eProsima/Fast-DDS">RT DDS</a> *</td>
          <td width="25%" align="center"><a href="https://github.com/spacemit-com/v2d-test">2D ACC</a></td>
        </tr>
      </table>
    </td>
  </tr>
  
  <!-- Robot OS Layer -->
  <tr>
    <td align="center"><strong>Robot OS</strong></td>
    <td>
      <table width="100%">
        <tr>
          <td width="25%" align="center"><strong>Protocol Stack</strong></td>
          <td width="75%" colspan="3" align="center"><strong>AI Robot SDK</strong></td>
        </tr>
        <tr>
          <td width="25%" align="center"><a href="https://github.com/CANopenNode/CANopenNode">CANOpen</a> *</td>
          <td width="25%" align="center"><a href="https://github.com/spacemit-com/model-zoo-vision">Model Zoo</a></td>
          <td width="25%" align="center"><a href="https://github.com/spacemit-robotics/audio_process">Audio Pipeline</a></td>
          <td width="25%" align="center">Video Pipeline</td>
        </tr>
        <tr>
          <td width="25%" align="center"><a href="https://gitlab.com/etherlab.org/ethercat">IGH EtherCAT</a> *</td>
          <td width="25%" align="center">SDK-Display</td>
          <td width="25%" align="center">SDK-G2D</td>
          <td width="25%" align="center">SDK-Frame</td>
        </tr>
        <tr>
          <td width="25%" align="center"><a href="https://github.com/open62541/open62541">OPC-UA pub/sub</a> *</td>
          <td width="25%" align="center"><a href="https://github.com/spacemit-com/k1x-cam">SDK-CAM</a></td>
          <td width="25%" align="center"><a href="https://github.com/spacemit-com/ai-sdk">SDK-INF</a></td>
          <td width="25%" align="center"><a href="https://github.com/spacemit-com/k1x-jpu">SDK-Codec</a></td>
        </tr>
        <tr>
          <td width="25%" align="center"></td>
          <td width="25%" align="center"><a href="https://github.com/opencv/opencv">OpenCV</a> *</td>
          <td width="25%" align="center"><a href="https://github.com/spacemit-com/onnxruntime">ONNX Runtime</a></td>
          <td width="25%" align="center"><a href="https://github.com/spacemit-com/mpp">MPP</a></td>
        </tr>
        <tr>
          <td width="25%" align="center"></td>
          <td width="25%" align="center"><a href="https://gitlab.com/libeigen/eigen">Eigen</a> *</td>
          <td width="25%" align="center"></td>
          <td width="25%" align="center"></td>
        </tr>
      </table>
    </td>
  </tr>
  
  <!-- Kernel Space Layer -->
  <tr>
    <td align="center"><strong>Kernel Space</strong></td>
    <td>
      <table width="100%">
        <tr>
          <td width="25%" align="center"><a href="https://github.com/spacemit-com/linux">RS485</a></td>
          <td width="25%" align="center"><a href="https://github.com/spacemit-com/linux">Modbus</a></td>
          <td width="25%" align="center"><a href="https://github.com/spacemit-com/linux">CAN-FD</a></td>
          <td width="25%" align="center">EtherCAT Master Driver</td>
        </tr>
        <tr>
          <td width="25%" align="center"><a href="https://github.com/spacemit-com/linux">Linux</a></td>
          <td width="25%" align="center"><a href="https://github.com/spacemit-com/linux">Linux Driver</a></td>
          <td width="25%" align="center"><a href="https://github.com/OpenAMP/open-amp">OpenAMP</a> *</td>
          <td width="25%" align="center">RTOS / RTOS Driver</td>
        </tr>
      </table>
    </td>
  </tr>
  
  <!-- Hardware Layer -->
  <tr>
    <td align="center"><strong>Hardware</strong></td>
    <td>
      <table width="100%">
        <tr>
          <td width="16.6%" align="center"><a href="https://github.com/spacemit-com/docs-chip">TSN</a></td>
          <td width="16.6%" align="center"><a href="https://github.com/spacemit-com/docs-chip">EtherCAT</a></td>
          <td width="16.6%" align="center"><a href="https://github.com/spacemit-com/docs-chip">Modbus</a></td>
          <td width="16.6%" align="center"><a href="https://github.com/spacemit-com/docs-chip">CAN</a></td>
          <td width="16.6%" align="center"><a href="https://github.com/spacemit-com/docs-chip">RS485</a></td>
          <td width="16.6%" align="center"><a href="https://github.com/spacemit-com/docs-chip">Wi-Fi/BLE</a></td>
        </tr>
        <tr>
          <td colspan="3" align="center"><a href="https://github.com/spacemit-com/docs-chip"><strong>K1 Chip Platform</strong></a></td>
          <td colspan="3" align="center"><a href="https://github.com/spacemit-com/docs-chip"><strong>K3 Chip Platform</strong></a></td>
        </tr>
      </table>
    </td>
  </tr>
</table>



