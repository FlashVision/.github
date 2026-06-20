<div align="center">
  <p>
    <a href="https://github.com/FlashVision" target="_blank">
      <img width="180" src="https://raw.githubusercontent.com/FlashVision/.github/main/assets/logo.svg" alt="FlashVision">
    </a>
  </p>

  <h1>FlashVision</h1>
  <p><b>Ultra-Lightweight Vision AI for Real-Time Edge Inference</b></p>

  <br>

  <a href="https://pypi.org/project/flashdet/"><img src="https://img.shields.io/pypi/v/flashdet?logo=pypi&logoColor=white&label=flashdet&color=blue" alt="FlashDet PyPI"></a>
  <a href="https://pypi.org/project/flashseg/"><img src="https://img.shields.io/pypi/v/flashseg?logo=pypi&logoColor=white&label=flashseg&color=blue" alt="FlashSeg PyPI"></a>
  <a href="https://github.com/FlashVision/FlashDet/actions"><img src="https://img.shields.io/github/actions/workflow/status/FlashVision/FlashDet/ci.yml?logo=github&label=CI" alt="CI"></a>
  <a href="https://github.com/FlashVision/FlashDet/blob/main/LICENSE"><img src="https://img.shields.io/badge/License-MIT-green.svg" alt="License"></a>
  <img src="https://img.shields.io/badge/Python-3.8+-3776AB?logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/PyTorch-2.0+-EE4C2C?logo=pytorch&logoColor=white" alt="PyTorch">

</div>

<br>

At **FlashVision**, we build state-of-the-art computer vision models optimized for real-time inference on edge devices. Our models achieve **100+ FPS** with as few as **0.3M parameters** — bringing production-grade AI to embedded systems, mobile devices, and IoT hardware.

Every model supports **LoRA/QLoRA fine-tuning** for efficient domain adaptation and **Knowledge Distillation** for maximum accuracy at minimal model size.

---

## <div align="center">Projects</div>

<div align="center">

| | Repository | Description | Params | Speed |
|:---:|:---|:---|:---:|:---:|
| ⚡ | **[FlashDet](https://github.com/FlashVision/FlashDet)** | Real-time object detection with tracking & analytics | 0.49M – 2.44M | 100+ FPS |
| 🎨 | **[FlashSeg](https://github.com/FlashVision/FlashSeg)** | Semantic segmentation, background removal, lane detection | 0.3M – 3.2M | 80+ FPS |
| 🏷️ | **[FlashCls](https://github.com/FlashVision/FlashCls)** | Image classification with multi-backbone support | 0.35M – 2.8M | 200+ FPS |
| 🎯 | **[FlashTrack](https://github.com/FlashVision/FlashTrack)** | Multi-object tracking with ReID encoders | 0.5M – 2.0M | 90+ FPS |
| 📝 | **[FlashOCR](https://github.com/FlashVision/FlashOCR)** | Text recognition (CTC + Attention decoder) | 0.4M – 2.5M | 120+ FPS |
| 🔄 | **[FlashDownUP](https://github.com/FlashVision/FlashDownUP)** | Lossless & lossy image resampling (S2D, DWT-Haar, D2S) | — | — |

</div>

---

## <div align="center">Quick Start</div>

<details open>
<summary><b>Installation</b></summary>

```bash
pip install flashdet    # Object Detection
pip install flashseg    # Segmentation
pip install flashcls    # Classification
pip install flashtrack  # Tracking
pip install flashocr    # OCR
pip install flashdownup # Down/Upsampling Operators
```

</details>

<details open>
<summary><b>Inference</b></summary>

```python
from flashdet import Predictor

detector = Predictor(pretrained_coco=True)
detections = detector.predict("image.jpg")

for cls_name, score, x1, y1, x2, y2 in detections:
    print(f"{cls_name}: {score:.2f}")
```

</details>

<details open>
<summary><b>Fine-Tune with LoRA (< 5 min, single GPU)</b></summary>

```python
from flashdet import Trainer

trainer = Trainer(
    pretrained_coco=True,
    lora=True,
    lora_rank=8,
    epochs=50,
    batch_size=32,
)
trainer.train()
```

</details>

---

## <div align="center">Key Features</div>

<div align="center">
  <table>
    <tr>
      <td align="center" width="33%"><b>🚀 Ultra-Fast</b><br><sub>100+ FPS on edge GPUs<br>Optimized for TensorRT & ONNX</sub></td>
      <td align="center" width="33%"><b>🪶 Ultra-Light</b><br><sub>0.3M–3M parameters<br>Runs on Jetson Nano, RPi, Mobile</sub></td>
      <td align="center" width="33%"><b>🎛️ LoRA / QLoRA</b><br><sub>Adapt to any domain<br>Train in minutes, not hours</sub></td>
    </tr>
    <tr>
      <td align="center"><b>📚 Knowledge Distillation</b><br><sub>Teacher → Student transfer<br>Max accuracy at minimal size</sub></td>
      <td align="center"><b>📦 Export Ready</b><br><sub>ONNX, TensorRT, CoreML<br>FP16 & INT8 quantization</sub></td>
      <td align="center"><b>🔌 Built-in Solutions</b><br><sub>Object counting, speed estimation<br>Heatmaps, parking, security</sub></td>
    </tr>
  </table>
</div>

---

## <div align="center">Architecture</div>

```
Input → ShuffleNetV2 (Backbone) → GhostPAN (Neck) → Task Head → Output
         0.3M–1.5M params          Efficient FPN       Det/Seg/Cls/OCR
```

Unified CLI across all projects:

```bash
flashdet train --pretrained-coco --lora --epochs 50
flashseg train --data my_dataset/ --model m
flashcls train --data flowers/ --backbone shufflenet
flashocr train --data text_dataset/ --decoder attention
```

---

## <div align="center">License</div>

<div align="center">

All FlashVision projects are released under the [MIT License](https://github.com/FlashVision/FlashDet/blob/main/LICENSE) — free for commercial and academic use.

<br>

<a href="https://github.com/FlashVision"><img src="https://img.shields.io/badge/GitHub-FlashVision-181717?style=for-the-badge&logo=github" alt="GitHub"></a>

</div>
