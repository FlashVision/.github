<div align="center">
  <p>
    <a href="https://github.com/FlashVision" target="_blank">
      <img width="100%" src="https://raw.githubusercontent.com/FlashVision/.github/main/assets/banner.png" alt="FlashVision Banner">
    </a>
  </p>

  <a href="https://pypi.org/project/flashdet/"><img src="https://img.shields.io/pypi/v/flashdet?logo=pypi&logoColor=white&label=flashdet&color=blue" alt="FlashDet PyPI"></a>
  <a href="https://pypi.org/project/flashseg/"><img src="https://img.shields.io/pypi/v/flashseg?logo=pypi&logoColor=white&label=flashseg&color=blue" alt="FlashSeg PyPI"></a>
  <a href="https://github.com/FlashVision/FlashDet/actions"><img src="https://img.shields.io/github/actions/workflow/status/FlashVision/FlashDet/ci.yml?logo=github&label=CI" alt="CI"></a>
  <a href="https://github.com/FlashVision/FlashDet/blob/main/LICENSE"><img src="https://img.shields.io/badge/License-MIT-green.svg" alt="License"></a>
  <img src="https://img.shields.io/badge/Python-3.8+-3776AB?logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/PyTorch-2.0+-EE4C2C?logo=pytorch&logoColor=white" alt="PyTorch">

  <br>
  <br>

  <div>
    <a href="https://github.com/FlashVision/FlashDet"><img src="https://github-readme-stats.vercel.app/api/pin/?username=FlashVision&repo=FlashDet&theme=transparent&hide_border=true" alt="FlashDet"></a>
    <a href="https://github.com/FlashVision/FlashSeg"><img src="https://github-readme-stats.vercel.app/api/pin/?username=FlashVision&repo=FlashSeg&theme=transparent&hide_border=true" alt="FlashSeg"></a>
  </div>
</div>

## <div align="center">Ultra-Lightweight Vision AI for Real-Time Edge Inference</div>

At **FlashVision**, we build state-of-the-art computer vision models optimized for real-time inference on edge devices. Our models achieve **100+ FPS** with as few as **0.3M parameters** — bringing production-grade AI to embedded systems, mobile devices, and IoT hardware.

Every model supports **LoRA/QLoRA fine-tuning** for domain adaptation with minimal compute, and **Knowledge Distillation** for maximum accuracy at any model size.

## <div align="center">Projects</div>

| | Repository | Description | Params | Speed |
|:---:|:---|:---|:---:|:---:|
| ⚡ | **[FlashDet](https://github.com/FlashVision/FlashDet)** | Real-time object detection with tracking & analytics | 0.49M – 2.44M | 100+ FPS |
| 🎨 | **[FlashSeg](https://github.com/FlashVision/FlashSeg)** | Semantic segmentation, background removal, lane detection | 0.3M – 3.2M | 80+ FPS |
| 🏷️ | **[FlashCls](https://github.com/FlashVision/FlashCls)** | Image classification with multi-backbone support | 0.35M – 2.8M | 200+ FPS |
| 🎯 | **[FlashTrack](https://github.com/FlashVision/FlashTrack)** | Multi-object tracking with ReID | 0.5M – 2.0M | 90+ FPS |
| 📝 | **[FlashOCR](https://github.com/FlashVision/FlashOCR)** | Text recognition (CTC + Attention decoder) | 0.4M – 2.5M | 120+ FPS |
| 🔄 | **[FlashDownUP](https://github.com/FlashVision/FlashDownUP)** | Lossless & lossy image downsampling/upsampling (S2D, DWT-Haar, D2S) | — | — |

## <div align="center">Quick Start</div>

<details open>
<summary>Installation</summary>

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
<summary>Usage</summary>

```python
from flashdet import Predictor

# Detect objects with COCO-pretrained model
detector = Predictor(pretrained_coco=True)
detections = detector.predict("image.jpg")

for cls_name, score, x1, y1, x2, y2 in detections:
    print(f"{cls_name}: {score:.2f}")
```

```python
from flashdet import Trainer

# Fine-tune with LoRA on custom data (< 5 min on single GPU)
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

## <div align="center">Key Features</div>

<div align="center">
  <table>
    <tr>
      <td align="center"><b>🚀 Ultra-Fast</b><br>100+ FPS on edge GPUs<br>Optimized for TensorRT/ONNX</td>
      <td align="center"><b>🪶 Ultra-Light</b><br>0.3M–3M parameters<br>Runs on Jetson Nano, RPi</td>
      <td align="center"><b>🎛️ LoRA Fine-Tuning</b><br>Adapt to any domain<br>Train in minutes, not hours</td>
    </tr>
    <tr>
      <td align="center"><b>📚 Knowledge Distillation</b><br>Teacher→Student transfer<br>Maximum accuracy/size ratio</td>
      <td align="center"><b>📦 Production Ready</b><br>ONNX/TensorRT export<br>INT8 quantization support</td>
      <td align="center"><b>🔌 Solutions Built-in</b><br>Counting, speed, heatmaps<br>Parking, security, analytics</td>
    </tr>
  </table>
</div>

## <div align="center">Architecture</div>

```
Input → ShuffleNetV2 (Backbone) → GhostPAN (Neck) → Task Head → Output
         0.3M-1.5M params          Efficient FPN       Det/Seg/Cls/OCR
```

All models share the same lightweight backbone and can be trained with a unified CLI:

```bash
flashdet train --pretrained-coco --lora --epochs 50
flashseg train --data my_dataset/ --model m
flashcls train --data flowers/ --backbone shufflenet
```

## <div align="center">License</div>

All FlashVision projects are released under the [MIT License](https://github.com/FlashVision/FlashDet/blob/main/LICENSE) — free for commercial and academic use.

<div align="center">
  <br>
  <a href="https://github.com/FlashVision"><img src="https://img.shields.io/badge/GitHub-FlashVision-181717?logo=github" alt="GitHub"></a>
</div>
