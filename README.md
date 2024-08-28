
# Save People from Drowning in the Swimming Pool using Mediapipe and YOLO

This project aims to detect people in swimming pools and identify when someone may need help by analyzing their poses using Mediapipe. The system also includes a YOLO model to detect and track people in the frame. If a potentially dangerous pose is detected, an alarm is triggered to alert nearby lifeguards or individuals.

## Features

- **Pose Detection**: Utilizes Mediapipe to analyze body landmarks and detect potentially dangerous poses that indicate a person might be struggling in the water.
- **Object Detection and Tracking**: Uses YOLO (You Only Look Once) for real-time person detection and tracking within the swimming pool area.
- **Alarm System**: Automatically triggers an audio alarm if someone is detected in a potentially dangerous situation, such as a drowning posture.
- **Real-time Processing**: Capable of processing video input in real-time, making it suitable for live surveillance scenarios.

## Requirements

- Python 3.x
- OpenCV
- Mediapipe
- YOLOv8 (Ultralytics)
- Miniaudio
- Mutagen

## Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/yourusername/swimming-pool-safety.git
    cd swimming-pool-safety
    ```

2. Install the required Python packages:

    ```bash
    pip install -r requirements.txt
    ```

3. Download the YOLO model and COCO classes file, and place them in the project directory:
    - `yolov8s.pt` (Download from Ultralytics' YOLO repository)
    - `coco.txt` (List of class names)

## Usage

1. Place your video file (e.g., `vid.mp4`) and audio file (e.g., `audio.mp3` for the alarm) in the project directory.
2. Run the script:

    ```bash
    python main.py
    ```

   Replace `main.py` with the name of your script if different.

3. The script will start processing the video. If a person in a potentially dangerous pose is detected, an alarm will be triggered.

## Configuration

- **Video File**: Update the path to the video file in the `process_video` function call.
- **Audio File**: Update the path to the audio file for the alarm.
- **Model Path**: Update the path to the YOLO model file (`yolov8s.pt`).
- **Classes File**: Update the path to the COCO classes file (`coco.txt`).

## How It Works

1. **Pose Detection**: The Mediapipe library is used to detect human body landmarks and calculate angles between them. The system looks for specific angles and positions that indicate a drowning pose.
2. **Object Detection**: YOLOv8 is used to detect and classify objects in the frame, specifically focusing on people.
3. **Tracking**: Detected people are tracked across frames to maintain their IDs and monitor movements.
4. **Alarm Trigger**: If the detected pose matches a potentially dangerous scenario, the system triggers an alarm sound to alert those nearby.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request or open an Issue for any bugs, enhancements, or suggestions.


