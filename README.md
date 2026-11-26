# CSD5730: Natural Language Processing with R (Spring 2026)

**Live portfolio:** https://ahmypeace.github.io/CSD5730_NLP_R_Spring2026/

Coursework for CSD5730, Natural Language Processing for Biobehavioral and Neuroscience Applications, at Temple University. The assignments build one text analysis pipeline in R, from basic string handling to dictionary methods, psycholinguistic norms, and semantic distance. A cleaning function that starts in Week 3 grows into `peace_genie_pro()`, which the later projects reuse.

## Assignments

| Week | Assignment | Source | Report |
|------|------------|--------|--------|
| 1 | Text Manipulation in R | [Week_01](Week_01) | [View](https://ahmypeace.github.io/CSD5730_NLP_R_Spring2026/reports/week-01-text-manipulation.html) |
| 2 | Text Cleaning and Tokenization | [Week_02](Week_02) | [View](https://ahmypeace.github.io/CSD5730_NLP_R_Spring2026/reports/week-02-text-cleaning.html) |
| 3 | Cleaning Genie | [Week_03](Week_03) | [View](https://ahmypeace.github.io/CSD5730_NLP_R_Spring2026/reports/week-03-cleaning-genie.html) |
| 4 | Unabomber Manifesto Pipeline | [Week_04](Week_04) | [View](https://ahmypeace.github.io/CSD5730_NLP_R_Spring2026/reports/week-04-unabomber-pipeline.html) |
| 5 | Professional Genie and Psycholinguistic Scores | [Week_05](Week_05) | [View](https://ahmypeace.github.io/CSD5730_NLP_R_Spring2026/reports/week-05-professional-genie.html) |
| 6 | Gaslighting Hypothesis | [Week_06](Week_06) | [View](https://ahmypeace.github.io/CSD5730_NLP_R_Spring2026/reports/week-06-gaslighting.html) |
| 6 | Genie Contest: `peace_genie_pro_max()` | [Week_06/Genie_Contest](Week_06/Genie_Contest) | [View](https://ahmypeace.github.io/CSD5730_NLP_R_Spring2026/reports/genie-contest.html) |
| 10 | Cleaning Pipeline Cheat Sheet | [Week_10](Week_10) | [View](https://ahmypeace.github.io/CSD5730_NLP_R_Spring2026/reports/week-10-pipeline-cheat-sheet.html) |
| 11 | Semantic Distance: GloVe vs. SD15 | [Week_11](Week_11) | [View](https://ahmypeace.github.io/CSD5730_NLP_R_Spring2026/reports/week-11-semantic-distance.html) |

## Repository Structure

```
CSD5730_NLP_R_Spring2026/
├── Week_01/ … Week_06/   R Markdown source, rendered HTML, data, and styles for each week
├── Week_10/              Cleaning pipeline cheat sheet
├── Week_11/              Semantic distance analysis
├── assets/               Shared stylesheet and logo
├── docs/                 Portfolio website served by GitHub Pages
└── README.md
```

## How to Run

1. Open the `.Rmd` file for a week in RStudio or Positron.
2. Install any packages listed in its setup chunk.
3. Knit to HTML.

Most datasets load directly from the [Reilly Concepts and Cognition Lab public data repository](https://github.com/Reilly-ConceptsCognitionLab/reillylab_publicdata), so an internet connection is needed.

## Tools

R, R Markdown, quanteda (with quanteda.textstats and quanteda.textplots), tidyverse, dplyr, stringr, ggplot2, textstem, kableExtra, text2vec, and the SemanticDistance package.

## Author

**Amaka Peace Onebunne**
PhD Student, Media and Communication, Temple University
[ahmypeace.github.io](https://ahmypeace.github.io)
