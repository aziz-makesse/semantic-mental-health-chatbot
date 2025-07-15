# 🧠 Semantic Chatbot for Mental Health Support

This project implements a **semantic chatbot** trained on the [Mental Health Conversational Dataset](https://www.kaggle.com/datasets/elvis23/mental-health-conversational-data). It uses **SentenceTransformers** for semantic similarity to detect user intent and generate relevant responses.

---

## 📦 Dataset

The chatbot is powered by the dataset:  
**📁** `mental-health-conversational-data.zip`  
**🔗** [Kaggle Dataset URL](https://www.kaggle.com/datasets/elvis23/mental-health-conversational-data)

It includes conversational patterns and intent-based responses centered on mental health topics (e.g., grief, anxiety, depression, happiness, etc.).

---

## 🛠️ How It Works

1. **Embeddings**: The chatbot uses [`all-MiniLM-L6-v2`](https://www.sbert.net/docs/pretrained_models.html) model from the `sentence-transformers` library to compute sentence embeddings.
2. **Similarity Matching**: It compares user input with all predefined patterns using **cosine similarity**.
3. **Intent Prediction**: The intent with the highest similarity above a threshold (default: `0.6`) is selected.
4. **Response Generation**: A response is randomly chosen from the associated intent's responses.

---

## 🚀 Quickstart

### 🧱 Requirements

- Python 3.7+
- `sentence-transformers`
- `pandas`, `numpy`
- (Optional for dataset) `kaggle`

### 📜 Setup in Google Colab

```python
# Upload your Kaggle API key (kaggle.json)
from google.colab import files
files.upload()

# Prepare kaggle.json
!mkdir -p ~/.kaggle
!cp kaggle.json ~/.kaggle/
!chmod 600 ~/.kaggle/kaggle.json

# Download dataset
!kaggle datasets download -d elvis23/mental-health-conversational-data
!unzip mental-health-conversational-data.zip -d ./data
