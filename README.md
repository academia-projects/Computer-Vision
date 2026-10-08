# Computer Vision Coursework Repository

<p align="center">
  A structured collection of computer vision assignments spanning classical AR/SfM pipelines and deep-learning based image classification.
</p>

---

## Overview

This repository organizes assignment work for a computer vision course into separate modules (`A1`-`A4`).
Each assignment is mostly self-contained and includes its own scripts, assets, and outputs.

At a high level, the repository includes:
- **A1**: AR tag detection, homography-based overlays, and camera calibration tools.
- **A2**: Multi-view geometry and localization experiments, including COLMAP-assisted workflows.
- **A3**: Deep learning experiments for land-use image classification using ResNet/SE-ResNet/DeiT variants.
- **A4**: Assignment specification document only.

---

## Repository Organization

```text
Computer-Vision/
├── A1/  # AR tag detection + 2D/3D overlays + camera calibration helpers
├── A2/  # SfM, epipolar geometry, triangulation, localization, COLMAP integration
├── A3/  # CNN/ViT training, evaluation, tuning, and visualization
├── A4/  # Assignment PDF
└── README.md
```

---

## Main Entry Points

### `A1` — AR Tag Detection & Overlay
- `A1/main.py`: Main runtime script for tag detection from webcam/video and overlay modes.
- `A1/get_images.py`: Captures chessboard images for calibration.
- `A1/caliberate_camera.py`: Computes and saves camera intrinsics/distortion values.

### `A2` — Geometry, Reconstruction, and Localization
- `A2/main.py`: End-to-end experimental script for feature matching, essential matrix, triangulation, and pose tasks.
- `A2/colmap.py`: Runs a COLMAP pipeline (frame extraction, mapping, text export).
- `A2/localization.py`: Localization pipeline using a custom map representation.
- `A2/colmap_localization.py`: Localization over COLMAP-exported map data.
- `A2/task_5.py`: COLMAP point/descriptor extraction and reconstruction comparison utilities.

### `A3` — Deep Learning Pipeline
- `A3/train.py`: Model training (ResNet18 / SE-ResNet18 / DeiT3 / DeiT3+DyT).
- `A3/test.py`: Evaluation and metric reporting on test data.
- `A3/hp_tuning.py`: One-at-a-time hyperparameter tuning experiments.
- `A3/visualize.py`: Grad-CAM and attention visualizations.
- `A3/models.py`, `A3/utils.py`: Shared model and data/metric utilities.

---

## Quick Start

> There is no single root-level runner; execute scripts inside each assignment folder.

### A1
```bash
cd A1
pip install numpy opencv-python
python main.py
```

### A3
```bash
cd A3
pip install -r requirements.txt
python train.py --help
python test.py --help
```

### A2
`A2` depends on additional scientific/CV tooling (e.g., OpenCV contrib features, SciPy stack, Open3D, and COLMAP for relevant scripts). Run scripts directly after setting up your environment and required datasets/videos.

---

## Notes

- Assignment folders contain intermediate outputs and media artifacts generated during experimentation.
- Some scripts assume specific local dataset/video paths; update paths as needed before execution.
- Detailed assignment-specific usage is available in local docs such as `A1/USAGE.md` and `A3/README.md`.
