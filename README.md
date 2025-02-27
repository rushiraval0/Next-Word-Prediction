# Next Word Prediction using LSTM Networks


## Overview
This repository presents a Next Word Prediction model implemented using LSTM (Long Short-Term Memory) networks. The project focuses on training a sequence prediction model on the "Alice in Wonderland" text dataset (`alice.txt`). Key steps include text preprocessing, tokenization, sequence generation, model architecture design, and evaluation. Two models are compared: a baseline LSTM and an improved model with Bidirectional LSTM, Dropout, and Layer Normalization to mitigate overfitting. The project also explores text generation with temperature-based sampling to control output diversity.

## Methods
### Data Preprocessing
- **Text Cleaning**: Convert text to lowercase and remove punctuation/special characters.
- **Tokenization**: Use `Tokenizer` from Keras to map words to integers.
- **Sequence Generation**: Create input-output pairs of n-gram sequences for training.

### Model Architectures
1. **Model 1 (Baseline LSTM)**:
   - Embedding Layer (100 dimensions)
   - LSTM Layer (150 units)
   - Dense Layer with Softmax Activation

2. **Model 2 (Improved Architecture)**:
   - Bidirectional LSTM with Layer Normalization and Dropout
   - Regularization techniques to reduce overfitting

### Training
- **Hyperparameters**: 20 epochs, Adam optimizer, categorical cross-entropy loss.
- **Validation**: 80-20 train-validation split with `random_state=25`.

### Text Generation
- A custom function generates text using temperature to adjust prediction randomness:
  - **Low temperature (0.05)**: Conservative, high-confidence predictions.
  - **High temperature (1.5)**: Diverse, creative predictions.

### Generated Text Examples
- **Temperature 0.05**:  
  `"Forest is that the mock turtle went on the trumpet and looked"`
- **Temperature 1.5**:  
  `"Forest is next different they're a violent mary family silence and its"`

## Discussion
- **Overfitting**: Model 1’s large gap between training and validation accuracy highlights the need for regularization.
- **Architecture Choices**: Bidirectional LSTMs and Layer Normalization improved validation performance but increased computational cost.
- **Stop Words**: Retaining stop words preserved grammatical structure, critical for coherent text generation.
- **Applications**: Useful for chatbots, autocomplete features, and creative writing tools.

## Prerequisites
- Python 3.x
- Libraries: TensorFlow, NumPy, scikit-learn
- Dataset: Place `alice.txt` in the project directory.
