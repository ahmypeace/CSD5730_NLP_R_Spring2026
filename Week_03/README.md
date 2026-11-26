# Assignment 3: Cleaning Genie

**CSD5730 | NLP in R | Spring 2026**
**Author:** Amaka Peace Onebunne

## Overview

This assignment focuses on basic text preprocessing and token analysis using R.
The objective was to import a messy text file (`sticks_messy.txt`), build a simple cleaning function, and evaluate how cleaning affects token counts.

The cleaning function normalizes the text and removes noise like punctuation, numeric artifacts, and malformed tokens.

---

## Files in This Folder

* `Assignment_03.Rmd`: R Markdown source
* `Assignment_03.html`: rendered report
* `Week_3 Cheat Sheet.Rmd` and `Week_3-Cheat-Sheet.html`: cheat sheet for the week
* `Data2/sticks_messy.txt`: original raw text file
* `Styles/Amy.css` and `Images/Amy_Logo.png`: stylesheet and logo

* `data/sticks_cleaned.txt`: cleaned output, written by `Assignment_03.Rmd` when knitted

---

## Cleaning Strategy

The `cleaning_genie()` function performs the following steps:

1. Replace line breaks and tabs with spaces
2. Convert text to lowercase
3. Remove punctuation and symbols
4. Remove standalone numbers
5. Remove mixed alphanumeric tokens (e.g., 89769hlj)
6. Remove extra whitespace
7. Trim leading and trailing spaces

The goal was not deep linguistic normalization, but structured, reproducible cleaning appropriate for introductory NLP workflows.

---

## Token Analysis

Token counts were computed using a space `" "` as the separator.

| Raw Token Count | Cleaned Token Count | Tokens Removed |
| --------------- | ------------------- | -------------- |
| 426             | 400                 | 26             |

The cleaning process removed 26 noisy tokens, primarily numeric fragments and malformed alphanumeric strings.

---

## Demonstration

The cleaning function was also tested on three independent sample strings to demonstrate that:

* Punctuation is removed
* Case is normalized
* Token counts decrease after cleaning
* Extra spaces are collapsed

These examples are included in the HTML output.


## Notes

This assignment emphasizes:

* Reproducible preprocessing
* Clear function design
* Transparent token accounting
* Structured output formatting

All code and outputs are fully documented in the R Markdown file.

## Live Report

[View the rendered report](https://ahmypeace.github.io/CSD5730_NLP_R_Spring2026/reports/week-03-cleaning-genie.html)
