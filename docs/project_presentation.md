# Project Presentation — LSTM News Text Generation

## Slide 1 — Title
**LSTM News Text Generation**
Character-level sequence modeling with Python and TensorFlow/Keras.

## Slide 2 — Problem and goal
Explore how a recurrent neural network learns character patterns from a news-text corpus and generates a continuation from a short seed. This is a learning prototype, not a factual news generator.

## Slide 3 — Data and preparation
- Original records: 14,991
- Records after cleaning: 14,892
- Combined text: 35,258,965 characters
- Vocabulary: 128 characters
- Sequence length: 100 characters; batch size: 64
- Dataset source/license and redistribution rights must be documented before publishing the data.

## Slide 4 — Modeling workflow
Text cleaning → character vocabulary → integer encoding → 100-character input/next-character target → train/validation split → LSTM training → iterative sampling.

## Slide 5 — Model architecture
Embedding (64 dimensions) → LSTM (128 units) → Dense (128 logits). Optimizer: Adam, learning rate 0.001. Loss: sparse categorical cross-entropy from logits. Recorded parameter count: 123,520.

## Slide 6 — Recorded experiment
| Metric | Value |
|---|---:|
| Training loss | 1.4746 |
| Training accuracy | 57.10% |
| Validation loss | 1.5627 |
| Validation accuracy | 54.99% |

These are next-character metrics only. The run reported an input-pipeline warning near the end, so the results are preliminary and should be interpreted cautiously.

## Slide 7 — Output review
Show a few real generated samples from the notebook, including an example that demonstrates limitations. Do not invent or polish samples to imply stronger performance than observed.

## Slide 8 — Limitations and responsible use
Generated text may be repetitive, incoherent, biased, or factually wrong. It is not a fact-checker and must not be published as verified news.

## Slide 9 — Production-minded next steps
1. Publish the complete end-to-end notebook and document environment/data source.
2. Correct and document the input pipeline so each epoch's data handling is explicit.
3. Save/version the trained checkpoint and make inference reproducible.
4. Add a Streamlit inference dashboard with clear generation controls and a visible experimental-output disclaimer.
5. Compare sampling settings and a subword baseline; report evaluation limitations.

## Slide 10 — Skills demonstrated
Python, data cleaning, NLP fundamentals, sequence modeling, LSTM/RNN, TensorFlow/Keras, model evaluation, experiment documentation, responsible AI.

**Presenter note:** Replace any placeholder sample slide with genuine output from the notebook and add the dataset citation before sharing publicly.