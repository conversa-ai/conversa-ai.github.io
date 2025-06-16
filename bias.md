---
layout: default
title: "Bias Annotation & Detection"
---

# Bias Annotation & Detection

## Introduction
We examine racism and sexism biases in forum data and train Prodigy-based models to detect these biases.

## Annotated Datasets
- **Sources:** Public forums (e.g., Reddit, local forums)
- **Languages:** Spanish
- **Schema:** Labels for racist, sexist, and neutral instances

## Annotation Process
- **Tool:** Prodigy (textcat recipes)
- **Interface:** interactive labeling and batch annotation
- **Quality:** inter-annotator agreement ≥ 0.8

## Bias Detection Models
- **Architecture:** Transformer-based models (e.g., BERT)
- **Training:** fine-tuned on annotated datasets
- **Evaluation:** precision, recall, F1 per class

## Results
Key findings: distribution of bias instances and model performance per language.

## Related Publications
- “Title of Bias Paper A”, Future Internet, 2025. [PDF]