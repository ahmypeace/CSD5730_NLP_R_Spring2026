# Assignment 4 — Unabomber Manifesto: Text Cleaning & Analysis
**CSD5730 | NLP in R | Spring 2026**  
**Author:** Peace Onebunne  
**Date:** February 2026

---

## Overview

This assignment demonstrates a full NLP pipeline in R using the **Unabomber Manifesto** as source text. Starting from a raw `.txt` file pulled directly from GitHub, the workflow walks through text cleaning, corpus construction, tokenization, lexical analysis, and visualization — all using **base R** and **Quanteda**.

---

## What's in This Assignment

| Step | Description |
|------|-------------|
| 1 | Read in the Unabomber text from GitHub |
| 2 | Examine the structure of the raw object |
| 3 | Run the Cleaning Genie (Base R only) |
| 4 | Create a Quanteda Corpus |
| 5 | Tokenize the Text |
| 6 | Compare Lexical Characteristics (Pre vs Post cleaning) |
| 7 | Create a Document-Feature Matrix (DFM) |
| 8 | Print Top 20 Words |
| 9 | Lexical Dispersion Plot (5 Words) |
| 10 | Wordcloud |
| 11 | Print DFM (Top 20 Words Only) |

---

## Libraries Used

```r
library(quanteda)
library(quanteda.textplots)
library(ggplot2)
library(knitr)
library(kableExtra)
```

---

## The Cleaning Genie

A custom base R cleaning function was written for this assignment. It handles:

- Lowercasing
- Number removal
- Punctuation removal
- Whitespace normalization and trimming

> No external packages were used in the cleaning step — base R only.

---

## Key Results

| Version | Tokens | Types | TTR |
|---------|--------|-------|-----|
| Pre-Clean | 34,085 | 4,589 | 0.13 |
| Post-Clean | 17,891 | 3,915 | 0.22 |

The **Type-Token Ratio (TTR)** increased after cleaning, reflecting higher lexical diversity once stopwords and noise were removed.

**Top 5 Most Frequent Words (post-cleaning):**
`society`, `system`, `people`, `power`, `one`

---

## Visualizations

- **Lexical Dispersion Plot** — tracks where the top 5 words appear across the document, split into 300-word chunks
- **Wordcloud** — visual overview of the 100 most dominant terms in the cleaned text

---

## Key Takeaways

- Always inspect structure before cleaning
- Cleaning dramatically affects token and type counts
- Stopword removal changes interpretation of dominant themes
- The DFM is the foundation for most downstream text analysis
- Visualization (dispersion + wordcloud) helps surface patterns quickly

---

## Live Report

> [View Rendered HTML Report](https://ahmypeace.github.io/CSD5730_NLP_R_Spring2026/Assignment_4.html)

---

## Data Source

Unabomber Manifesto sourced from:  
`https://raw.githubusercontent.com/Reilly-ConceptsCognitionLab/reillylab_publicdata/main/unabomber_manifesto.txt`

---

*Styled with OnebunnePro.css | Submitted as part of CSD5730 — NLP in R, Spring 2026*
