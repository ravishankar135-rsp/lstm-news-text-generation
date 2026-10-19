# LSTM News Text Generation — Project Documentation

> **Status:** Educational prototype; generated text is experimental and may be incoherent or factually incorrect.

## Overview
A character-level Long Short-Term Memory (LSTM) model that learns patterns from a news-text corpus and generates continuation text by predicting one character at a time. The project demonstrates data cleaning, character encoding, sequence construction, neural-network training, evaluation, and text sampling.

## Stack
Python · TensorFlow/Keras · Pandas · NumPy · Google Colab

## Recorded configuration
| Parameter | Value |
|---|---:|
| Initial rows | 14,991 |
| Rows after cleaning | 14,892 |
| Text corpus | ~35.26 million characters |
| Character vocabulary | 128 |
| Sequence length | 100 |
| Batch size | 64 |
| Embedding dimension | 64 |
| LSTM units | 128 |
| Optimizer | Adam, learning rate 0.001 |
| Loss | Sparse categorical cross-entropy from logits |
| Train/validation split | 95% / 5% |
| Parameters | ~123,520 |

## Recorded 10-epoch result
- Training loss: 1.4746
- Training accuracy: 57.10%
- Validation loss: 1.5627
- Validation accuracy: 54.99%

These are character-level next-character metrics; they do not measure factual correctness or news quality.

## Checkpoint
The repository includes `best_news_lstm.weights.h5`, a **weights-only** checkpoint. It is not a complete Keras model. Inference requires recreating the exact model architecture and restoring the matching character-to-index and index-to-character mappings. Those mappings should be saved as artifacts alongside the notebook before claiming fully reproducible inference.

## Reproduce / continue the project
1. Add the complete notebook used for the training run.
2. Document the dataset source and its licence; do not commit data unless redistribution is permitted.
3. Pin package versions in a requirements file.
4. Save the character mappings and model configuration used at training time.
5. Test loading the checkpoint in a fresh runtime and generate a sample before building a public demo.

## Limitations and responsible use
- Character-level LSTMs may generate fragments, repetition, and ungrammatical text.
- Generated content can be false even when it sounds plausible; do not publish it as verified reporting.
- Dataset bias and misinformation may be reflected in the output.
- Use only data and weights you are permitted to redistribute.

## Related documentation
- [Project presentation](project_presentation.md)
- [Dashboard specification](dashboard_spec.md)
- [Training summary](../reports/training_summary.md)

## Author
[GitHub profile](https://github.com/ravishankar135-rsp)
