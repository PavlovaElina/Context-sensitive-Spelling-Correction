# Context-Sensitive Spelling Correction

This project implements a context-sensitive spelling corrector using n-gram language models. The system goes beyond simple word-level correction by considering surrounding context to make more accurate spelling corrections.

## Project Overview

The spelling corrector uses interpolated n-gram models (unigram, bigram, trigram) with weighted probabilities to select the best candidate corrections. It incorporates:
- **Context-aware correction** using language models
- **Keyboard layout error handling** (QWERTY adjacent key errors)
- **Edit distance candidate generation** (edit distance 1 and 2)
- **Laplace smoothing** for handling unseen n-grams

## Performance

The implementation significantly outperforms Norvig's baseline approach:
- **Word-level accuracy**: 97.50% vs Norvig's 78.67%
- **Sentence-level accuracy**: 70.52% vs Norvig's 2.22%

## Technical Implementation

### Key Features
- **N-gram Models**: Built from Norvig's `big.txt` corpus
- **Candidate Generation**: Edit distance 1/2 with keyboard layout considerations
- **Probability Scoring**: Weighted interpolation (0.1 unigram, 0.3 bigram, 0.6 trigram)
- **Error Handling**: QWERTY keyboard adjacent key error simulation

### Dataset
- Training: Norvig's `big.txt` corpus
- Testing: Wikipedia sentences (`wiki_sentences_v2.csv`) with synthetic noise added

## Project Structure

```
├── NLP_Assignment1.ipynb          # Main implementation notebook
├── big.txt                        # Norvig's training corpus
├── wiki_sentences_v2.csv          # Test dataset
└── README.md                      # This file
```

## Usage

The notebook contains complete implementation and evaluation code. Key functions include:
- `correct_spelling()`: Main correction function with context sensitivity
- `get_candidates()`: Candidate generation with keyboard error handling
- `probability_of_correction()`: Weighted n-gram probability scoring

## Results Analysis

The context-sensitive approach demonstrates substantial improvement over the context-agnostic Norvig method, particularly at the sentence level where contextual information is crucial for accurate correction.

## Resources

- [Norvig's Spelling Corrector](https://norvig.com/spell-correct.html)
- [N-grams Data](https://www.ngrams.info/download_coca.asp)
- [Damerau–Levenshtein Distance](https://en.wikipedia.org/wiki/Damerau–Levenshtein_distance)
