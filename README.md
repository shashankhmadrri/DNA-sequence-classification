# DNA Sequence Classification Using Deep Learning

## Overview

This project focuses on classifying DNA sequences into **promoter** and **non-promoter** regions using deep learning models. DNA sequence classification is important in bioinformatics because it helps identify functional genomic regions that play a role in gene regulation.

The project converts raw DNA sequences into numerical format using **one-hot encoding** and trains deep learning models such as **CNN** and **CNN-BiLSTM** to learn biological patterns from DNA data.

---

## Project Objective

The main objective of this project is to build an automated deep learning system that can accurately classify DNA sequences as:

- Promoter sequences
- Non-promoter sequences

This helps reduce manual genomic analysis and supports faster biological interpretation.

---

## Dataset Information

The dataset contains DNA sequences with the following details:

- Total sequences: **36,131**
- Sequence length: **251 base pairs**
- Classes:
  - Promoter
  - Non-promoter
- Nucleotide alphabet:
  - A
  - T
  - C
  - G

### Dataset Split

| Dataset | Number of Sequences |
|---|---|
| Training | 27,097 |
| Testing | 9,034 |

### Class Distribution

| Set | Promoter | Non-Promoter |
|---|---:|---:|
| Training | 14,742 | 12,355 |
| Testing | 4,915 | 4,119 |

---

## Methodology

The complete workflow of the project includes:

1. Dataset acquisition
2. Data cleaning
3. Sequence preprocessing
4. One-hot encoding
5. Data splitting
6. CNN model training
7. CNN-BiLSTM model training
8. Model evaluation
9. Final model comparison

---

## Data Preprocessing

Raw DNA sequences were cleaned by removing invalid or noisy characters. Only valid nucleotide bases were retained:

```text
A, C, G, T
