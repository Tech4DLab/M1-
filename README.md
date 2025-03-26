<h1 align="center">🐟 M1 && M1+: Benchmarking Deep Learning Models for Fish Classification with Explainability and Model Transparency 🔎</h1>
<h3 align="center">🌊 Tech4DLab GLORiA 🎣</h3>

<p align="center">
  <img src="images/Abstract.png" alt="Abstract image" width="900"/>
</p>

## 🧠 Abstract

Aquaculture is the fastest-growing food production
sector of this century. Although artificial intelligence has driven
numerous advancements in this field, no studies have focused
on the risks associated with fish escapes from aquaculture
farms. These events can cause environmental issues, disrupt
wild populations, compromise the health of other species and
negatively impact both aquaculture and traditional fisheries.
This work introduces an innovative approach to determining
the origin of two economically significant Mediterranean fish
species, Sparus aurata and Dicentrarchus labrax, using a CLIP-
based multimodal framework combined with a lightweight Linear
Probe classifier. By integrating expert-crafted textual descriptions
with visual embeddings, the proposed system achieves high
classification accuracy, outperforming traditional CNN and ViT
models, which require extensive pretraining. Additionally, the
methodology is validated with various explainability techniques,
including GRAD-ECLIP, expert-driven feature importance anal-
ysis and manual feature manipulation, ensuring a transparent
and interpretable system for aquaculture professionals. Eval-
uations conducted on wild, farmed and escaped fish and the
validation done demonstrate the model’s strong performance
and its potential to improve traceability and management in
aquaculture.

## 🧠 Architecture

<p align="center">
  <img src="images/Abstract.png" alt="Abstract image" width="900"/>
</p>

The proposed classification framework is based on the CLIP model, leveraging both textual descriptions and visual embeddings to distinguish between wild and farmed fish.  
The architecture of our approach follows these main components:

1. **Vision Encoder (ViT-B/16)**: The image of a fish is processed through a Vision Transformer encoder, generating a high-dimensional feature representation.
2. **Text Encoder (GPT Transformer)**: Expert-curated textual descriptions are encoded into a multimodal space using CLIP’s text encoder.
3. **Feature Aggregation**: Multiple textual embeddings (T₁, T₂, ..., Tₙ) are combined to refine the classification decision. Additionally, weighted feature vectors, *WF* (Wild Features) and *CF* (Cultivated Features), are computed as the average of image embeddings extracted from a training set.
4. **Cosine Similarity Computation**: The embeddings from the image, text encoders, and weighted features are compared using cosine similarity to determine the alignment between visual and textual features.
5. **Classification Methods**: The concatenated embedding (e.g., `I1T2`) is passed through different classifiers including **Linear Probe (LP)**, **k-Nearest Neighbors (KNN)**, **Random Forest (RF)**, and **Support Vector Machine (SVM)**.

---

## 📈 Performance

### 🧪 Convolutional Networks (CNNs)

| Model          | Total (%) | *D. labrax* (%) | *S. aurata* (%) |
|----------------|-----------|------------------|------------------|
| MobileNetV2    | 79.0      | 61.0             | 97.0             |
| ResNet50       | 80.5      | 74.0             | 87.0             |
| VGG            | 84.0      | 78.0             | 90.0             |
| **InceptionV3**| **85.5**  | **74.0**         | **97.0**         |

---

### 🧪 Multimodal Models (Image + Text Prompts)

| Model       | Total (%) | *D. labrax* (%) | *S. aurata* (%) |
|-------------|-----------|------------------|------------------|
| BLIP        | 55.0      | 50.0             | 60.0             |
| ALIGN       | 56.5      | 74.0             | 39.0             |
| BLIP-2      | 68.0      | 71.0             | 65.0             |
| Kosmos-2    | 68.0      | 71.0             | 65.0             |
| OpenCLIP    | 84.0      | 74.0             | 94.0             |
| **CLIP**    | **86.5**  | **83.0**         | **90.0**         |

---

### 🧪 Vision Transformers (ViTs)

| Model        | Total (%) | *D. labrax* (%) | *S. aurata* (%) |
|--------------|-----------|------------------|------------------|
| ViT-L/14     | 0.0       | 0.0              | 0.0              |
| **ViT-B/32** | **92.0**  | **87.0**         | **97.0**         |
| ViT-B/16     | 0.0       | 0.0              | 0.0              |

---

### 🧪 ResNet and ViT Variants

| Model    | Total (%) | *D. labrax* (%) | *S. aurata* (%) |
|----------|-----------|------------------|------------------|
| RN50     | 84.0      | 87.0             | 81.0             |
| RN101    | 74.0      | 87.0             | 61.0             |
| RN50x4   | 63.5      | 30.0             | 97.0             |
| **ViT-B/16** | **86.5** | **83.0**       | **90.0**         |
| ViT-B/32 | 86.5      | 83.0             | 90.0             |
| *ViT-L/14* | *86.0*   | *91.0*           | *81.0*           |

---

### 🧪 Classifier Comparison (ViT Models)

#### ViT-B/16 (~86M params)

| Classifier | Total (%) | *D. labrax* (%) | *S. aurata* (%) |
|------------|-----------|------------------|------------------|
| KNN        | 84.0      | 78.0             | 90.0             |
| RF         | 84.0      | 78.0             | 90.0             |
| **SVC**    | **93.5**  | **87.0**         | **100.0**        |
| **LP**     | **93.5**  | **87.0**         | **100.0**        |

#### ViT-B/32 (~86M params)

| Classifier | Total (%) | *D. labrax* (%) | *S. aurata* (%) |
|------------|-----------|------------------|------------------|
| KNN        | 84.0      | 74.0             | 94.0             |
| RF         | 86.5      | 83.0             | 90.0             |
| SVC        | 90.0      | 83.0             | 97.0             |
| **LP**     | **92.0**  | **87.0**         | **97.0**         |

#### ViT-L/14 (~304M params)

| Classifier | Total (%) | *D. labrax* (%) | *S. aurata* (%) |
|------------|-----------|------------------|------------------|
| KNN        | 90.5      | 87.0             | 94.0             |
| RF         | 89.0      | 91.0             | 87.0             |
| **SVC**    | **95.0**  | **96.0**         | **94.0**         |
| LP         | 92.5      | 91.0             | 94.0             |

---

*The best-performing models for each category are highlighted in bold.*

## 🧠 Explainability

---

## 🗂️ Repository Organization

```bash
├── images/              # Visuals and figures used in the README
├── CNNs/                # Trained model checkpoints for CNN-based architectures
├── ViTs/                # Trained model checkpoints for Vision Transformers
├── CLIP/                # Trained model checkpoints for CLIP-based models
└── README.md            # This file


