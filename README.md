import speech_recognition as sr

# Initialize recognizer
recognizer = sr.Recognizer()

# Load the audio file (make sure it's .wav format and in the same folder)
AUDIO_FILE = "sample.wav"  # Replace with your file name

# Read and recognize audio
with sr.AudioFile(AUDIO_FILE) as source:
    print("🎧 Listening to the audio...")
    audio = recognizer.record(source)

try:
    # Convert speech to text
    print("🔍 Recognizing...")
    text = recognizer.recognize_google(audio)
    print("\n📝 Transcription:")
    print(text)

except sr.UnknownValueError:
    print("❌ Could not understand the audio.")
except sr.RequestError as e:
    print(f"⚠️ Could not request results; check your internet. Error: {e}")
