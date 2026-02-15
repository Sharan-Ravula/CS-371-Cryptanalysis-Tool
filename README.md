# Cryptanalysis Project: Frequency Analysis & Decryption

---

## Project Overview:

- This project focuses on the **cryptanalysis of a monoalphabetic substitution cipher**. 
- By analyzing the statistical properties of letter frequencies, bigrams, and trigrams in reference English texts—specifically Shakespeare's *Hamlet* and *The Merchant of Venice*
- We developed an algorithm to map ciphertext characters back to their original plaintext.

---

> The project features two distinct implementations: in **Python** and in **C++**

---

## Solution Design & Implementation:

### 1. Frequency Analysis
The analysis process involved scanning reference texts to identify:
  - **Single Letters**: Identified 'e', 't', and 'a' as the most frequent characters.
  - **Bi-grams**: Common sequences like 'th', 'he', and 'in' were used to identify word structures.
  - **Tri-grams**: 'the' and 'and' were used as anchors to confirm high-probability mappings.

### 2. Letter Mapping
The mapping was established through an iterative process:
  - **Initial Mapping**: Based purely on frequency rankings (e.g., mapping the most frequent ciphertext letter 'x' to 'e').
  - **Refinement**: Adjustments were made by identifying common linguistic patterns and resolving ambiguous characters through context.

**Final Mapping discovered:**

  `x->e`, `t->h`, `j->t`, `m->o`, `p->n`, `c->a`, `r->n`, `b->s`, `n->i`, `v->r`, `g->d`, `w->u`, `y->l`.
  
---

## Deciphered Plaintext

The final deciphered text was identified as a passage from the **Book of Daniel** in the Bible.

**Sample Output:**
  
  > "in the same hour came forth fingers of a man's hand, and wrote oder against the candlestick upon the plaster of the wall of the king's palace; and the king saw the part of the hand that wrote..."

---

### Analyze Letter Frequencies:

  - freqAnalyze.py:

    ```bash
    python3 freqAnalyze.py merchantofvenice.txt
    python3 freqAnalyze.py hamlet.txt
    python3 freqAnalyze.py ciphertext.txt
  
  - decipher.py:

    ```bash
    python3 decipher.py ciphertext.txt
### 3. Contributors:
   - Sharan Ravula (Python)
   - Ivan Garcia (C++)
   - Tucker Baum (C++)
