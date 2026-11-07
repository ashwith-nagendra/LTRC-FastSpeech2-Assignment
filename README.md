# FastSpeech2-Based Text-to-Speech Synthesis for English and Telugu

## Overview

This repository contains the implementation of a **FastSpeech2-based Text-to-Speech (TTS)** system developed as part of the **Language Technologies Research Centre (LTRC), IIIT Hyderabad Assignment**.

The project extends the reference FastSpeech2 implementation to support both **English** and **Telugu** speech synthesis. It includes dataset preprocessing, forced alignment using Montreal Forced Aligner (MFA), model training, inference, and evaluation of synthesized speech.

---

## Features

- FastSpeech2 implementation for non-autoregressive speech synthesis
- English and Telugu language support
- Dataset preprocessing and feature extraction
- Montreal Forced Aligner (MFA) based alignment
- HiFi-GAN vocoder for waveform generation
- Telugu language customization
- Speech synthesis using trained checkpoints
- Generated audio samples and variance adaptor visualizations

---

## Project Structure

```text
LTRC-FastSpeech2-Assignment
│
├── English/
├── Telugu/
├── Results/
├── Report/
├── README.md
└── requirements.txt
```

---

## Technologies Used

- Python
- PyTorch
- FastSpeech2
- HiFi-GAN
- Montreal Forced Aligner (MFA)
- NumPy
- Librosa
- PyYAML
- Matplotlib

---

## Dataset

### English
- Dataset preparation
- Text preprocessing
- MFA alignment
- Feature extraction

### Telugu
- Dataset preparation
- Text preprocessing
- MFA alignment
- Mel spectrogram generation
- Pitch, Energy and Duration extraction
- Model training
- Speech synthesis

---

## Results

The repository contains:

- Generated Telugu speech samples
- Mel spectrogram images
- Variance adaptor visualizations
- Configuration files
- Source code
- Technical report

---

## Running the Project

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
python inference.py
```

---

## Repository Contents

- Source code for preprocessing, training and inference
- English and Telugu configuration files
- Generated speech samples
- Variance adaptor plots
- Technical report
- Project documentation

---

## References

1. FastSpeech2: Fast and High-Quality End-to-End Text-to-Speech (ICLR 2021)
2. HiFi-GAN Vocoder
3. Montreal Forced Aligner (MFA)
4. IndicTTS Dataset
5. Svarah Dataset

---

## Author

**Konda Ashwith Nagendra**

B.Tech Computer Science and Engineering (AI & ML)

Marri Laxman Reddy Institute of Technology and Management

Hyderabad, India

---

## Model Checkpoint

The trained Telugu model checkpoint (`100.pth.tar`) is not included in this repository because it exceeds GitHub's recommended file size.

Download the checkpoint from Google Drive:

**Google Drive:**  
https://drive.google.com/file/d/1V1mgNvwiOYD0ImAtDFazbInf9M5NoAOz/view?usp=sharing

After downloading, place the checkpoint in:

```text
Telugu/
└── checkpoints/
    └── 100.pth.tar
```

After placing the checkpoint, the inference script can be executed normally.
