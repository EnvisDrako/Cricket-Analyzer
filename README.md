# 🏏 Cricket Shot Analyzer

A modular Python application that performs real-time biomechanical analysis of cricket cover drives from video footage. The analyzer uses MediaPipe for pose estimation, calculates key biomechanical metrics, and provides detailed evaluation with visual feedback.

## ✨ Features

- **Real-time pose estimation** using MediaPipe
- **Biomechanical analysis** of cricket batting technique
- **Live metric overlays** on video output
- **Comprehensive HTML reports** with detailed feedback
- **Temporal analysis** with metric visualization
- **Configurable thresholds** for different skill levels
- **Phase-based analysis** (Stance, Stride, Downswing, Impact, Follow-through, Recovery)

## 🚀 Quick Start

### Prerequisites

- Python 3.8 or higher
- pip package manager

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/cricket-shot-analyzer.git
   cd cricket-shot-analyzer
   ```

2. **Create a virtual environment (recommended):**
   ```bash
   python -m venv cricket_env
   
   # On macOS/Linux:
   source cricket_env/bin/activate
   
   # On Windows:
   .\cricket_env\Scripts\activate
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Place your video file:**
   - Add your cricket video to the project directory
   - Update the `input_video` path in `config.ini` (auto-generated on first run)

### Usage

```bash
python cricket_analyzer.py
```

The script will:
- Process the video with real-time progress display
- Show annotated video window with live metrics
- Generate comprehensive analysis outputs

## 📁 Project Structure

```
cricket-analyzer/
├── cricket_analyzer.py      # Main application script
├── requirements.txt         # Python dependencies
├── config.ini              # Configuration file (auto-generated)
├── input_video.mp4         # Your cricket video (example)
└── output/                 # Generated analysis files
    ├── annotated_video.mp4 # Annotated output video
    ├── evaluation.json     # Raw analysis data
    ├── temporal_metrics.png # Metrics visualization
    └── report.html         # Comprehensive HTML report
```

## ⚙️ Configuration

The application behavior is controlled by `config.ini`:

### File Paths
```ini
[PATHES]
input_video = input_video.mp4
output_video = output/annotated_video.mp4
output_json = output/evaluation.json
output_plot = output/temporal_metrics.png
output_report = output/report.html
```

### Detection Settings
```ini
[THRESHOLDS]
min_detection_confidence = 0.8
min_tracking_confidence = 0.5
visibility_threshold = 0.5
max_missed_frames = 5
fps_target = 30
```

### Biomechanical Thresholds
```ini
elbow_angle_min = 120
elbow_angle_max = 160
spine_lean_max = 30
head_knee_max = 0.3
foot_angle_min = 10
foot_angle_max = 45
contact_velocity_threshold = 50
```

### Reference Values
```ini
[REFERENCE]
elbow_angle_ideal = 140
spine_lean_ideal = 15
head_knee_ideal = 0.1
foot_angle_ideal = 25
```

## 📊 Output Files

| File | Description |
|------|-------------|
| `annotated_video.mp4` | Original video with pose skeleton and live metric overlays |
| `evaluation.json` | Raw scores, feedback, and temporal data in JSON format |
| `temporal_metrics.png` | Visualization chart of key metrics over time |
| `report.html` | Comprehensive HTML report with analysis summary |

## 🎯 Understanding Results

### Scoring System
- **10/10**: Professional-level technique
- **8-9/10**: Advanced amateur level
- **6-7/10**: Intermediate level with room for improvement
- **4-5/10**: Beginner level, needs significant work
- **1-3/10**: Major technical issues

### Key Metrics Analyzed

#### Elbow Angle
Position and extension of the front elbow during the swing

#### Head Position
Alignment of the head with the front knee for balance

#### Spine Lean
Evaluation of body posture and balance throughout the shot

#### Foot Direction
Front foot positioning relative to the bowling crease

#### Follow-through
Completion and fluidity of the swing motion

### Phase Analysis

1. **Stance**: Initial ready position
2. **Stride**: Forward movement in preparation
3. **Downswing**: Bat movement toward the ball
4. **Impact**: The moment of bat-ball contact
5. **Follow-through**: Post-contact swing completion
6. **Recovery**: Return to ready position

## 🔧 Troubleshooting

### Common Issues

**"Error processing video"**
- Verify the video file path in `config.ini`
- Ensure the video file exists and is readable

**"Module not found" error**
- Install dependencies: `pip install -r requirements.txt`
- Verify virtual environment activation

**Slow analysis or low FPS**
- Use shorter video clips
- Reduce video resolution
- Lower `model_complexity` in the script (0, 1, or 2)

**Pose detection fails**
- Ensure good lighting and clear view of the batsman
- Adjust `min_detection_confidence` in config
- Check if the batsman is fully visible in frame

**Permission errors**
- Run with administrator privileges
- Check write permissions for output directory

## 🛠️ Dependencies

```txt
opencv-python>=4.5.0
mediapipe>=0.8.0
numpy>=1.21.0
matplotlib>=3.3.0
```

## 📋 Requirements

- **Python**: 3.8 or higher
- **OS**: Windows, macOS, or Linux
- **Hardware**: Webcam or video file input
- **Memory**: Minimum 4GB RAM recommended


