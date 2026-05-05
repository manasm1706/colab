# 🧠 Multilingual Handwritten Text Recognition (HTR) + NLP Pipeline

A modular, debug-friendly pipeline for **handwritten text recognition (HTR)** combined with **language detection and NLP analysis**.

> ⚠️ Current Status: Only FINAL_HTR_Pipeline has Fully functional HTR for **English handwritten text**.
> 🚀 Multilingual support (Marathi, Hindi, Tamil, Telugu) is under active development.

---

## 📌 Overview

This project implements an end-to-end pipeline that takes a handwritten image and processes it through multiple stages:

1. **Image Preprocessing**
2. **Line Segmentation**
3. **Word Segmentation (Dual Method)**
4. **OCR (CNN-based + heuristics)**
5. **Language Detection**
6. **Post-processing + NLP (Sentiment, Entities)**

The system is designed with **maximum debuggability**, with visual outputs at every stage.

---

## 🏗️ Pipeline Architecture

```
Input Image
     ↓
Preprocessing (grayscale, binarization, noise removal)
     ↓
Line Segmentation (morphology + contours)
     ↓
Word Segmentation
    ├── Connected Components
    └── X-Projection Profile
     ↓
Merge Word Boxes
     ↓
OCR (CNN / heuristic fallback)
     ↓
Language Detection (visual + text-based)
     ↓
Text Reconstruction
     ↓
NLP (Sentiment + Entity Recognition)
```

---

## 🔍 Key Features

### 🧪 Debug-First Design

* Visual outputs at every stage
* Projection profiles for segmentation tuning
* Bounding box overlays
* Word-level predictions visualization

### ✍️ Robust Word Segmentation

* Dual approach:

  * Connected Components
  * Projection Profiles
* Merged results → better accuracy

### 🌍 Multilingual-Aware Pipeline

* Designed for:

  * English ✅ (working)
  * Marathi (planned)
  * Hindi (planned)
  * Tamil (planned)
  * Telugu (planned)

### 🧠 NLP Integration

* Sentiment Analysis (multilingual BERT fallback)
* Named Entity Recognition (spaCy)
* POS tagging

---

## ⚙️ Tech Stack

* **Deep Learning:** TensorFlow / Keras
* **Computer Vision:** OpenCV, Albumentations
* **Datasets:** EMNIST (training)
* **NLP:** HuggingFace Transformers, spaCy
* **Utilities:** NumPy, Matplotlib

---

## 🚀 How to Run

### 1. Install dependencies

```bash
pip install tensorflow tensorflow-datasets opencv-python albumentations matplotlib numpy transformers spacy datasets
```

---

### 2. Run the pipeline

```python
pipeline_state = run_full_pipeline(
    image_path="your_image.png",
    debug=True,
    apply_shirorekha_fix=False
)
```

---

### 3. Output

The pipeline returns:

```python
{
    'raw_text': "...",
    'language': "...",
    'english_text': "...",
    'word_results': [...],
    'line_boxes': [...],
    'nlp': {
        'entities': [...],
        'sentiment': {...}
    }
}
```

---

## 📸 Debug Visualizations

* Preprocessing stages
* Binary image
* Line segmentation output
* Word bounding boxes
* Projection profiles
* OCR predictions per word

---

## ⚠️ Current Limitations

* Only **English OCR is stable**
* Multilingual OCR still under development
* Word segmentation may need tuning for:

  * cursive handwriting
  * tightly spaced words

---

## 🔮 Future Improvements

* ✅ Multilingual OCR models (Hindi, Marathi, Tamil, Telugu)
* 🔤 Script-aware segmentation (Shirorekha handling)
* 🧠 Transformer-based OCR (TrOCR / Donut)
* 📊 Confidence calibration & error correction
* 📱 Real-time inference (mobile/web)
* 🗂️ Dataset expansion (custom handwritten datasets)

---

## 🧠 Research Potential

This project is designed with **research extensibility** in mind:

* Modular pipeline (easy to swap components)
* Debug visualization at every stage
* Suitable for:

  * OCR research
  * Multilingual document understanding
  * Low-resource handwriting datasets

---

## 🙌 Acknowledgements

* EMNIST Dataset
* HuggingFace Transformers
* OpenCV Community

---

## 👨‍💻 Author

Built as part of a **research-oriented OCR + NLP system** focusing on real-world handwritten data.

---

## ⭐ If you like this project

Give it a star and feel free to contribute!

---
