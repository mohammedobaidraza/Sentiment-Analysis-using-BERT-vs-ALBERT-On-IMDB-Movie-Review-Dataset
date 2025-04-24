# Sentiment Analysis using BERT & ALBERT on IMDB Movie Reviews

This project demonstrates how to perform sentiment analysis using two transformer-based models: **BERT (Bidirectional Encoder Representations from Transformers)** and **ALBERT (A Lite BERT)**.

Both models are trained and evaluated on the **IMDB Movie Review dataset**, focusing on optimizing for performance in **CPU-constrained environments** (like Google Colab free tier).

---

## 🗂 Dataset

- **Source**: [IMDB Movie Reviews Dataset (50,000 samples)]([https://ai.stanford.edu/~amaas/data/sentiment/](https://www.kaggle.com/datasets/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews))
- **Labels**: Binary classification — `positive` or `negative`
- **Original Size**: 50,000 reviews (25k positive, 25k negative)
- **Reduced Subset Used**:
  - 1,000 training samples
  - 200 test samples

---

## ⚙️ Model Architectures

### BERT
- Model: `bert-base-uncased`
- Tokenizer: WordPiece
- Tasks: Masked Language Modeling + Next Sentence Prediction
- Fine-tuned using TensorFlow

### ALBERT
- Model: `albert-base-v2`
- Optimizations:
  - Factorized embeddings
  - Cross-layer weight sharing
  - Sentence Order Prediction
- Lightweight and memory-efficient

---

## 🧠 Training Setup

| Parameter       | Value                    |
|----------------|--------------------------|
| Epochs          | 1                        |
| Batch Size      | 8                        |
| Max Token Length| 64                       |
| Optimizer       | AdamW (`create_optimizer`) |
| Loss Function   | Sparse Categorical Crossentropy |
| Metrics         | Accuracy                 |

---

## 📊 Results

| Metric   | BERT        | ALBERT       |
|----------|-------------|--------------|
| Accuracy | 75.00%      | 57.00%       |
| Loss     | 0.5180      | 0.6845       |

- BERT outperformed ALBERT on the reduced dataset in both accuracy and loss.
- ALBERT trained faster and used fewer resources — suitable for lightweight deployment.

---

## 📈 Visuals

- Review length distribution
- Training loss and accuracy curves
- Final performance comparison chart (Accuracy vs Loss)

---

## 💡 Conclusion

- **BERT** is more powerful but heavier and slower — ideal when maximum accuracy is the goal.
- **ALBERT** trades off a small amount of performance for a large gain in speed and efficiency — ideal for limited hardware.

---

## 🧑‍💻 Author

Developed by [Obaid Raza](https://github.com/mohammedobaidraza)

---

## 📁 File

You can open the full Notebook:  
[Colab](https://colab.research.google.com/drive/1xNqkluJIQSDTY5wWpmJ514hy3_dkUn8J#scrollTo=vsz6FPlsKvOS&uniqifier=1)

---
