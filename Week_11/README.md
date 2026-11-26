# Assignment 8: Semantic Distance

**CSD5730 | NLP in R | Spring 2026**
**Author:** Amaka Peace Onebunne

## Overview

This analysis compares two ways of measuring how close two words are in meaning. GloVe embeddings place words by the contexts they share in text. SD15 places words by human ratings of sensory, motor, and emotional experience. The analysis samples 469 unique word pairs, computes a cosine distance for each pair under both measures, and compares the two.

## Key Results

| Measure | Mean | SD | Range |
|---------|------|----|-------|
| GloVe (embedding) | 0.806 | 0.141 | 0.239 to 1.103 |
| SD15 (experiential) | 0.726 | 0.315 | 0.035 to 1.628 |

- The two distances correlate at Pearson r = 0.342 (Spearman rho = 0.346), about 12 percent shared variance.
- GloVe rates "the" and "you" as close because they appear together often. SD15 rates them as far apart.
- SD15 rates lobster and soda, and garlic and squid, as nearly identical because they share taste and smell. GloVe rates them as distant.

## Files

- `Assignment_08_Semantic_Distance.Rmd`: R Markdown source
- `Assignment_08_Semantic_Distance.html`: rendered report
- `Figs/`: distribution plot of GloVe and SD15 distances
- `Styles/onebunne_semantic_distance.css`: stylesheet

## How to Run

Open `Assignment_08_Semantic_Distance.Rmd` in RStudio or Positron and knit to HTML. It needs the [SemanticDistance R package](https://github.com/Reilly-ConceptsCognitionLab/SemanticDistance) from the Reilly Concepts and Cognition Lab.

## Live Report

[View the rendered report](https://ahmypeace.github.io/CSD5730_NLP_R_Spring2026/reports/week-11-semantic-distance.html)
