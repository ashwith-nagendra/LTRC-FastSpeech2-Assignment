# FastSpeech2-Based Text-to-Speech Synthesis for English and Telugu

## Overview

This repository contains the implementation of the **FastSpeech2 Text-to-Speech (TTS)** system developed as part of the **LTRC (Language Technologies Research Centre), IIIT Hyderabad Assignment**.

The project is based on the official FastSpeech2 implementation and has been adapted to support **English** and **Telugu** speech synthesis. The work includes dataset preprocessing, Montreal Forced Aligner (MFA) based forced alignment, model training, inference, and evaluation of synthesized speech.

---

## Objectives

The primary objectives of this project are:

- Implement the FastSpeech2 architecture.
- Prepare English and Telugu speech datasets.
- Generate TextGrid alignments using Montreal Forced Aligner.
- Train FastSpeech2 models for both languages.
- Generate speech samples for the provided evaluation sentences.
- Analyse duration, pitch, and energy predictions produced by the Variance Adaptor.
- Document implementation details and experimental observations.

---

# FastSpeech2 Architecture

FastSpeech2 is a non-autoregressive Text-to-Speech model that directly predicts mel-spectrograms from text.

The architecture consists of:

- Text Encoder
- Variance Adaptor
  - Duration Predictor
  - Pitch Predictor
  - Energy Predictor
- Decoder
- Mel Spectrogram Generator
- HiFi-GAN Vocoder

Unlike autoregressive models such as Tacotron2, FastSpeech2 enables significantly faster inference while maintaining high-quality synthesized speech.

---

# Project Structure

```
LTRC-FastSpeech2-Assignment/
│
├── English/
│   ├── train.py
│   ├── preprocess.py
│   ├── inference.py
│   ├── config/
│   └── checkpoints/
│
├── Telugu/
│   ├── train.py
│   ├── preprocess.py
│   ├── inference.py
│   ├── config/
│   └── checkpoints/
│       └──100.pth.tar
│
├── Results/
│   ├── English/
│   │   ├── test_generated_audios/
│   │   └── variance_adaptor_plots/
│   │       ├── duration/
│   │       ├── pitch/
│   │       └── energy/
│   │
│   └── Telugu/
│       ├── test_generated_audios/
│       └── variance_adaptor_plots/
│           ├── duration/
│           ├── pitch/
│           └── energy/
│
├── Report/
│   └── Technical_Report.pdf
│
├── README.md
│
└── requirements.txt
```

---

# Datasets

## English

**Dataset:** Svarah

Completed work:

- Dataset preparation
- Text normalization
- MFA alignment
- TextGrid generation
- Feature extraction
- Configuration setup

---

## Telugu

**Dataset:** IndicTTS Telugu

Completed work:

- Dataset preparation
- Montreal Forced Aligner
- TextGrid generation
- Mel-spectrogram extraction
- Pitch extraction
- Energy extraction
- Duration extraction
- FastSpeech2 training
- Speech synthesis

---

# Data Preprocessing

The preprocessing pipeline performs the following operations:

- Audio normalization
- Text cleaning
- Forced alignment using Montreal Forced Aligner
- Mel Spectrogram extraction
- Pitch extraction
- Energy extraction
- Duration extraction
- Metadata generation

The Telugu implementation additionally includes:

- Telugu text cleaner
- Telugu symbol support
- Telugu preprocessing configuration
- Telugu inference support

---

# Model Configuration

| Parameter | Value |
|-----------|---------|
| Model | FastSpeech2 |
| Vocoder | HiFi-GAN |
| Sampling Rate | 22050 Hz |
| Mel Channels | 80 |
| Batch Size | 16 |
| Encoder Hidden Size | 256 |
| Decoder Hidden Size | 256 |
| Transformer Encoder Layers | 4 |
| Transformer Decoder Layers | 6 |
| Optimizer | Adam |
| Training Steps | 100 |

---

# Training

The Telugu model was trained using the configured FastSpeech2 architecture.

Training observations:

- Training loss decreased consistently.
- Validation loss also showed steady improvement.
- Model convergence was observed within the limited training steps.

Checkpoint generated:

```
100.pth.tar
```

---

# Inference

Speech synthesis was performed using the trained Telugu checkpoint.

Generated outputs include:

- WAV audio
- Mel spectrogram visualization
- Variance Adaptor plots

---

# Results

The repository contains:

### Telugu

- Trained checkpoint
- Generated speech samples
- Mel spectrogram images
- Training loss
- Validation loss
- Variance adaptor outputs

### English

The English preprocessing pipeline, TextGrid generation, and dataset preparation were successfully completed.

Due to limited computational resources and the assignment deadline, the English model training could not be completed. However, all preprocessing steps and configuration files required for training are included.

---

# Modifications Performed

Compared to the original FastSpeech2 implementation, the following modifications were made:

- Added Telugu language support.
- Implemented Telugu text cleaner.
- Extended the symbol set for Telugu Unicode characters.
- Added Telugu preprocessing configuration.
- Updated inference pipeline for Telugu.
- Generated Telugu TextGrid alignments using Montreal Forced Aligner.
- Configured Telugu-specific preprocessing pipeline.
- Trained Telugu FastSpeech2 model.
- Generated synthesized Telugu speech.

---

# Requirements

The project was developed using:

- Python 3.11
- PyTorch
- NumPy
- SciPy
- Librosa
- PyYAML
- Montreal Forced Aligner
- HiFi-GAN
- g2p_en
- pypinyin
- matplotlib
- tqdm

Install dependencies using:

```bash
pip install -r requirements.txt
```

---

# Running the Project

### Preprocessing

```bash
python preprocess.py
```

### Training

```bash
python train.py
```

### Inference

```bash
python synthesize.py
```

---

# Experimental Observations

- FastSpeech2 enables significantly faster inference than autoregressive TTS models.
- Telugu synthesis demonstrated reasonable pronunciation for most words after limited training.
- Some long and numerically rich sentences require additional training for improved naturalness.
- Increasing the number of training steps is expected to improve speech quality.

---

# Limitations

- English model training could not be completed within the available computational resources.
- Telugu training was performed for a limited number of steps.
- Certain long Telugu sentences exhibited pronunciation inaccuracies.
- Further training would improve overall speech naturalness.

---

# Future Work

Possible improvements include:

- Train both language models using the complete datasets.
- Increase training duration.
- Improve pronunciation of complex Telugu words.
- Support multilingual synthesis.
- Incorporate speaker adaptation.
- Evaluate using objective metrics such as MOS and MCD.

---

# References

1. Ren, Y., Hu, C., Qin, T., Zhao, S., Zhao, Z., & Liu, T.-Y. (2021). **FastSpeech2: Fast and High-Quality End-to-End Text-to-Speech.** ICLR 2021.

2. FastSpeech2 Official GitHub Repository

3. Montreal Forced Aligner Documentation

4. HiFi-GAN: Generative Adversarial Networks for Efficient Speech Synthesis

5. IndicTTS Dataset

6. Svarah Dataset

---

# Author

**Konda Ashwith Nagendra**

B.Tech Computer Science and Engineering (Artificial Intelligence & Machine Learning)

Marri Laxman Reddy Institute of Technology and Management

Hyderabad, India

---

**Assignment:** FastSpeech2-Based Text-to-Speech Synthesis

**Organization:** Language Technologies Research Centre (LTRC), IIIT Hyderabad

**Year:** 2026