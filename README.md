# NLP-Homework_1

---
# 2.2 Mini BPE Learner 

The code:
- Takes a small text corpus as input
- Splits each word into characters and appends an end-of-word marker `_`
- Counts adjacent symbol pairs (bigrams)
- Repeatedly merges the most frequent pair
- Prints the merged pair and current vocabulary size at each step
- Uses the learned merges to segment new and unseen words

The script is written in a **single file** and uses only standard Python libraries (`collections.Counter`).


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

## 2.2.3(How subword tokens solved the OOV (out-of-vocabulary) problem.)
  Subword tokens help with the out-of-vocabulary (OOV) problem because they allow the model to break unknown words into smaller parts that it already knows. Instead of treating a new word as completely unknown, the model represents it using familiar subwords. For example, a word like *newestest* may not appear in the training data, but it can still be split into known parts such as *new* and *est*. This helps the model understand and process new words more easily. One example of a meaningful subword learned by BPE is **er_**, which appears in words like *newer* and *wider*. This subword matches the English suffix “-er,” showing that BPE can learn useful word parts that have real meaning.

---
# 2.3 BPE learner in your own language/english



This model contains a **short and clean Python script** that trains a mini BPE model on a small English paragraph.

The code:
- Cleans the text (removes punctuation and lowercases words)
- Splits words into characters and adds an end-of-word marker `_`
- Learns **30 BPE merges** by repeatedly merging the most frequent symbol pairs
- Prints the top merge and vocabulary size at each step
- Shows the **top 5 merges** and **5 longest subword tokens**
- Segments 5 example words, including a rare word and a derived word

## what the output shows
- Step-by-step BPE merge process (each step prints the most frequent pair merged)
- Top 5 most frequent merges (shown after training)
- Five longest learned subword tokens (from the final vocabulary)
- Segmentation results for example words such as:
  - `language`
  - `processing`
  - `tokenization`
  - `generalize`
  - `vocabulary`

 ## 2.3.4 (	What kinds of subwords were learned (prefixes, suffixes, stems, whole words?	Two concrete pros/cons of subword tokenization for your language)
 The BPE model learned different types of subwords such as full words, word stems, and common suffixes. Some words became single tokens, while others were split into smaller parts that appear often in the text. Suffixes like -ing and -tion were learned because they are common in English words. One advantage of subword tokenization is that it can handle new or unseen words by breaking them into known parts. Another advantage is that it keeps the vocabulary size smaller, which makes models more efficient. A disadvantage is that words can be split into many pieces, making sentences longer. Another drawback is that subwords do not always match real grammar or meaning perfectly.







