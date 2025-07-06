# RainDistill

RainDistill refines ensemble rainfall forecasts through real-time bias correction.  
Powered by knowledge distillation, it delivers precision where forecasts fail.

---

## Overview

RainDistill is a real-time machine learning framework for bias correction of ensemble rainfall forecasts.  
By leveraging a teacher–student architecture (LSTM → XGBoost), it learns to emulate complex corrections using only real-time inputs, making it deployable even without observed data.

This project addresses the challenge of underestimation and bias in raw ensemble forecasts, especially during high-impact extreme events. RainDistill transforms these noisy predictions into accurate, actionable rainfall forecasts.

---

## Key Features

- Real-time bias correction of ensemble rainfall forecasts  
- Knowledge distillation using LSTM (teacher) and XGBoost (student)  
- Forecast-only inputs at inference time (no observed data needed)  
- Evaluation across full distribution and extremes (>90th/<10th percentile)  
- Spatial and temporal analysis: maps, skill metrics, and time series

---

## Methodology

RainDistill uses a two-stage distillation framework:

1. **Teacher Model**  
   - Trained using LSTM models (1 per lead time)  
   - Inputs: Forecast features + observed-derived features  
   - Outputs: Residuals between ensemble mean and observed rainfall  
   - Corrected Prediction = Ensemble Mean - Predicted Residual

2. **Student Model**  
   - XGBoost trained only on real-time forecast features  
   - Learns to mimic the teacher’s residual predictions  
   - Inference-time output:  
     `Distilled Prediction = Ensemble Mean - Distilled Residual`

---

## Forecast Dataset Availability

The ensemble forecast dataset used in this project is not included in the repository due to its large size and storage constraints.

Researchers or users who wish to access the data for replication or academic exploration may contact the contributor directly. Access may be granted upon request for non-commercial and research purposes.

Contact: manast2485@gmail.com
