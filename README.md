# Graded Semantic Line Detection

> **Notice: This repository is currently under construction.**
>
> This is the anonymous repository for our CVPR 2027 submission, *"Graded Semantic Line Detection."*
>
> To comply with the double-blind review process, all identifying information (authors, affiliations, etc.) has been temporarily removed. The GSLD dataset and the source code of GSLDNet will be made available in this repository.

## Overview

We introduce **Graded Semantic Line Detection (GSLD)**, a new formulation that models semantic lines across different levels of semantic evidence rather than treating them as a single deterministic set.

To this end, we construct the **GSLD dataset**, a large-scale benchmark that preserves line-wise semantic evidence from multiple independent annotators. We further propose **GSLDNet**, a controllable semantic line detector that conditions Hough-space reasoning on a target grade, enabling a single model to predict semantic lines across different grades.

## Dataset Preparation

The GSLD dataset contains **10,000 images**, divided into 8,000 training and 2,000 test images. Each image is independently annotated by five annotators, and semantic lines are assigned grades according to the degree of annotator agreement.

The dataset provides five target grades:

- **τ = 0.2:** Lines selected by at least one annotator.
- **τ = 0.4:** Lines selected by at least two annotators.
- **τ = 0.6:** Lines selected by at least three annotators.
- **τ = 0.8:** Lines selected by at least four annotators.
- **τ = 1.0:** Lines selected by all five annotators.

### Download Links

Dataset download links will be provided here.

## GSLDNet

GSLDNet is a controllable semantic line detection network that integrates image and Hough representations through grade-conditioned cross-attention.

The network consists of image token embedding, Hough token embedding, semantic grade embedding, and a Hough regression head. The target grade is encoded into a continuous representation and used to modulate attention through Feature-wise Linear Modulation (FiLM).

This design enables a single model to detect semantic lines at different grades, including intermediate grades unseen during training.

## Code

The source code, including training and evaluation scripts, will be provided here.
