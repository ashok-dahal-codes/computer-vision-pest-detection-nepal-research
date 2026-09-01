# Literature Screening

This directory documents the literature-search and study-screening process used for the systematic review:

**Computer Vision for Insect Pest Detection in Nepalese Agriculture: A Systematic Review, Research Gaps, and Future Directions**

The screening process was designed to identify studies relevant to **computer vision and image-based insect-pest analysis in agriculture**, with particular attention to evidence relevant to Nepalese agricultural research.

---

## Overview

The systematic review considered publications from **2018–2025** and searched three academic databases:

* IEEE Xplore
* SpringerLink
* ScienceDirect

A total of **381 records** were retrieved.

The records were then assessed using predefined eligibility criteria.

The final eligibility-stage review corpus contained **137 records**.

---

## Search Results

| Database      | Records Retrieved |
| ------------- | ----------------: |
| IEEE Xplore   |               171 |
| SpringerLink  |               199 |
| ScienceDirect |                11 |
| **Total**     |           **381** |

These counts represent the records obtained from the database searches before eligibility assessment.

---

## Search Strategy

The literature search used combinations of terms related to:

* Agricultural insect pests
* Computer vision
* Deep learning
* Image classification
* Object detection
* Image segmentation
* CNNs
* YOLO
* Agricultural crops

A general search expression used to guide the database searches was:

```text
("insect pest" OR "crop pest" OR "agricultural pest")
AND
("computer vision" OR "deep learning" OR CNN
OR "convolutional neural network" OR YOLO
OR "object detection" OR "image classification")
AND
(crop OR agriculture OR agricultural)
```

The exact query syntax could vary between databases because IEEE Xplore, SpringerLink, and ScienceDirect use different search interfaces and query rules.

---

## Screening Workflow

The study-selection process can be summarized as:

```text
Records identified from databases
n = 381
        │
        ▼
Duplicate records removed
n = 0
        │
        ▼
Records assessed for eligibility
n = 381
        │
        ├──────────────► Records excluded
        │                n = 244
        ▼
Records meeting eligibility criteria
n = 137
        │
        ▼
Eligible review corpus
n = 137
```

---

## Study-Selection Summary

| Stage                                          | Number of Records |
| ---------------------------------------------- | ----------------: |
| Records identified                             |               381 |
| Duplicate records removed                      |                 0 |
| Records assessed for eligibility               |               381 |
| Records excluded                               |               244 |
| Records meeting eligibility criteria           |               137 |
| **Records retained in eligible review corpus** |           **137** |

---

## Duplicate Handling

Records retrieved from the three databases were checked for duplicates.

The duplicate-removal stage resulted in:

```text
Duplicate records removed = 0
```

Therefore, all **381 retrieved records** proceeded to eligibility assessment.

---

## Inclusion Criteria

A study was considered eligible when it satisfied the review's inclusion requirements.

Relevant studies generally needed to:

1. Address an **agricultural insect pest** or closely related insect-pest problem.

2. Use **image-based or computer-vision methods**.

3. Apply methods such as:

   * Image classification
   * Object detection
   * Semantic segmentation
   * Instance segmentation
   * CNN-based recognition
   * Deep learning
   * Transfer learning
   * YOLO-based detection
   * Related computer-vision techniques

4. Provide sufficient methodological or experimental information to contribute to the review.

5. Fall within the review period of **2018–2025**.

---

## Exclusion Criteria

Records were excluded when they were not sufficiently aligned with the scope of the systematic review.

Examples include studies that:

* Were unrelated to agricultural insect pests
* Focused only on plant diseases without an insect-pest component
* Focused only on weeds
* Focused only on nutrient deficiencies
* Did not use image-based or computer-vision methods
* Were outside the defined publication period
* Did not provide sufficient information relevant to the review questions
* Were otherwise outside the scope of computer-vision-based agricultural insect-pest analysis

---

## Eligibility Assessment

After duplicate checking, **381 records** were assessed against the eligibility criteria.

The result was:

```text
381 records assessed
        │
        ├── 244 excluded
        │
        └── 137 met eligibility criteria
```

Therefore:

```text
Eligibility rate
= 137 / 381 × 100
≈ 35.96%
```

Approximately **36% of the retrieved records** met the eligibility criteria.

---

## What the 137 Records Represent

The **137 records** should be interpreted as the **eligibility-stage review corpus**.

This distinction is important.

The number does not imply that every one of the 137 records contributed equally to every quantitative comparison presented in the research paper.

Different parts of the review rely on different forms of evidence.

For example:

* Some studies provide methodological evidence.
* Some provide dataset information.
* Some provide classification results.
* Some provide object-detection results.
* Some discuss deployment challenges.
* Some contribute to the identification of research gaps.
* Specific benchmark values are taken from the corresponding cited primary sources.

Therefore, the review should not be interpreted as a pooled meta-analysis of all 137 records.

---

## Data Extraction

For relevant studies, the review considered information such as:

| Category        | Information Considered                               |
| --------------- | ---------------------------------------------------- |
| Bibliographic   | Author, year, title, source                          |
| Agricultural    | Crop, pest species                                   |
| Computer Vision | Classification, detection, segmentation              |
| Model           | CNN, ResNet, YOLO, Faster R-CNN, ViT, etc.           |
| Dataset         | Dataset name, size, classes                          |
| Image Source    | Laboratory, field, trap, web, public dataset         |
| Annotation      | Image labels, bounding boxes, masks                  |
| Training        | Transfer learning, augmentation, preprocessing       |
| Evaluation      | Accuracy, precision, recall, F1, AP, mAP             |
| Deployment      | Mobile, edge, real-time considerations               |
| Limitations     | Class imbalance, domain shift, field complexity      |
| Nepal Relevance | Direct or indirect relevance to Nepalese agriculture |

Not every publication necessarily reported every variable.

Missing information should therefore be treated as unavailable rather than inferred.

---

## Main Screening Focus

The screening process was designed around the central question:

> Does the study provide evidence relevant to image-based or computer-vision analysis of agricultural insect pests?

The review therefore prioritizes research involving the relationship:

```text
Agriculture
     +
Insect Pest
     +
Image Data
     +
Computer Vision / Deep Learning
```

Studies substantially outside this intersection were excluded.

---

## Scope of the Review

The review focuses primarily on:

```text
Agricultural Crops
        ↓
Insect Pests
        ↓
Image Acquisition
        ↓
Computer Vision
        ↓
Classification / Detection / Segmentation
        ↓
Evaluation
        ↓
Potential Agricultural Application
```

The review is not intended to comprehensively cover every application of artificial intelligence in agriculture.

For example, research focusing exclusively on the following topics falls outside the central scope unless directly connected to insect-pest computer vision:

* Crop-yield prediction
* Weather forecasting
* Irrigation prediction
* Soil analysis
* Fertilizer recommendation
* Plant-disease recognition
* Weed detection
* General remote sensing

---

## PRISMA-Style Reporting

The study-selection process is reported using a **PRISMA-style flow diagram** in the research paper.

The flow diagram represents:

```text
Identification
      ↓
Duplicate Checking
      ↓
Eligibility Assessment
      ↓
Eligible Review Corpus
```

The corresponding counts are:

```text
Identification     381
        ↓
Duplicates           0
        ↓
Eligibility        381
        ↓
Excluded           244
        ↓
Eligible           137
```

The PRISMA-style figure is available in:

```text
../figures/prisma_flow_diagram.png
```

---
---

## Recommended Screening Spreadsheet

For stronger reproducibility, a future screening spreadsheet can contain columns such as:

| Field             | Description                 |
| ----------------- | --------------------------- |
| Record ID         | Unique screening identifier |
| Title             | Publication title           |
| Authors           | Publication authors         |
| Year              | Publication year            |
| Database          | Source database             |
| DOI               | DOI where available         |
| Duplicate         | Yes / No                    |
| Agricultural Pest | Yes / No                    |
| Insect Pest       | Yes / No                    |
| Computer Vision   | Yes / No                    |
| Within Date Range | Yes / No                    |
| Eligible          | Yes / No                    |
| Exclusion Reason  | Reason for exclusion        |
| Notes             | Additional screening notes  |

An example structure would be:

```text
Record_ID,Title,Year,Database,Duplicate,Insect_Pest,Computer_Vision,Eligible,Exclusion_Reason
IEEE_001,...,2023,IEEE Xplore,No,Yes,Yes,Yes,
SPR_001,...,2021,SpringerLink,No,No,Yes,No,Not an insect-pest study
SD_001,...,2024,ScienceDirect,No,Yes,No,No,No computer-vision method
```

This would make the screening process easier to audit and reproduce.

---

## Reproducibility

The purpose of maintaining this directory is to make the systematic-review methodology more transparent.

A reproducible literature review should ideally document:

* Databases searched
* Search dates
* Search queries
* Number of retrieved records
* Duplicate handling
* Eligibility criteria
* Exclusion criteria
* Screening decisions
* Reasons for exclusion
* Final eligible records

Future revisions of this repository may include additional screening documentation where redistribution is permitted.

---

## Important Methodological Note

The systematic review uses a deliberately bounded screening procedure.

The reported numbers should therefore be interpreted within the scope of:

* The three selected databases
* The defined search expressions
* The 2018–2025 publication period
* The stated inclusion criteria
* The stated exclusion criteria

The review does not claim that the **137 eligible records represent every computer-vision insect-pest study published worldwide**.

Instead, they represent the records that met the eligibility criteria within the defined search and screening procedure.

---

## Post-Review Contextual Evidence

Research published outside the defined **2018–2025** review window should not be added retrospectively to the screened corpus without formally updating the systematic search.

Such publications may instead be identified as **contextual or post-review evidence**.

For example, later Nepal-specific research can be discussed as contextual evidence while remaining separate from the 137-record eligibility-stage corpus.

This preserves the methodological boundary of the systematic review.

For an overview of the complete project, see:

[`../README.md`](../README.md)

---

## Author

**Ashok Dahal**

Email: [ashokdahal717@gmail.com](mailto:ashokdahal717@gmail.com)
