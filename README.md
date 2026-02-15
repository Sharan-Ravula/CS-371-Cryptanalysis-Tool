# Cryptanalysis Project: Frequency Analysis & Decryption

## Project Overview
[cite_start]This project focuses on the **cryptanalysis of a monoalphabetic substitution cipher**[cite: 13]. [cite_start]By analyzing the statistical properties of letter frequencies, bigrams, and trigrams in reference English texts—specifically Shakespeare's *Hamlet* and *The Merchant of Venice*—we developed an algorithm to map ciphertext characters back to their original plaintext[cite: 5, 10].

[cite_start]The project features two distinct implementations: a primary version in **Python** and a parallel version in **C++**[cite: 3].

---

## Team & Contributions
[cite_start]Due to the technical requirements, the team implemented the solution in both Python and C++ to ensure robustness[cite: 3].

### Sharan Ravula (Python Lead)
* [cite_start]**Python Implementation**: Independently designed and developed the full suite of cryptanalysis tools in Python[cite: 4].
* [cite_start]**Frequency Analysis**: Conducted statistical analysis on reference texts to establish baseline letter and n-gram distributions[cite: 5].
* [cite_start]**Algorithm Design**: Developed the core mapping algorithm used to translate encrypted characters into plaintext[cite: 6].
* [cite_start]**Deciphering & Documentation**: Finalized the deciphering process using linguistic knowledge and authored the project's technical documentation[cite: 7, 8].

### Ivan Garcia & Tucker Baum (C++ Team)
* [cite_start]**C++ Implementation**: Developed the C++ version of the cryptanalysis solution using C++ data structures and algorithms[cite: 9, 13].
* [cite_start]**Testing & Optimization**: Provided feedback on mapping algorithms and optimized the C++ codebase for performance[cite: 11, 12, 15].

---

## Solution Design & Implementation

### 1. Frequency Analysis
The analysis process involved scanning reference texts to identify:
* **Single Letters**: Identified 'e', 't', and 'a' as the most frequent characters.
* **Bi-grams**: Common sequences like 'th', 'he', and 'in' were used to identify word structures.
* **Tri-grams**: 'the' and 'and' were used as anchors to confirm high-probability mappings.

### 2. Letter Mapping
The mapping was established through an iterative process:
1. **Initial Mapping**: Based purely on frequency rankings (e.g., mapping the most frequent ciphertext letter 'x' to 'e').
2. **Refinement**: Adjustments were made by identifying common linguistic patterns and resolving ambiguous characters through context.

**Final Mapping discovered:**
`x->e`, `t->h`, `j->t`, `m->o`, `p->n`, `c->a`, `r->n`, `b->s`, `n->i`, `v->r`, `g->d`, `w->u`, `y->l`.

---

## Deciphered Plaintext
The final deciphered text was identified as a passage from the **Book of Daniel** in the Bible.

**Sample Output:**
> "in the same hour came forth fingers of a man's hand, and wrote oder against the candlestick upon the plaster of the wall of the king's palace; and the king saw the part of the hand that wrote..."

---

## Execution Instructions (Python Version)

Ensure all text files and scripts are in the same directory.

### Analyze Letter Frequencies:
```bash
python3 freqAnalyze.py merchantofvenice.txt
python3 freqAnalyze.py hamlet.txt
python3 freqAnalyze.py ciphertext.txt
