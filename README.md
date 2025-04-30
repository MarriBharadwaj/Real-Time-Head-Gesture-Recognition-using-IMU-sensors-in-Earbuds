## IMU Earable: Real-Time Head Gesture Recognition using Earbuds

This repository presents a full machine learning pipeline for **real-time head gesture recognition** using **Inertial Measurement Unit (IMU)** data from wireless earbuds. By combining **signal processing**, **feature engineering**, and **advanced classification models**, we accurately classify facial and head gestures performed by 29 individuals.

> *Project by Marri Bharadwaj (B21CS045)  
Mentors: Dr. Suchetana Chakraborty, Mr. Garvit Chugh*

---

### Objectives

- **Activity Classification**: Classify head/facial gestures using IMU sensor data from earbuds.
- **Feature Engineering**: Extract over 160 time- and frequency-domain features to capture motion characteristics.
- **Model Comparison**: Evaluate multiple classifiers (LightGBM, XGBoost, ExtraTrees, Random Forest, and Voting Ensemble).
- **Real-time Compatibility**: Maintain lightweight, efficient computation suitable for wearable devices.

---

### Repository Contents

| File | Description |
|------|-------------|
| `IMU_Earable_Main.ipynb` | Final notebook with best model (window size = 4s, step = 2s) |
| `IMU_Earable_Window2_Step1.ipynb` | Experiment with finer granularity (window = 2s, step = 1s) |
| `IMU_Earable_Window5_Step3.ipynb` | Experiment with wider context (window = 5s, step = 3s) |
| `IMU_Earable_Presentation.pptx` | Project presentation summarizing methodology, results, and key insights |

---

### Feature Engineering

A total of **162 features** were extracted from each IMU windowed segment, including:

- **Time-Domain**: Mean, Std, Min/Max, Range, Skew, Kurtosis, Energy, Peaks, Troughs, Zero-crossings
- **Frequency-Domain**: FFT energy, dominant frequency (FFT peak), spectral entropy
- **Motion Dynamics**: Jerk statistics (mean, max, std)
- **Magnitude-Based**: Combined `acc_mag` and `gyro_mag` features
- **Cross-Correlation**: Between axes (e.g., `ax` & `ay`, `gy` & `gz`)

---

### Results

| Model | Accuracy | Macro F1 | Notes |
|-------|----------|----------|-------|
| **Voting Classifier** | **92.90%** | 0.93 | Best overall performance |
| LightGBM | 92.08% | 0.92 | Strong baseline |
| XGBoost | 91.30% | 0.91 | Competitive |
| ExtraTrees | 91.49% | 0.92 | Consistent and robust |
| Random Forest | 89.88% | 0.90 | Lower but stable |

3-Fold CV Mean Accuracy: **91.97%**  
Std. Deviation across folds: **0.0003**  
➡*Very high reliability and generalizability*

---

### Hyperparameter Tuning

Tested 3 segmentation strategies:
- **Window=2s, Step=1s** → More granular, but lower performance
- **Window=4s, Step=2s** *Best balance between detail and stability*
- **Window=5s, Step=3s** → Wider context but slight drop in accuracy

---

### References

- Ferlini et al., *EarSet: A Multi-Modal In-Ear Dataset*, Zenodo, 2023  
- IMUPoser (CHI 2023): Full-body pose estimation using IMUs in earbuds and wearables

---

### Acknowledgments

Special thanks to my mentors and the UbiSys Lab for guidance and feedback throughout this project.

---
