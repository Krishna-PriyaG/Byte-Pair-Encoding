# Byte Pair Encoding (BPE) Implementation and Evaluation

This repository contains an implementation of Byte Pair Encoding (BPE) for text tokenization and an evaluation of its performance on various corpora.

## Table of Contents

- [Introduction](#introduction)
- [Installation](#installation)
- [Usage](#usage)
- [Evaluation](#evaluation)
- [Results](#results)

## Introduction

Byte Pair Encoding (BPE) is a subword segmentation algorithm that iteratively merges the most frequent pairs of bytes (or characters) in a text corpus to create a more compact representation. This repository implements BPE and evaluates its performance on text tokenization tasks.

## Installation

To run the code in this repository, you'll need to have Python installed along with the following libraries:

- `nltk`
- `tqdm`
- `numpy`
- `matplotlib`

You can install the required libraries using `pip`:

```bash
pip install nltk tqdm numpy matplotlib
```
Additionally, you'll need to download the gutenberg book data for NLTK. You can do this by running the following Python command:
```python
import nltk
nltk.download('gutenberg')
```
## Usage

### Training BPE
The following books were used for training the BPE model:

- 'austen-emma.txt'
- 'blake-poems.txt'
- 'shakespeare-hamlet.txt'

To train BPE on a corpus, use the Bytepairencoding function:
```python
vocab, vocab_sizes, merge_frequencies = Bytepairencoding(corpus, num_merges=10000)
```
### Testing BPE
The following books were used for evaluating the BPE model:

- 'whitman-leaves.txt'
- 'shakespeare-macbeth.txt'
- 'austen-sense.txt'

### Tokenizing Text
To tokenize text using the trained BPE model, use the tokenize_with_bpe function:
```python
tokenized_text, bpe_token = tokenize_with_bpe(evaluation_corpus, vocab)
```

## Evaluation

The repository includes functions to evaluate the BPE tokenization performance, including accuracy, precision, recall, F1 score, and Jaccard similarity.

## Results
### Vocabulary Evolution
The evolution of vocabulary size during the BPE training process can be visualized using the plot_vocabulary_evolution function:
```python
plot_vocabulary_evolution(vocab_sizes)
```
### Merge Frequencies
The frequency of byte pair merges over iterations can be visualized using the plot_merge_frequencies function:

```python
plot_merge_frequencies(merge_frequencies, max_xticks=50)
```
