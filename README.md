# Bug_Prediction_System
AI Powered Bug Prediction and Fix System

# Overview

This project demonstrates an end-to-end bug detection and automated code-fixing system using transformer-based models. The workflow involves:
- Bug detection – Identifying whether a given code snippet contains a bug.
- Confidence scoring – Quantifying how certain the model is about its prediction.
- Bug fixing – Generating a corrected version of the buggy code using a sequence-to-sequence model.

# Methods Used
1. Bug Detection
- Tokenizer: The buggy code is tokenized using bug_tokenizer to convert text into model-readable tensors.
- Model: bug_model processes the inputs and outputs logits representing bug/no-bug classification.
- Prediction:
- prediction == 1 → Bug detected
- prediction == 0 → No bug detected
- Why: This binary classification approach is simple, interpretable, and effective for debugging tasks.
- Result: -  The bug detection model classified your input code as buggy (prediction == 1).
- Confidence 0.95: The softmax probability was 95%, which is very high. This means the model is strongly convinced the code has a bug.


2. Confidence Scoring
- Softmax probabilities are used to calculate confidence in predictions.
- Why: Confidence scores help users understand the reliability of the model’s output, which is crucial in debugging scenarios.

3. Bug Fix Suggestion
- Tokenizer: The buggy code is tokenized again using fix_tokenizer.
- Model: fix_model.generate(...) produces a candidate fix.
- Decoding: The output tokens are decoded back into readable Python code.
- Why: Sequence-to-sequence generation allows the model to propose syntactically valid fixes, even for complex bugs


