---

# Week 03 — Cleaning Genie (Text Preprocessing Assignment)

## Overview

This assignment focuses on basic text preprocessing and token analysis using R.
The objective was to import a messy text file (`sticks_messy.txt`), build a simple cleaning function, and evaluate how cleaning affects token counts.

The cleaning function was designed to normalize and standardize text while removing noise such as punctuation, numeric artifacts, and malformed tokens.

---

## Files in This Folder

* `Assignment_03.Rmd` — R Markdown source file
* `Assignment_03.html` — Rendered HTML output
* `sticks_messy.txt` — Original raw text file
* `sticks_cleaned.txt` — Cleaned output text file

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
