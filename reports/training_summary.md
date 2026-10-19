# Training Summary

## Run configuration

| Setting | Recorded value |
|---|---|
| Framework | TensorFlow/Keras |
| Model | Character-level Embedding + LSTM + Dense |
| Vocabulary size | 128 characters |
| Embedding dimension | 64 |
| LSTM units | 128 |
| Input sequence length | 100 characters |
| Batch size | 64 |
| Optimizer | Adam, learning rate 0.001 |
| Loss | Sparse categorical cross-entropy from logits |
| Parameters | 123,520 |
| Split | 95% training / 5% validation |
| Epochs recorded | 10 |

## Dataset preparation

The observed run started with 14,991 records and retained 14,892 after cleaning. The combined text corpus contained 35,258,965 characters. The character vocabulary contained 128 symbols.

## Final recorded metrics

| Metric | Value |
|---|---:|
| Training loss | 1.4746 |
| Training accuracy | 57.10% |
| Validation loss | 1.5627 |
| Validation accuracy | 54.99% |

## Interpretation

These values describe next-character prediction. They do not measure factual correctness, coherence, originality, or suitability for publication. The recorded training run also emitted an input-pipeline warning indicating that the input ran out near the end. Results are therefore preliminary and the input pipeline should be reviewed before making benchmark claims.

## Artifacts and reproducibility gaps

- The reviewed notebook copy begins at Step 14B and does not include the full setup and preprocessing workflow.
- The checkpoint path noted in Colab was `/content/best_news_lstm.weights.h5`; this is temporary runtime storage unless downloaded or saved persistently.
- Exact character mappings and model configuration must be saved alongside the checkpoint for reliable inference.
- Dataset source, license, package versions, and generated examples should be documented before a public release.

## Recommended next actions

1. Upload the complete notebook, not only its later cells.
2. Download and verify the actual trained checkpoint without retraining.
3. Record genuine generated examples and inspect them for quality.
4. Add an inference dashboard only after checkpoint and vocabulary artifacts are present.
5. Revisit the input pipeline and document the fix in a later experiment rather than rewriting historical metrics.
