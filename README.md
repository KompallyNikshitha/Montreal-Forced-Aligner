# 🎧 Montreal Forced Aligner (MFA) Assignment

## 📌 Project Overview

This project demonstrates the use of **Montreal Forced Aligner (MFA)** for automatic speech-text alignment. The objective is to align audio recordings with their corresponding transcripts and generate **Praat TextGrid** files containing word-level and phoneme-level timestamps.

The project uses audio and transcript files from the **ISLE corpus** and **F2BJRLP** datasets.

---

## 🎯 Objective

To perform forced alignment between speech recordings and text transcripts using Montreal Forced Aligner and analyze the generated alignments.

---

## 🧠 What is Forced Alignment?

Forced alignment is the process of synchronizing spoken audio with its written transcript. It automatically determines the start and end times of words and phonemes within an audio recording.

### Example

**Audio:**
HELLO WORLD

**Transcript:**
HELLO WORLD

**Alignment Output:**

| Phoneme | Time Interval |
| ------- | ------------- |
| HH      | 0.00 – 0.10   |
| AH      | 0.10 – 0.25   |
| L       | 0.25 – 0.40   |
| OW      | 0.40 – 0.55   |
| W       | 0.55 – 0.65   |
| ER      | 0.65 – 0.80   |
| L       | 0.80 – 0.90   |
| D       | 0.90 – 1.00   |

---

## 📂 Repository Structure

```text
.
├── corpus/
│   ├── F2BJRLP1.wav
│   ├── F2BJRLP1.TXT
│   ├── F2BJRLP2.wav
│   ├── F2BJRLP2.TXT
│   ├── F2BJRLP3.wav
│   ├── F2BJRLP3.TXT
│   ├── ISLE_SESS0131_BLOCKD02_01_sprt1.wav
│   ├── ISLE_SESS0131_BLOCKD02_01_sprt1.txt
│   ├── ISLE_SESS0131_BLOCKD02_02_sprt1.wav
│   ├── ISLE_SESS0131_BLOCKD02_02_sprt1.txt
│   ├── ISLE_SESS0131_BLOCKD02_03_sprt1.wav
│   └── ISLE_SESS0131_BLOCKD02_03_sprt1.txt
│
├── output/
│   ├── F2BJRLP1.TextGrid
│   ├── F2BJRLP2.TextGrid
│   ├── F2BJRLP3.TextGrid
│   ├── ISLE_SESS0131_BLOCKD02_01_sprt1.TextGrid
│   ├── ISLE_SESS0131_BLOCKD02_02_sprt1.TextGrid
│   ├── ISLE_SESS0131_BLOCKD02_03_sprt1.TextGrid
│   └── alignment_analysis.csv
│
├── Assignment1.pdf
├── reportiiit.pdf
└── README.md
```

---

## ⚙️ Tools and Technologies

* Montreal Forced Aligner (MFA)
* Praat
* Python
* Git & GitHub
* Windows / Ubuntu (WSL)

---

## 🧩 Installation

### Create Environment

```bash
conda create -n mfa_env python=3.10 -y
conda activate mfa_env
```

### Install MFA

```bash
pip install montreal-forced-aligner
```

### Install Dependencies

```bash
sudo apt-get update
sudo apt-get install -y praat dos2unix
```

---

## 🧠 Model Preparation

Download the required dictionary and acoustic model:

```bash
mfa model download dictionary english_us_arpa
mfa model download acoustic english_us_arpa
```

---

## 🔍 Validate Corpus

```bash
mfa validate corpus english_us_arpa
```

or

```bash
mfa validate corpus custom.dict
```

---

## 🎯 Run Alignment

Using default dictionary:

```bash
mfa align corpus english_us_arpa english_us_arpa output --overwrite --num_jobs 4
```

Using custom dictionary:

```bash
mfa align corpus custom.dict english_us_arpa output --overwrite --num_jobs 4
```

---

## 📊 Results

The alignment process successfully generated TextGrid files for all audio samples.

| Audio File                          | Output                                   |
| ----------------------------------- | ---------------------------------------- |
| F2BJRLP1.wav                        | F2BJRLP1.TextGrid                        |
| F2BJRLP2.wav                        | F2BJRLP2.TextGrid                        |
| F2BJRLP3.wav                        | F2BJRLP3.TextGrid                        |
| ISLE_SESS0131_BLOCKD02_01_sprt1.wav | ISLE_SESS0131_BLOCKD02_01_sprt1.TextGrid |
| ISLE_SESS0131_BLOCKD02_02_sprt1.wav | ISLE_SESS0131_BLOCKD02_02_sprt1.TextGrid |
| ISLE_SESS0131_BLOCKD02_03_sprt1.wav | ISLE_SESS0131_BLOCKD02_03_sprt1.TextGrid |

Additional analysis results are available in:

```text
output/alignment_analysis.csv
```

---

## 📄 Reports

* Assignment1.pdf
* reportiiit.pdf

These documents contain methodology, implementation details, observations, and analysis of the alignment results.

---

## 👩‍💻 Author

**Kompally Nikshitha**

GitHub: https://github.com/KompallyNikshitha

---

## ⭐ Acknowledgements

* Montreal Forced Aligner (MFA)
* Praat
* ISLE Speech Corpus
* Carnegie Mellon University Speech Tools
