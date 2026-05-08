# DNA Sequence Classification Using Deep Learning

A deep learning-based bioinformatics project for classifying DNA sequences into **Promoter** and **Non-Promoter** regions using **Convolutional Neural Networks (CNN)** and **Hybrid CNN-BiLSTM architectures**.

This project was developed for **Bioinformatics and Artificial Intelligence**.

---

# Team Members

* **Vaditya Venkat Trishal Jadav**
* **Shivaram Velidineni**
* **Shashankh Madrri**

---

# Project Overview

DNA sequence classification is an important task in bioinformatics that helps identify biologically functional regions in genomic sequences.

Promoters are DNA regions responsible for initiating gene transcription. Accurate identification of promoter regions is critical in:

* Gene regulation studies
* Disease analysis
* Drug discovery
* Personalized medicine
* Genomic research

Traditional biological analysis is expensive and time-consuming. This project uses deep learning to automatically identify promoter regions from raw DNA sequences.

---

# Problem Statement

Modern sequencing technologies generate massive amounts of genomic data every day. Although DNA sequencing has become faster and cheaper, interpreting this data remains a major challenge.

Traditional laboratory-based analysis methods are:

* Slow
* Expensive
* Difficult to scale

This creates the need for automated, scalable, and accurate computational models for DNA sequence classification.

---

# Motivation

This project was developed to support:

## Personalized Medicine

DNA classification helps design patient-specific treatments based on genetic information.

## Early Disease Detection

Promoter identification helps detect genetic mutations related to diseases such as cancer.

## Pathogen Identification

DNA classification can help identify bacterial and viral genomes.

## Drug Discovery

Understanding promoter regions helps researchers identify target genes for drug development.

---

# Dataset Information

The dataset consists of DNA promoter and non-promoter sequences.

## Dataset Specifications

| Feature           | Value                  |
| ----------------- | ---------------------- |
| Total Sequences   | 36,131                 |
| Sequence Length   | 251 base pairs         |
| Number of Classes | 2                      |
| Classes           | Promoter, Non-Promoter |
| Alphabet          | A, T, C, G             |

---

## Dataset Split

| Dataset  | Number of Samples |
| -------- | ----------------: |
| Training |            27,097 |
| Testing  |             9,034 |

---

## Class Distribution

### Training Set

| Class        | Samples |
| ------------ | ------: |
| Promoter     |  14,742 |
| Non-Promoter |  12,355 |

### Testing Set

| Class        | Samples |
| ------------ | ------: |
| Promoter     |   4,915 |
| Non-Promoter |   4,119 |

---

# Literature Review

This project was inspired by the following research works:

## 1. DeepBind (2015)

One of the earliest deep learning models for DNA sequence analysis.

Key contribution:

* Used CNNs for motif detection.

## 2. DanQ (2016)

Hybrid deep learning architecture.

Key contribution:

* Combined CNN and LSTM.

## 3. DeeperBind (2016)

Improved sequence modeling.

Key contribution:

* Better positional dependency learning.

---

# Methodology

The complete workflow consists of:

```text
Dataset Acquisition
        ↓
Data Cleaning
        ↓
Sequence Preprocessing
        ↓
One-Hot Encoding
        ↓
Train / Validation / Test Split
        ↓
CNN Model Training
        ↓
CNN-BiLSTM Model Training
        ↓
Hyperparameter Tuning
        ↓
Evaluation
        ↓
Final Model Selection
```

---

# Step 1 — Dataset Acquisition

DNA promoter and non-promoter sequences were collected from standard training and testing datasets.

These sequences represent real genomic information from biological sources.

---

# Step 2 — Data Cleaning

Raw genomic data may contain:

* Invalid characters
* Ambiguous bases
* Formatting issues

We removed unwanted symbols and retained only:

```text
A, C, G, T
```

This ensures biologically meaningful input.

---

# Step 3 — Sequence Preprocessing

DNA sequences vary in length.

To provide fixed-size input for deep learning models, all sequences were standardized to:

```text
251 base pairs
```

Two techniques were used:

* Padding
* Truncation

---

# Step 4 — One-Hot Encoding

Each DNA nucleotide was converted into a binary vector.

```text
A = [1,0,0,0]
C = [0,1,0,0]
G = [0,0,1,0]
T = [0,0,0,1]
```

Each sequence became:

```text
251 × 4 matrix
```

This matrix was used as model input.

---

# Step 5 — Data Splitting

The dataset was divided into:

* Training Set
* Validation Set
* Testing Set

Purpose:

* Training → Model learning
* Validation → Hyperparameter tuning
* Testing → Final unbiased evaluation

---

# Models Used

## 1. CNN Model

The CNN model extracts local promoter motifs from DNA sequences.

Key advantages:

* Fast training
* Strong local pattern detection
* Efficient motif extraction

---

## 2. Hybrid CNN-BiLSTM Model

This hybrid model combines:

### CNN

Extracts local DNA motifs.

### BiLSTM

Captures long-range sequence dependencies.

This helps understand complex biological relationships.

---

# Model Training

Two models were trained independently:

* CNN
* CNN-BiLSTM

Training included:

* Batch optimization
* Loss minimization
* Validation monitoring

---

# Hyperparameter Tuning

The following parameters were optimized:

* Number of filters
* Kernel size
* Dropout rate
* Learning rate
* LSTM units

This improved model performance and stability.

---

# Evaluation Metrics

Model performance was evaluated using:

* Accuracy
* Precision
* Recall
* F1-Score
* ROC-AUC
* PR-AUC
* Confusion Matrix
* Classification Report

---

# Results

## Final CNN Model

| Metric    |  Value |
| --------- | -----: |
| Accuracy  |  90.6% |
| Precision |  0.955 |
| Recall    |  0.869 |
| F1-Score  |   0.91 |
| ROC-AUC   | 0.9648 |
| PR-AUC    | 0.9755 |

### Observations

The CNN model achieved outstanding classification performance with strong promoter detection.

---

## Final Hybrid CNN-BiLSTM Model

| Metric   |  Value |
| -------- | -----: |
| Accuracy |  72.2% |
| ROC-AUC  | 0.8469 |

### Observations

The hybrid model showed moderate performance but lower accuracy compared to CNN.

---

# Final Model Comparison

The CNN model outperformed CNN-BiLSTM in:

* Accuracy
* Precision
* Recall
* ROC-AUC
* PR-AUC

This indicates promoter classification depends more on local sequence motifs.

---

# Technologies Used

* Python
* NumPy
* Pandas
* Matplotlib
* Seaborn
* Scikit-learn
* TensorFlow
* Keras
* Deep Learning

---

# Installation

## Clone Repository

```bash
git clone <your-repository-url>
cd DNA-Sequence-Classification
```

---

## Install Dependencies

```bash
pip install numpy pandas matplotlib seaborn scikit-learn tensorflow keras
```

---

# Running the Project

Open Jupyter Notebook:

```bash
jupyter notebook final_bio_code.ipynb
```

Run all cells sequentially.

---

# Project Structure

```text
DNA-Sequence-Classification
│
├── final_bio_code.ipynb
├── README.md
├── dataset/
├── models/
├── results/
├── figures/
└── references/
```

---

# Applications

This project can be applied in:

* Cancer genomics
* Gene regulation studies
* Disease mutation detection
* Drug discovery
* Personalized medicine
* Biological sequence analysis

---

# Future Work

Future improvements may include:

* Transformer-based DNA models
* Attention mechanisms
* Multi-class genomic classification
* Real-time genome analysis
* Larger genomic datasets

---

# Conclusion

This project demonstrates that deep learning can successfully classify DNA sequences into promoter and non-promoter regions.

Among all tested architectures, the CNN model achieved the best performance with:

```text
Accuracy = 90.6%
ROC-AUC = 0.9648
```

The results show that convolutional neural networks effectively capture promoter motifs and can support future genomic research.

---

# References

1. DeepBind (2015)
2. DanQ (2016)
3. DeeperBind (2016)
4. DNABERT (2021)
5. Deep Learning – LeCun, Bengio, Hinton

---

**Project files and experimental setup are based on your uploaded notebook and project materials.** 
