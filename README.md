# 🗣️ Speech-to-Text using Google API and Wav2Vec2

This project demonstrates a simple yet powerful comparison between two popular speech-to-text (STT) engines:

- **Google Web Speech API** (via `SpeechRecognition` library)
- **Facebook's Wav2Vec2 transformer model** (via Hugging Face `transformers`)

Given a `.wav` audio file, it outputs the transcriptions from both engines side by side.

---

## 📁 Repository Structure

```text
.
├── demoaudio.wav      # Sample audio file (replace with your own)
├── transcribe.py      # Main script to run
└── README.md          # This documentation
```

## ⚙️ Features

- ✅ Transcribes speech using both online (Google) and offline (Wav2Vec2) methods
- ✅ Preprocesses and resamples audio to 16kHz mono
- ✅ Supports stereo and various bit depths (`int16`, `int32`, `uint8`)
- ✅ Easy to run and modify
- ✅ No API key needed for Google STT (uses free tier)

---

## 🚀 Installation

Make sure you have **Python 3.7+** and install the dependencies:

```bash
pip install speechrecognition torch transformers scipy numpy
```
Also ensure you have pyaudio installed for speech_recognition. If not:
pip install pyaudio
# or if it fails on Windows:
pip install pipwin
pipwin install pyaudio
How to Use
Replace or rename your audio file to demoaudio.wav (must be .wav format).

Run the script:

bash
Copy
Edit
python transcribe.py
Output will show both transcriptions:

Copy
Edit
Transcribing file: demoaudio.wav

--- SpeechRecognition (Google Web Speech API) ---
Hello this is a test audio

--- Wav2Vec2 (HuggingFace Transformers) ---
hello this is a test audio
🧠 Script Overview
transcribe_with_speechrecognition(audio_file)
Uses the Google Web Speech API to convert audio to text.

Requires internet connection.

transcribe_with_wav2vec2(audio_file)
Loads Wav2Vec2 tokenizer and model from Hugging Face.

Processes audio: resampling, normalization, and inference.

Works fully offline once the model is downloaded.

📌 Notes
Audio should be clear, mono or stereo .wav file.

Wav2Vec2 expects audio sampled at 16,000 Hz.

If audio isn't found, the script will exit with an error.

🛠 Example Fix
Make sure your script ends with the correct block:

python
Copy
Edit
if __name__ == "__main__":
Do not use:

python
Copy
Edit
if name == "main":
