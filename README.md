# CODETECH-TASK-2
# Task 2 - CODTECH Internship
# Speech Recognition using speech_recognition library

import speech_recognition as sr

# Initialize recognizer
recognizer = sr.Recognizer()

# Load your audio file (must be .wav format)
AUDIO_FILE = "sample.wav"  # Replace with your file name

# Read the audio data
with sr.AudioFile(AUDIO_FILE) as source:
    print("🔊 Listening to the audio...")
    audio_data = recognizer.record(source)

# Try to recognize the speech
try:
    print("📝 Recognizing...")
    text = recognizer.recognize_google(audio_data)
    print("\n📃 Transcribed Text:\n")
    print(text)

except sr.UnknownValueError:
    print("❌ Could not understand the audio.")
except sr.RequestError as e:
    print(f"⚠️ Could not request results; check internet connection. Error: {e}")
