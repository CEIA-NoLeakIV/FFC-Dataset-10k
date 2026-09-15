# FFC-Dataset-10k

Reproducibility resources for the paper:

**A Comparative Evaluation of Pretrained Face Embedding Models for Face Verification**

## Overview

FFC-Dataset-10k is a face image dataset constructed for the evaluation of pretrained face embedding models in face verification.

The dataset contains **10,000 images from 5,000 identities**, with two images associated with each identity. The images were selected from seven publicly available face datasets.

The dataset was used to evaluate multiple pretrained face embedding models under a standardized face verification protocol.

## Source Datasets

The FFC-Dataset-10k was constructed using images from the following datasets:

* Selfies-and-Videos
* Selfies-and-ID
* Pins-Face
* FEI-Face
* FaceScrub
* MORPH-2
* BUPT-CBFace-12

The file [`selected_images.csv`](https://github.com/CEIA-NoLeakIV/FFC-Dataset-10k/blob/main/selected_images.csv) provides the list of images selected to construct the FFC-Dataset-10k, together with their corresponding source datasets. This file is provided to facilitate the reproducibility of the dataset construction process.

## Dataset Organization

Each identity is represented by a separate folder containing two face images.

The dataset follows the structure:

```text
FFC-Dataset-10k/
├── CBFACE_0/
│   ├── image_1
│   └── image_2
├── CBFACE_1/
│   ├── image_1
│   └── image_2
├── ...
├── FACESCRUB_0/
│   ├── image_1
│   └── image_2
└── ...
```

The naming convention identifies the source dataset and the corresponding identity.

## Evaluation Pipeline

The accompanying notebook [`ArcFace-embeddings-v4.ipynb`](https://github.com/CEIA-NoLeakIV/FFC-Dataset-10k/blob/main/ArcFace-embeddings-v4.ipynb) provides an example of the evaluation pipeline used with the ArcFace model.

The general evaluation procedure consists of:

1. Resizing images while preserving their aspect ratio, with a maximum dimension of 640 pixels.
2. Face detection and alignment.
3. Face embedding extraction.
4. L2 normalization of the embeddings.
5. Face verification using cosine distance.
6. Evaluation using ROC-AUC, Equal Error Rate (EER), Precision, Recall, and F1-score.

The complete study evaluated eleven pretrained face embedding models through the DeepFace framework.

## Experimental Evaluation

The experiments were conducted using:

* **5 folds**
* **1,000 images**
* **2,500 images**
* **5,000 images**
* **10,000 images**

The evaluated models were:

* VGG-Face
* FaceNet
* FaceNet512
* OpenFace
* DeepFace
* DeepID
* ArcFace
* Dlib
* SFace
* GhostFaceNet
* Buffalo_L

## Reproducibility

This repository provides the dataset selection information and an example evaluation notebook to facilitate reproduction and further experimentation.

The [`selected_images.csv`](https://github.com/CEIA-NoLeakIV/FFC-Dataset-10k/blob/main/selected_images.csv) file identifies the images used to construct the FFC-Dataset-10k from the source datasets.

The [`ArcFace-embeddings-v4.ipynb`](https://github.com/CEIA-NoLeakIV/FFC-Dataset-10k/blob/main/ArcFace-embeddings-v4.ipynb) notebook demonstrates the embedding extraction and evaluation procedure for ArcFace. The same general experimental protocol was applied to the other models evaluated in the study.

## Dataset Availability

The images in FFC-Dataset-10k originate from publicly available datasets. Users should consult the terms and licenses of the respective source datasets before redistributing or reusing the images.

This repository provides the selection information and evaluation resources rather than redistributing the complete collection of source images.

## Citation

If you use the FFC-Dataset-10k or the evaluation resources provided in this repository, please cite:

**A Comparative Evaluation of Pretrained Face Embedding Models for Face Verification**

## Repository

This repository contains the reproducibility resources associated with the study:

* [`selected_images.csv`](https://github.com/CEIA-NoLeakIV/FFC-Dataset-10k/blob/main/selected_images.csv) — list of selected images and their source datasets.
* [`ArcFace-embeddings-v4.ipynb`](https://github.com/CEIA-NoLeakIV/FFC-Dataset-10k/blob/main/ArcFace-embeddings-v4.ipynb) — example ArcFace embedding extraction and evaluation notebook.
