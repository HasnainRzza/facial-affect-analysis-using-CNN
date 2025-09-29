Facial Analysis Dataset Preparation
Project Overview
This repository contains a Jupyter notebook (i221996_01.ipynb) designed to extract and organize a dataset for facial analysis or emotion recognition tasks. The notebook processes a ZIP archive containing images and annotations (expression, valence, arousal, and landmarks) and compiles them into a structured Pandas DataFrame. It serves as a preprocessing step for machine learning pipelines, with support for potential image augmentation using the Albumentations library.
Dataset Description
The dataset is sourced from a ZIP file (DL_Assignment1_Dataset.zip) and includes:

Images: Stored as .jpg files in Dataset/Dataset/images.
Annotations: Stored as .npy files in Dataset/Dataset/annotations, with labels for:
expression: Integer labels (e.g., 0-7, likely for emotions like neutral, happy, etc.).
valence and arousal: Float values (-1 to 1) representing emotional dimensions.
landmark: Float values, likely indicating facial landmark distances or coordinates.


Output: A Pandas DataFrame with 3999 records, mapping image paths to their respective labels.

Requirements

Python Version: 3.12.3
Dependencies:pip install albumentations==1.4.3 numpy pandas opencv-python-headless


Environment: Google Colab with GPU acceleration (T4) and Google Drive integration.
Storage: Access to Google Drive for the dataset ZIP file (/content/drive/MyDrive/A01_Dataset_DL_/DL_Assignment1_Dataset.zip).

Installation

Clone the repository:git clone https://github.com/your-username/facial-analysis-dataset-prep.git


Install dependencies:pip install -r requirements.txt


Ensure the dataset ZIP file is available in your Google Drive or local storage, and update the ARCHIVE_PATH in the notebook if necessary.

Usage

Open the Notebook:

Run i221996_01.ipynb in Google Colab or a local Jupyter environment.
Mount Google Drive in Colab to access the dataset:from google.colab import drive
drive.mount('/content/drive')




Key Steps in the Notebook:

Extracts the ZIP archive to /content/dataset_space if not already extracted.
Processes images and annotations, filtering out invalid entries (negative expressions).
Creates a Pandas DataFrame with columns: path, expression, valence, arousal, landmark.
Prepares an augmentation directory (aug_photos) for future use.


Output:

A DataFrame with 3999 records and no missing annotations.
Sample output:| path                                               | expression | valence   | arousal   | landmark  |
|----------------------------------------------------|------------|-----------|-----------|-----------|
| /content/dataset_space/Dataset/Dataset/images/... | 0          | -0.176846 | -0.077640 | -0.006667 |
| ...                                                | 0          | -0.367789 | 0.183895  | 44.951579 |




Running the Notebook:

Ensure the dataset ZIP is accessible.
Execute all cells sequentially. The notebook is lightweight and processes ~4000 records efficiently.



Directory Structure
facial-analysis-dataset-prep/
├── i221996_01.ipynb          # Main Jupyter notebook
├── README.md                 # This file
├── requirements.txt          # Python dependencies
└── /content/dataset_space/   # Extracted dataset (created during execution)
    ├── Dataset/Dataset/
    │   ├── images/           # JPG images
    │   ├── annotations/      # .npy files for labels
    └── aug_photos/           # Directory for augmented images (unused)

Future Work

Implement image augmentation using Albumentations to enhance dataset diversity.
Visualize data distributions (e.g., expression histograms, valence-arousal scatter plots).
Split the dataset into train/test sets for machine learning tasks.
Develop models for emotion classification (using expression) or regression (using valence and arousal).

Contributing
Contributions are welcome! Please:

Fork the repository.
Create a feature branch (git checkout -b feature/your-feature).
Commit changes (git commit -m 'Add your feature').
Push to the branch (git push origin feature/your-feature).
Open a pull request.

License
This project is licensed under the MIT License. See the LICENSE file for details.
Contact
For questions or suggestions, please open an issue or contact [your-email@example.com].
