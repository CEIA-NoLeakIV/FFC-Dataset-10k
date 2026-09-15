# Frontal Face Composition Dataset (FFC-10k-Dataset) - Construction Guide

This repository contains the scripts and methodology required for the curation and construction of the **Frontal Face Composition Dataset (FFC-10k-Dataset)**.

The FFC-10k-Dataset is a curated face dataset composed primarily of images featuring faces in a frontal position. It was constructed by selecting and reorganizing identities and images from multiple publicly available face datasets according to predefined curation rules.

---

## 1. Prerequisites

To execute the dataset construction process, you will need the following resources:

* **Python 3.x** and **Jupyter Notebook** as the execution environment.
* **Image processing libraries**, such as `opencv-python`, `scikit-image`, and other dependencies required by the notebook. It is recommended to install them using the provided `requirements.txt` file, if available.
* **Mapping files (.csv)** containing the selection and renaming information used during the curation process.
* **Construction notebook:** `create_ffc10k_dataset.ipynb`.

---

## 2. Construction Methodology

The construction of the FFC-10k-Dataset follows a sequential three-phase methodology designed to ensure consistent data curation, organization, and traceability.

### Phase 1: Preparation and Organization of Source Data

This phase consists of obtaining the source datasets and organizing them using the directory structure expected by the construction notebook.

#### A. Download and Decompression of Original Datasets

Obtain and extract the image files from the following original face datasets.

Create a dedicated working directory, such as `original_datasets`, to store the extracted datasets.

| Dataset            | Access Link                                                                                                            |
| :----------------- | :--------------------------------------------------------------------------------------------------------------------- |
| Selfies-and-Videos | [Kaggle](https://www.kaggle.com/datasets/tapakah68/selfies-and-video-dataset-4-000-people?select=selfie_and_video.csv) |
| Selfies-and-ID     | [Kaggle](https://www.kaggle.com/datasets/tapakah68/selfies-id-images-dataset)                                          |
| Pins-Face          | [Kaggle](https://www.kaggle.com/datasets/hereisburak/pins-face-recognition/data)                                       |
| FEI-Face           | [Kaggle](https://www.kaggle.com/datasets/whizzkid/fei-face-data)                                                       |
| Facescrub          | [Kaggle](https://www.kaggle.com/datasets/rajnishe/facescrub-full)                                                      |
| MORPH-2            | [Kaggle](https://www.kaggle.com/datasets/chiragsaipanuganti/morph/data)                                                |
| BUPT-CBFace-12     | [Official Dataset Page](https://buptzyb.github.io/CBFace/?reload=true#download)                                        |

> **Note:** The original datasets are not redistributed in this repository. Users are responsible for obtaining the source datasets and complying with their respective licenses and terms of use.

#### B. Directory Standardization

**Rename the extracted directories exactly** as shown below. The construction notebook expects these directory names when locating the source datasets.

```text
original_datasets/
├── Selfies-and-Videos-Dataset/
├── Selfies-and-ID-Images-Dataset/
├── Pins-Face-Recognition-Dataset/
├── FEI-Face-Dataset/
├── Facescrub-Dataset/
├── MORPH-2-Dataset/
└── BUPT-CBFace-12/
```

---

### Phase 2: Obtaining Curation Resources

Ensure that the following files are available in your working environment before executing the construction process.

1. **Mapping Files**

   Download or obtain the **CSV mapping files** containing the selection and renaming information used by the construction notebook.

   These files contain the reference columns required for the curation process, including fields such as:

   * `original_class_name`
   * `new_class_name`
   * and other reference columns required by the notebook.

2. **Construction Notebook**

   Obtain the construction notebook:

   ```text
   create_ffc10k_dataset.ipynb
   ```

---

### Phase 3: Execution of the Composition Process

Once the original datasets and curation resources are properly organized, execute the construction notebook.

#### 1. Execute the Notebook

Open:

```text
create_ffc10k_dataset.ipynb
```

using Jupyter Notebook or another compatible Jupyter environment.

#### 2. Configure the Paths

In the initial configuration cell, provide the appropriate paths for:

* the root directory containing the **original datasets**;
* the directory containing the **CSV mapping files**;
* the **destination directory** where the resulting FFC-10k-Dataset will be generated.

For example:

```text
original_datasets/
mapping_files/
ffc_output/
```

The exact paths depend on the user's local environment.

#### 3. Run the Construction Process

Execute all cells in the notebook.

The construction pipeline will use the provided mapping files and source datasets to:

1. locate the selected source identities and images;
2. apply the defined curation and selection criteria;
3. reorganize the selected identities;
4. rename classes and images according to the mapping files; and
5. generate the final **FFC-10k-Dataset** in the specified output directory.

After successful execution, the resulting dataset will be organized into its corresponding identity classes.

---

## 3. Output Structure

The resulting dataset is expected to follow an identity-based directory structure similar to:

```text
ffc_output/
├── class_0001/
│   ├── image_0001.jpg
│   ├── image_0002.jpg
│   └── ...
├── class_0002/
│   ├── image_0001.jpg
│   ├── image_0002.jpg
│   └── ...
└── ...
```

The exact class and image naming conventions are determined by the mapping files and the construction notebook.

---

## 4. Reproducibility

To reproduce the construction of the FFC-10k-Dataset:

1. Obtain the original datasets listed in **Phase 1**.
2. Extract and rename the datasets according to the required directory structure.
3. Obtain the mapping files used by the curation process.
4. Download `create_ffc10k_dataset.ipynb`.
5. Configure the paths in the notebook.
6. Execute all notebook cells.
7. Verify the generated output directory.

This procedure allows the dataset construction process to be reproduced from the original source datasets and the provided curation resources.
