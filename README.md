# 🔍 Image Denoising with Computer Vision

> Image restoration and denoising using advanced computer vision techniques and Markov Random Fields

![Python](https://img.shields.io/badge/Python-3.x-blue)
![OpenCV](https://img.shields.io/badge/OpenCV-4.x-orange)
![License](https://img.shields.io/badge/License-MIT-green)
![PSNR](https://img.shields.io/badge/PSNR-28--33dB-brightgreen)

---

## 📋 Overview

This project implements **image denoising and restoration** techniques using classical computer vision algorithms and probabilistic graphical models. The main objectives are:

| Task | Description |
|------|-------------|
| 🔍 Noise Characterization | Identify noise type (Gaussian, Salt-and-Pepper, Poisson) |
| 🧹 Spatial Filtering | Apply Gaussian and Median filters |
| ⚡ Adaptive Filtering | Implement Adaptive Wiener Filter |
| 🎯 MRF Model | Train Markov Random Field with ICM algorithm |
| 📊 Quality Assessment | Evaluate using MSE and PSNR metrics |

---

## 🏗️ Project Architecture

```
Original Images (gr7/Original/)
        │
        ▼
   Noise Analysis
   ├── Histogram Analysis
   └── Power Spectrum
        │
        ▼
   Denoising Pipeline
   ├── Gaussian Filter
   ├── Median Filter
   ├── Adaptive Wiener Filter
   └── MRF + ICM
        │
        ▼
   Quality Metrics
   ├── MSE
   └── PSNR
```

---

## ⚙️ Tech Stack

| Category | Library |
|----------|---------|
| **Image Processing** | OpenCV |
| **Numerical Operations** | NumPy |
| **Visualization** | Matplotlib |
| **Signal Processing** | SciPy |

---

## 📊 Results

| Noise Type | Best Filter | PSNR Range |
|------------|-------------|------------|
| Gaussian | Gaussian Filter | 28-32 dB |
| Salt-and-Pepper | Median Filter | 30-33 dB |
| Poisson | Adaptive Wiener | 28-31 dB |

### Quality Metrics

| Metric | Description |
|--------|-------------|
| **MSE** | Mean Squared Error between original and denoised |
| **PSNR** | Peak Signal-to-Noise Ratio (higher is better) |

---

## 🚀 Setup

### 1. Clone the repository

```bash
git clone https://github.com/StefoXCaffeine/ComputerVision-Denoising.git
cd ComputerVision-Denoising
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Dataset structure

```
gr7/
├── Original/          # 10 uncorrupted grayscale images
└── Noisy/             # 10 corresponding noise-corrupted images
```

### 4. Run the notebook

```bash
jupyter notebook DenoisingAssignment.ipynb
```

---

## 💡 Usage

### Noise Analysis

The project analyzes noise characteristics through:

1. **Histogram Analysis**: Examines intensity distribution to identify noise type
2. **Power Spectrum**: Analyzes frequency response patterns

### Denoising Methods

| Method | Best For | Parameters |
|--------|----------|------------|
| Gaussian Filter | Gaussian noise | kernel_size, sigma |
| Median Filter | Salt-and-Pepper | kernel_size |
| Adaptive Wiener | Mixed noise | window_size |
| MRF + ICM | Structural preservation | iterations, beta |

### Quality Evaluation

```python
# PSNR calculation
psnr = 20 * log10(max_val / sqrt(MSE))
```

---

## 📁 Main Files

| File | Description |
|------|-------------|
| `DenoisingAssignment.ipynb` | Complete pipeline with analysis and results |
| `README.md` | This documentation |
| `gr7/Original/` | Original uncorrupted images (10 files) |
| `gr7/Noisy/` | Noise-corrupted images (10 files) |

---

## 🔮 Key Algorithms

### 1. Histogram Analysis (`plotNoises`)
- Analyzes noise distribution in selected regions
- Calculates mean, variance, and salt/pepper density

### 2. Adaptive Wiener Filter
```
I'(x,y) = I(x,y) + α(x,y)[I(x,y) - μ(x,y)]
```

### 3. Markov Random Field (MRF)
- Probabilistic graphical model for spatial dependencies
- Data term: squared distance between pixels
- Data penalty: convolution-based regularization

### 4. Iterated Conditional Modes (ICM)
- Optimization algorithm for MRF training
- Iteratively updates pixel labels to maximize posterior probability

---

## 🔮 Future Improvements

- [ ] Implement Non-Local Means (NLM) denoising
- [ ] Add BM3D algorithm comparison
- [ ] Deep learning approaches (DnCNN, UNet)
- [ ] Batch processing for multiple images
- [ ] GUI for interactive parameter tuning

---

## 📜 License

MIT License - see `LICENSE` file for details.

---

## 👤 Author

**StefoXCaffeine**

- GitHub: [@StefoXCaffeine](https://github.com/StefoXCaffeine)
- LinkedIn: [linkedin.com/in/stefano-corrao](www.linkedin.com/in/stefano-corrao)

---

*⭐ If you find this project useful, leave a star!*
