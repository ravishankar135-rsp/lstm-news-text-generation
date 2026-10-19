# Inference Dashboard — Implementation Notes

## Purpose
Provide a small Streamlit interface for experimenting with the already-trained character-level LSTM. The app must perform inference only; it must never launch training automatically.

## User flow
1. Open the dashboard.
2. Enter a seed phrase (for example, a short news-style opening).
3. Select a maximum number of characters and sampling temperature.
4. Generate a continuation from the saved model checkpoint.
5. Review the generated text alongside a persistent experimental-output disclaimer.

## Required model artifacts
- Saved model weights/checkpoint from the completed Colab run.
- Exact model architecture/configuration used during training.
- Character-to-index and index-to-character mappings from training.
- A small metadata file recording sequence length, vocabulary size, TensorFlow version, and training date/run details.

**Important:** The reviewed notebook indicates a checkpoint path of `/content/best_news_lstm.weights.h5`, which is temporary Colab runtime storage unless downloaded or saved to persistent storage. The checkpoint has not yet been verified as present in this GitHub repository. Do not create fake outputs or substitute randomly initialized weights.

## Proposed UI
- Header: LSTM News Text Generation — Experimental Demo
- Sidebar: generation length, temperature, optional random seed
- Main area: seed input, Generate button, generated output, copy control
- Status panel: checkpoint loaded / missing, model metadata
- Footer disclaimer: output may be incoherent or factually incorrect; not for publishing as verified news

## Suggested evaluation before release
- Test empty and very short prompts.
- Test output lengths and multiple temperatures.
- Verify repeatability with a fixed random seed where supported.
- Check CPU memory/runtime and handle missing checkpoint with a helpful message.
- Include genuine generated examples and avoid implying factual verification.

## Release gate
Do not label the dashboard runnable until the trained checkpoint, model definition, vocabulary mappings, dependency versions, and inference smoke test are committed and verified.