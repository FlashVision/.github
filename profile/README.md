<p align="center">
  <img src="https://raw.githubusercontent.com/FlashVision/FlashDet/main/assets/logo.png" width="150" alt="FlashVision">
</p>

<h1 align="center">FlashVision</h1>

<p align="center">
  <b>Ultra-lightweight computer vision models for real-time edge inference</b>
</p>

<p align="center">
  <a href="https://pypi.org/project/flashdet/"><img src="https://img.shields.io/pypi/v/flashdet?color=blue&logo=pypi&logoColor=white" alt="PyPI"></a>
  <a href="https://github.com/FlashVision/FlashDet"><img src="https://img.shields.io/badge/FlashDet-Object_Detection-ee4c2c?logo=pytorch&logoColor=white" alt="FlashDet"></a>
  <img src="https://img.shields.io/badge/License-MIT-green.svg" alt="License">
</p>

---

At **FlashVision**, we build ultra-lightweight AI models designed for real-time inference on GPUs, edge devices, and mobile platforms. Our models achieve state-of-the-art accuracy-speed trade-offs with minimal parameter counts (sub-5M) and tiny model sizes (< 5 MB FP16).

---

### Featured Projects

| Project | Description | Params | Speed |
|---------|-------------|--------|-------|
| **[FlashDet](https://github.com/FlashVision/FlashDet)** | Real-time object detection with tracking, LoRA, and analytics | 0.49M – 2.44M | 100+ FPS GPU |

---

### Quick Start

```bash
pip install flashdet

flashdet check
flashdet train --config configs/flashdet_m_320_coco.yaml --device cuda
flashdet predict --model best.pth --source photo.jpg
```

### Key Capabilities

- **Sub-5M parameter models** — Deploy anywhere: edge, mobile, embedded
- **`pip install flashdet`** — One command install from PyPI
- **LoRA / QLoRA** — Parameter-efficient fine-tuning (6 variants)
- **Knowledge Distillation** — Train compact students from larger teachers
- **Multi-Object Tracking** — ByteTracker, SORT, BoTSORT
- **Built-in Solutions** — Object counting, speed estimation, heatmaps, security
- **Config-driven Training** — Pick a YAML config, train. No code changes.
- **ONNX Export** — Deploy to any edge runtime

---

<p align="center">
  <sub>Open-source lightweight AI for everyone</sub>
</p>
