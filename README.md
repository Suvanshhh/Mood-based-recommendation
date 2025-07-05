# Emotion-Based Music Recommender

A real-time web app that detects your emotion from your webcam and recommends songs on YouTube tailored to your mood, language, and singer preference.

## 🚀 Features

- **Real-time emotion detection** using your webcam and a deep learning model.
- **Personalized music recommendations** based on detected emotion, language, and singer.
- **Modern, interactive UI** built with Streamlit.
- **No external music API required**—uses YouTube search for broad coverage.
- **All state managed in memory** for reliability and multi-user support.

## 🖥️ Demo

1. Enter your preferred language and singer in the sidebar.
2. Look at the camera; your emotion will be detected and displayed.
3. Click the "Recommend me songs" button to open YouTube with personalized song suggestions.

## 📂 File Structure

```
emotion-music-recommender/
│
├── app.py                # Main Streamlit app
├── model.h5              # Trained Keras emotion recognition model
├── labels.npy            # Numpy array of emotion labels
├── requirements.txt      # Python dependencies
└── README.md             # This file
```

## 🛠️ Setup & Installation

### 1. Clone the Repository

```bash
git clone 
cd emotion-music-recommender
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

**requirements.txt:**
```
streamlit
streamlit-webrtc
opencv-python
mediapipe
keras
numpy
av
```

### 3. Add Model Files

- Place your trained `model.h5` and `labels.npy` in the project directory.

### 4. Run the App

```bash
streamlit run app.py
```

- Open [http://localhost:8501](http://localhost:8501) in your browser.

## 🧑‍💻 How It Works

1. **Webcam Activation:**  
   The app uses your webcam to capture video frames in real time.

2. **Landmark Detection:**  
   MediaPipe extracts facial and hand landmarks from each frame.

3. **Emotion Prediction:**  
   The app normalizes landmark data and feeds it to a pre-trained Keras model to predict your emotion.

4. **Session State:**  
   The detected emotion is stored in Streamlit's session state for a seamless user experience.

5. **Music Recommendation:**  
   When your emotion is detected, a button appears. Clicking it opens a YouTube search for songs matching your language, emotion, and singer.

## 📝 Example Usage

1. **Enter Language:**  
   e.g., `Hindi`, `English`, `Spanish`

2. **Enter Singer:**  
   e.g., `Arijit Singh`, `Taylor Swift`

3. **Look at the Camera:**  
   Wait for your emotion to be detected (e.g., Happy, Sad, Angry).

4. **Click "Recommend me songs":**  
   YouTube opens with a search like:  
   `Hindi Happy song Arijit Singh`

## 🎨 UI Overview

- **Sidebar:** Language and singer input.
- **Main Area:** Webcam feed, detected emotion, and recommendation button.
- **Footer:** Attribution and credits.

## ⚙️ Customization

- **Model:**  
  Replace `model.h5` and `labels.npy` with your own trained model and labels for different emotion sets.
- **UI:**  
  Modify the Streamlit layout, colors, and text to match your branding or preferences.
- **Recommendation Logic:**  
  Change the YouTube search query format for different recommendation styles.

## 🛡️ Privacy & Security

- **Camera access** is local to your browser; no images or video are uploaded or stored.
- **All emotion detection** happens in your browser session.

## 🧩 Dependencies

- [Streamlit](https://streamlit.io/)
- [streamlit-webrtc](https://github.com/whitphx/streamlit-webrtc)
- [OpenCV](https://opencv.org/)
- [MediaPipe](https://mediapipe.dev/)
- [Keras](https://keras.io/)
- [NumPy](https://numpy.org/)
- [av](https://github.com/PyAV-Org/PyAV)

## ❓ Troubleshooting

| Issue                        | Solution                                      |
|------------------------------|-----------------------------------------------|
| Camera not opening           | Allow camera access in browser/OS, close other apps using the camera |
| Emotion not detected         | Ensure face is well-lit and visible, check model files |
| YouTube not opening          | Use the provided "Recommend me songs" button, allow pop-ups |
| Import/module errors         | Install all dependencies from `requirements.txt` |
