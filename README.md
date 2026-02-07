# NLP-Homework_1

---
# Mini BPE Learner 

The code:
- Takes a small text corpus as input
- Splits each word into characters and appends an end-of-word marker `_`
- Counts adjacent symbol pairs (bigrams)
- Repeatedly merges the most frequent pair
- Prints the merged pair and current vocabulary size at each step
- Uses the learned merges to segment new and unseen words

The script is written in a **single file** and uses only standard Python libraries (`collections.Counter`).

---

## How the Code is Structured

- **Tokenization functions**  
  Convert words into character lists with `_` at the end.

- **Bigram counting**  
  Counts how often adjacent symbols appear in the corpus.

- **Merge logic**  
  Replaces the most frequent symbol pair with a new merged token.

- **Training loop**  
  Repeats the merge process for a fixed number of steps or until no bigrams remain.

- **Segmentation function**  
  Applies the learned merges to split new words into subword tokens.

---
## What the Output Shows

- Step-by-step BPE merge process, displaying:
  - the most frequent adjacent symbol pair at each step
  - the vocabulary size after each merge

- Final segmentation results for example words, including:
  - `new`
  - `newer`
  - `lowest`
  - `widest`
  - an invented word (e.g., `newestest`)




