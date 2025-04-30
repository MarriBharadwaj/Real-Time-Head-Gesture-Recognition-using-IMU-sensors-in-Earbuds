---

## Real-Time Head Gesture Recognition using IMU Sensors in Earbuds

This repository contains feature engineering and signal processing pipelines for extracting meaningful features from IMU data collected via wearable earables. The primary goal is to enable accurate classification and analysis of head movements using filtered sensor data (accelerometer and gyroscope).

---

### Main Notebook

- `IMU_Earable_Main.ipynb`  
  → This notebook implements the complete pipeline using the optimal hyperparameters:  
  **Window Size = 4**, **Step Size = 2**

---

### Hyperparameter Tuning Experiments

- `IMU_Earable_Window2_Step1.ipynb`  
  → Experiment with smaller window and step size  
- `IMU_Earable_Window5_Step3.ipynb`  
  → Experiment with larger window and step size  

These experiments were run in parallel to evaluate the impact of different temporal resolutions on model performance.

---

### Presentation

- `IMU_Earable_Presentation.pptx`
  → Slide deck used during the project presentation summarizing the methodology, feature engineering, and classification results.

---

### ✅ Results

The optimal configuration (Window = 4, Step = 2) achieved the best balance between temporal sensitivity and signal stability, leading to improved performance in downstream classification.

---

Let me know if you want a badge-style header or visuals added too — happy to help with that!
