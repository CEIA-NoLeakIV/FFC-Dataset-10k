# Frontal Face Composition Dataset (FFC-10k-Dataset) - Construction Guide

This repository contains the scripts and methodology required for the curation and construction of the **Frontal Face Composition Dataset (FFC-10k-Dataset)**.

The FFC-10k-Dataset is a strategically designed dataset composed primarily of images featuring faces in a frontal position.

---

## 1. Prerequisites

To execute the construction process, you will need the following resources:

* **Python (version 3.x)** and **Jupyter Notebook** (runtime environment).
* **Image Processing Libraries:** (E.g., `opencv-python`, `scikit-image`, etc. - *It is recommended to install via a `requirements.txt` file*).
* **Mapping Files (.csv):** The spreadsheets containing the 5 reference columns (included in this repository).
* **Construction Script:** The `create_ffc10k_dataset.ipynb` file (in this repository).

---

## 2. Construction Methodology (Three Phases)

The construction of the FFC-10k-Dataset follows a clear and sequential methodology, ensuring precision in data curation and traceability.

### PHASE 1: Preparation and Organization of Source Data

This phase ensures that all source data is accessible and organized under a standardized nomenclature.

#### A. Download and Decompression of Original Datasets

Obtain and extract the compressed image files from the following original face datasets. Create a dedicated working directory (e.g., `original_datasets`) to store them:

| Dataset | Access Link |
| :--- | :--- |
| Selfies-and-Videos | `https://www.kaggle.com/datasets/tapakah68/selfies-and-video-dataset-4-000-people?select=selfie_and_video.csv` |
| Selfies-and-ID | `https://www.kaggle.com/datasets/tapakah68/selfies-id-images-dataset` |
| Pins-Face | `https://www.kaggle.com/datasets/hereisburak/pins-face-recognition/data` |
| FEI-Face | `https://www.kaggle.com/datasets/whizzkid/fei-face-data` |
| Facescrub | `https://www.kaggle.com/datasets/rajnishe/facescrub-full` |
| MORPH-2 | `https://www.kaggle.com/datasets/chiragsaipanuganti/morph/data` |
| BUPT-CBFace-12 | `https://buptzyb.github.io/CBFace/?reload=true#download` |

#### B. Directory Standardization

**Rename the extracted directories exactly** according to the list below to ensure the composition script can locate and access them correctly:

```bash
/original_datasets/Selfies-and-Videos-Dataset
/original_datasets/Selfies-and-ID-Images-Dataset
/original_datasets/Pins-Face-Recognition-Dataset
/original_datasets/FEI-Face-Dataset
/original_datasets/Facescrub-Dataset
/original_datasets/MORPH-2-Dataset
/original_datasets/BUPT-CBFace-12
```

---

### PHASE 2: Obtaining Curation Resources

Ensure the following files are in your working environment, ready to be loaded by the script:

1. **Download Mapping Files:** Download the **CSV/spreadsheet mapping file** that contains the selection rules and the five reference columns:
   <!-- TODO: substitua pelos nomes reais das 5 colunas -->
   * `original_class_name`
   * `new_class_name`
   * *(coluna 3)*
   * *(coluna 4)*
   * *(coluna 5)*
2. **Download Execution Script:** Obtain the construction program **`create_ffc10k_dataset.ipynb`**.

---

### PHASE 3: Execution of the Composition Process

This phase automates the curation, selection, and final renaming of the images.

1. **Execute the Script:** Open and run the **`create_ffc10k_dataset.ipynb`** program in your Jupyter Notebook environment.
2. **Parameter Configuration:** In the initial configuration cell, **provide the full paths** for:
   * The root directory of the **original datasets** (as renamed in PHASE 1).
   * The location of the **CSV mapping files**.
   * The **destination directory** (e.g., `/ffc_output`) where the final FFC-10k-Dataset will be saved and organized into its classes (identities).
3. **Processing:** Execute all cells in the notebook. The script will fetch the images, apply frontal filtering, rename classes and images, and compose the final FFC-10k-Dataset.
