# Facial Emotion Recognition Using Convolutional Neural Networks

This repository contains the research paper **"Facial Emotion Recognition Using Convolutional Neural Networks"** and its accompanying implementation in Python (Google Colab).  
The project explores how CNN architectures such as **VGGNet** and **ResNet50** can recognize human emotions from facial images.

---

## 📄 Paper
**Title:** Facial Emotion Recognition Using Convolutional Neural Networks  
**Author:** Milana Pak  
**Abstract:**  
This study investigates the ability of CNNs to detect human emotions—anger, fear, and happiness—from facial images. Using the VGGNet and ResNet50 architectures, several experiments were performed with different optimization strategies. Results show that CNNs can often predict emotions correctly, although certain emotions such as fear and anger are frequently confused with happiness due to dataset complexity.

Full paper: [`Facial Emotion Recognition Using Convolutional Neural Networks.pdf`](Facial%20Emotion%20Recognition%20Using%20Convolutional%20Neural%20Networks.pdf)

---

## 🧠 Model Overview
The CNN pipeline consists of:
1. **Face detection and preprocessing** – grayscale conversion and resizing to 48×48.  
2. **Convolutional + pooling layers** – for feature extraction.  
3. **Fully connected layers** – for classification.  
4. **Output layer** – predicting one of the emotion classes.

Architectures used:
- **VGGNet**
- **ResNet50**

---

## 📊 Dataset
- ~10,000 facial images labeled with 3 emotions: *anger, fear, happiness*  
- Grayscale, 48×48 pixels  
- Split into training and testing subsets  

*(Dataset is not uploaded here due to storage limits. You can replace this section with a dataset link if you decide to share it.)*

---

## 💻 Code
Notebook: [`Milana_Facial_Recog_v2_with_data_save.ipynb`](Milana_Facial_Recog_v2_with_data_save.ipynb)

The notebook includes:
- Data preprocessing  
- CNN model training  
- Evaluation with confusion matrices  
- Experiment comparison between VGG and ResNet50  

Run it in Google Colab:
1. Open the `.ipynb` in Colab.  
2. Upload your dataset to the `/data` folder.  
3. Run all cells.  

---

## 🧩 Results Summary
| Model      | Emotions Tested | Accuracy | Notes |
|-------------|----------------|-----------|--------|
| VGGNet      | Fear, Anger     | ~0.18     | Confused fear with happiness |
| ResNet50    | Fear, Anger, Happy | ~0.22 | Improved happy recognition, but anger confusion remains |

---


