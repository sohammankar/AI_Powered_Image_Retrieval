# 🖼️ AI-Powered Image Retrieval System

An interactive deep learning-based system to retrieve visually similar images using a fine-tuned ResNet model and FAISS indexing. Built with PyTorch, Streamlit, and Caltech101 dataset.


---

[App Screenshot](./web-app.png)

---

## 🚀 Features

- Upload an image and find visually similar images from a gallery
- Fine-tuned **ResNet-18** model for compact feature extraction
- Fast similarity search using **FAISS**
- Simple and elegant UI with **Streamlit**
- Image pre-processing, embedding generation, and FAISS indexing pipeline

---

## 🧱 Project Structure

```
├── caltech101/            # Caltech101 image dataset
├── data/                  # FAISS index + metadata
├── weights/               # Trained model (model.pth)
├── src/                   # ResNetTransferModel definition
├── utils/                 # Image, FAISS, and display utilities
├── app.py                 # Streamlit application
├── precompute_features.py # Script to build embeddings and index
├── requirements.txt       # Python dependencies
```

---

## ⚙️ Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/sohammankar/AI_Powered_Image_Retrieval.git
cd AI_Powered_Image_Retrieval
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Precompute Features & Build FAISS Index

```bash
python precompute_features.py \
  --model weights/model.pth \
  --data train_val.json \
  --faiss data/faiss_index.bin \
  --pickle data/features.pickle \
  --num-per-class 10
```

### 4. Run the App

```bash
streamlit run app.py
```

App will open in your browser where you can upload images and see results.

---

## 🧠 Model Details

- **Backbone**: ResNet-18 (fine-tuned on Caltech101)
- **Embedding Size**: 128-D
- **Top-1 Accuracy**: ~90%
- **Top-5 Accuracy**: ~97.8%
- Training and extraction done in Google Colab (see Colab notebook PDF)

---

## 📊 Demo Overview

- **Sidebar**: Adjust number of results, set paths, view categories
- **Main View**: Upload image → Search → View similar results
- **Similarity Score**: Cosine similarity with normalized embeddings

---

## 🧩 Future Work

- Add support for multimodal search (image + text)
- Deploy to cloud via Hugging Face Spaces or Docker container
- Introduce relevance feedback and better re-ranking

---

## 🙋‍♂️ Author

**Soham Mankar**  
🔗 [LinkedIn](https://www.linkedin.com/in/soham-mankar-12675a18b/) 
📂 [GitHub](https://github.com/sohammankar)

---


## ⭐️ Show Your Support

If you find this useful, consider giving a ⭐️ to the repository.
