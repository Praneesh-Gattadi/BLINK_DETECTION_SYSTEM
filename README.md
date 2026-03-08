# BLINK-DETECTION-SYSTEM

A Python-based **real-time blink detection system** using **OpenCV** and **MediaPipe Face Mesh**, featuring **auto-calibration**, **noise reduction**, and **stability checks** for high
accuracy. This project is ideal for **human-computer interaction**, **driver drowsiness detection**, and **eye-based activity tracking**.


## 📌 Features

- **Automatic EAR Calibration** — Detects your open-eye Eye Aspect Ratio (EAR) within 2 seconds.
- **Real-time Blink Counting** — Displays live blink count on screen.
- **Stability & Yaw Checks** — Ensures face stability and frontal orientation to reduce false positives.
- **Motion Filtering** — Ignores blinks during significant head movement.
- **Smoothed EAR Values** — Reduces jitter using a rolling average.
- **Full-Screen Display** — Immersive real-time video output.


## 🛠️ Requirements

Make sure you have **Python 3.7+** installed, then install the dependencies:

pip install opencv-python mediapipe numpy


🚀 How to Run

1. Clone the Repository
git clone https://github.com/Praneesh-Gattadi/BLINK_DETECTION_SYSTEM

3. Run the Script
python blink_detection.py

4. Calibration
Look straight at the camera.
Keep your face steady and eyes open for ~2 seconds.
The system will auto-calibrate EAR thresholds.

5. Controls
Press q or Esc to quit.


📷 How It Works

1. Face Detection
Uses MediaPipe Face Detection to locate the face in each frame.

2. Face Mesh & Eye Landmark Detection
Extracts 6 key landmarks per eye to calculate the Eye Aspect Ratio (EAR).

3. Blink Detection Logic
Detects eye closure when EAR drops below the close threshold.
Detects eye reopening when EAR rises above the open threshold.
Validates blinks using duration, movement stability, and minimum interval.

4. Noise Reduction
EAR smoothing via rolling average.
Rejects frames when the face is unstable or turned.

📊 Configuration
You can adjust parameters in the config section of the script:

| Parameter                | Default | Description                                   |
| ------------------------ | ------- | --------------------------------------------- |
| `EAR_SMOOTHING_LEN`      | `5`     | Number of frames to smooth EAR                |
| `CALIBRATION_TIME`       | `2.0`   | Time (seconds) for auto-calibration           |
| `DEFAULT_EAR_CLOSE_FRAC` | `0.65`  | Fraction of open-eye EAR for closed threshold |
| `MIN_BLINK_DUR`          | `0.06`  | Minimum blink duration (seconds)              |
| `MAX_BLINK_DUR`          | `0.5`   | Maximum blink duration (seconds)              |

📂 Project Structure

├── blink_detection.py   # Main script               
├── README.md            # Project documentation   


🖼️ Example Output

- Blink Count displayed on the video feed.
- Stability indicator showing if face is stable.
- EAR values for debugging.


💡 Use Cases

- Driver drowsiness detection
- Eye fatigue monitoring
- Human-computer interaction (HCI) research
- Assistive technologies

📜 License

This project is licensed under the MIT License — see the LICENSE file for details.

🙌 Acknowledgements

- OpenCV for computer vision tools.
- MediaPipe for fast and accurate face/eye landmark detection.
