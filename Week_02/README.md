# Assignment 2: Text Cleaning and Tokenization

**CSD5730 | NLP in R | Spring 2026**
**Author:** Amaka Peace Onebunne

## Overview

This assignment reads a messy text file (`sticks_messy.txt`) into R, cleans it with a chained base R function, splits it into tokens, and compares token counts and the type-token ratio (TTR) before and after cleaning. An annotated cheat sheet summarizes the splitting and cleaning steps.

## Files

- `Assignment_02.Rmd`: R Markdown source
- `Assignment_02.html`: rendered report
- `CheatSheet_TextCleaning.Rmd` and `Cheatsheet_TextCleaning.html`: annotated cheat sheet
- `style.css`: stylesheet for both documents
- `Data/`: raw text files, including `sticks_messy.txt`

## Key Results

| Version | Tokens | Types | TTR |
|---------|--------|-------|-----|
| Before cleaning | 427 | 264 | 0.62 |
| After cleaning | 406 | 227 | 0.56 |

This first cleaning pass lowercased the text and removed punctuation, but it kept numbers and stray fragments like `89769hlj`. The Week 3 Cleaning Genie added steps to remove them.

## How to Run

Open `Assignment_02.Rmd` in RStudio or Positron and knit to HTML. The cheat sheet knits separately from `CheatSheet_TextCleaning.Rmd`.

## Live Report

- [Assignment 2 report](https://ahmypeace.github.io/CSD5730_NLP_R_Spring2026/reports/week-02-text-cleaning.html)
- [Cheat sheet](https://ahmypeace.github.io/CSD5730_NLP_R_Spring2026/reports/week-02-cheat-sheet.html)
