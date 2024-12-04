# **⚽ Football Match Analysis**

## **📚 Table of Contents**

1. [📖 Project Overview](#project-overview)
2. [✨ Features](#features)
3. [📂 Project Structure](#project-structure)
4. [🚀 Getting Started](#getting-started)
5. [💡 Implementation Ideas](#implementation-ideas)
6. [📊 Metrics](#metrics)
7. [🛠️ Usage](#usage)
8. [🤝 Contributing](#contributing)
9. [🧑‍💻 Project By](#project-by)

---

## **📖 Project Overview**

This project leverages advanced computer vision techniques and the YOLO (You Only Look Once) object detection model to analyze football matches. It processes videos to:  
⚽ Detect players and the ball  
📍 Track movements and positions  
📊 Provide key metrics like player speed, distance covered, and team classifications.

---

## **✨ Features**

- **🔍 Player and Ball Detection**: Identifies players and the ball in each video frame.
- **📈 Tracking**: Maintains consistent IDs for objects throughout the match.
- **🎥 Camera Movement Estimation**: Stabilizes dynamic camera angles.
- **🔵 Team Assignment**: Classifies players by jersey color.
- **⚡ Speed & Distance Calculation**: Computes velocity and total distance covered.
- **📽️ Output Visualization**: Creates annotated videos showcasing the analysis.

---

## **📂 Project Structure**

Here's the modular folder structure for this project:

```plaintext
.
├── development_and_analysis/  # Jupyter notebooks for experimental analysis
│   └── color_assignment.ipynb
├── input_videos/              # Folder to store raw football videos
│   └── put_input_video_here.txt
├── models/                    # Stores pre-trained YOLO models
│   └── put_your_model.txt
├── output_videos/             # Contains processed videos and screenshots
│   ├── cropped_image.jpg
│   └── screenshot.png
├── player_ball_assigner/      # Assigns ball possession to players
│   ├── __init__.py
│   └── player_ball_assigner.py
├── speed_and_distance_estimator/  # Calculates speed and distance metrics
│   ├── __init__.py
│   └── speed_and_distance_estimator.py
├── stubs/                     # Testing data and stubs for the project
│   ├── camera_movement_stub.pkl
│   └── track_stubs.pkl
├── team_assigner/             # Classifies players into teams
│   ├── __init__.py
│   └── team_assigner.py
├── trackers/                  # Handles object tracking
│   ├── __init__.py
│   └── tracker.py
└── training/                  # Training YOLO or other models
```

---

## **📊 Datasets**

This project combines datasets to improve accuracy:  
| **Use Case** | **Dataset** |  
|-----------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
| Soccer Player Detection | [![Download Dataset](https://app.roboflow.com/images/download-dataset-badge.svg)](https://universe.roboflow.com/roboflow-jvuqo/football-players-detection-3zvbc) |

Additionally, a **manually annotated Kaggle dataset** was used to:  
✅ Improve model accuracy  
✅ Augment data for robust training

---

## **🚀 Getting Started**

### **1️⃣ Prerequisites**

- Python 3.8+
- A GPU (optional but speeds up processing)
- Libraries: OpenCV, PyTorch, NumPy, Matplotlib

### **2️⃣ Installation**

Clone the repository and install dependencies:

```bash
git clone https://github.com/AymenKtari01/Football-Match-Analysis-ComputerVision.git
cd Football-Match-Analysis-ComputerVision
pip install -r requirements.txt
```

### **3️⃣ Setup**

- Add raw videos to `input_videos/`.
- Place YOLO weights in `models/`.

### **4️⃣ Run**

Analyze a video with:

```bash
python main.py
```

---

## **💡 Implementation Ideas**

### **1. Object Detection**

- Use YOLO for player and ball detection.

### **2. Tracking**

- Implement tracking algorithms (e.g., SORT/DeepSORT).

### **3. Team Classification**

- Assign teams based on jersey colors.

### **4. Speed & Distance**

- Calculate distances and velocities from player trajectories.

### **5. Camera Movement Stabilization**

- Normalize camera shifts for improved analysis.

---

## **📊 Metrics**

- **🎯 Detection Precision**: Measure correct detections.
- **🏃 Tracking Accuracy**: Ensure consistent IDs.
- **⏳ Processing Time**: Optimize analysis speed.
- **📏 Metric Accuracy**: Validate calculations.

---

## **🛠️ Usage**

### **Player Detection & Tracking**

```bash
python trackers/tracker.py --input input_videos/match1.mp4 --output output_videos/result.mp4
```

### **Speed & Distance Estimation**

```bash
python speed_and_distance_estimator/speed_and_distance_estimator.py --input output_videos/result.mp4
```

### **Team Classification**

```bash
python team_assigner/team_assigner.py --input output_videos/result.mp4
```

---

## **🤝 Contributing**

🤗 Contributions are welcome!

1️⃣ Fork the repo  
2️⃣ Make your changes  
3️⃣ Submit a pull request

---

## **🧑‍💻 Project By**

<a href="https://github.com/AymenKtari01/Football-Match-Analysis-ComputerVision/graphs/contributors">
    <img src="https://contrib.rocks/image?repo=AymenKtari01/Football-Match-Analysis-ComputerVision" />
</a>

---
