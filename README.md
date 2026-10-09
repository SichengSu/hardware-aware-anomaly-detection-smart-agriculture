# Is Low-Pass Pre-Filtering a Free Lunch?
Trade-offs and Noise-Aware Conformal Calibration in Reconstruction-Based Sensor Anomaly Detection
> Author: Sicheng Su | Electronic Engineering, King's College London

## Project Overview
Applying a low-pass filter (e.g., Butterworth IIR or moving average) in front of edge anomaly detectors is a standard engineering heuristic to suppress transient hardware and circuit noise. However, low-pass filtering cannot distinguish noise from signal by origin—it attenuates by frequency. Short transient events (often critical anomalies) are high-frequency signals that get smeared, delayed, or removed entirely.

Key Results (consistent with manuscript):
- Raw Signal (No Filter + AE): FAR = 97.90%, Recall = 100.00%, AUPRC = 1.000, Latency = 0.0 samples
- Moving Average Filter (L = 9): FAR = 46.50%, Recall = 96.70%, AUPRC = 0.915, Latency = 4.0 samples
- 4th-order Causal Butterworth: FAR = 12.00%, Recall = 83.30%, AUPRC = 0.729, Latency = 6.3 samples
- Noise-Aware Conformal Calibration (NACC): FAR = 5.70%, Recall = 100.00%, AUPRC = 0.993, Latency = 0.0 samples

## Manuscript
Unpublished technical report formatted in IEEE conference template.
- PDF: [`paper/manuscript.pdf`](paper/manuscript.pdf)
- LaTeX source: [`paper/ieee_source/`](paper/ieee_source/)

## Repository Structure
- `main_experiment.ipynb`: Full reproducible experiment code. Contains data loading, Butterworth low-pass filtering, PyTorch autoencoder model, fault injection, ablation studies and all visualization plots.
- `paper/manuscript.pdf`: Unpublished IEEE-style technical report
- `requirements.txt`: Python environment dependencies

## Environment & Dependencies
Python >=3.9
```bash
pip install -r requirements.txt
