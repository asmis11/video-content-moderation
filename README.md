# video-content-moderation

From this project, I have concluded that a Fusion model with Audio, Text and Video (with 3D CNN) is a best model for vidoe content moderation.
## Part 1 - Visual-only 3D CNN Model and Fusion Model

# Part 2 - Phase-Wise Multimodal Model

### Phase-by-Phase Approach:

| Phase | Description |
|:------|:------------|
| Phase 1 | Frame Classification with MobileNetV2 |
| Phase 2 | Metadata Random Forest Model |
| Phase 3 | Visual + Text Fusion (BERT + Logistic Regression) |
| Phase 4 | Video Sequence LSTM (MobileNetV2 + LSTM) |
| Phase 5 | Spatio-Temporal 3D CNN (Conv3D) |
| Phase 6 | Fusion Model (Audio + Visual + Text Confidence) |
| Phase 7 | Vision Transformer (ViT) Frame Classification |

# Structure

| File | Description |
|:-----|:------------|
| `Hackathon.ipynb` | Part 1 Notebook |
| `Phases.ipynb` | Part 2 Notebook|
| `README.md` | This README |
| `video.mp4` | Short Demo video |
| `Write Up.docx` | Summary |
---


