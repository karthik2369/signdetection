# signdetection

# 🧠 Real-Time Sign Language Action Detection

This project implements a real-time **action detection system** for **sign language recognition**, using **MediaPipe**, **OpenCV**, and a custom **LSTM-based model** trained on keypoint sequences.

It helps in bridging communication gaps for the hearing and speech impaired by identifying hand gestures and converting them into actions.
---

## 🔧 Technologies Used

- 🧠 MediaPipe Holistic for keypoint detection (face, pose, hands)
- 🎥 OpenCV for real-time video capture
- 🔢 NumPy & Pandas for data manipulation
- 🤖 TensorFlow / Keras for model training
- 📈 Matplotlib for visualization

---

## 📂 Project Structure
action-detection-sign/
│
├── data/                     # Raw and processed keypoint data
│   └── extracted_keypoints/
│
├── models/                   # Saved Keras model
│   └── action.h5
│
├── notebooks/                # Jupyter notebook (core development)
│   └── Action Detection Refined.ipynb
│
├── scripts/                  # Python scripts (optional)
│   ├── detect.py             # Real-time detection script
│   ├── train.py              # Model training script
│
├── demo.gif / demo.mp4       # Demo visuals
├── requirements.txt
└── README.md

---

## 🗃️ Dataset Info

- **Type**: Custom dataset based on body landmarks
- **Classes**: `Hello`, `Thanks`, `I Love You` (customizable)
- **Source**: Webcam input
- **Format**: Sequences of 30 frames containing keypoints
- **Keypoint Count**: 1662 per frame (Pose + Face + Left/Right hand landmarks)

---

## 🏗️ Model Architecture

A simple LSTM model processes sequences of 30 frames (each frame contains MediaPipe keypoints):

``python
Input(shape=(30, 1662)) → LSTM → Dropout → Dense → Softmax

##How to Run

1. Install Dependencies
   pip install -r requirements.txt
2.Train the Model
   # Optional if you already have action.h5
     python scripts/train.py
3.Run Real-Time Detection
  python scripts/detect.py
 
##Future Work
	•Add more sign language classes (ASL/ISL dataset)
	•Export model to TF.js or TFLite for web/mobile
	•Add text-to-speech output
	•Create full-stack web app with Flask or Streamlit

 Connect
	•Name: S Karthik
	•GitHub: karthik2369
	•LinkedIn: www.linkedin.com/in/skarthikml
