# Protein Sequence Classification and Generation

This project presents a deep learning pipeline developed in **PyTorch** for classifying protein sequences into functional categories and generating new synthetic sequences. The final trained classifier is deployed via a **Flask** web application, allowing real-time prediction through a user interface and REST API.

---

## Dataset

**Source**: [Kaggle - Protein Dataset](https://www.kaggle.com/datasets/shahir/protein-data-set)

**Files:**
- `pdb_data_no_dups.csv` — Contains structural and biochemical attributes.
- `pdb_data_seq.csv` — Contains the amino acid sequences of proteins.

---

## Project Structure

- **Preprocessing & EDA**: Cleans data, fills missing values, filters proteins, selects the top 20 classes, and encodes sequences.
- **BiLSTM Classifier**: A PyTorch-based BiLSTM model trained to classify sequences into 20 functional classes.
- **Protein Generator**: An LSTM-based generator trained using next-token prediction to synthesize plausible amino acid sequences.
- **Model Evaluation**: Includes validation accuracy, confusion matrix, and classification report.
- **Flask App**: Offers a simple web interface and `/predict` endpoint for protein classification.

---

## Model Performance

### Classifier:
- **Architecture**: BiLSTM with embedding, batch normalization, dropout, and fully connected layers.
- **Validation Accuracy**: ~90%
- **Target Classes**: Top 20 most frequent protein functions
- **Label Transformation**: Handled using `LabelEncoder`

### Generator:
- **Architecture**: LSTM trained for amino acid token prediction
- **Training**: Character-level sequence prediction
- **Output**: Realistic protein sequences reclassified using the BiLSTM model

---

## Requirements

The following Python packages are required:

```
flask
torch
numpy
pandas
scikit-learn
matplotlib
seaborn
keras
kagglehub
```

---

## Results Compared to Literature

Our BiLSTM-based approach achieves competitive accuracy with state-of-the-art models discussed in the literature, confirming its efficacy for protein classification tasks.

---

## Citation

Farzana Tasnim et al.  
**"Protein Sequence Classification Through Deep Learning and Encoding Strategies."**  
*Procedia Computer Science*, Volume 238, 2024, Pages 876–881.  
DOI: [10.1016/j.procs.2024.06.106](https://doi.org/10.1016/j.procs.2024.06.106)
