# Facial Analysis Dataset Preparation

A Jupyter notebook for preprocessing facial analysis datasets, extracting images and annotations into a structured Pandas DataFrame for emotion recognition tasks.

## Project Overview

This project is designed to extract and organize a dataset for facial analysis or emotion recognition tasks. The notebook processes a ZIP archive containing images and annotations (expression, valence, arousal, and landmarks) and compiles them into a structured Pandas DataFrame.

This serves as a preprocessing step for machine learning pipelines, with support for potential image augmentation using the Albumentations library.

## Dataset Description

The dataset is sourced from a ZIP file (`Facial_AFFECT.zip`) and includes:

- **Images**: `.jpg` files in `Dataset/Dataset/images/`
- **Annotations**: `.npy` files in `Dataset/Dataset/annotations/` with labels for:
  - `expression`: Integer labels (0-7) for emotion categories
  - `valence` and `arousal`: Float values (-1 to 1) representing emotional dimensions
  - `landmark`: Float values for facial landmark coordinates/distances

## Features

- Extracts and processes dataset from ZIP archive
- Creates structured Pandas DataFrame with 3999 records
- Filters invalid entries (negative expressions)
- Prepares augmentation directory for future use
- Maps image paths to their respective labels

## Installation

### Prerequisites

- Python 3.12.3
- Google Colab with GPU acceleration (T4) recommended

### Dependencies

```bash
pip install albumentations==1.4.3 numpy pandas opencv-python-headless
```

### Setup

```bash
git clone https://github.com/HasnainRzza/facial-affect-analysis.git
cd facial-analysis-dataset-prep
```

## Usage

1. Update the `ARCHIVE_PATH` in the notebook to point to your local dataset.
2. Run all cells sequentially.

## Output Example

```
path	expression	valence	arousal	landmark
/content/dataset_space/Dataset/Dataset/images/...\t0\t-0.176846\t-0.077640\t-0.006667
...\t0\t-0.367789\t0.183895\t44.951579
```

## Results Snapshot

```
Final metrics:
Accuracy  : 0.5341
F1        : 0.5102
Kappa     : 0.4675
RMSE      : 14.1450
ValCCC    : 0.5967
ValCorr   : 0.6399
AroCCC    : 0.4907
AroCorr   : 0.5255
LndCCC    : -0.0000
LndCorr   : -0.0012
```

## Project Structure

```
facial-analysis-dataset-prep/
├── i221996_01.ipynb          # Main Jupyter notebook
├── README.md                 # Project documentation
├── requirements.txt          # Python dependencies
└── /content/dataset_space/   # Extracted dataset (created during execution)
    ├── Dataset/Dataset/
    │   ├── images/           # JPG images
    │   ├── annotations/      # .npy files for labels
    └── aug_photos/           # Directory for augmented images
```

## Contact

```
Email: workflow.raza@gmail.com
[Linkedin] (https://www.linkedin.com/in/muhammad-hasnain-mhr/)
```
