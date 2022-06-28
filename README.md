# python-voice-assistant
import speech_recognition as sr
from operation_produced import *
r = sr.Recognizer()
with sr.Microphone() as source:
    print('Say something:')
    audio = r.listen(source,timeout=2)
    print('Audio listened!')
try:
    text = r.recognize_google(audio)
    print("Text: " + text)
    main(op_text=text)
except:
    print('Audio not recognized!')
