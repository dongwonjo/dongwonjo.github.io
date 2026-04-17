---
title: "Mobile Stable Diffusion"
excerpt: "SqueezeBits team and collaborator SNU-VLSI lab have successfully developed Mobile Stable Diffusion by compressing the Stable Diffusion v2.1 model to run on Galaxy S22 device. <br/><img src='/images/projects/mobile_stable_diffusion.PNG'>"
collection: portfolio
date: 2023-05-01
---

Find more information about SqueezeBits Inc. on [squeezebits.com](http://squeezebits.com/)

## Keywords

- Stable Diffusion v2.1
- Galaxy S22 (Snapdragon 8 Gen 1)
- TensorFlow Lite (w/ GPU delegate)
- Quantized, pruned and distilled
- < 8 sec / image (512×512)

---

## What is Stable Diffusion?

Stable Diffusion is a deep learning-based text-to-image generation model released in 2022 by Stability AI. Since the model has been open-sourced to the public, a number of applications have been created (e.g. image-to-image, text-to-video, etc.)

The model consists of three sub-components: a **text encoder**, a **diffusion model (U-Net)**, and a **decoder**. In total, Stable Diffusion has 1B+ parameters and requires 2GB+ memory (assuming FP16 precision). Thus, most Stable Diffusion-based applications rely on GPUs in local or cloud environments.

---

## Compressing Stable Diffusion for Mobile

We applied three complementary model compression techniques to the U-Net denoising backbone of Stable Diffusion v2.1:

### 1. Knowledge Distillation (Step Distillation)

The diffusion model (U-Net) accounts for ~94% of total latency (1.88% × 50 steps), making step reduction the highest-leverage optimization. We applied a two-stage distillation pipeline:

- **Stage 1 — Classifier-free guidance (CFG) distillation**: Standard CFG requires two forward passes per step (conditional + unconditional). We train a w-conditioned student that absorbs the guidance weight directly, eliminating the unconditional pass and yielding a **~2× speedup**.
- **Stage 2 — Progressive distillation**: Iteratively distills a T-step teacher into a T/2-step student. Applied repeatedly, this yields an speedup with minimal quality degradation, reducing from 20 steps down to the final deployment count while preserving output fidelity.

### 2. Quantization

Hexagon DSP (INT8) delegation was not viable, so we ran on the **mobile GPU (Adreno) via TFLite GPU delegate with FP16 activations and INT8/FP16 mixed-precision weights**. Key considerations:

- **W8 weight quantization** reduces model size; however, TFLite handles it differently across backends — CPUs dequantize on-the-fly to A8 and use integer kernels, while GPUs dequantize weights to FP16 and use floating-point kernels. Results must be validated carefully across both paths.
- **FP16 numerical instability**: layers with division, squares, or cubes require careful dynamic range handling to avoid Infs/NaNs.
- **Convolution layer size limit**: GPU delegate fails to allocate Image2D for excessively large convolution layers; serialization is used as a workaround at some latency cost.

### 3. Structured Pruning

Applied structured pruning without a sensitivity metric, targeting the largest layers of the U-Net. ~**11% of U-Net parameters** are pruned with negligible visual quality degradation.

### Deployment Pipeline

**PyTorch → TensorFlow → TFLite + Android NativeActivity App**

Several non-trivial engineering challenges were addressed:

- **Conversion**: Implemented a custom PyTorch-to-Keras conversion path for Stable Diffusion v2.1 (no off-the-shelf tool supported this at the time).
- **Diffusion loop optimization**: Naïvely looping the GPU delegate incurs Host↔Device memory transfer overhead on every iteration. We implemented a custom GPU delegate with a *diffusion mode* that swaps input/output buffer indices of the OpenCL program via `clSetKernelArgs`, achieving the same speed as graph unrolling while keeping memory usage equivalent to repeated inference.
- **Async pipeline**: Loading all four components (Text Encoder, Image Encoder, U-Net, Decoder) onto the GPU simultaneously causes kernel panic on Android due to memory limits. We implemented an **asynchronous load/unload pipeline**. The U-Net persists on GPU memory throughout the diffusion loop, while the Decoder is preloaded in a separate thread during the final denoising step to hide its loading latency.

---

## Demo

<video width="100%" controls>
  <source src="/images/projects/MobileStableDiffusion_bgm.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

---

## Results

| | Qualcomm (2023.02) | **Ours** |
|---|---|---|
| Device | Galaxy S23 (Snapdragon 8 Gen 2) | Galaxy S22 (Snapdragon 8 Gen 1) |
| Model | Stable Diffusion v1.5 | Stable Diffusion v2.1 |
| Processor | Hexagon DSP | Mobile GPU (Adreno) |
| Framework | SNPE | TensorFlow Lite |
| Latency | ~15 sec / image | **< 8 sec / image** |
| Resolution | 512×512 | 512×512 |

---

## Links
- 📄 [Project Page](https://squeezebits.notion.site/Mobile-Stable-Diffusion-2549eb534be54ddda3c86f2a32795948)
- 📰 [Press Release (BusinessWire)](https://www.businesswire.com/news/home/20230421005299/en/SqueezeBits-Demonstrates-Worlds-Fastest-On-device-Image-Generation-AI-for-Mobile-Devices)
