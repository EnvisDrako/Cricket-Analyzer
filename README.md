# 🏏 Cricket Shot Analyzer

A Python application that performs real-time biomechanical analysis of a cricket cover drive from a video. It uses MediaPipe for pose estimation, calculates key biomechanical metrics, and provides a detailed evaluation of the shot.



---

## ✨ Features

-   **Real-time Pose Estimation:** Utilizes MediaPipe to detect and track 33 body landmarks.
-   **Biomechanical Metrics:** Calculates key performance indicators like elbow angle, spine lean, and head position.
-   **Phase Detection:** Automatically identifies the distinct phases of a cricket shot (stance, stride, impact, follow-through).
-   **Scoring & Feedback:** Provides a quantitative score (out of 10) and qualitative feedback for each metric.
-   **Comprehensive Reporting:** Generates an annotated video, a JSON data file, a temporal metrics plot, and a final summary in an HTML report.

---

## 🚀 Quick Start Guide

### 1. Prerequisites

-   Python 3.8+
-   `pip` package manager

### 2. Installation

1.  **Clone or create the project directory:**
    ```sh
    git clone <your-repo-url>
    # or
    mkdir cricket-analyzer
    cd cricket-analyzer
    ```

2.  **Create `requirements.txt`:**
    Create a file named `requirements.txt` with the following content:
    ```txt
    opencv-python
    mediapipe
    numpy
    matplotlib
    ```

3.  **Create a virtual environment (Recommended):**
    ```sh
    python -m venv cricket_env
    ```
    -   **On macOS/Linux:**
        ```sh
        source cricket_env/bin/activate
        ```
    -   **On Windows:**
        ```sh
        .\cricket_env\Scripts\activate
        ```

4.  **Install dependencies:**
    ```sh
    pip install -r requirements.txt
    ```

5.  **Add your video:**
    Place the video file you wish to analyze in the project's root directory. The script defaults to `input_video.mp4`.

### 3. Running the Analysis

Execute the main script from your terminal:
```sh
python cricket_analyzer.py
