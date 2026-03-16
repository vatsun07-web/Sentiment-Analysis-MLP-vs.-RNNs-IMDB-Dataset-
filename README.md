# Sentiment Analysis: MLP vs. RNNs (IMDB Dataset)

## Overview
This project performs binary sentiment classification on the IMDB Movie Review dataset using deep learning techniques. We compare three distinct architectures—**Multi-Layer Perceptron (MLP)**, **Long Short-Term Memory (LSTM)**, and **Gated Recurrent Unit (GRU)**—to determine the most effective model for sentiment prediction.



## Project Objectives
* Automate the classification of movie reviews into **Positive** or **Negative** sentiment.
* Evaluate the trade-offs between simple keyword-based models (MLP) and complex sequential models (RNNs).
* Identify a high-performance, scalable model suitable for production environments.

## Methodology
1. **Data Preprocessing:** HTML tag removal, tokenization, and padding to a fixed sequence length of $200$.
2. **Model Training:**
   - **MLP:** Baseline model utilizing `GlobalAveragePooling1D`.
   - **LSTM/GRU:** Recurrent models designed to capture sequential dependencies.




## Performance Summary
| Architecture | Peak Validation Accuracy | Training Stability |
| :--- | :--- | :--- |
| **MLP** | **82.88%** | High |
| **LSTM** | 54.90% | Low |
| **GRU** | 53.78% | Low |



## Key Findings
* **The MLP Advantage:** For this specific dataset, the MLP model outperformed recurrent architectures significantly. This indicates that sentiment is primarily driven by "signal" keywords rather than long-range word order.
* **Overfitting:** Both LSTM and GRU architectures showed signs of rapid overfitting, failing to generalize to test data as effectively as the MLP.
* **Production Recommendation:** The MLP is the recommended model due to its high accuracy, stability, and extremely low training time ($< 15$ seconds).


## Future Steps
* Perform **Hyperparameter Tuning** with `KerasTuner`.
* Expand the training dataset to provide more context for RNN-based models.
* Explore `DistilBERT` for potential accuracy improvements using transfer learning.
