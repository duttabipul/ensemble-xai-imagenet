# Ensemble XAI on ImageNet-S

A reproducible portfolio project for exploring how normalization and aggregation choices affect ensemble explainable-AI heatmaps.

## Overview

The notebook uses a pretrained ResNet18 classifier and seven Captum attribution methods. It normalizes the attribution maps with four strategies, combines them with three non-duplicate aggregation rules, visualizes the results, and calculates transparent diagnostic proxies.

This repository is a cleaned portfolio edition by **Bipul Dutta**.

## Tech stack

- Python, Jupyter
- PyTorch and torchvision
- Captum
- OpenCV, NumPy, pandas, Matplotlib
- ImageNet-S segmentation masks

## Repository structure

```text
ensemble-xai-imagenet/
├── ensemble_xai_imagenet.ipynb
├── requirements.txt
├── .gitignore
├── LICENSE
└── README.md
```

## Setup

1. Create and activate a virtual environment.
2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Download the ImageNet-S50 masks from the official ImageNet-S project.
4. Obtain matching ImageNet images through the Kaggle API under its applicable terms.
5. Arrange the data as follows:

   ```text
   data/input/
   ├── ImageNetS50/train-semi-segmentation/<class-id>/*.png
   └── images/<class-id>/*.JPEG
   ```

6. Start Jupyter and run the notebook from top to bottom:

   ```bash
   jupyter notebook
   ```

Set `XAI_DATA_DIR` if your data folder is elsewhere.

## Sample results

### Aggregation comparison

The same image is shown with mean, weighted-mean, median, and geometric-mean ensemble attribution maps.

![Aggregation comparison](results/aggregation-comparison.png)

### Attribution and segmentation overlay

The visualization compares the source image, segmentation mask, attribution heatmap, and their overlay.

![Attribution and segmentation overlay](results/attribution-overlay.png)

## Important evaluation note

The included evaluation values are lightweight, transparent diagnostic proxies. They are **not official Quantus benchmark metrics**. The notebook labels them accordingly so that results are not overstated. A future extension can add documented Quantus metric classes with their required model and data wrappers.

## Privacy and data

Kaggle credentials, downloaded datasets, generated outputs, local paths, and personal/course records are excluded through `.gitignore`. Do not commit `kaggle.json`, raw ImageNet data, pickle files, or private information.

## License

Code in this cleaned repository is released under the MIT License. External datasets, pretrained weights, and libraries remain subject to their own licenses and terms.
