# 👁️✋ Gesture-Controlled Security System  
### *Biometric Shutdown Trigger via Offensive Gestures*  

<div align="center">
  
![Python](https://img.shields.io/badge/Python-3.7%2B-blue?logo=python)  
![MediaPipe](https://img.shields.io/badge/MediaPipe-0.8.11-red?logo=google)  
![OpenCV](https://img.shields.io/badge/OpenCV-4.5-brightgreen?logo=opencv)  
![PyGame](https://img.shields.io/badge/PyGame-2.1-purple?logo=pygame)  

![DEMO]([https://media4.giphy.com/media/v1.Y2lkPTc5MGI3NjExZjNlaGpkcGg2NW5tOXlzejhjZGV4eml2MG90cjZiaG11ODV4amthZSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/GeimqsH0TLDt4tScGw/giphy.gif](https://media4.giphy.com/media/v1.Y2lkPTc5MGI3NjExZDdtamhhODhxZTRsb2tlam51YTZpYWwwNG9hbHZ0NzhjMHJoZjZ5OSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/lJNoBCvQYp7nq/giphy.gif))

</div>

## 🔍 System Overview
Real-time hybrid detection system that:
- Tracks **21 hand landmarks** via MediaPipe
- Applies **face overlays** with alpha blending
- Triggers **instant shutdown** on offensive gestures
- Provides **visual/audio warnings** before action

## 🖥️ Core Features
```python
# Key components from your code
Hands = mp.solutions.hands.Hands(
    static_image_mode=False,
    max_num_hands=2,
    min_detection_confidence=0.7
)

FaceDetection = mp.solutions.face_detection.FaceDetection(
    model_selection=1,
    min_detection_confidence=0.5
)

Gesture Detection Logic

def detect_gesture(fingers):
    # Middle finger raised = offensive gesture
    if fingers[2] == 1 and sum(fingers) == 1:  
        return "WARNING: Offensive gesture detected"
    return "Gesture: Normal"

Cross-Platform Shutdown

if platform.system() == "Windows":
    os.system("shutdown /s /t 1")  # Immediate force-shutdown
elif platform.system() == "Linux":
    os.system("shutdown now") 
elif platform.system() == "Darwin":
    subprocess.run(["osascript", "-e", 'tell app "System Events" to shut down'])

⚠️ Safety Mechanisms
3-Layer Verification:

Hand landmark confidence > 70%

Isolated middle finger detection

Continuous 2-second hold

📜 License
MIT License - Use at your own risk. Not responsible for accidental shutdowns.

<div align="center">
⚠️ Warning: System contains no TensorFlow - pure MediaPipe/OpenCV solution ⚠️

</div> ```
