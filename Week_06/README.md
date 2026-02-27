
# Assignment 6 — Hypothesis Construction on the Gaslighting Dataset

**CSD5730 | NLP in R | Spring 2026**
**Author:** Peace Onebunne
**Date:** February 2026

---

## Overview

This assignment develops a theory-driven hypothesis about linguistic patterns in the Gaslighting Dataset. Using a custom-built text cleaning pipeline, dictionary-based feature engineering, and frequency analysis, the project tests whether gaslighting can be operationalized as a structured communicative phenomenon rather than isolated emotional disagreement.

The analysis moves from text normalization → corpus construction → tokenization → theory-based dictionary lookup → statistical frequency testing → visualization.

---

## What’s in This Assignment

| Step | Description                                        |
| ---- | -------------------------------------------------- |
| 1    | Load and inspect the Gaslighting corpus            |
| 2    | Convert ID variables to factor format              |
| 3    | Apply upgraded `peace_genie_pro()` cleaner         |
| 4    | Compare raw vs cleaned text (100-word view table)  |
| 5    | Construct a quanteda corpus                        |
| 6    | Tokenize and remove stopwords                      |
| 7    | Convert text to a Document-Feature Matrix          |
| 8    | Build a theory-driven gaslighting dictionary       |
| 9    | Extract manipulation features using `dfm_lookup()` |
| 10   | Compute frequency statistics                       |
| 11   | Visualize feature dominance                        |
| 12   | Interpret results and evaluate hypothesis          |

---

## Libraries Used

```r
library(tidyverse)
library(quanteda)
library(quanteda.textstats)
library(ggplot2)
library(knitr)
library(kableExtra)
library(textstem)
library(dplyr)
```

---

## The Cleaning Pipeline — `peace_genie_pro()`

This function was developed incrementally throughout the semester and upgraded for this assignment.

### Key Features:

* UTF-8 normalization
* NA handling and encoding repair
* HTML tag removal
* Smart quote normalization
* Roman numeral preservation
* URL and email removal
* Hyphen splitting
* Number removal
* Elongation collapse (e.g., "soooo" → "so")
* Controlled punctuation handling
* Optional apostrophe preservation
* Whitespace normalization

> Apostrophes are intentionally preserved to retain conversational constructions central to gaslighting narratives (e.g., “you didn’t,” “I never said that”).

All steps are vectorized and reproducible.

---

## Hypothesis

> *Texts in the gaslighting dataset will contain elevated frequencies of denial, blame attribution, emotional invalidation, control language, and memory destabilization markers.*

If gaslighting operates as patterned communication, it should appear systematically in word usage.

---

## Theory-Driven Dictionary Categories

The feature dictionary was constructed from peer-reviewed gaslighting research.

| Category       | What It Captures                          |
| -------------- | ----------------------------------------- |
| `denial`       | Contradiction of memory or perception     |
| `blame`        | Responsibility shifting                   |
| `invalidation` | Emotional dismissal or competence attacks |
| `control`      | Directive or dominance-based language     |
| `doubt_memory` | Cognitive destabilization                 |

Instead of selecting frequent words arbitrarily, each category is grounded in psychological theory.

Feature extraction was performed using:

```r
gas_features <- dfm_lookup(dfm_gaslight, gaslight_dict)
```

---

## Statistical Analysis

Frequency counts were calculated using:

```r
textstat_frequency(gas_features)
```

This converts communicative strategies into measurable variables.

The goal is not sentiment scoring, but structural pattern detection.

---

## Visualization

A Temple-red gradient palette was used to visualize feature dominance across categories.

* Horizontal bar plot
* Feature categories ordered by frequency
* Legend removed for clarity
* Designed for interpretability and presentation

---

## Key Findings

* **Control language** emerged as the most frequent feature category.
* **Denial** and **emotional invalidation** followed.
* **Blame attribution** and **memory destabilization** appeared consistently.

The hypothesis was supported.

Gaslighting appears not as isolated emotional disagreement, but as recurring linguistic structures that redistribute responsibility and destabilize perception.

---

## Folder Structure

```
Week_06/
├── Onebunne_Assignment_6.Rmd
├── Onebunne_Assignment_6.html
├── Images/
│   ├── Amy_Logo.png
├── Styles/
│   └── OnebunnePro.css
└── README.md
```

---

## Live Report

> [View Rendered HTML Report](https://ahmypeace.github.io/CSD5730_NLP_R_Spring2026/Assignment6_Onebunne.html)

---

## Data Source

| File                | Source                                              |
| ------------------- | --------------------------------------------------- |
| Gaslighting Dataset | Reilly Concepts & Cognition Lab — Public Repository |

Loaded directly via:

```r
load(url("https://github.com/Reilly-ConceptsCognitionLab/reillylab_publicdata/blob/main/gaslight.rda?raw=true"))
```

---

## Conceptual Contribution

This assignment demonstrates:

* How interpersonal manipulation can be operationalized linguistically
* How dictionary-based feature engineering links theory to computation
* How text analysis can measure destabilization patterns in narrative form

Rather than reducing gaslighting to emotion, this project treats it as structured communication.

---

*Styled with OnebunnePro.css | Submitted as part of CSD5730 — NLP in R, Spring 2026*
