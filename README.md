<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0F172A,50:F97316,100:FBBF24&height=190&section=header&text=Rachit%20Jain&fontSize=48&fontColor=FFFFFF&fontAlignY=34&desc=Computer%20Engineering%20%40%20UC%20Irvine&descAlignY=54&descSize=16&animation=fadeIn" width="100%" alt="Rachit Jain - Computer Engineering at UC Irvine" />

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=20&duration=3200&pause=700&color=F97316&center=true&vCenter=true&width=760&height=45&lines=INT8+quantization+written+from+first+principles;15x+faster+convolution+with+VNNI+dot+products;Bare-metal+STM32%2C+FreeRTOS%2C+register-level+control;CUDA+GEMM+kernels%2C+naive+toward+cuBLAS" alt="What I work on" />

<br />


[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:rjrachit06@gmail.com)
![Location](https://img.shields.io/badge/Irvine,_CA-0F172A?style=for-the-badge&logo=googlemaps&logoColor=F97316)

</div>

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:0F172A,50:F97316,100:FBBF24&height=3&section=header" width="100%" alt="" />

## About

Computer Engineering student at UC Irvine, working on **efficient AI inference for embedded hardware**.

I was an undergraduate researcher at UCI's **Calit2 Computer Vision Lab** (wildfire detection) and am currently a **Controls Systems Engineer on UCI HyperXite** (Hyperloop). I'm building toward getting neural networks to run fast and correctly on constrained hardware. Embedded systems give me the hardware discipline (bare-metal STM32, FreeRTOS, register-level control), and AI inference with quantization is where I apply it (INT8 PTQ, custom C++ inference engines, CUDA kernel optimization).

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:0F172A,50:F97316,100:FBBF24&height=3&section=header" width="100%" alt="" />

## Featured Projects

### 🔥 Custom INT8 Quantization and C++ Inference Engine for YOLOv8n

> Custom INT8 inference engine for YOLOv8n fire/smoke detection, written from scratch in C++.

- Built the whole inference pipeline by hand in C++, from the convolution math up to drawing labelled boxes on the photo, without using a machine learning library
- Wrote the compression math from first principles instead of calling a library function, taking the model from 32-bit decimals to 8-bit integers, four times smaller, while keeping 99.6% of the original detection accuracy (0.8826 vs 0.8859 mAP)
- Vectorized the convolution around the processor's 8-bit dot product instruction, 15x faster and byte-for-byte identical to the plain loop

![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![AVX-512 VNNI](https://img.shields.io/badge/AVX--512_VNNI-F97316?style=flat-square&logo=intel&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![ONNX](https://img.shields.io/badge/ONNX-005CED?style=flat-square&logo=onnx&logoColor=white)
![CMake](https://img.shields.io/badge/CMake-064F8C?style=flat-square&logo=cmake&logoColor=white)

[![Repository](https://img.shields.io/badge/View_Repository-F97316?style=for-the-badge&logo=github&logoColor=white)](https://github.com/rachitj27/Custom-Quantization-and-Inference-Engine-)

<br />

### ⚡ cuda-gemm-from-scratch

> CUDA GEMM kernels built from naive to optimized, targeted at eventual integration into the inference engine's conv2d path via im2col.

- Kernels 1 (naive) and 2 (coalesced) complete on T4
- Kernel 3 (shared memory tiling) in progress
- Benchmarked against cuBLAS as the reference ceiling

![CUDA](https://img.shields.io/badge/CUDA-76B900?style=flat-square&logo=nvidia&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)

[![Repository](https://img.shields.io/badge/View_Repository-76B900?style=for-the-badge&logo=github&logoColor=white)](https://github.com/rachitj27/cuda-gemm-from-scratch)

<br />

### 🚄 HyperXite Controls (STM32 / FreeRTOS)

> Real-time controls firmware for UCI's Hyperloop pod.

- FreeRTOS on STM32 with multi-priority tasks
- UART telemetry pipeline for live pod state
- Register-level HAL work for peripheral drivers

![STM32](https://img.shields.io/badge/STM32-03234B?style=flat-square&logo=stmicroelectronics&logoColor=white)
![FreeRTOS](https://img.shields.io/badge/FreeRTOS-01AC5E?style=flat-square&logo=freertos&logoColor=white)
![C](https://img.shields.io/badge/C-A8B9CC?style=flat-square&logo=c&logoColor=black)

![Coming Soon](https://img.shields.io/badge/Repository-Coming_Soon-64748B?style=for-the-badge&logo=github&logoColor=white)

<br />

### 📡 STM32F446RE Bare-Metal Proximity Alert System

> Ultrasonic distance sensor driving a three-LED threshold indicator, written entirely against the STM32F446RE's memory-mapped registers with zero HAL dependency.

- Direct register manipulation for GPIO configuration (MODER, BSRR) and peripheral clock gating (AHB1ENR), no CubeMX-generated init code
- Hardware timer (TIM CNT) captures HC-SR04 echo pulse width for microsecond-resolution distance measurement
- Three-tier LED threshold logic driven off the computed distance, exercising the full sensor to compute to actuate loop without abstraction layers

![STM32](https://img.shields.io/badge/STM32-03234B?style=flat-square&logo=stmicroelectronics&logoColor=white)
![C](https://img.shields.io/badge/C-A8B9CC?style=flat-square&logo=c&logoColor=black)

[![Repository](https://img.shields.io/badge/View_Repository-03234B?style=for-the-badge&logo=github&logoColor=white)](https://github.com/rachitj27/stm-32-ultrasonicLED)

<br />

### ⚙️ RISC-V Single-Cycle Processor (Verilog)

> A working 32-bit RISC-V processor designed from scratch in Verilog and verified in simulation.

- Designed the actual circuitry of a computer processor, the part that reads instructions and does the work a program asks for
- Built each piece by hand and wired them together: the arithmetic unit, the memory, the registers, and the control logic that decides what every instruction does
- Verified the design by simulating a 20-instruction test program and confirming the processor produced the correct result at every single step

![Verilog](https://img.shields.io/badge/Verilog-4B5563?style=flat-square)
![Vivado](https://img.shields.io/badge/Vivado-E01F27?style=flat-square&logo=xilinx&logoColor=white)
![RISC-V](https://img.shields.io/badge/RISC--V-283272?style=flat-square&logo=riscv&logoColor=white)

[![Repository](https://img.shields.io/badge/View_Repository-283272?style=for-the-badge&logo=github&logoColor=white)](https://github.com/rachitj27/riscv-single-cycle-processor)

<br />

### 🛰️ FRND (IrvineHacks 2026)

> Disaster mesh network with an on-device LLM chat assistant.

- SmolLM2-135M running via llama.cpp on Arduino UNO Q
- Mesh routing for offline peer-to-peer messaging
- Fully on-device inference, no cloud dependency

![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![Arduino](https://img.shields.io/badge/Arduino-00979D?style=flat-square&logo=arduino&logoColor=white)
![llama.cpp](https://img.shields.io/badge/llama.cpp-8B5CF6?style=flat-square)

[![Repository](https://img.shields.io/badge/View_Repository-00979D?style=for-the-badge&logo=github&logoColor=white)](https://github.com/vrushang1234/FRND)

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:0F172A,50:F97316,100:FBBF24&height=3&section=header" width="100%" alt="" />

## Tech Stack

<div align="center">

**Languages**

![C](https://img.shields.io/badge/C-A8B9CC?style=for-the-badge&logo=c&logoColor=black)
![C++](https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=cplusplus&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![CUDA](https://img.shields.io/badge/CUDA-76B900?style=for-the-badge&logo=nvidia&logoColor=white)
![Verilog](https://img.shields.io/badge/Verilog-4B5563?style=for-the-badge&logoColor=white)
![Vivado](https://img.shields.io/badge/Vivado-E01F27?style=for-the-badge&logo=xilinx&logoColor=white)

**AI / Inference**

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![ONNX](https://img.shields.io/badge/ONNX-005CED?style=for-the-badge&logo=onnx&logoColor=white)
![TensorRT](https://img.shields.io/badge/TensorRT-76B900?style=for-the-badge&logo=nvidia&logoColor=white)
![OpenVINO](https://img.shields.io/badge/OpenVINO-0068B5?style=for-the-badge&logo=intel&logoColor=white)

**Embedded / Systems**

![STM32](https://img.shields.io/badge/STM32-03234B?style=for-the-badge&logo=stmicroelectronics&logoColor=white)
![FreeRTOS](https://img.shields.io/badge/FreeRTOS-01AC5E?style=for-the-badge&logo=freertos&logoColor=white)
![Arduino](https://img.shields.io/badge/Arduino-00979D?style=for-the-badge&logo=arduino&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![CMake](https://img.shields.io/badge/CMake-064F8C?style=for-the-badge&logo=cmake&logoColor=white)

</div>

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:0F172A,50:F97316,100:FBBF24&height=3&section=header" width="100%" alt="" />

## Currently Working On

```mermaid
flowchart LR
    A["FP32 YOLOv8n<br/>baseline"] --> B["INT8 PTQ<br/>from scratch"]
    B --> C["C++ engine<br/>23 layers"]
    C --> D["VNNI kernel<br/>15x faster"]
    D --> E["im2col + GEMM<br/>conv2d path"]
    E --> F["FPGA accelerator<br/>Verilog"]

    G["cuda-gemm<br/>K1 + K2 done"] --> H["K3 shared-mem<br/>tiling"]
    H --> I["2D register<br/>tiling"]
    I --> E

    classDef done fill:#F97316,stroke:#0F172A,stroke-width:2px,color:#fff
    classDef active fill:#FBBF24,stroke:#0F172A,stroke-width:2px,color:#0F172A
    classDef next fill:#0F172A,stroke:#F97316,stroke-width:2px,color:#fff
    class A,B,C,D,G done
    class E,H active
    class F,I next
```

- Kernel 3 of cuda-gemm-from-scratch (shared memory tiling), then a 2D register-tiled kernel
- Wiring an im2col + GEMM path into custom engine's conv2d to replace the reference loops
- HyperXite pod controls firmware for the next competition cycle

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:0F172A,50:F97316,100:FBBF24&height=3&section=header" width="100%" alt="" />

## Contact

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/rachit-jain27/)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:rjrachit06@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-0F172A?style=for-the-badge&logo=github&logoColor=F97316)](https://github.com/rachitj27)

</div>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:FBBF24,50:F97316,100:0F172A&height=120&section=footer" width="100%" alt="" />
