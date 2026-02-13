# Facial Emotion Recognition via Deep Convolutional Architectures

## Project Overview

This project investigates **Facial Emotion Recognition (FER)** using deep convolutional neural networks, with emphasis on:

- Architectural comparison (VGG vs. ResNet)
- Optimization behavior
- Systematic confusion between semantically adjacent classes
- Limitations of unimodal visual supervision

The accompanying research manuscript is available in this repository:
*Facial Emotion Recognition using Convolutional Neural Networks*

---

## Problem Formulation

Given a grayscale facial image \( x \in \mathbb{R}^{48 \times 48} \), the goal is to learn a function:

\[
f_\theta(x) \rightarrow y
\]

where  

\[
y \in \{\text{anger, fear, happiness, sadness, neutral, surprise}\}
\]

The model is trained by minimizing categorical cross-entropy:

\[
\mathcal{L} = - \sum_{i=1}^{C} y_i \log(\hat{y}_i)
\]

Evaluation focuses not only on accuracy but also on representational behavior and failure modes.

---

## Dataset

- >10,000 labeled facial images  
- Preprocessed to **48×48 grayscale**
- Experiments conducted on:
  - 3-class setting (anger, fear, happiness)
  - Extended 6-class setting

---

## Architectural Design

### 1. VGG16 / VGG19

- Deep convolutional stacks with 3×3 kernels  
- Hierarchical feature extraction  
- No residual connections  
- Fully connected classification head  

Used to evaluate performance under standard deep CNN feature extraction.

---

### 2. ResNet50

- 50-layer residual architecture  
- Identity shortcut connections  
- Improved gradient propagation  
- Higher representational capacity  

Used to analyze the impact of residual learning on subtle inter-class discrimination.

---

## Training Configuration

- Loss: Cross-Entropy  
- Optimizers: SGD / Adam (comparative experiments)  
- Learning rate scheduling  
- Epoch-based training  
- Evaluation metrics:
  - Accuracy
  - Confusion matrices
  - Qualitative misclassification analysis

---

## Experimental Findings

### 1. Systematic Class Ambiguity

Confusion matrices revealed strong overlap between:

- Fear ↔ Happiness  
- Anger ↔ Happiness  

This suggests that purely visual supervision encourages reliance on dominant features (e.g., mouth curvature), rather than distributed facial representations.

---

### 2. Architectural Impact

ResNet50 showed modest improvements over VGG in extended emotion settings, suggesting:

- Residual connections stabilize deeper representations  
- Increased capacity alone does not resolve semantic ambiguity  

---

### 3. Representation Limitation

Observed failure modes indicate:

- High intra-class variability  
- Over-reliance on localized discriminative regions  
- Lack of contextual or relational modeling  

This exposes a key limitation of global CNN pooling under unimodal learning.

---

## Analytical Reflection

Traditional CNN classifiers operate under a **global feature aggregation paradigm**, where semantic similarity is inferred from visual embedding proximity alone.

However, emotional expressions often require:

- Fine-grained regional attention  
- Contextual reasoning  
- Multi-signal integration  

The confusion between semantically adjacent classes suggests:

\[
\text{Visual similarity} \not\equiv \text{Semantic equivalence}
\]

This motivates exploration of:

- Region-level modeling  
- Cross-modal supervision  
- Attention-guided feature refinement  
- Interaction-based representation learning  
---

## Reproducibility

### Dependencies

```bash
pip install torch torchvision numpy matplotlib scikit-learn
```

### Execution

```bash
jupyter notebook Milana_Facial_Recog_v2_with_data_save.ipynb
```

---

## Future Directions

Potential extensions include:

- Region-based modeling (e.g., R-CNN feature extraction)
- Contrastive learning for fine-grained alignment
- Cross-modal supervision incorporating textual emotion descriptors
- Attention-guided training to reduce shortcut learning
- Robustness evaluation under noisy or partial facial cues

---

## Author

Milana Pak  

