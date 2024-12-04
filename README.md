# **Football-Match-Analysis**

## **Table of Contents**

1. [Project Overview](#project-overview)
2. [Features](#features)
3. [Project Structure](#project-structure)
4. [Getting Started](#getting-started)
5. [Implementation Ideas](#implementation-ideas)
6. [Metrics](#metrics)
7. [Usage](#usage)
8. [Contributing](#contributing)
9. [Project By](#projectby)

---

## **Project Overview**

This project uses advanced computer vision techniques and the YOLO (You Only Look Once) object detection model to analyze football games. By processing videos, the system identifies and tracks players, the ball, and movements, providing critical metrics such as player speed, distance covered, and team classification.

## **Features**

- **Player and Ball Detection**: Identify players and the ball in each video frame.
- **Tracking**: Track player and ball movements over time.
- **Camera Movement Estimation**: Handle dynamic camera angles and stabilize analysis.
- **Team Assignment**: Classify players into their respective teams based on jersey color.
- **Speed and Distance Calculation**: Measure player velocity and distance covered during the match.
- **Output Visualization**: Generate processed videos with overlays showing the tracked players, ball, and other annotations.

---

## **Project Structure**

The project follows a modular structure to simplify development and analysis.

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

## ⚽ Datasets

This project utilizes the following datasets for soccer player detection and model improvement:

| Use Case                | Dataset                                                                                                                                                          |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Soccer Player Detection | [![Download Dataset](https://app.roboflow.com/images/download-dataset-badge.svg)](https://universe.roboflow.com/roboflow-jvuqo/football-players-detection-3zvbc) |

In addition to the Roboflow dataset, I am also using a **Kaggle dataset**, which I annotated manually to enhance the model's performance and augment the training data. This combined approach helps to create a more robust and accurate detection model.

## **Getting Started**

Follow these steps to set up and run the project.

### **1. Prerequisites**

- Python 3.8 or higher
- A compatible GPU (optional but recommended for faster processing)
- Libraries: OpenCV, PyTorch, NumPy, Matplotlib

### **2. Installation**

Clone the repository and install the required dependencies:

```bash
git clone https://github.com/AymenKtari01/Football-Match-Analysis-ComputerVision.git
cd Football-Match-Analysis-ComputerVision
pip install -r requirements.txt
```

### **3. Setup**

- Place your raw input videos in the `input_videos` folder.
- Download pre-trained YOLO weights and place them in the `models` folder.
- Ensure that the `models` folder includes `best.pt` file of the YOLOv8 model.

### **4. Run the Project**

Start analyzing a video by running the main script:

```bash
python main.py
```

---

## **Implementation Ideas**

1. **Object Detection with YOLO**

   - Load YOLO weights to detect players and the ball.
   - Use bounding boxes to locate each object in every frame.

2. **Tracking**

   - Implement a tracker (e.g., SORT or DeepSORT) to maintain consistent IDs for players and the ball across frames.

3. **Team Assignment**

   - Use color analysis from `color_assignment.ipynb` to classify players into their teams.

4. **Speed and Distance Estimation**

   - Calculate the Euclidean distance between player positions in consecutive frames.
   - Convert frame distance to real-world distance using the frame rate and field dimensions.

5. **Camera Movement Stabilization**

   - Use the `camera_movement_estimator.py` to normalize camera shifts and improve tracking accuracy.

6. **Output Videos**
   - Annotate frames with bounding boxes, player IDs, ball positions, and other metrics.

---

## **Metrics**

- **Detection Precision**: Percentage of correctly identified players and balls.
- **Tracking Accuracy**: Accuracy of maintaining consistent object IDs across frames.
- **Processing Time**: Time required to process a video.
- **Speed/Distance Accuracy**: Comparison of calculated metrics with ground truth data.

---

## **Usage**

### **Player Detection and Tracking**

Run the tracker on an input video:

```bash
python trackers/tracker.py --input input_videos/match1.mp4 --output output_videos/result.mp4
```

### **Speed and Distance Estimation**

Calculate metrics for players in a video:

```bash
python speed_and_distance_estimator/speed_and_distance_estimator.py --input output_videos/result.mp4
```

### **Team Classification**

Classify players into teams based on colors:

```bash
python team_assigner/team_assigner.py --input output_videos/result.mp4
```

---

## **Contributing**

We welcome contributions to improve the project.

- Fork the repository and make your changes.
- Submit a pull request with a detailed description of your modifications.

## Project By

<a href="https://github.com/AymenKtari01/Football-Match-Analysis-ComputerVision/graphs/contributors">
    <img src="https://contrib.rocks/image?repo=AymenKtari01/Football-Match-Analysis-ComputerVision" />
</a>
