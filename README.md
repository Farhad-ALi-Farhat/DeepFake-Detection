# 🕵️ DeepFake Detection (Image & Video-based)

This repository contains two complementary approaches for **DeepFake detection**:
1. **Image-based detection** using **Xception CNN** on single representative frames.
2. **Video-based detection** using **Xception + LSTM** on sequences of frames.

Both methods use the **FaceForensics++ dataset** and demonstrate how deep learning can detect manipulated (fake) videos.

---

## 📌 Features
### 🖼 Image-based Detection
- Extracts the **middle frame** from each video.
- Uses **Xception (ImageNet-pretrained)** as backbone CNN.
- Custom Dense layers for binary classification (Real vs Fake).
- Trains with callbacks: EarlyStopping, ReduceLROnPlateau, ModelCheckpoint.
- Saves best/final models (`.h5`, `.keras`).
- Plots **Accuracy, Loss, Precision, Recall**.

### 🎥 Video-based Detection
- Extracts **multiple frames** per video (e.g., every 5th frame, max 40 frames).
- Data augmentation applied during preprocessing.
- Uses **TimeDistributed Xception** for frame-level features.
- Sequences passed through **LSTM / BiLSTM** for temporal modeling.
- Classifies **entire video** as Real or Fake.
- Supports validation split and metric visualization.

---

## 📂 Dataset
Both models use the **FaceForensics++ dataset**:
- **Real videos**: Actors, YouTube sources.
- **Fake videos**: DeepFakeDetection, Deepfakes, Face2Face, FaceSwap, NeuralTextures, FaceShifter.

> ⚠️ Dataset is **not included** in this repo due to size restrictions.  
Download it here: [https://github.com/ondyari/FaceForensics](https://github.com/ondyari/FaceForensics)

---

## 🚀 Installation
Clone this repository:
```bash
git clone https://github.com/your-username/DeepFake-Detection.git
cd DeepFake-Detection
