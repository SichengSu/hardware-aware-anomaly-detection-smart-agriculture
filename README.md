# Hardware-Aware Hybrid Anomaly Detection in Smart Agriculture
Combining Butterworth Signal Filtering with PyTorch Autoencoders for IoT edge sensor anomaly detection.
> Author: Sicheng Su | Electronic Engineering, King's College London

## Project Overview
Field-deployed agricultural IoT sensors suffer high false alarm rates from circuit thermal noise and contact instability. This work proposes a hybrid pipeline: classical 4th/8th-order Butterworth low-pass filtering for signal preprocessing, followed by an unsupervised bottleneck Autoencoder for time-series anomaly detection.

Controlled fault-injection experiments are built on the Numenta Anomaly Benchmark (NAB) sensor dataset. We quantify the tradeoff between filter parameters, false alarm rate and computational cost via systematic ablation studies.

Key Results (consistent with manuscript):
- Baseline (raw signal, no filter): FAR = 100.00%, event detection rate = 100%
- 4th-order Butterworth (0.05 Hz cutoff): FAR reduced to 61.55%
- 8th-order Butterworth (0.05 Hz cutoff): FAR reduced to 48.47%
- All tested configurations retain 100% detection sensitivity for wildlife intrusion transients

## Manuscript
Unpublished technical report formatted in IEEE conference template.
- PDF: [`paper/manuscript.pdf`](paper/manuscript.pdf)
- LaTeX source: [`paper/ieee_source/`](paper/ieee_source/)

## Repository Structure
- `src/`: Core Python implementation (filtering, PyTorch autoencoder, fault injection)
- `experiments/`: Scripts for main experiment and ablation studies
- `paper/`: IEEE-formatted manuscript, figures and LaTeX source

## Environment & Dependencies
Python >=3.9
```bash
pip install -r requirements.txt
