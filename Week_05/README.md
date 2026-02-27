# Assignment 5 — Professional Genie & CSS Styling
**CSD5730 | NLP in R | Spring 2026**  
**Author:** Peace Onebunne  
**Date:** February 2026

---

## Overview

This assignment builds directly on Assignment 4 by upgrading the text cleaning pipeline, applying a professional CSS stylesheet, and running a psycholinguistic analysis of the Unabomber Manifesto using a curated lexical lookup database. Four emotional and semantic variables are tracked across the full document to test a hypothesis about tone and intensity.

---

## What's in This Assignment

| Step | Description |
|------|-------------|
| 1 | Upgrade the Cleaning Genie → `peace_genie_pro()` |
| 2 | Re-run the Unabomber pipeline with the new cleaner |
| 3 | Build a 3-row lexical comparison table (Raw / Clean / No Stopwords) |
| 4 | State a hypothesis about tone and emotional trajectory |
| 5 | Score each text chunk using Dr. Jamie's lookup database |
| 6 | Join scores and compute chunk-level averages |
| 7 | Line plots — one per variable |
| 8 | Combined facet plot across all four variables |
| 9 | Describe results in plain language |

---

## Libraries Used

```r
library(tidyverse)
library(quanteda)
library(quanteda.textplots)
library(ggplot2)
library(knitr)
library(kableExtra)
library(textstem)
```

---

## The Upgraded Genie — `peace_genie_pro()`

The cleaner was renamed and improved from Assignment 4. Key features:

- Multi-line input collapsed into a single string automatically
- Double-pass UTF-8 encoding fix (handles PDF and web artifacts)
- Smart quote normalization (curly → straight)
- URL and email removal
- Hyphen and underscore splitting
- Number removal
- Optional apostrophe preservation via token placeholder
- Whitespace normalization and trimming

> Still base R only for the core cleaning — no external packages in the pipeline.

---

## Lexical Comparison Table

| Version | Tokens | Types | TTR |
|---------|--------|-------|-----|
| Raw | ~34,085 | ~4,589 | ~0.13 |
| Clean | ~34,486 | ~4,030 | ~0.12 |
| Clean + Stopwords Removed | ~17,891 | ~3,915 | ~0.22 |

TTR rises after stopword removal, reflecting the increase in meaningful lexical diversity once high-frequency function words are stripped out.

---

## Hypothesis

> *"The tone of the Unabomber manifesto will become more emotionally intense as the text progresses — showing higher anger, higher arousal, lower valence, and consistently low concreteness toward the later sections."*

---

## Four Variables Analyzed

Scored using **Dr. Jamie Reilly's psycholinguistic lookup database** (`lookup_Jul25.rda`):

| Variable | What It Measures |
|----------|-----------------|
| `emo_anger_rescale` | Anger level of the language |
| `emo_valence_b24_rescale` | Positive vs. negative emotional tone |
| `emo_arousal_b24_rescale` | Emotional intensity / activation |
| `sem_cnc_b24_rescale` | Concreteness — abstract vs. tangible language |

The manifesto was split into **300-word chunks**, lemmatized, joined to the lookup database, and averaged per chunk.

---

## Visualizations

- **4 individual line plots** — one per variable, tracking mean score across all text chunks
- **1 combined facet plot** — all four variables side by side for easy comparison

---

## Key Findings

- **Anger** fluctuates throughout but does not build linearly toward the end
- **Arousal** varies across chunks with no consistent upward trend
- **Valence** shifts back and forth — negativity is not concentrated in later sections
- **Concreteness** stays consistently low across the entire text, confirming the manifesto's abstract, system-level register

The hypothesis was **partially supported** — the abstract orientation held up, but the predicted linear escalation in anger, arousal, and negativity did not materialize.

---

## Folder Structure

```
Assignment_05/
├── Assignment5_Onebunne.Rmd
├── Assignment5_Onebunne.html
├── Images/
│   └── Amy_Logo.png
└── Styles/
    └── OnebunnePro.css
```

---

## Live Report

> [View Rendered HTML Report](https://ahmypeace.github.io/CSD5730_NLP_R_Spring2026/Assignment5_Onebunne.html)

---

## Data Sources

| File | Source |
|------|--------|
| Unabomber Manifesto | [Reilly Lab GitHub](https://raw.githubusercontent.com/Reilly-ConceptsCognitionLab/reillylab_publicdata/main/unabomber_manifesto.txt) |
| Lookup Database | [lookup_Jul25.rda — Reilly Lab GitHub](https://github.com/Reilly-ConceptsCognitionLab/reillylab_publicdata/blob/main/lookup_Jul25.rda?raw=true) |

---

*Styled with OnebunnePro.css | Submitted as part of CSD5730 — NLP in R, Spring 2026*
