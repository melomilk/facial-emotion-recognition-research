Below is a research-lab level README.
It is more technical, less descriptive, and emphasizes architectural reasoning, experimental design, and analytical findings.

You can paste this directly into your repository.

Facial Emotion Recognition via Deep Convolutional Architectures
Project Summary

This project investigates Facial Emotion Recognition (FER) using deep convolutional neural networks, with emphasis on:

Architectural comparison (VGG vs. ResNet)

Optimization behavior

Confusion analysis between semantically adjacent classes

Limitations of unimodal visual supervision

The accompanying research manuscript is available here:
📄 Facial Emotion Recognition using Convolutional Neural Networks 

Facial Emotion Recognition Usin…

Problem Formulation

Given a grayscale facial image 
𝑥
∈
𝑅
48
×
48
x∈R
48×48
, the task is to learn a function:

𝑓
𝜃
(
𝑥
)
→
𝑦
f
θ
	​

(x)→y

where 
𝑦
∈
{
anger, fear, happiness, sadness, neutral, surprise
}
y∈{anger, fear, happiness, sadness, neutral, surprise}.

The objective is to minimize categorical cross-entropy:

𝐿
=
−
∑
𝑖
=
1
𝐶
𝑦
𝑖
log
⁡
(
𝑦
^
𝑖
)
L=−
i=1
∑
C
	​

y
i
	​

log(
y
^
	​

i
	​

)

while analyzing representational behavior and failure modes.

Dataset

10,000 labeled facial images

Preprocessed to 48×48 grayscale

Experiments conducted on:

3-class setting (anger, fear, happiness)

Extended 6-class setting

Architectural Design
1. VGG16 / VGG19

Deep convolutional stacks with small receptive fields (3×3 kernels)

Hierarchical feature extraction

No residual connections

Fully connected classification head

Used to evaluate performance under standard deep CNN feature extraction.

2. ResNet50

50-layer residual architecture

Identity shortcut connections

Improved gradient propagation

Higher representational capacity

Used to analyze impact of residual learning on subtle inter-class discrimination.

Training Configuration

Loss: Cross-Entropy

Optimizers: SGD / Adam (comparative experiments)

Learning rate scheduling

Epoch-based training

Evaluation via:

Accuracy

Confusion matrices

Qualitative misclassification inspection

Experimental Findings
1. Systematic Class Ambiguity

Confusion matrices revealed strong overlap between:

Fear ↔ Happiness

Anger ↔ Happiness

This suggests that purely visual supervision encourages reliance on dominant features (e.g., mouth curvature), rather than distributed facial representations.

2. Architectural Impact

ResNet50 showed modest improvements over VGG in extended emotion settings, suggesting:

Residual connections help stabilize deeper representations.

However, deeper capacity alone does not resolve semantic ambiguity.

3. Representation Limitation

Observed failure modes indicate:

High intra-class variability.

Over-reliance on localized discriminative regions.

Lack of contextual or relational modeling.

This exposes a key limitation of global CNN pooling under unimodal learning.
