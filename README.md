# video-content-moderation

#Harmful Content Detection (Two Approaches)

## 📚 Project 1 - Visual-only 3D CNN Model (Hackathon Submission)

---

## 🌟 Objective:
- Classify TikTok videos into:
  - **Adult Content**
  - **Harmful Content**
  - **Safe**
  - **Suicide**
- **Predict Safe/Unsafe + Confidence + Notes**

---

## 📋 Steps:

### 1. Upload Dataset
- Upload manually `tikharm_dataset.zip`.

```python
from google.colab import files
uploaded = files.upload()
```

### 2. Unzip Dataset

```python
import zipfile
with zipfile.ZipFile("/content/tikharm_dataset.zip", 'r') as zip_ref:
    zip_ref.extractall("/content/tikharm_dataset")
```

✅ Dataset folders:
- `/content/tikharm_dataset/tikharm_dataset/train/`
  - `adult/`
  - `harmful/`
  - `safe/`
  - `suicide/`

### 3. Install Libraries

```python
!pip install torch torchvision moviepy
```

### 4. Data Preparation
- **Extract 8 frames** from each video.
- **Resize frames** to `112x112`.
- Stack as `[C, T, H, W]` for input to 3D CNN.

### 5. Build the Model
- **Backbone:** `r3d_18` (ResNet 3D, pretrained).
- Final layer: 4-class classification head.

### 6. Train the Model
- Loss: CrossEntropy
- Optimizer: Adam
- 3 Epochs
- Batch size = 2

### 7. Upload and Predict
- Upload any new video.
- Extract frames and predict:
  - Category
  - Safe/Unsafe
  - Confidence
  - Notes

## ✅ Deliverables:

| Deliverable | Details |
|:------------|:--------|
| Trained 3D CNN | Only video frames |
| Safe/Unsafe Prediction | Confidence score |
| Notes Generation | For explanation |

## 🏆 Advantages:
- Lightweight (only visual input)
- Fast training
- Perfect for TikTok moderation tasks

---

# 📄 Project 2: Phase-Wise Multimodal Model (Frame, Audio, Text, Transformer Fusion)

---

## 🌟 Objective:
- Detect harmful content by combining:
  - **Frame-Level Features**
  - **Audio Analysis**
  - **Text Metadata Analysis**
  - **BERT Embeddings**
  - **Vision Transformers (ViT)**

---

## 📋 Steps:

### 1. Upload Dataset
- Upload manually `tikharm_dataset.zip`.

### 2. Unzip Dataset

```python
import zipfile
with zipfile.ZipFile("/content/tikharm_dataset.zip", 'r') as zip_ref:
    zip_ref.extractall("/content/tikharm_dataset")
```

### 3. Install Libraries

```python
!pip install torch torchvision torchaudio torchvggish moviepy ffmpeg-python transformers
```

### 4. Phase-by-Phase Approach:

| Phase | Description |
|:------|:------------|
| Phase 1 | Frame Classification with MobileNetV2 |
| Phase 2 | Metadata Random Forest Model |
| Phase 3 | Visual + Text Fusion (BERT + Logistic Regression) |
| Phase 4 | Video Sequence LSTM (MobileNetV2 + LSTM) |
| Phase 5 | Spatio-Temporal 3D CNN (Conv3D) |
| Phase 6 | Fusion Model (Audio + Visual + Text Confidence) |
| Phase 7 | Vision Transformer (ViT) Frame Classification |

---

## 💚 Deliverables:
- Phase-by-phase trained models.
- Frame, Audio, Text feature extraction.
- Fusion models and transformers.
- Safe/Unsafe predictions with explanation notes.

---

## 🏆 Advantages:
- Complete multimodal learning pipeline.
- Integration of CNNs, LSTM, Transformers.
- Visual, audio, text data all utilized.
- Scalable and extendable.

---

# Structure

| File | Description |
|:-----|:------------|
| `Hackathon.ipynb` | Project 1 Notebook (3D CNN only) |
| `Phases.ipynb` | Project 2 Notebook (Multimodal pipeline) |
| `tikharm_dataset.zip` | Dataset |
| `README.md` | This README |
| `video.mp4` | Short Demo video |

---


