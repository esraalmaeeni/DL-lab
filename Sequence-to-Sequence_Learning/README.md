# English to Spanish Translation using Seq2Seq LSTM

This project implements an English-to-Spanish machine translation system using a Sequence-to-Sequence (Seq2Seq) architecture in PyTorch. It includes both a basic encoder-decoder model and extensions with attention mechanisms.

## Features

- Encoder-Decoder architecture with LSTM
- Word embeddings (trainable)
- Teacher forcing during training
- Tokenization, padding, and vocabulary construction
- BLEU score evaluation
- Optional support for Bahdanau and Luong attention (to be added)

## Model Architecture

### Part 1: LSTM Encoder-Decoder (without Attention)

- Encoder: LSTM that processes input English sequence  
- Decoder: LSTM that generates Spanish translation  
- Teacher Forcing: Used to speed up convergence  
- Loss: CrossEntropyLoss ignoring `<pad>` tokens

### (Optional Part 2: With Attention)

- Bahdanau Attention (Additive)  
- Luong Attention (Multiplicative)

## Dataset

The dataset consists of English-Spanish sentence pairs in a plain text file:

We use a subset of 10,000 sentence pairs.  
Split into:

- 80% Training  
- 10% Validation  
- 10% Testing

## Preprocessing

- Lowercasing
- Word tokenization
- Adding `<sos>` and `<eos>` tokens to Spanish sentences
- Padding sequences
- Vocabulary creation with `<pad>` and `<unk>` tokens

## Evaluation

- Evaluated using BLEU score on the test set
- Sample translations shown for manual inspection

## Example Inference

```python
translate(model, "how are you?")
# Output: "¿cómo estás?"
