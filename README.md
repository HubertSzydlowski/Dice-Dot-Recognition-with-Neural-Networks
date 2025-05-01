# Dice Dot Recognition with Neural Networks

## **🧑‍💻 Author**

### Hubert Szydłowski

---

## 🎯 Project Goal

This project uses an artificial neural network (ANN), specifically a convolutional neural network (CNN), to analyze images of dice. The model learns to recognize the number of pips or detect invalid dice based on visual input.
The aim is to develop an AI model that can:
- recognize whether the image shows a valid die,
- if valid — determine the number of dots (pips) on its top face.

---

## 🧾 Dataset Description

The dataset `dice_ext.csv` contains 70,000 dice images, each represented as:
- resolution: 28×28 pixels (784 values),
- grayscale pixel values from 0 to 255 (MNIST-style, where 255 = black),
- labels:
  - **first value**: `1` = valid die, `0` = invalid die,
  - **second value**: number of pips (1–6) or type of defect (0–9).

All dice appear against a contrasting background, in random rotations, with the top face fully visible.

---

## 📌 Project Stages

### Stage 1 – Data Verification & Preparation

- Validate CSV format and structure,
- Check row and column count (expected: 70,000 × 786),
- Confirm pixel values are within [0, 255],
- Ensure all images are unique,
- Visualize sample images,
- Label distribution check:
  - 60,000 valid dice (10,000 per class from 1 to 6),
  - 10,000 invalid dice (10 error types × 1,000 each).

### Stage 2 – Classification using Neural Network

A convolutional neural network (CNN) was built to classify each image into one of 7 classes:
- 6 classes for the number of pips (valid dice),
- 1 class for invalid dice.

#### Model architecture:

1. **Conv2D (32, 3×3, ReLU)**  
2. **Conv2D (64, 3×3, ReLU)**  
3. **MaxPooling2D (2×2)**  
4. **Conv2D (128, 3×3, ReLU)**  
5. **MaxPooling2D (2×2)**  
6. **Flatten**  
7. **Dense (128, ReLU)**  
8. **Dropout (0.3)**  
9. **Output Dense (7, softmax)**

---

## 📈 Results

- **Accuracy** on test set: **99.81%**
- **Number of unique images**: 70,000
- **Confusion matrix**: very low misclassification

The model accurately detects invalid dice and correctly classifies valid ones.

---

## 🛠 Technologies Used

- Python 3
- NumPy, Pandas
- Matplotlib
- TensorFlow / Keras
