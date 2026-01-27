# Week 02 – Text Cleaning and Tokenization (R)

This folder contains all files for **Week 02** of  
**CSD5730: Natural Language Processing with R (Spring 2026)**.

The focus of this week is text cleaning, tokenization, and basic lexical analysis using base R functions and reproducible workflows.

---

## Contents
Week_02/
│
├── Assignment_02.Rmd # Main assignment source file
├── Assignment_02.Rproj # R project file
├── CheatSheet_TextCleaning.Rmd # Annotated cheatsheet (required)
├── index.Rmd # Assignment landing page
├── about.Rmd # About page
├── _site.yml # Site configuration
├── style.css # Custom CSS for HTML output
│
├── Data/
│ └── sticks_messy.txt # Raw text for cleaning
│
└── README.md


---

## Assignment Objectives

This week’s assignment demonstrates how to:

1. Read a raw text file into R
2. Build a custom cleaning function using chained operations
3. Clean and normalize messy text
4. Tokenize text into one-word-per-row format
5. Compute token counts before and after cleaning
6. Compute Type-Token Ratio (TTR)
7. Present results in clean HTML tables
8. Document methods clearly for reproducibility

---

## How to Run

1. Open `Assignment_02.Rproj` in RStudio or Positron
2. Open `Assignment_02.Rmd`
3. Knit to HTML
4. Open the rendered file in your browser

The cheatsheet can be knitted separately from:

CheatSheet_TextCleaning.Rmd

---

## Notes

- All code is fully annotated
- Paths use `file.path()` for portability
- Tables are rendered using `knitr::kable()`
- Styling is handled via `style.css`
- Raw data is preserved in the `Data/` folder

---

## Author

**Amaka Peace Onebunne**  
PhD Student, Media and Communication  
Temple University
