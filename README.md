# Multimodal Automatic Video Trailer and Highlight Generator

An AI-powered multimodal video summarization pipeline that automatically detects important moments in long videos and generates compact highlight reels using Vision Transformers and semantic scene understanding.

This project leverages **CLIP ViT-B/32** for zero-shot visual-semantic scoring, temporal segmentation, and automated highlight generation on the **TVSum50 benchmark dataset**, achieving meaningful correlation with human-annotated ground truth without any finetuning.

---

# Features

- Automatic video highlight detection
- Zero-shot semantic scene understanding using CLIP
- Temporal importance scoring and smoothing
- Automatic highlight reel generation
- Human-ground-truth evaluation using TVSum50
- Support for both:
  - Benchmark dataset videos
  - Custom YouTube videos
- Fully open-source pipeline runnable on:
  - Kaggle
  - Google Colab

---

# Project Pipeline

```text
Input Video
     ↓
Frame Extraction
     ↓
CLIP Semantic Scene Scoring
     ↓
Temporal Smoothing
     ↓
Highlight Segment Selection
     ↓
MoviePy Clip Stitching
     ↓
Generated Highlight Reel
```

---

# Model Architecture

## Vision Encoder
- CLIP ViT-B/32
- OpenAI pretrained model
- Zero-shot semantic retrieval

## Temporal Processing
- Uniform temporal smoothing
- Segment merging
- Threshold-based highlight selection

## Video Rendering
- MoviePy-based clip stitching
- Automatic highlight compilation

---

# Dataset

## TVSum50

The project uses the **TVSum50 benchmark dataset** for evaluation.

### Dataset Details
- 50 YouTube videos
- Multiple genres:
  - documentaries
  - sports
  - vlogs
  - news
  - cooking
  - travel
- Human-annotated importance scores
- 20 annotators per video

### Evaluation Metrics
- Kendall Tau Correlation
- Spearman Rank Correlation

---

# Results

| Metric | Score |
|---|---|
| Spearman Correlation | 0.47 |
| Kendall Tau Correlation | 0.32 |
| Video Compression Ratio | 83% |

The system demonstrates meaningful alignment with human-perceived video importance despite operating entirely in a zero-shot setting without task-specific training.

---

# Example Workflow

## 1. Extract Frames
Frames are sampled periodically from the source video.

## 2. Semantic Scene Scoring
Each frame is scored against semantic highlight prompts such as:
- exciting moments
- emotional scenes
- action-packed events
- cinematic shots

## 3. Temporal Highlight Selection
High-scoring frames are merged into continuous highlight segments.

## 4. Highlight Reel Generation
Selected segments are stitched into a final compressed highlight reel.

---

# Sample Outputs

## Generated Files

```text
highlight_reel.mp4
clip_scores_timeline.png
sample_frames.png
clip_vs_gt.png
```

---

# Technologies Used

## Deep Learning / AI
- PyTorch
- HuggingFace Transformers
- CLIP ViT-B/32

## Video Processing
- OpenCV
- MoviePy

## Data Processing
- NumPy
- SciPy
- Matplotlib

## Platform
- Kaggle P100 GPU
- Google Colab

---

# Installation

## Clone Repository

```bash
git clone https://github.com/yourusername/video-highlight-generator.git
cd video-highlight-generator
```

---

## Install Dependencies

```bash
pip install torch torchvision transformers
pip install moviepy opencv-python
pip install matplotlib scipy pillow
pip install yt-dlp
```

---

# Running the Project

## Option 1 — TVSum Benchmark Evaluation

Run the notebook cells sequentially to:
- load TVSum
- extract frames
- score scenes
- generate highlights
- evaluate against human annotations

---

## Option 2 — Custom YouTube Video

Provide a YouTube link:

```python
CUSTOM_YOUTUBE_URL = "YOUR_YOUTUBE_LINK"
```

The pipeline will:
- download the video
- extract frames
- detect highlights
- generate a trailer automatically

---

# Folder Structure

```text
project/
│
├── tvsum_data/
├── tvsum_matlab/
├── tvsum_videos/
│
├── extracted_frames/
├── highlight_reel.mp4
├── sample_frames.png
├── clip_scores_timeline.png
├── clip_vs_gt.png
│
└── notebook.ipynb
```

---

# Evaluation

The project compares generated semantic importance scores against human annotations from TVSum50.

## Correlation Metrics

### Spearman Correlation
Measures ranking similarity between:
- CLIP semantic scores
- Human importance scores

### Kendall Tau
Measures pairwise agreement between rankings.

---

# Key Contributions

- Built a fully zero-shot video summarization pipeline
- Achieved meaningful alignment with human annotations
- Implemented semantic scene scoring using Vision Transformers
- Developed temporal highlight selection without finetuning
- Generated compact automatic highlight reels from long-form videos

---

# Future Improvements

- Audio-aware highlight scoring
- Whisper-based speech understanding
- Scene transition detection
- Reinforcement learning for summary optimization
- Multimodal LLM-based trailer narration
- Real-time streaming summarization

---

# Applications

- Automatic trailer generation
- Sports highlight generation
- Media content summarization
- Streaming platform previews
- Video recommendation systems
- Multimedia retrieval systems

---

# Acknowledgements

- OpenAI CLIP
- HuggingFace Transformers
- TVSum50 Dataset
- MoviePy
- OpenCV

---

# Author

Shaikh Saniya Ali, Vishal P
