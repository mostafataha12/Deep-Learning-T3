# 🧠 Human Action Recognition using CNN + LSTM

## 📌 Project Overview

This project implements a **hybrid deep learning model** that combines:

* **Convolutional Neural Networks (CNN)** for feature extraction
* **Long Short-Term Memory (LSTM)** for sequence modeling

The goal is to classify **human actions** into 15 different categories such as:

> calling, clapping, cycling, dancing, drinking, eating, fighting, hugging, laughing, listening to music, running, sitting, sleeping, texting, and using a laptop.

---

## 🎯 Objectives

* Extract meaningful **spatial features** from images using CNN
* Model **temporal/sequential patterns** using LSTM
* Perform **multi-class classification** of human actions
* Demonstrate a **CNN + LSTM pipeline** on a real dataset

---

## 📊 Dataset

* Total Images: **12,600**
* Classes: **15 human actions**
* Split: **85% training / 15% testing**

### ⚠️ Important Note

The dataset consists of **independent images (not videos)**.
To apply LSTM, sequences were **artificially created** by grouping multiple images from the same class.

---

## 🏗️ Model Architecture

```
Input (Sequence of Images)
        ↓
CNN (MobileNetV2 - Feature Extraction)
        ↓
Feature Vectors per Frame
        ↓
LSTM (Sequence Learning)
        ↓
Dense Layers
        ↓
Output (15 Classes)
```

### 🔹 Components:

* **CNN**: MobileNetV2 (pretrained on ImageNet)
* **LSTM**: 128 units
* **Dense Layers**: Fully connected classifier
* **Activation**: ReLU + Softmax

---

## ⚙️ Workflow

1. Load dataset from Kaggle
2. Preprocess images (resize, normalize)
3. Create sequences (e.g., 5 images per sample)
4. Extract features using CNN
5. Feed sequence into LSTM
6. Train model using cross-entropy loss
7. Evaluate performance on test set

---

## 🧪 Training Details

| Parameter       | Value                    |
| --------------- | ------------------------ |
| Image Size      | 224 × 224                |
| Sequence Length | 5                        |
| Batch Size      | 8                        |
| Epochs          | 10                       |
| Optimizer       | Adam                     |
| Loss Function   | Categorical Crossentropy |

---

## 📈 Results

* The model successfully learned to classify human actions.
* Training and validation accuracy improved over epochs.
* Performance can be further improved with:

  * More epochs
  * Data augmentation
  * Fine-tuning CNN layers

---

## 🧠 Why CNN + LSTM?

* **CNN** captures spatial information (objects, shapes, features)
* **LSTM** captures temporal relationships (sequence patterns)
* Together, they allow the model to understand both **what** and **how it changes over time**

---

## 🚀 How to Run

### ▶️ Kaggle Notebook

1. Upload dataset to Kaggle
2. Open a new Notebook
3. Paste the provided code
4. Update dataset path:

   ```python
   DATASET_PATH = "/kaggle/input/your-dataset-name"
   ```
5. Run all cells

---

## 📂 Project Structure

```
├── notebook.ipynb
├── README.md
└── dataset/
    ├── train/
    └── test/
```

---

## 📌 Key Insight

Even though the dataset is not sequential, this project demonstrates how **LSTM can still be applied by constructing pseudo-sequences**, making it suitable for academic purposes.

---

## 🔮 Future Improvements

* Use real video datasets (e.g., UCF101)
* Apply data augmentation
* Use GRU instead of LSTM
* Deploy as a real-time action recognition system

---

## 👨‍💻 Author

**Mostafa Taha**

---

## 📜 License

This project is for **educational purposes only**.
