# Assignment 7: Cleaning Pipeline Cheat Sheet

**CSD5730 | NLP in R | Spring 2026**
**Author:** Amaka Peace Onebunne

## Overview

A one-page reference for the full text analysis workflow built across the course, run on the Unabomber Manifesto. It refines the cleaning function into `peace_genie_pro()`, then walks through corpus creation, tokenization, lemmatization, a document-feature matrix, and a word frequency plot.

## What `peace_genie_pro()` Does

- Collapses multi-line input into one string
- Repairs text encoding to UTF-8
- Normalizes curly quotes to straight quotes
- Lowercases text
- Removes URLs, email addresses, and numbers
- Splits hyphenated words
- Collapses extra whitespace

## Files

- `Assignment_07_Cheat_Sheet.Rmd`: R Markdown source
- `Assignment_07_Cheat_Sheet.html`: rendered report
- `Figs/`: word frequency plot
- `Styles/` and `Images/`: stylesheet and logo

## How to Run

Open `Assignment_07_Cheat_Sheet.Rmd` in RStudio or Positron and knit to HTML. The manifesto text loads from the Reilly Lab public data repository, so an internet connection is needed.

## Libraries Used

tidyverse, quanteda, quanteda.textplots, textstem, kableExtra, ggplot2

## Live Report

[View the rendered report](https://ahmypeace.github.io/CSD5730_NLP_R_Spring2026/reports/week-10-pipeline-cheat-sheet.html)
