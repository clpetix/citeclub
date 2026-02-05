## BibTeX Auburn CSL & BibTeX Key Tidying Tools

This repository contains tools to streamline the process of generating and 
tidying BibTeX entries that I find useful.  

### 1. BibTex_Auburn.csl

This is a custom Citation Style Language (CSL) file designed to format BibTeX entries exported from Zotero. It generates citation keys in the format:

	firstauthorlastname:journal:year

For example: `Petix_Fakhraei_Kieslich_Howard: journal={Journal of Chemical Theory and Computation}:2024`

**Fields included in each BibTeX entry:**
- `title` — Title of the work
- `volume` — Journal volume
- `DOI` — Digital Object Identifier
- `number` — Issue number
- `journal` or `booktitle` — Journal or book title
- `author` — Author(s) in BibTeX format
- `year` — Year of publication
- `month` — Month of publication (if available)
- `pages` — Page numbers (if available)

This format works well for my academic writing in the mphowardlab. 

**How to use:**
- Import `BibTex_Auburn.csl` into Zotero as a custom export style.
- Create bibliography from items with `BibTex_Auburn` style selected. 

### 2. tidy_key.py

This Python script further tidies and standardizes the BibTeX keys in your exported `.bib` file. 
It ensures keys follow the mphowardlab preferred style and tries to handle edge 
cases, such as journal name mapping and author name formatting. 

For example, the key above becomes: `petix:jctc:2024`

**Features:**
- Processes `.bib` files or individual BibTeX entries.
- Processes `@article`, `@book`, and `@inabook` styles. 
- Customizeable journal names mapping to standardized BibTeX keys.
- Handles author name formatting and accent removal.
- Outputs a new `-tidied.bib` file, leaving the original untouched.

**Usage:**
```bash
python tidy_key.py -f yourfile.bib
```
or
```bash
python tidy_key.py -i 'your bibtex entry here'
```

### Final Formatting Suggestion

Once your BibTeX keys are tidied, you can further clean and format your `.bib` 
file using this excellent online tool:

[BibTeX-Tidy](https://flamingtempura.github.io/bibtex-tidy/)

This website helps remove duplicates, sort entries, and ensure consistent 
formatting for your bibliography.

---
**Recommended Workflow:**
1. Export references from Zotero using `BibTex_Auburn.csl`.
2. Run `tidy_key.py` to standardize keys.
3. Use [BibTeX-Tidy](https://flamingtempura.github.io/bibtex-tidy/) for final formatting.
