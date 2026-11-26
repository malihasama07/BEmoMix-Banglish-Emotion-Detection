# BEmoMix: Multi-Label Banglish Emotion Detection

**BEmoMix: Multi-Label Banglish Emotion Detection Using Transformer and Recurrent Models**

This repository contains research experiments on multi-label emotion detection in Banglish (Romanized Bengali-English code-mixed text) using Transformer-based and recurrent neural network architectures.

The project investigates how multilingual language models and deep learning approaches can identify multiple overlapping emotions in Banglish social media text.

## Project Overview

Banglish is a code-mixed language in which Bengali is written using Roman characters and frequently combined with English expressions. Informal spelling, transliteration variations, abbreviations, and code-switching make emotion detection challenging.

This research introduces **BEmoMix**, a multi-label Banglish emotion dataset containing 27,809 text instances annotated with seven emotion categories.

Unlike conventional single-label classification, this project allows multiple emotions to be associated with a single text instance.

## Emotion Categories

The dataset contains seven emotion labels:

1. Joy
2. Sadness
3. Anger
4. Fear
5. Hate
6. Surprise
7. Love

## Dataset Overview

BEmoMix consists of two data sources:

| Dataset Component | Number of Samples |
|---|---:|
| BNSENTMIX dataset | 15,648 |
| Newly collected samples | 12,161 |
| **Total** | **27,809** |

The dataset is divided into three subsets:

| Dataset Split | Samples |
|---|---:|
| Training | 19,466 |
| Validation | 4,171 |
| Testing | 4,172 |
| **Total** | **27,809** |

The dataset includes both single-label and multi-label instances.

**Note:** Dataset access and redistribution are subject to licensing, platform policies, and privacy constraints.

## Models and Experiments

This repository contains experimental implementations and comparisons involving the following architectures:

### Transformer-Based Models
- BanglishBERT
- XLM-RoBERTa-Base
- XLM-RoBERTa-Large
- Multilingual BERT (mBERT)
- DistilBERT
- mDeBERTa-v3
- Multilingual E5 embeddings

### Ensemble Learning
- XLM-RoBERTa and mDeBERTa ensemble
- Three-model Transformer ensemble
- Probability averaging and threshold optimization

### Recurrent and Hybrid Models
- BiLSTM
- BiLSTM with Attention
- Multilingual E5 embeddings with XGBoost

### Additional Experiments
- Attention-based feature extraction
- Multi-label classification
- Ablation studies
- Model performance comparison

## Proposed Framework: XLMR-OPT

The research paper proposes XLMR-OPT, a task-specific framework based on XLM-RoBERTa-Base.

Its main components include:

1. Targeted data augmentation using synonym replacement.
2. XLM-RoBERTa tokenization and contextual representation.
3. Hybrid CLS and attention pooling.
4. Focal loss with label smoothing.
5. Layer-wise learning-rate decay.
6. Adaptive per-class threshold optimization.

These components are integrated to improve multi-label emotion classification in noisy, code-mixed Banglish text.

## Evaluation Metrics

The models are evaluated using multiple multi-label classification metrics:

- Macro Precision
- Macro Recall
- Macro F1-score
- Micro F1-score
- Hamming Accuracy
- Exact Match Ratio (Strict Accuracy)
- Jaccard Similarity
- Label Ranking Average Precision (LRAP)
- Ranking Loss

Macro F1-score is the primary evaluation metric because it gives equal importance to all emotion categories.

## Reported Research Results

According to the research paper, the proposed XLMR-OPT framework achieved:

| Evaluation Metric | Score |
|---|---:|
| Macro F1-score | 0.7495 |
| Micro F1-score | 0.7486 |
| Hamming Accuracy | 0.9154 |
| Strict Accuracy | 0.6240 |
| Jaccard Similarity | 0.7058 |
| LRAP | 0.8491 |
| Ranking Loss | 0.0822 |

These are the results reported in the research paper and should not be interpreted as independently reproduced results for every notebook in this repository.

## Repository Structure

```text
BEmoMix-Banglish-Emotion-Detection/
│
├── README.md
│
├── notebooks/
│   ├── Transformer_Models/
│   ├── Ensemble_Models/
│   ├── Recurrent_Models/
│   ├── Embedding_Based_Models/
│   └── Ablation_Studies/
│
├── results/
│
└── requirements.txt
```

The structure above represents the suggested organization of the repository.

## Technologies Used

- Python
- PyTorch
- Hugging Face Transformers
- Hugging Face Datasets
- Scikit-learn
- NumPy
- Pandas
- XGBoost
- Kaggle Notebooks

## Research Contributions

The main contributions of this research include:

- Development of a large-scale multi-label Banglish emotion dataset.
- Evaluation of Transformer-based and recurrent neural architectures.
- Investigation of hybrid CLS-attention pooling.
- Exploration of ensemble learning for multi-label emotion detection.
- Analysis of emotion-wise performance, label correlations, and classification errors.
- Ablation analysis of the proposed XLMR-OPT framework.

## Limitations and Future Directions

Despite promising results, Banglish emotion detection remains challenging due to:

- Non-standard Romanized spelling.
- Sarcasm and implicit emotional expressions.
- Overlapping emotion categories.
- Class imbalance and rare emotion combinations.
- Regional and dialectal variations.

Future research may explore label-dependency-aware architectures, cross-lingual transfer learning, sarcasm-aware modelling, and multilingual large language models.

## Citation

If you use this research, please cite the corresponding paper:

**Swarna Saha, Maliha Ahmed Sama, and Hrithik Majumdar Shibu. (2026). BEmoMix: Multi-Label Banglish Emotion Detection Using Transformer and Recurrent Models. Proceedings of the 4th International Conference on Computing Advancements (ICCA 2026), ACM.**

## Acknowledgements

We acknowledge the contributions of the researchers and developers of the pretrained multilingual language models and open-source NLP libraries used in this research.

---

**Project:** BEmoMix – Banglish Multi-Label Emotion Detection  
**Research Area:** Natural Language Processing (NLP), Multilingual NLP, Emotion Detection, Deep Learning.
