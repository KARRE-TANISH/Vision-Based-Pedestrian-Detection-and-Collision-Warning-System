# Vision-Based Pedestrian Detection and Collision Warning System

##  Project Overview

The **Vision-Based Pedestrian Detection and Collision Warning System** is a computer-vision-based safety prototype that detects pedestrians using a camera and provides a warning when a detected pedestrian appears to be relatively close to the camera.

The system uses **Python, OpenCV, and YOLOv8** to process live camera frames, detect pedestrians, display bounding boxes, and generate visual and audio warnings.

This project demonstrates a software-level concept inspired by **Advanced Driver Assistance Systems (ADAS)**.

> **Note:** This is an academic prototype and is not intended to replace a production vehicle safety system.

---

##  Objectives

- Detect pedestrians using a live camera feed.
- Process camera frames using computer vision.
- Identify pedestrians using YOLOv8.
- Display bounding boxes around detected pedestrians.
- Use detection confidence to filter unreliable detections.
- Estimate relative proximity using the detected pedestrian's bounding-box area.
- Generate visual and audio warnings when a pedestrian is considered close.

---

##  Technologies Used

- **Python**
- **OpenCV**
- **YOLOv8**
- **Ultralytics**
- **Computer Vision**
- **Windows `winsound`**

---

##  How the System Works

The system follows these steps:

1. The webcam captures a live video frame.
2. OpenCV reads and resizes the frame.
3. The frame is passed to the YOLOv8 model.
4. YOLOv8 detects objects present in the frame.
5. The system checks for the **person class**.
6. Detections with confidence below **70%** are ignored.
7. A bounding box is drawn around detected pedestrians.
8. The bounding-box area is calculated.
9. If the detected pedestrian's bounding-box area is greater than **2000**, the system considers the pedestrian to be relatively close.
10. A visual warning and audio beep are generated.

### Project Workflow

```text
Camera
  ↓
Capture Frame
  ↓
OpenCV Processing
  ↓
YOLOv8 Detection
  ↓
Person Detected?
  ├── No → Continue
  │
  └── Yes
        ↓
   Confidence > 70%?
      ├── No → Ignore
      │
      └── Yes
            ↓
       Bounding Box
            ↓
       Calculate Area
            ↓
        Area > 2000?
          ├── No → Continue
          │
          └── Yes
                ↓
          Warning Alert
          ↓           ↓
      Visual       Audio
