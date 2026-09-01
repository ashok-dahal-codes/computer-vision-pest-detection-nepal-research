# Computer Vision for Insect Pest Detection in Nepalese Agriculture

### A Systematic Review, Research Gaps, and Future Directions

**Ashok Dahal**
Email: [ashokdahal717@gmail.com](mailto:ashokdahal717@gmail.com)

---

## Overview

This repository contains a systematic review of **computer vision and deep learning approaches for insect pest detection in agriculture**, with particular emphasis on their relevance to **Nepalese agricultural environments**.

The study examines computer-vision techniques used for insect-pest recognition, including:

* Image classification
* Object detection
* Semantic segmentation
* Instance segmentation
* Convolutional Neural Networks (CNNs)
* Transfer learning
* YOLO-based object detectors
* Lightweight and mobile-oriented models
* Vision Transformers (ViTs)

The research also analyzes existing insect-pest datasets, particularly **IP102**, investigates benchmark performance, maps important crop-pest problems relevant to Nepal, and identifies research gaps that should be addressed before reliable computer-vision pest-detection systems can be deployed in Nepalese agricultural environments.

---

## Research Motivation

Insect pests are an important constraint on agricultural productivity and can reduce both crop yield and quality.

Traditional pest identification generally depends on:

* Farmer experience
* Visual field inspection
* Agricultural technicians
* Field scouting
* Trapping
* Expert diagnosis

Although these approaches remain essential, pest identification can become difficult when insects are small, visually similar, partially hidden, or present at different developmental stages.

Computer vision provides an opportunity to support pest identification using images captured from smartphones, cameras, drones, traps, or other field devices.

However, a major challenge is **generalization**.

Models trained using international datasets may not necessarily perform reliably in Nepal because of differences in:

* Climate
* Altitude
* Crop varieties
* Pest populations
* Agricultural practices
* Field backgrounds
* Lighting conditions
* Camera devices
* Pest developmental stages

This research therefore investigates not only existing computer-vision techniques but also their practical relevance to Nepalese agriculture.

---

## Research Objectives

The main objectives of this study are:

1. Examine existing computer-vision approaches for agricultural insect-pest recognition and detection.
2. Categorize existing studies according to computer-vision task, model architecture, crop, pest species, dataset, and experimental setting.
3. Analyze the characteristics and limitations of datasets used for insect-pest research.
4. Examine evaluation metrics and the comparability of reported results.
5. Identify research gaps relevant to Nepalese agricultural environments.
6. Propose a future research agenda for robust and deployable pest-detection systems in Nepal.

---

## Research Questions

The systematic review investigates the following questions:

**RQ1:** What computer-vision methods have been used for agricultural insect pest recognition and detection?

**RQ2:** Which crops and insect pest species have received the greatest research attention?

**RQ3:** What datasets, image-acquisition environments, annotation strategies, and dataset sizes have been used?

**RQ4:** Which evaluation metrics are commonly reported, and to what extent are results comparable across studies?

**RQ5:** What limitations related to generalization, dataset quality, environmental variation, and deployment are reported?

**RQ6:** What research gaps are particularly relevant to insect pest detection in Nepalese agriculture?

**RQ7:** What methodological and technological directions should guide future Nepal-specific experimental research?

---

## Systematic Review Methodology

The research follows a systematic-review approach inspired by **PRISMA 2020** reporting principles.

Literature was collected from:

* IEEE Xplore
* SpringerLink
* ScienceDirect

The review considered publications from **2018–2025**.

### Study Selection

| Selection Stage                          | Records |
| ---------------------------------------- | ------: |
| IEEE Xplore                              |     171 |
| SpringerLink                             |     199 |
| ScienceDirect                            |      11 |
| **Total records identified**             | **381** |
| Duplicate records removed                |       0 |
| Records assessed for eligibility         |     381 |
| Records excluded                         |     244 |
| **Records meeting eligibility criteria** | **137** |

The records were evaluated using predefined inclusion and exclusion criteria focusing on agricultural insect pests and image-based or computer-vision methods.

---

## Computer-Vision Approaches

The review organizes existing approaches into four major computer-vision tasks.

| Task                  | Output                  | Agricultural Application                 |
| --------------------- | ----------------------- | ---------------------------------------- |
| Classification        | Class label             | Identify pest species                    |
| Object Detection      | Class + bounding box    | Locate and count pests                   |
| Semantic Segmentation | Pixel-level classes     | Estimate affected areas                  |
| Instance Segmentation | Individual object masks | Separate individual or overlapping pests |

### Classification

Classification determines which pest species is represented in an image.

Representative architectures include:

* ResNet
* DenseNet
* EfficientNet
* MobileNet

### Object Detection

Object detection identifies both the pest class and its location within an image.

Representative approaches include:

* YOLO
* Faster R-CNN
* FPN
* SSD
* RefineDet

Object detection is particularly relevant to field applications because a single agricultural image may contain multiple insects.

### Segmentation

Segmentation provides pixel-level information and can potentially support:

* Pest boundary identification
* Pest size estimation
* Damage-area estimation
* Separation of overlapping insects
* Detailed crop-damage analysis

---

## IP102 Dataset Analysis

A major dataset examined in this research is **IP102**, a large-scale benchmark for insect-pest recognition.

### Dataset Statistics

| Property          |  Value |
| ----------------- | -----: |
| Total images      | 75,222 |
| Pest classes      |    102 |
| Training images   | 45,095 |
| Validation images |  7,508 |
| Testing images    | 22,619 |
| Detection images  | 18,983 |

The classification dataset follows an approximately:

**60% training / 10% validation / 30% testing**

distribution.

IP102 also exhibits a natural long-tailed class distribution, making class imbalance an important consideration when evaluating models.

---

## Nepal-Relevant IP102 Subsets

Three IP102 crop groups are particularly relevant to major staple crops in Nepal.

| Crop       | Pest Classes |     Images |
| ---------- | -----------: | ---------: |
| Rice       |           14 |      8,417 |
| Corn/Maize |           13 |     14,015 |
| Wheat      |            9 |      3,418 |
| **Total**  |       **36** | **25,850** |

Together, these subsets represent approximately **34.36% of the complete IP102 dataset**.

However, IP102 is an international benchmark and should not be interpreted as a Nepal-specific dataset.

---

## Published IP102 Classification Performance

The original IP102 benchmark demonstrates that insect-pest recognition remains a difficult computer-vision problem.

| Model     |   F1 (%) | G-mean (%) | Accuracy (%) |
| --------- | -------: | ---------: | -----------: |
| AlexNet   |     34.1 |       27.0 |         41.8 |
| GoogLeNet |     32.7 |       21.3 |         43.5 |
| VGGNet    |     38.7 |       30.9 |         48.2 |
| ResNet    | **40.1** |   **31.5** |     **49.4** |

The difference between accuracy and G-mean also demonstrates the effect of class imbalance.

---

## Performance on Nepal-Relevant Crop Groups

The original IP102 study reported substantial differences in ResNet performance across crop groups.

| Crop       | Classes | F1 (%) | Accuracy (%) |
| ---------- | ------: | -----: | -----------: |
| Rice       |      14 |   30.4 |         32.1 |
| Corn/Maize |      13 |   54.6 |         62.2 |
| Wheat      |       9 |   35.5 |         53.0 |

The difference between corn/maize and rice classification accuracy is **30.1 percentage points**.

This demonstrates that performance obtained for one crop-pest group should not automatically be generalized to another.

---

## Object-Detection Benchmark

The IP102 object-detection benchmark also demonstrates the difficulty of detecting small insects in complex environments.

| Detector     | Backbone   |    AP (%) |  AP50 (%) |  AP75 (%) |
| ------------ | ---------- | --------: | --------: | --------: |
| Faster R-CNN | VGG-16     |     21.05 |     47.87 |     15.23 |
| FPN          | ResNet-50  | **28.10** | **54.93** | **23.30** |
| SSD300       | VGG-16     |     21.49 |     47.21 |     16.57 |
| RefineDet    | VGG-16     |     22.84 |     49.01 |     16.82 |
| YOLOv3       | DarkNet-53 |     25.67 |     50.64 |     21.79 |

These relatively low AP values illustrate the difficulty of accurately locating insects under realistic image conditions.

---

## Nepalese Agricultural Context

The research considers pest-detection opportunities associated with several important crops in Nepal.

### Rice

Representative pest:

**Yellow stem borer (*Scirpophaga incertulas*)**

Potential applications include pest classification, detection, and field monitoring.

### Maize

Representative pest:

**Fall armyworm (*Spodoptera frugiperda*)**

Fall armyworm is particularly relevant because pest appearance and crop damage can vary considerably across developmental stages and field conditions.

### Wheat

Representative pest:

**Aphids**

Potential research includes field-based pest detection and damage assessment.

### Potato

Representative pest:

**Potato tuber moth (*Phthorimaea operculella*)**

Potential applications include insect detection, damage detection, and crop-health assessment.

### Tomato

Representative pest:

**Tomato leaf miner (*Tuta absoluta*)**

Potential applications include pest detection and damage quantification.

### Cucurbits

Representative pests:

**Cucurbit fruit flies (*Bactrocera/Zeugodacus* spp.)**

Potential applications include infestation and fruit-damage detection.

---

## Major Research Gaps

The review identifies several important gaps that should be addressed before reliable computer-vision pest-detection systems can be deployed in Nepal.

### 1. Nepal-Specific Dataset Gap

A large-scale, publicly available dataset representing Nepalese insect pests and Nepalese agricultural field conditions was not identified in the reviewed evidence.

### 2. Geographic Generalization Gap

Models trained using international datasets may experience domain shift when applied to Nepalese agricultural environments.

### 3. Environmental Gap

Real agricultural fields contain difficult visual conditions including:

* Shadows
* Direct sunlight
* Complex vegetation
* Soil backgrounds
* Partial occlusion
* Small pest objects
* Damaged leaves
* Variable object scales

### 4. Species and Life-Stage Gap

The same pest species can appear substantially different across:

* Eggs
* Larvae
* Pupae
* Adults

Meanwhile, different pest species may have highly similar appearances.

### 5. Annotation Gap

Annotation effort increases approximately as:

```text
Image Label
    ↓
Bounding Box
    ↓
Segmentation Mask
```

### 6. Class-Imbalance Gap

Naturally collected pest datasets may contain significantly different numbers of images for different pest species.

### 7. Reproducibility Gap

Future research should clearly report datasets, preprocessing, training procedures, model configurations, evaluation metrics, hardware, and source code where possible.

### 8. Deployment Gap

A practical Nepalese system may need to operate under:

* Limited mobile connectivity
* Low-cost Android hardware
* CPU-only inference
* Limited memory
* Limited battery capacity
* Offline conditions

---

## Proposed Nepal-Specific Dataset Pipeline

The research proposes the following dataset-development process:

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

A Nepal-specific dataset should capture variation in geography, altitude, season, crop variety, pest developmental stage, lighting, camera devices, object scale, background complexity, and crop-growth stage.

---

## Proposed Experimental Extension

The systematic review serves as the foundation for future experimental research.

A particularly important experiment would compare:

```text
Experiment A

IP102
  ↓
Model Training
  ↓
IP102 Test Set
```

with:

```text
Experiment B

IP102
  ↓
Model Training
  ↓
Nepalese Field Test Set
```

and:

```text
Experiment C

IP102 Pre-training
        ↓
Nepal Dataset Fine-tuning
        ↓
Independent Nepal Test Set
```

The objective would be to directly measure **geographic domain shift** between international benchmark datasets and Nepalese agricultural environments.

---

## Future Development

The planned experimental extension of this research may include:

* Nepal-specific pest-image collection
* Expert pest annotation
* IP102 preprocessing
* ResNet baseline classification
* EfficientNet classification
* MobileNet classification
* YOLO-based pest detection
* Faster R-CNN/FPN comparison
* Transfer-learning experiments
* Cross-dataset evaluation
* Cross-location evaluation
* Model robustness testing
* Mobile/edge deployment analysis

The longer-term objective is to investigate an end-to-end system:

```text
Image Capture / Upload
          ↓
Image Preprocessing
          ↓
Computer-Vision Model
          ↓
Pest Classification / Detection
          ↓
Pest Class + Confidence + Location
          ↓
Decision-Support Information
```

---

## Repository Structure

```text
computer-vision-pest-detection-nepal/
│
├── README.md
│
├── LICENSE
│
├── .gitignore
│
│
├── paper/
│   ├── Computer_Vision_Insect_Pest_Detection_Nepal.pdf
│   └── Computer_Vision_Insect_Pest_Detection_Nepal.docx
│
├── figures/
|
│
├── data/
│   └── README.md
│
├── screening/
│   └── README.md
│
└── experiments/
    └── README.md
```

---

## Research Paper

The complete systematic review is available in the [`paper/`](paper/) directory.

The paper contains the complete methodology, dataset analysis, benchmark evaluation, Nepal-specific crop-pest analysis, research gaps, discussion, future research agenda, and references.

---

## Current Project Status

**Systematic Review:** Completed

**Literature Screening:** Completed

**Dataset Analysis:** Completed

**Research Gap Analysis:** Completed

**Nepal-Specific Dataset Collection:** Proposed future work

**Experimental Model Training:** Proposed future work

**Field Evaluation:** Proposed future work

**Deployment:** Proposed future work

This distinction is important: the repository currently represents a **systematic review and research framework**, not a completed Nepal-specific pest-detection model.

---

## Technologies and Research Areas

`Computer Vision` `Deep Learning` `Machine Learning` `CNN` `YOLO` `Object Detection` `Image Classification` `Image Segmentation` `Transfer Learning` `Vision Transformers` `IP102` `Agricultural AI` `Systematic Review` `PRISMA` `Nepal`

---

## Citation

If you use or reference this work, please cite the repository and research paper appropriately.

```text
Dahal, A. Computer Vision for Insect Pest Detection in Nepalese Agriculture:
A Systematic Review, Research Gaps, and Future Directions.
```

> This work is currently presented as an independent systematic review/research project and should not be interpreted as a peer-reviewed publication unless a formally published version becomes available.

---

## Author

**Ashok Dahal**

Research interests include machine learning, deep learning, computer vision, and practical AI applications.

Email: [ashokdahal717@gmail.com](mailto:ashokdahal717@gmail.com)

