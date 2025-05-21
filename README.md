#  Real-Time Traffic Congestion Detection and Signal Adjustment  
### Project: [TraffixAI](https://github.com/StellarSolutions5/Real-Time-Traffic-Congestion-Detection-and-Signal-Adjustment/projects?query=is%3Aopen)
### Organization: [StellarSolutions5](https://github.com/StellarSolutions5)

---

## Table of Contents  
- [Overview](#overview)
- [Dataset](#dataset)
- [Problem Statement](#problem-statement)
- [Approach](#approach)
- [Results](#results)
- [Future Scope](#future-scope)
- [How to Run](#how-to-run)
- [Project Structure](#project-structure)
- [Demo](#demo)
- [Authors](#authors)

---

## Overview

**TraffixAI** is an AI-powered solution designed to dynamically manage urban traffic by detecting vehicle density and adjusting signal timings in real-time using computer vision and machine learning.

- Real-time detection of vehicle types using **YOLOv5**
- Dynamic signal adjustment using **SVR**, **Decision Tree**, and **Linear Regression**
- Interactive traffic management interface built with **PyQt5**

The project aims to modernize urban traffic control for better efficiency, reduced congestion, and improved commuter experience.

---

## Dataset

> **Note:** Due to privacy concerns, the original video footage cannot be open-sourced.

- **Source:** CCTV camera feeds from major traffic intersections in **Nagpur**, provided by **Nagpur Municipal Corporation (NMC)** and **Traffic Police Commission**
- **Type:** Video footage processed into structured datasets
- **Formats Supported:** Live or recorded feeds from 3-way, 4-way, 6-way, and 8-way intersections

**Vehicle Categories Detected:**
- **Light Vehicles (LV):** Cars, SUVs  
- **Heavy Vehicles (HV):** Buses, Trucks  
- **Two-Wheelers:** Bikes, Scooters

---

## Problem Statement

Traditional traffic signals with fixed timers do not adapt to real-time congestion, leading to inefficiencies such as:

- Prolonged waiting times  
- Increased emissions and fuel use  
- Traffic bottlenecks during peak hours

**TraffixAI** aims to solve this by building a system that:

- Counts vehicles in real-time using object detection  
- Predicts optimal green light duration using ML models  
- Provides a user-friendly GUI for traffic management

---

## Approach

### 1. Vehicle Detection (YOLOv5)
- Uses `yolov5s.pt` pre-trained weights
- Detects LV, HV, and Two-Wheelers
- Fast, accurate, and real-time frame processing

### 2. Signal Timing Prediction
- Models Used:
  - Linear Regression
  - Support Vector Regression (`svr_model.pkl`)
  - Decision Tree Regression (`decision_tree_model.pkl`)
- Scalers for Normalization:
  - `scaler_X.pkl` for input features
  - `scaler_y.pkl` for output labels

### 3. Graphical Interface (PyQt5)
- Live camera feed display
- Countdown timers for each lane
- Dropdown to select junction types (3-way to 8-way)
- Manual override option for emergency control

---

## Results

### Detection Accuracy
- Light Vehicles: **~98%**
- Heavy Vehicles & Two-Wheelers: **~95%**

### 🔍 Model Performance

| Model               | MSE     | MAE     | R² Score |
|--------------------|---------|---------|----------|
| Linear Regression  | 1.0673  | **0.3409**  | **0.9904** |
| SVR                | 1.6544  | 0.5509  | 0.9901 |
| Decision Tree      | **0.9682** | 1.635   | 0.9682 |

> 📌 **Support Vector Regression** was selected as the best performing model.

### Impact
- Reduced congestion by **~20%** in controlled trials
- Real-time adaptability led to **shorter idle times** and **efficient flow**

---

## Future Scope

- Upgrade to **YOLOv8/YOLOv10** for better detection under low visibility
- Introduce **Reinforcement Learning** for self-improving signal predictions
- Expand to **multi-intersection synchronization**
- Add **pedestrian and cyclist detection** for inclusive road safety
- Incorporate **ambulance and emergency vehicle prioritization** using real-time detection and preemption logic to ensure faster passage during emergencies shorter

---

## How to Run

```bash
# Step 1: Install dependencies
pip install -r requirements.txt

# Step 2: Launch the application
python app/main_app.py
```

Requires: Python 3.8+, PyQt5, OpenCV, scikit-learn, YOLOv5

---

## Project Structure
```bash
Real-Time Traffic Congestion Detection and Signal Adjustment/
├── app/
│   └── main_app.py
├── assets/
│   └── traffic_demo.gif
├── data/
│   └── traffic_dataset.csv
├── junction_layouts/
│   ├── 3-way.png
│   ├── 4-way.png
│   ├── 6-way.png
│   └── 8-way.png
├── models/
│   ├── yolov5s.pt
│   ├── decision_tree_model.pkl
│   ├── svr_model.pkl
│   ├── scaler_X.pkl
│   ├── scaler_y.pkl
│   └── traffic_predictor.ipynb
├── ui/
│   ├── traffic_ui.ui
│   └── traffic_ui_controller.py
├── vehicle_counter.py
└── requirements.txt


```
---

## Demo

Due to data privacy agreements, the full CCTV-based system cannot be open-sourced. However, a working demo of the prototype is shown below.

![Traffic Demo](./assets/traffic_demo.gif)

---

## Authors

- [Zainab Khan](https://github.com/ZainabKhan9)
    
- [Mayuri Lakhotia](https://github.com/iMayuriLakhotia)
    
- [Anuja Vaidya](https://github.com/AnujaVaidya15)
  
- [Parul Nakhate](https://github.com/ParulNakhate1)
    
- [Sakshi Kubitkar](https://github.com/Sakshisk22)	

---

For collaborations or demos, feel free to connect!


