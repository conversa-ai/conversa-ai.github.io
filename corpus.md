---
layout: default
title: "Multilingual Dialogue Corpus"
---

# Multilingual Dialogue Corpus

## Overview
We introduce **esCorpiusDialog**, a comprehensive multilingual dialogue corpus designed to support the development of advanced conversational AI systems in Spanish, Catalan, Basque, and Galician. It is the largest dataset of its kind for these languages, consisting of dialogues sourced from diverse platforms including movie subtitles, forums, newsgroups, and books.

## Languages
- **Spanish:** ~29.8 million dialogues  
- **Catalan:** ~92 thousand dialogues  
- **Basque:** ~116 thousand dialogues  
- **Galician:** ~63 thousand dialogues  

## Dataset Statistics
- **Total Size:** 20.4 GiB  
- **Total Dialogues:** 30 092 360  
- **Total Turns:** 122 795 025  
- **Total Tokens:** 2 816 643 356  

| Source         | Dialogues    | Turns        | Turns/Dialogue | Tokens          | Size (GB) |
|----------------|--------------|--------------|----------------|-----------------|-----------|
| OpenSubtitles  | 20 254 311   | 96 925 151   | 4.8            | 1 009 773 637   | 4.1       |
| Usenet (es)    |    494 928   |  1 799 788   | 3.6            |   294 166 758   | 4.1       |
| Forums (es)    |  9 330 256   | 23 974 761   | 2.6            | 1 510 109 378   | 12.2      |
| Gutenberg      |     12 865   |     95 325   | 7.4            |     2 593 583   | 0.01      |

## Data Sources
- **OpenSubtitles:** Movie subtitles from various films and series.  
- **Usenet:** Conversations from historical newsgroups.  
- **Forums:** Discussions from Spanish forums such as Meneame, Mediavida, and Reddit.  
- **Gutenberg:** Dialogues extracted from books in Spanish and Catalan.  

## Data Creation Tools

### Scraping
- Custom Python Scrapy spiders for forums and APIs  
- Extraction pipelines for subtitles and newsgroups  

### Cleaning and Processing
- Text normalization (removal of HTML tags, profanity, and personal data)  
- Dialogue turn segmentation based on timestamps and conversation structures  

### Organizing
- JSON and CSV formats with clear metadata  
- Dialogues structured by chronological and conversational coherence  

## Evaluation Framework
- Adapted Spanish MT-Eval benchmark  
- Tasks: Recollection, Expansion, Refinement, and Follow-up  
- Performance evaluated using fine-tuned Llama-3 models  

## Results and Impact
- Significant improvement in multi-turn dialogue capabilities when fine-tuned on esCorpiusDialog  
- Reduced performance gap between smaller and larger models  
- Enables advanced multilingual conversational systems  

## Ethical Considerations
- Anonymized personal data  
- Recognition of potential biases and plans for future bias mitigation  

## Access
- **Dataset & Code:** Available openly under CC-BY-NC-ND 4.0 license  
- [Zenodo DOI](https://doi.org/10.5281/zenodo.15017668)  

## Related Publication
**esCorpiusDialog**: A Large-Scale Multilingual Dialogue Dataset in Spanish, Catalan, Basque, and Galician to Improve LLMs in Conversational Tasks.  
Kharitonova et al., Under review (2025).  
