# Genie Contest: `peace_genie_pro_max()`

**CSD5730 | NLP in R | Spring 2026**
**Author:** Amaka Peace Onebunne

## Overview

A class contest entry for the most complete text cleaning function. `peace_genie_pro_max()` extends the cleaner used across the course into a single function with switches for each step, so it can be adapted to different corpora.

## Options

| Argument | What it does |
|----------|--------------|
| `fix_encoding` | Repairs text encoding to UTF-8 |
| `normalize_quotes` | Converts curly quotes to straight quotes |
| `expand_contractions` | Expands forms like "won't" and "they're" |
| `keep_apostrophes` | Keeps apostrophes inside words |
| `preserve_roman` | Protects Roman numerals from number removal |
| `remove_urls`, `remove_emails`, `remove_numbers` | Strips web addresses, emails, and digits |
| `split_hyphens` | Splits hyphenated words |
| `remove_stopwords` | Optional stopword removal |
| `lemmatize`, `tokenize` | Optional lemmatization and tokenized output |
| `verbose` | Reports how many strings were cleaned, were NA, and ended up empty |

The report demonstrates the function on sample text with and without stopword removal.

## Files

- `Onebunne_Genie_Contest.Rmd`: R Markdown source
- `Onebunne_Genie_Contest.html`: rendered report

## Live Report

[View the rendered report](https://ahmypeace.github.io/CSD5730_NLP_R_Spring2026/reports/genie-contest.html)
