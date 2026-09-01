# Data

This directory contains information related to the datasets discussed and analyzed in the research project:

**Computer Vision for Insect Pest Detection in Nepalese Agriculture: A Systematic Review, Research Gaps, and Future Directions**

The repository does **not** redistribute the complete third-party datasets discussed in the research. Original datasets should be obtained from their respective official sources and used according to their licenses and terms of use.

---

## Primary Dataset: IP102

The primary benchmark dataset analyzed in this research is **IP102**, a large-scale dataset developed for insect-pest recognition and detection.

### Dataset Summary

| Property          |  Value |
| ----------------- | -----: |
| Total images      | 75,222 |
| Pest classes      |    102 |
| Training images   | 45,095 |
| Validation images |  7,508 |
| Testing images    | 22,619 |
| Detection images  | 18,983 |

The classification dataset follows an approximately:

```text
60% Training
10% Validation
30% Testing
```

split.

IP102 also contains **18,983 images with bounding-box annotations** for object-detection research.

---

## Nepal-Relevant IP102 Subsets

The research gives particular attention to IP102 crop groups that are relevant to major crops cultivated in Nepal.

| Crop Group | Pest Classes |     Images |
| ---------- | -----------: | ---------: |
| Rice       |           14 |      8,417 |
| Corn/Maize |           13 |     14,015 |
| Wheat      |            9 |      3,418 |
| **Total**  |       **36** | **25,850** |

These three crop groups account for approximately **34.36% of the complete IP102 dataset**.

They provide useful benchmark data for studying pest-recognition methods relevant to rice, maize, and wheat.

However, these images should **not** be interpreted as Nepal-specific agricultural data.

---

## Why IP102 Is Important to This Research

IP102 is particularly useful because it provides:

* A relatively large number of insect-pest images
* 102 pest classes
* Multiple crop-associated pest groups
* Classification data
* Object-detection annotations
* Naturally imbalanced class distributions
* A common benchmark for comparing computer-vision models

The dataset therefore provides a useful starting point for evaluating insect-pest recognition methods.

---

## Dataset Challenges

Several characteristics of insect-pest datasets make computer-vision modeling difficult.

### Class Imbalance

IP102 has a naturally long-tailed class distribution.

Some pest classes contain significantly more images than others.

As a result, classification accuracy alone may not provide a complete picture of model performance.

Metrics such as the following should also be considered:

* Precision
* Recall
* F1-score
* G-mean
* Per-class performance
* Confusion matrix

---

### Small Objects

In object-detection images, insects may occupy only a small portion of the complete image.

This makes localization difficult, particularly in natural agricultural environments.

---

### Complex Backgrounds

Field images can contain:

* Leaves
* Stems
* Soil
* Shadows
* Other insects
* Crop damage
* Overlapping vegetation
* Variable lighting
* Partial occlusion

These conditions make pest recognition substantially more difficult than recognition from controlled images.

---

### Visual Similarity

Different insect species may have similar:

* Shape
* Color
* Texture
* Body structure

At the same time, the appearance of the same species may change across developmental stages.

For example:

```text
Egg
 ↓
Larva
 ↓
Pupa
 ↓
Adult
```

This creates additional challenges for computer-vision models.

---

## Geographic Domain Shift

One of the central research questions of this project concerns whether models trained on international pest datasets can generalize to Nepalese agricultural environments.

A model may perform well on:

```text
IP102 Training Data
        ↓
      Model
        ↓
IP102 Test Data
```

while performing substantially differently on:

```text
IP102 Training Data
        ↓
      Model
        ↓
Nepal Field Images
```

Potential sources of domain shift include:

* Geographic location
* Climate
* Altitude
* Crop varieties
* Pest populations
* Agricultural practices
* Camera devices
* Lighting
* Background vegetation
* Pest developmental stages
* Seasonal variation

For this reason, IP102 is treated as an **international benchmark**, not as a substitute for Nepal-specific field data.

---

## Proposed Nepal-Specific Dataset

A major future direction identified by this research is the development of a Nepal-specific insect-pest image dataset.

The proposed dataset-development pipeline is:

```text
Pest Selection
      ↓
Multi-location Field Collection
      ↓
Expert Verification
      ↓
Annotation
      ↓
Quality Control
      ↓
Train / Validation / Test Split
      ↓
Public Dataset
```

---

## Proposed Data Collection Strategy

Future Nepal-specific data should ideally be collected across multiple:

* Geographic locations
* Agroecological zones
* Altitudes
* Seasons
* Crop varieties
* Crop-growth stages
* Pest developmental stages
* Lighting conditions
* Camera devices
* Field environments

Collecting images from only one farm or one location could introduce geographic bias into the dataset.

---

## Proposed Annotation Levels

Depending on the computer-vision task, different annotation strategies may be required.

### Image Classification

```text
Image → Pest Class
```

Example:

```text
rice_001.jpg → Yellow Stem Borer
```

---

### Object Detection

```text
Image
  ↓
Pest Class + Bounding Box
```

Example:

```text
Image: maize_001.jpg

Object:
Class: Fall Armyworm
Bounding Box: [x, y, width, height]
```

---

### Segmentation

```text
Image
  ↓
Pixel-Level Mask
```

Segmentation annotations would enable more detailed analysis but require substantially more annotation effort.

---

## Expert Verification

Pest labels should ideally be verified by qualified experts.

Potential verification sources include:

* Entomologists
* Agricultural researchers
* Crop-protection specialists
* Plant-protection experts
* Trained agricultural technicians

Expert verification is particularly important when visually similar pest species are present.

---

## Recommended Metadata

Future Nepal-specific images should ideally include metadata such as:

| Field                  | Example                  |
| ---------------------- | ------------------------ |
| Image ID               | NP_RICE_0001             |
| Crop                   | Rice                     |
| Pest                   | Yellow stem borer        |
| Scientific name        | *Scirpophaga incertulas* |
| Life stage             | Larva                    |
| Location               | Nepal                    |
| Collection environment | Natural field            |
| Annotation type        | Bounding box             |
| Verification           | Expert verified          |

Additional metadata may include altitude, season, crop-growth stage, camera device, date of collection, and environmental conditions where appropriate.

Sensitive or personally identifiable location information should not be published unnecessarily.

---

## Suggested Future Dataset Structure

If Nepal-specific data are collected, the dataset could be organized as:

```text
data/
│
├── README.md
│
├── raw/
│   ├── rice/
│   ├── maize/
│   ├── wheat/
│   ├── potato/
│   ├── tomato/
│   └── cucurbits/
│
├── processed/
│   ├── train/
│   ├── validation/
│   └── test/
│
├── annotations/
│   ├── classification/
│   ├── detection/
│   └── segmentation/
│
└── metadata/
    └── dataset_metadata.csv
```

> This structure represents proposed future experimental work. These directories do not imply that a Nepal-specific dataset has already been collected.

---

## Data Leakage Prevention

When constructing future train, validation, and test sets, special care should be taken to prevent data leakage.

Images originating from the same:

* Farm
* Collection session
* Video sequence
* Camera burst
* Near-duplicate image group

should not be unintentionally distributed across training and testing sets.

For geographic-generalization experiments, location-based splitting may be preferable.

For example:

```text
Training:
Kathmandu + Chitwan

Validation:
Chitwan

Independent Geographic Test:
Pokhara
```

The exact locations would depend on the actual data-collection design.

---

## Planned Experimental Use

Future experiments may use the data in three main settings.

### Experiment A — International Benchmark

```text
IP102
  ↓
Training
  ↓
IP102 Test
```

This establishes benchmark performance.

### Experiment B — Geographic Generalization

```text
IP102
  ↓
Training
  ↓
Nepal Field Test
```

This measures how well an internationally trained model transfers to Nepalese agricultural conditions.

### Experiment C — Nepal Fine-Tuning

```text
IP102 Pre-training
        ↓
Nepal Training Data
        ↓
Fine-tuning
        ↓
Independent Nepal Test
```

This evaluates whether Nepal-specific fine-tuning can reduce geographic domain shift.

---

## Data Availability

### IP102

The complete IP102 dataset is **not redistributed through this repository**.

Researchers interested in using IP102 should obtain the dataset from its original source and review the corresponding publication, license, and usage conditions.

### Nepal-Specific Dataset

A Nepal-specific dataset is currently part of the **proposed future experimental work**.

The current systematic-review project does not claim to provide a completed large-scale Nepal-specific insect-pest dataset.

If such a dataset is developed in the future, information about its availability, annotation format, license, collection methodology, and citation requirements can be added to this directory.

---

## Important Notice

The presence of dataset statistics, analyses, or references in this repository does not imply ownership of the original datasets.

Third-party datasets remain the property of their respective authors or organizations and are subject to their original licenses and terms of use.

This repository currently provides **research analysis and documentation**, rather than redistribution of the original datasets.

---

## Related Project

For the complete research methodology, literature review, benchmark analysis, Nepal-specific research gaps, and proposed experimental framework, see the main repository:

[`../README.md`](../README.md)

The complete research paper is available in:

[`../paper/`](../paper/)
