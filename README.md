# Face Recognition Based Attendance 📋

> Automated attendance system using real-time face recognition with cloud logging.

## Overview

A real-time face recognition attendance system built using **Python**, **DepthAI**, **OpenCV**, and the `face_recognition` library. The system captures live video, identifies known faces, and automatically logs attendance with timestamps. Records are stored in **Google Sheets** for cloud-based access and backed up locally for reliability.

This project provided hands-on experience with embedded AI, camera pipelines, and practical computer vision deployment.

## Features

- 🎯 **Real-Time Face Identification** — Identifies known individuals from a live camera feed
- 🕐 **Automatic Timestamping** — Logs the time of attendance for each detected person
- ☁️ **Google Sheets Integration** — Pushes records to a shared spreadsheet for easy access
- 💾 **Local Backup** — Saves attendance records locally as a fallback
- 🔒 **Privacy-Aware** — Face encodings stored locally, no cloud face processing

## System Architecture

```
Camera Feed
    ↓
DepthAI Pipeline (Frame Capture)
    ↓
Face Detection (face_recognition)
    ↓
Identity Matching (Encodings Database)
    ↓
Attendance Log (Timestamp + Name)
    ↓
Google Sheets API ──→ Cloud Sheet
Local CSV Backup
```

## Tech Stack

| Category | Tools |
|---|---|
| Language | Python 3 |
| AI Camera | DepthAI (OAK-D) |
| Face Recognition | face_recognition, dlib |
| Computer Vision | OpenCV |
| Cloud Storage | Google Sheets API |
| Hardware | Raspberry Pi / OAK-D Camera |

## Project Structure

```
Face-Recognition-Attendance/
├── main.py                    # Entry point
├── face_encoder.py            # Encode known faces
├── recogniser.py              # Live recognition pipeline
├── attendance_logger.py       # Log to Sheets + local
├── known_faces/               # Reference face images
├── credentials/               # Google API credentials
├── attendance_log.csv         # Local backup log
├── requirements.txt
└── README.md
```

## Getting Started

### Prerequisites

```bash
pip install opencv-python face-recognition depthai gspread oauth2client numpy
```

### Setup

1. Add reference face images to `known_faces/` (one image per person, named `FirstName_LastName.jpg`)
2. Enable Google Sheets API and add `credentials.json` to `credentials/`
3. Encode known faces:
```bash
python face_encoder.py
```

### Run

```bash
python main.py
```

## Results

- ✅ Successfully identifies known faces in real time
- ✅ Attendance logged with sub-second latency
- ✅ Google Sheets updated automatically on detection

## Skills Demonstrated

`Python` · `DepthAI` · `OpenCV` · `Face Recognition` · `Google Sheets API` · `Embedded AI` · `Attendance Automation`
