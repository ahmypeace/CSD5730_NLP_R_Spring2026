
# Assignment 6: Developing a Hypothesis on the Gaslighting Dataset

**Author:** Peace Onebunne
**Course:** CSD 5730 – NLP in R
**Semester:** Spring 2026

---

## Project Overview

This project develops and tests a theory-driven hypothesis using the publicly available *Gaslighting Dataset* from the Reilly Concepts & Cognition Lab.

Rather than treating gaslighting as emotion alone, this analysis conceptualizes gaslighting as a communicative structure reflected in recurring linguistic patterns. The project applies a custom text preprocessing pipeline, dictionary-based feature extraction, and frequency-based statistical analysis to test whether gaslighting communication manifests in measurable language patterns.

The final submission is rendered as an HTML document styled using a custom professional CSS theme.

---

## Research Question

If gaslighting exists as a communicative phenomenon, can it be detected through recurring linguistic markers in narrative text?

---

## Hypothesis

Texts in the gaslighting dataset will contain higher frequencies of linguistic markers associated with:

* Denial of reality
* Blame attribution
* Emotional invalidation
* Control or directive language
* Memory destabilization

In short:

If gaslighting is structurally communicative, we should see it in word usage patterns.

---

## Dataset

The dataset was loaded directly from the Reilly Lab public repository:

```r
load(url("https://github.com/Reilly-ConceptsCognitionLab/reillylab_publicdata/blob/main/gaslight.rda?raw=true"))
```

The corpus includes:

* Narrative descriptions of adult workplace interpersonal conflict
* Participant demographic variables
* Self-reported gaslighting experience

Initial inspection was conducted to verify encoding, structure, and categorical variable formatting.

---

## Methodological Pipeline

### 1. Custom Text Cleaning Function

A fully vectorized preprocessing function (`peace_genie_pro`) was developed throughout the semester and applied to stabilize linguistic representation.

Key preprocessing steps include:

1. UTF-8 normalization
2. NA handling
3. HTML tag removal
4. Unicode normalization
5. Smart quote normalization
6. Roman numeral preservation
7. Lowercasing
8. URL removal
9. Email removal
10. Hyphen splitting
11. Number removal
12. Elongation collapse (e.g., "soooo" → "so")
13. Symbol removal
14. Controlled punctuation removal
15. Whitespace normalization

Apostrophes were intentionally preserved to retain conversational constructions such as:

* "you didn’t"
* "you’re wrong"
* "I never said that"

These structures are theoretically meaningful in gaslighting communication.

---

### 2. Corpus Construction

Cleaned text was converted into a `quanteda` corpus:

```r
corp <- quanteda::corpus(gaslight$clean_text)
```

---

### 3. Tokenization & Stopword Removal

Tokenization was performed using `quanteda::tokens()`, followed by removal of English stopwords.

This reduces lexical noise while preserving psychologically meaningful terms.

---

### 4. Document-Feature Matrix

The tokenized corpus was converted into a Document-Feature Matrix (DFM):

```r
dfm_gaslight <- dfm(tokens_clean)
```

This step converts text into a numerical structure suitable for statistical analysis.

---

## Theory-Driven Dictionary Construction

Rather than selecting frequent words arbitrarily, features were derived from peer-reviewed gaslighting research.

The dictionary captures five communicative dimensions:

### 1. Denial

Contradiction of memory or perception
Examples: "deny", "never", "imagining"

### 2. Blame

Responsibility shifting
Examples: "fault", "because", "accuse"

### 3. Emotional Invalidation

Dismissal of feelings or competence
Examples: "crazy", "overreacting", "lazy"

### 4. Control Language

Directive or dominance-based language
Examples: "should", "must", "required"

### 5. Doubt Memory

Cognitive destabilization
Examples: "doubt", "confused", "remember"

Feature extraction was performed using:

```r
gas_features <- dfm_lookup(dfm_gaslight, gaslight_dict)
```

This aggregates lexical features into theoretically meaningful categories.

---

## Statistical Analysis

Frequency statistics were calculated using:

```r
textstat_frequency(gas_features)
```

This allows comparison of:

* Denial
* Blame
* Invalidation
* Control
* Doubt-memory language

---

## Visualization

Feature categories were visualized using `ggplot2` with a Temple-red gradient palette.

The visualization enables immediate comparison of communicative strategies across the corpus.

---

## Findings

The hypothesis was supported.

Control language emerged as the most frequent feature category, followed by denial and invalidation. Blame attribution and memory-doubt language also appeared consistently.

This suggests that gaslighting communication is not random disagreement, but rather structured through recurring linguistic strategies.

---

## Theoretical Contribution

This project demonstrates that:

* Psychological manipulation can be operationalized linguistically.
* Computational text analysis can measure interpersonal destabilization patterns.
* Dictionary-based feature engineering allows theory-driven quantitative validation.

Rather than reducing gaslighting to sentiment, this approach treats it as patterned communication.

---

## Required Packages

* tidyverse
* quanteda
* quanteda.textstats
* ggplot2
* textstem
* knitr
* kableExtra

---

## Reproducibility

To reproduce this project:

1. Install required packages.
2. Knit the R Markdown file:

   ```
   Onebunne_Assignment_6.Rmd
   ```
3. Ensure internet access for dataset loading.

---

## References

Bellomare, M., et al. (2024). Gaslighting exposure during emerging adulthood. *Journal of Interpersonal Violence*.

Darke, L., Paterson, H., & van Golde, C. (2025). Illuminating gaslighting: A comprehensive interdisciplinary review of gaslighting literature. *Journal of Family Violence*.

Ghaltakhchyan, S. (2024). Linguistic portrayal of gaslighting in interpersonal relationships. *Armenian Folia Anglistika*.

Klein, W. (2025). A theoretical framework for studying the phenomenon of gaslighting. *Personality and Social Psychology Review*.

Podosky, P. M. C. (2021). Gaslighting, first- and second-order. *Hypatia*.

