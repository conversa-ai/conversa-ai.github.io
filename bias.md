---
layout: default
title: "Bias Annotation & Detection"
---

# Bias Annotation & Detection

## Overview
We present **EsCorpiusBias**, a contextually‐annotated Spanish dialogue corpus for detecting sexism and racism in online forums. It comprises three-turn dialogue units from the Mediavida forum, annotated with Prodigy and fine‐tuned transformer models, achieving substantial gains over generic classifiers.

## Annotated Datasets

| Dataset | Source    | Dialogues | Positive (%) | Labels               | κ (Cohen’s Kappa) |
|---------|-----------|-----------|--------------|----------------------|-------------------|
| Sexism  | Mediavida | 1 001     | 22.1%        | sexist / non-sexist  | 0.55              |
| Racism  | Mediavida | 989       | 30.2%        | racist / non-racist  | 0.79              |

## Annotation Framework

### Definitions
- **Sexism**  
  - *Hostile*: open contempt or devaluation of women.  
  - *Benevolent*: “protective” stereotypes reinforcing gender roles.  
  - *Objectification*: reducing women to sexual objects.

- **Racism & Xenophobia**  
  - *Affect*: explicit hatred or anger based on race/ethnicity.  
  - *Evaluation*: negative judgments about inherent group traits.  
  - *Judgment*: negative assessments of group-typical behaviors.  
  - *Overt vs. Covert*: direct slurs vs. subtle implications (“You don’t look Spanish”).

### Protocol
1. Extract root-to-leaf three-turn dialogues via BFS.  
2. Clean text (remove PII, profanity filter, discard <10 chars).  
3. Annotate target turn in context using Prodigy’s `textcat.manual`.  
4. Adjudicate disagreements; produce final binary labels.

## Models for Bias Detection

- **Logistic Regression** on TF-IDF vectors (interpretable baseline).  
- **SpaCy TextCatBOW**: bag-of-words neural pipeline for fast inference.  
- **Transformer (BETO)**: SpaCy transformer pipeline fine-tuned on `dccuchile/bert-base-spanish-wwm-cased`.

Both single‐turn (ST) and contextualized (CTX) variants were trained with class‐balance oversampling.

## Evaluation & Results

### Sexism Detection

| Model                   | Variant | Precision | Recall | F1   | ROC-AUC |
|-------------------------|---------|-----------|--------|------|---------|
| Logistic Regression     | ST      | 52%       | 24%    | 33%  | 0.77    |
| Logistic Regression     | CTX     | 72%       | 43%    | 54%  | 0.82    |
| TextCatBOW (SpaCy)      | ST      | 69%       | 20%    | 31%  | 0.76    |
| TextCatBOW (SpaCy)      | CTX     | 64%       | 51%    | 57%  | 0.81    |
| BETO (SpaCy)            | ST      | 59%       | 76%    | 67%  | 0.85    |
| BETO (SpaCy)            | CTX     | 64%       | 71%    | 67%  | 0.87    |

### Racism Detection

| Model                   | Variant | Precision | Recall | F1   | ROC-AUC |
|-------------------------|---------|-----------|--------|------|---------|
| Logistic Regression     | ST      | 86%       | 53%    | 66%  | 0.87    |
| Logistic Regression     | CTX     | 93%       | 46%    | 61%  | 0.89    |
| TextCatBOW (SpaCy)      | ST      | 91%       | 50%    | 64%  | 0.88    |
| TextCatBOW (SpaCy)      | CTX     | 89%       | 60%    | 72%  | 0.88    |
| BETO (SpaCy)            | ST      | 84%       | 79%    | 81%  | 0.94    |
| BETO (SpaCy)            | CTX     | 75%       | 75%    | 75%  | 0.90    |

### Keyword Overlap Analysis

| Model              | Variant | Positives w/ Slur | Negatives w/ Slur |
|--------------------|---------|-------------------|-------------------|
| BETO (SpaCy)       | ST      | 96.36%            | 66.20%            |
| BETO (SpaCy)       | CTX     | 100.00%           | 96.48%            |
| TextCatBOW (SpaCy) | ST      | 96.88%            | 70.30%            |
| TextCatBOW (SpaCy) | CTX     | 100.00%           | 96.88%            |

## Ethical Considerations
- **Anonymization**: Usernames, emails, URLs removed.  
- **Bias Awareness**: Recognized potential for implicit biases; future “clean” release planned.  
- **License**: CC-BY-NC-ND 4.0 for code and data.

## Access
- **Dataset & Code**: Available under CC-BY-NC-ND 4.0  
- [Zenodo DOI](https://doi.org/10.5281/zenodo.15637906)

## Related Publication
**EsCorpiusBias:** “Contextual Annotation and Transformer-Based Detection of Racism and Sexism in Spanish Dialogues.” Kharitonova _et al._, *Future Internet*, 2025.
