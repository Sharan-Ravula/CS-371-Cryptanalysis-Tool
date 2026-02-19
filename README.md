# Cryptanalysis: Frequency-Based Deciphering Project

## 📌 Project Overview

This repository contains a frequency-based cryptanalysis tool designed to decipher text encrypted with a monoalphabetic substitution cipher. Developed for CS 371: Introduction to Computer Networking at the University of Kentucky, the project demonstrates how statistical properties of language (n-grams) can be used to break simple encryption without a known key. 

The tool analyzes reference texts (Shakespearean plays) to build a frequency profile of the English language and applies those patterns to recover plaintext from ciphertext.

> The project features two distinct implementations: in **Python** and in **C++**

---

## 📂 Repository Structure
```text
Cryptanalysis-Project/
│
├── scripts/
│   ├── freqAnalyze.py       # Python tool for n-gram frequency analysis
│   ├── decipher.py          # Script to apply mapping and recover plaintext
│
├── datasets/
│   ├── ciphertext.txt       # The encrypted target message
│   ├── hamlet.txt           # Reference text 1 (Shakespeare)
│   ├── merchantofvenice.txt # Reference text 2 (Shakespeare)
│
├── docs/
│   ├── CS371S24PA3.pdf      # Original project requirements
│   ├── documentation.txt    # Detailed design and implementation steps
│   └── writeup.txt          # Team contributions and Linkblue IDs
│
├── outputs/                 # PNG's of all the terminal output results
│
├── README.md                # Project overview and instructions
└── LICENSE                  # License information
```
---

## 🧠 Methodology: How it Works

The project uses Frequency Analysis, which relies on the fact that in any given language, certain letters and combinations appear with predictable regularity.

**The Deciphering Process**:

   - **Reference Profiling**: Analyze hamlet.txt and merchantofvenice.txt to determine the "standard" frequency of 1-grams (letters), 2-grams (bi-grams), and 3-grams (tri-grams).
     
   - **Ciphertext Analysis**: Run the same frequency analysis on the encrypted ciphertext.txt.
     
   - **Heuristic Mapping**:
      
      - Map the most frequent ciphertext letter (e.g., 'x') to the most frequent English letter ('e').
        
      - Use common tri-grams like "the" or "and" to anchor the mapping.
        
   - **Iterative Refinement**: Manually adjust the codebook based on linguistic patterns (e.g., if a word looks like t_at, the missing letter is likely h).

---

## ✨ The Analogy

**What is Cryptanalysis?** 🤔

Imagine you are in a room full of people speaking a secret code. You don't know the language, but you notice that every time someone points at a door, they say "Zog." You also notice "Zog" is the most common word said.

In English, the most common word is "the." By matching the "Zog" (Ciphertext) to "the" (Plaintext), you have just unlocked three letters: T, H, and E. You repeat this "pattern matching" until the entire secret language becomes clear.

---

## 💥 Solution Design & Implementation:

1. Frequency Analysis: The analysis process involved scanning reference texts to identify

  - **Single Letters**: Identified 'e', 't', and 'a' as the most frequent characters.
    
  - **Bi-grams**: Common sequences like 'th', 'he', and 'in' were used to identify word structures.
    
  - **Tri-grams**: 'the' and 'and' were used as anchors to confirm high-probability mappings.

2. Letter Mapping: The mapping was established through an iterative process

  - **Initial Mapping**: Based purely on frequency rankings (e.g., mapping the most frequent ciphertext letter 'x' to 'e').
    
  - **Refinement**: Adjustments were made by identifying common linguistic patterns and resolving ambiguous characters through context.

3. **Final Mapping discovered**:

  `x->e`, `t->h`, `j->t`, `m->o`, `p->n`, `c->a`, `r->n`, `b->s`, `n->i`, `v->r`, `g->d`, `w->u`, `y->l`.
  
---

## 💥 Analyze Letter Frequencies:

   - macOS/Linux:
     
     - **freqAnalyze.py**:

       ```bash
       python3 freqAnalyze.py ../datasets/merchantofvenice.txt
       python3 freqAnalyze.py ../datasets/hamlet.txt
       python3 freqAnalyze.py ../datasets/ciphertext.txt
  
     - **decipher.py**:

       ```bash
       python3 decipher.py ../datasets/ciphertext.txt

   - Windows:

     - **freqAnalyze.py**:

       ```bash
       python freqAnalyze.py ../datasets/merchantofvenice.txt
       python freqAnalyze.py ../datasets/hamlet.txt
       python freqAnalyze.py ../datasets/ciphertext.txt
  
     - **decipher.py**:

       ```bash
       python decipher.py ../datasets/ciphertext.txt

---

## 📊 Results & Observations

- **Target Text**: The deciphered plaintext was identified as a passage from the **Book of Daniel** in the Bible.
  
  > "in the same hour came forth fingers of a man's hand, and wrote oder against the candlestick upon the plaster of the wall of the king's palace; and the king saw the part of the hand that wrote..."
  
- **The "E" Factor**: In the reference texts, 'e' was consistently the most common letter (10,786 occurrences in Merchant of Venice).
  
- **The "THE" Anchor**: The tri-gram 'the' was the strongest indicator for mapping, appearing 1,420 times in the reference text.

---

## 💥 Contributors:

   - Sharan Ravula (Python)
     
   - Ivan Garcia (C++)
     
   - Tucker Baum (C++)
