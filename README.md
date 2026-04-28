# FLIR-ADAS-UDAOD
Dataset for RGB2IR UDAOD

# FLIR-ADAS Evaluation Protocol for RGB→IR Domain Adaptive Object Detection

[![License](https://img.shields.io/badge/license-CC%20BY--NC%204.0-blue.svg)](https://creativecommons.org/licenses/by-nc/4.0/)
[![Dataset](https://img.shields.io/badge/dataset-RGB--IR%20UDAOD-green.svg)]()

[中文版本](#flir-adas-rgbir域自适应目标检测评测协议-中文)

---

## Overview

This repository provides the **FLIR-ADAS Evaluation Protocol** specifically designed for **Unsupervised Domain Adaptive Object Detection (UDAOD)** from **RGB (Visible)** to **IR (Infrared)** domains. 

Built upon the FLIR-ADAS dataset, this protocol addresses the unique challenges of visible-to-thermal domain adaptation by introducing independent annotations, diverse source domains, and weak alignment mitigation strategies.

## Dataset Statistics

The evaluation protocol consists of three mutually exclusive subsets:

| Subset | Modality | Annotation | Images | Purpose |
|--------|----------|------------|--------|---------|
| Source Train | RGB (Visible) | With bounding box labels | **5,663** | Supervised training (Burn-in & source term) |
| Target Train | IR (Infrared) | Unlabeled | **4,856** | Pseudo-label generation & consistency learning |
| Target Eval | IR (Infrared) | With bounding box labels | **1,144** | Performance evaluation |

**Total**: ~10,000 images across RGB and IR modalities

## Key Features

### 1. Independent Annotations
Unlike fusion-oriented datasets with paired shared annotations, our protocol employs **independently annotated** RGB and IR images. This design:
- Eliminates annotation mismatch between modalities
- Prevents information leakage in domain adaptation evaluation
- Aligns with the true UDAOD setting (source: labeled RGB, target: unlabeled IR)

### 2. Diverse Source Domain
The RGB training set explicitly covers multiple scenarios:
- **Daytime** scenes with normal lighting
- **Nighttime** scenes with low illumination  
- **Glare** scenes with challenging lighting conditions

This diversity enables algorithms to leverage intra-domain variations for better cross-domain generalization.

### 3. Weak Alignment Mitigation
To ensure rigorous evaluation:
- Scene-level matching is performed to identify paired RGB-IR sequences
- For each scene, one modality is randomly dropped to prevent same-scene pairing
- This eliminates weak alignment issues and ensures no information leakage between training sets

### 4. Object Categories
The protocol focuses on the following categories relevant to autonomous driving:
- **Person** (Pedestrian)
- **Bicycle**
- **Car**
- **Sign** (Traffic signs)
- **Light** (Traffic lights)

## Dataset Visualization

### Dataset Distribution Statistics

Below are the distribution statistics for each subset of our protocol:

#### IR Unlabeled Training Set Distribution
![IR Training Set Distribution](appendix_v1_crop_1.png)
*Figure 1: Distribution statistics of the IR unlabeled training dataset across different object categories.*

#### IR Evaluation Set Distribution
![IR Evaluation Set Distribution](appendix_v1_crop_2.png)
*Figure 2: Distribution statistics of the IR evaluation dataset across different object categories.*

#### RGB Labeled Training Set Distribution
![RGB Training Set Distribution](appendix_v1_crop_3.png)
*Figure 3: Distribution statistics of the RGB labeled training dataset across different object categories.*

### Comparison with Previous Protocols

#### FLIR-ALIGN Dataset Examples
![FLIR Dataset Examples](appendix_v1_crop_4.png)
*Figure 4: Examples from the FLIR dataset showing paired RGB and IR images with shared annotations. This dataset was originally designed for fusion tasks.*

#### FLIR-ADAS Dataset Examples (Our Protocol)
![FLIR-ADAS Dataset Examples](appendix_v1_crop_5.png)
*Figure 5: Examples from our FLIR-ADAS protocol showing independently annotated RGB (including daytime, nighttime, and glare scenes) and IR images. The diverse scenarios better reflect real-world distribution.*

## Download

### Baidu Netdisk (百度网盘)
**Link**: [待填写 / To be filled]

**Extraction Code**: [待填写 / To be filled]

> **Note**: If the link expires or you encounter any issues accessing the dataset, please contact us via email.

### Alternative Access
If the download link is unavailable, please send an email to:

📧 **a18736522195@163.com**

Subject format: `[FLIR-ADAS Protocol] Dataset Request - [Your Institution]`

Please include:
- Your name and affiliation
- Purpose of use (research/education)
- Agreement to terms of use

## Dataset Structure
