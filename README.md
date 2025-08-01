# EO/IR Target Recognition & Classification Platform

[![Framework-Streamlit-red](https://img.shields.io/badge/Framework-Streamlit-red.svg)](https://streamlit.io)
[![Python-3.9+-blue](https://img.shields.io/badge/Python-3.9%2B-blue.svg)](https://www.python.org/)
[![Model-YOLOv5-blueviolet](https://img.shields.io/badge/Model-YOLOv5-blueviolet.svg)](https://github.com/ultralytics/yolov5)

A multi-modal Streamlit application for identifying and classifying objects in Electro-Optical (EO) and Infrared (IR) sensor data using the YOLOv5 object detection model.

## 🎯 Key Features

* **Multi-Modal Analysis:** Process standard videos, live webcam feeds, and batches of thermal images.
* **Offline Video Processing:** Upload a video file (`.mp4`, `.mov`, etc.), and the app will:
    1.  Extract frames at a set interval.
    2.  Run object detection on each frame.
    3.  Recompile the frames into a new video with detection boxes drawn on it.
* **Live Webcam Analysis:** Uses your local webcam for real-time object detection, displaying a live video feed and a continuously updated detection log.
* **Thermal Image Classification:** Batch-processes still IR/thermal images from a local directory (`flir_images/`) and displays the annotated results.
* **Enhanced Vision:** Applies automatic gamma correction to improve visibility in low-light or thermal footage before analysis.
* **Audible Alerts:** A special `alarm.mp3` is triggered if the model detects an object classified as "fire."
* **Comprehensive Logging:** All detections are timestamped and logged. The log can be viewed in the app and downloaded as an Excel file (`.xlsx`) for further analysis.

---

## ⚙️ How It Works

The application is split into a user-friendly frontend (`app.py`) and a powerful processing backend (`backend.py`).

1.  **`app.py` (Frontend):**
    * Built with **Streamlit** to create the interactive web interface.
    * Manages user inputs, file uploads, and application state (e.g., starting/stopping the live feed).
    * Displays processed videos, images, and data logs in a clean, multi-tab layout.

2.  **`backend.py` (Backend):**
    * Uses **Ultralytics YOLOv5** to perform the heavy lifting of object detection. The `yolov5s.pt` model is loaded once for efficiency.
    * **OpenCV** is used for all computer vision tasks: reading video files, extracting/writing frames, and rendering detection boxes.
    * **Pandas** is used to structure detection data and export it to Excel.
    * Handles image enhancement, file I/O, and the alarm system.

---

## 🛠️ Tech Stack

* **Application Framework:** Streamlit
* **Object Detection:** PyTorch, Ultralytics YOLOv5
* **Computer Vision:** OpenCV-Python
* **Data Handling:** Pandas, NumPy
* **Audio:** playsound

---

## 📂 Project Structure
