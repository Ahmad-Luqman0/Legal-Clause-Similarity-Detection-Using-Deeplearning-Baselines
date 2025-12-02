Assignment 2 — CS352 Machine Learning
Text Pair Classification Using Siamese Neural Networks

This project implements a text-pair similarity classification system using a Siamese Neural Network and an Attention-based Siamese model. The goal is to determine whether two clauses belong to the same clause type (positive pair) or different types (negative pair). The notebook includes dataset processing, pair generation, model building, training, and evaluation.

Objectives

Load and combine multiple CSV files containing clause texts.

Validate and clean the dataset.

Generate balanced positive and negative clause pairs.

Preprocess and tokenize the text.

Build two models:

Siamese LSTM Model

Attention-Enhanced Siamese Model

Train and evaluate both models.

Analyze predictions and misclassified samples.

Dataset Requirements

Each CSV file must contain at least the following columns:

Column Name	Description
text	The clause text
clause_type	The category/type of clause

The notebook automatically loads all CSV files from the dataset directory.

Main Features
1. Dataset Loading

Uses glob to load all CSV files from a specified directory.

Validates that required columns exist.

Combines all valid datasets.

2. Pair Creation

The function create_pairs():

Creates positive pairs (same clause type).

Creates negative pairs (different clause type).

Balances the number of pairs.

Returns a dataframe suitable for model training.

3. Data Splitting and Preprocessing

Stratified train/validation/test splitting.

Tokenization with Keras Tokenizer.

Sequence padding.

4. Model Architecture
Siamese LSTM Model

Shared Embedding Layer

Shared BiLSTM Encoder

Distance computation

Dense layers for similarity classification

Attention-Based Siamese Model

Incorporates an attention mechanism for better word-importance weighting.

Shared attention encoder for both inputs.

Fully connected layers for classification.

5. Evaluation

Accuracy

Precision

Recall

F1-Score

ROC-AUC (when possible)

Confusion Matrix

Classification Report

6. Prediction Inspection

Shows predicted probabilities for both models.

Highlights correct and incorrect predictions.

Useful for error analysis and model improvement.

How to Run

Install all required libraries:

pip install tensorflow pandas numpy matplotlib scikit-learn


Place all CSV files in your dataset folder.

Open the notebook and run all cells sequentially:

Data loading

Pair generation

Text preprocessing

Model training

Evaluation and analysis

Outputs

Processed and tokenized datasets

Two trained models (Siamese and Attention)

Performance metrics

Visualized predictions

Misclassified examples for analysis
