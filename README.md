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

---

## 🗂️ Repository Organization

```bash
├── images/              # Visuals and figures used in the README
├── CNNs/                # Trained model checkpoints for CNN-based architectures
├── ViTs/                # Trained model checkpoints for Vision Transformers
├── CLIP/                # Trained model checkpoints for CLIP-based models
└── README.md            # This file

