# Driver-Drowsiness-Detection-System
It is deep learning project that detect diver drowsiness using eyes close or open
🚗 Face Recognition for Secure Driving – Drowsiness Detection
📌 Overview
This project implements a real-time driver monitoring system that detects drowsiness by analyzing eye states (open/closed) using deep learning. It helps prevent accidents caused by fatigue by triggering visual + audio alerts when the driver appears drowsy.

🎯 Objectives
Detect face and eyes using webcam.

Classify eye state as Open or Closed.

Maintain a drowsiness score based on eye closure.

Trigger visual + audio alerts when driver seems drowsy.

🛠️ Tech Stack
Language: Python

Libraries: TensorFlow/Keras, OpenCV, NumPy, Pygame

Model: InceptionV3 (Transfer Learning)

Tools: Jupyter Notebook

Alert System: Pygame mixer for alarm sound

📂 Dataset & Preprocessing
Dataset: MRL Eye Dataset (Open & Closed eye images)

Image Size: 80 × 80 × 3

Preprocessing:

Rescale pixels (1./255)

Data augmentation (rotation, zoom, shift, shear)

🧠 Model Architecture
Base Model: InceptionV3 (imagenet, include_top=False)

Added Layers:

Flatten

Dense (64, ReLU)

Dropout (0.5)

Dense (2, Softmax → [Open, Closed])

Optimizer: Adam

Loss: Categorical Crossentropy

Training: Batch size = 8, Epochs = 20

⚙️ Drowsiness Logic
python
if prediction[0][0] > 0.30:  
    score += 1   # Closed eye detected  
elif prediction[0][1] > 0.70:  
    score -= 1   # Open eye detected  

if score > 5:  
    show_alert()  
    play_alarm()  
📊 Evaluation
Metrics: Accuracy, Precision, Recall, F1-score

Tested on separate dataset for validation

🚨 Output
Eye Open → Active
<img width="707" height="395" alt="image" src="https://github.com/user-attachments/assets/fad27932-d10c-4b5f-936c-376f03aa3faa" />
<img width="650" height="399" alt="image" src="https://github.com/user-attachments/assets/0e3e72de-db8f-459b-b59b-6fd9647d14ea" />
<img width="781" height="884" alt="image" src="https://github.com/user-attachments/assets/47f51e8d-d798-40ba-9b98-a972d0e97923" />

Eye Closed → Drowsy (Alert Triggered)

🌍 Applications
Vehicles: Alerts drivers to prevent accidents

Trains & Flights: Monitors pilots/train drivers

Defence: Keeps soldiers alert during missions

Education/Apps: Detects attentiveness in online learning

🚀 Future Scope
Deploy in intelligent vehicles

Improve accuracy with larger datasets

Integrate with IoT for smart car systems

📜 License
This project is licensed under the MIT License – feel free to use and modify.
