# Open-Field Behavioral Analysis Using DeepLabCut

This project demonstrates a basic computational workflow for quantitative behavioral analysis in a rodent open-field experiment using DeepLabCut-based pose estimation.

The pipeline combines pose tracking, locomotion quantification, and spatial analysis to extract interpretable behavioral metrics from video recordings.

---

## Project Overview

Behavioral neuroscience experiments often rely on manual observation and scoring, which can be time-consuming, subjective, and difficult to scale. Recent advances in pose-estimation frameworks such as DeepLabCut enable automated extraction of animal movement trajectories and body-part coordinates with high temporal resolution.

In this demo project, DeepLabCut outputs were used to perform downstream behavioral analysis including:

- Trajectory visualization
- Total distance traveled
- Velocity estimation
- Spatial occupancy heatmap generation

The project was implemented using Python, DeepLabCut, NumPy, pandas, SciPy, and Matplotlib.

---

## Workflow

### 1. Pose Estimation with DeepLabCut
A pretrained ResNet-50 backbone was used to track body-part coordinates from an open-field mouse video.

Pipeline stages included:

- Frame extraction and labeling
- Training dataset generation
- Network training and evaluation
- Video inference and labeled video generation

---

### 2. Coordinate Extraction
DeepLabCut output CSV files were parsed to extract:

- X coordinates
- Y coordinates
- Likelihood/confidence values

for selected body parts across video frames.

---

### 3. Behavioral Quantification

The extracted coordinates were used for:

#### Trajectory Analysis
Visualization of locomotion patterns and spatial exploration.

#### Distance Traveled
Frame-by-frame Euclidean displacement calculation to estimate total locomotion.

#### Velocity Estimation
Trajectory smoothing using Gaussian filtering followed by velocity calculation in pixels/second.

#### Spatial Occupancy Heatmap
Generation of heatmaps representing time spent across different regions of the arena.

---

## Example Outputs

### Mouse Trajectory
- Exploration path visualization
- Start and end position identification

### Velocity Profile
- Smoothed locomotion dynamics over time
- Mean and peak velocity estimation

### Spatial Heatmap
- Spatial occupancy distribution
- Identification of preferred exploration zones

---

## Repository Structure

```text
OpenField-Behavior-Analysis-DLC/
│
├── notebooks/
│   ├── DLC_pipeline.ipynb
│   └── behavioral_analysis.ipynb
│
├── figures/
│   ├── Mouse Trajectory.png
│   ├── Movement Velocity.png
│   └── Spatial Heatmap.png
│
├── Coordinates.csv
│
├── requirements.txt
│
└── README.md
