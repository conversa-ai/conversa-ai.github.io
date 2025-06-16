---
layout: default
title: "esCorpiusDialog"
---

# esCorpiusDialog

## Overview
A Large-Scale Multilingual Dialogue Dataset in Spanish, Catalan, Basque, and Galician to Improve LLMs in Conversational Tasks.

## Languages
- **Spanish**
- **Catalan**
- **Basque**
- **Galician**

## Data-Creation Tools
### Scraping
- Custom Python Scrapy spiders
- API clients for public forums
- OpenSubtitles internal database dumps

### Cleaning
- Text normalization (Unicode, punctuation)
- PII removal
- Language detection and filtering

## Evaluation Framework
- **Automatic metrics:** BLEU, METEOR
- **Human evaluation:** fluency and adequacy ratings
- **Annotation guidelines:** see `docs/evaluation_guidelines.md`

## Access
- Data download: [Zenodo DOI](https://doi.org/xxx)
- Tooling: `/tools/corpus` directory in this repo

## Related Publication
- “Title of Corpus Paper”, Journal Name, 2023. [DOI: 10.xxxx/xxxx]: