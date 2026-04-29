# Hate Speech Detection using Simple RNN

## 📌 Problem Statement

The goal of this project is to build a binary classification model that detects whether a tweet contains hate speech using a Simple Recurrent Neural Network (RNN).

---

## 📊 Dataset

The dataset contains tweets labeled as:

* 0 → Non-hate speech
* 1 → Hate speech

Only the `tweet` and `label` columns were used for this task.

---

## 🧹 Data Preprocessing

The following preprocessing steps were applied:

* Converted text to lowercase
* Removed @mentions
* Removed URLs
* Removed special characters and numbers
* Removed extra whitespace

These steps ensure that the model learns from clean and consistent textual data.

---

## 🔤 Tokenization & Vocabulary

* Tokenized text using Keras Tokenizer
* Vocabulary limited to top 5000 most frequent words
* Added:

  * `<PAD>` token = 0
  * `<OOV>` token for unknown words

This helps in handling unseen words during testing.

---

## 🔢 Text to Sequences

* Converted tweets into integer sequences
* Applied padding to a fixed length of 25 tokens

This ensures uniform input size for the RNN model.

---

## 🤖 Model Architecture

The model consists of:

* **Embedding Layer** (input_dim = 5000, output_dim = 64)
* **Simple RNN Layer** (64 units)
* **Dropout Layer** (to reduce overfitting)
* **Dense Output Layer** (Sigmoid activation for binary classification)

---

## ⚙️ Training Details

* Loss Function: Binary Crossentropy
* Optimizer: Adam
* Epochs: 10
* Batch Size: 32
* Validation Split: 10%
* Early Stopping applied to prevent overfitting

---

## 📉 Training Analysis

The training and validation accuracy curves were plotted to evaluate model performance.

* Training accuracy steadily increased to ~99%
* Validation accuracy fluctuated between ~91–93%
* A noticeable gap between training and validation accuracy was observed

### ⚠️ Observation

This indicates **overfitting**, where the model performs very well on training data but struggles to generalize on unseen data.

## 📈 Results

* Test Accuracy: ~85–92% (depending on configuration)
* Evaluation Metrics:

  * Confusion Matrix
  * Precision, Recall, F1-score

The model demonstrates strong ability to detect hate speech while maintaining balanced performance.

---

## 🚀 Future Improvements

* Use LSTM/GRU for better sequence learning
* Use pre-trained embeddings (GloVe, Word2Vec)
* Perform hyperparameter tuning
* Try advanced NLP techniques (transformers)

---

## 📁 Repository Structure

hate-speech-rnn/
│
├── data/ → Dataset
├── notebook/ → Jupyter Notebook
├── README.md

---

## 🧑‍💻 Author

Mrutyunjaya Debata
