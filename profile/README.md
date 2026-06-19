<p align="center">
  <img src="https://img.shields.io/badge/FlashVision-Lightweight_AI-ff6b35?style=for-the-badge&logoColor=white" alt="FlashVision">
</p>

<h1 align="center">FlashVision</h1>

<p align="center">
  <b>Ultra-lightweight computer vision models for real-time edge inference</b>
</p>

<p align="center">
  <a href="https://github.com/FlashVision/FlashDet"><img src="https://img.shields.io/badge/FlashDet-Object_Detection-ee4c2c?logo=pytorch&logoColor=white" alt="FlashDet"></a>
  <img src="https://img.shields.io/badge/PyTorch-2.0+-ee4c2c?logo=pytorch&logoColor=white" alt="PyTorch">
  <img src="https://img.shields.io/badge/ONNX-Export-005CED?logo=onnx&logoColor=white" alt="ONNX">
  <img src="https://img.shields.io/badge/License-MIT-green.svg" alt="License">
</p>

---

At **FlashVision**, we build ultra-lightweight AI models designed for real-time inference on GPUs, edge devices, and mobile platforms. Our models achieve state-of-the-art accuracy-speed trade-offs with minimal parameter counts (sub-5M) and tiny model sizes (< 5 MB FP16).

We integrate cutting-edge training techniques — **LoRA/QLoRA** fine-tuning, **Knowledge Distillation**, and **INT8 quantization** — to push the limits of efficient computer vision.

---

### 🔥 Featured Projects

| Project | Description | Params | Speed |
|---------|-------------|--------|-------|
| **[FlashDet](https://github.com/FlashVision/FlashDet)** | Real-time object detection (NanoDet-Plus architecture) | 0.49M – 2.44M | 100+ FPS GPU |

---

### Key Capabilities

- **Sub-5M parameter models** — Deploy anywhere: edge, mobile, embedded
- **LoRA / QLoRA** — Parameter-efficient fine-tuning with 60–85% memory savings
- **Knowledge Distillation** — Train compact students from larger teachers
- **INT8 Quantization** — 4x size reduction with < 1% accuracy loss
- **COCO Pretrained** — Transfer learning with auto-download checkpoints
- **Multi-format** — Import YOLO/VOC/COCO, export ONNX
- **Mixed Precision** — AMP training with Multi-GPU support

---

### Getting Started

```bash
git clone https://github.com/FlashVision/FlashDet.git
cd FlashDet
bash setup_env.sh
source venv/bin/activate

# Train a model
python train.py --model-size m --epochs 100 --device cuda

# LoRA fine-tuning
python train.py --lora --lora-rank 8 --epochs 50 --device cuda

# Export to ONNX
python scripts/convert_pth_to_onnx.py --checkpoint best.pth --output model.onnx --simplify
```

---

<p align="center">
  <sub>Open-source lightweight AI for everyone</sub>
</p>
