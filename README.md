Protein Sequence Classification and Generation
This project implements a deep learning pipeline using PyTorch to classify protein sequences into functional categories and generate synthetic protein sequences. The final model is deployable using a Flask web application.

Dataset
Source: Kaggle - Protein Dataset

Files:

pdb_data_no_dups.csv: Contains structural and biochemical attributes.

pdb_data_seq.csv: Contains the actual protein sequences.

Project Structure
Preprocessing & EDA: Handles missing values, filters protein types, selects top 20 classes, encodes sequences.

BiLSTM Classifier: A PyTorch-based model trained to classify sequences into 20 protein classes.

Protein Generator: A next-token prediction LSTM model trained to generate realistic sequences.

Model Evaluation: Includes validation accuracy, classification report, and confusion matrix.

Flask App: Provides a web interface and REST endpoint (/predict) to classify input sequences.

Model Performance
Classifier:

Architecture: BiLSTM with embedding + batchnorm + dropout + dense layers

Accuracy on validation set: ~90%

Classes: Top 20 frequent protein function classes

Label encoder used to transform class names

Generator:

Model: LSTM-based next-token generator

Trained using character-level amino acid prediction

Output: realistic amino acid sequences used for reclassification

Requirements.txt

flask
torch
numpy
pandas
scikit-learn
matplotlib
seaborn
keras
kagglehub

Results Compared to Literature
Compared to the 2024 Procedia CS paper:

CNN with Integer Encoding (Paper): 90% accuracy

BiLSTM (Ours): ~90% validation accuracy

SVM + Count Vectorizer (Paper): 92% accuracy (best in paper)

Our method is on par with state-of-the-art deep learning approaches.

Citation
Farzana Tasnim et al. Protein Sequence Classification Through Deep Learning and Encoding Strategies. Procedia Computer Science 238 (2024) 876–881.
