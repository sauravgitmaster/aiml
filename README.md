
# Jarvis: Voice Assistant in Python

**Jarvis** is a Python-based personal voice assistant that can perform searches, open websites, play music, tell the time, and send emails through voice commands.

***

## Features

- **Speech Recognition:** Listens to user commands via microphone.
- **Text to Speech:** Converts text responses to voice.
- **Query Wikipedia:** Summarizes responses from Wikipedia.
- **Open Websites:** Can open YouTube, Google, StackOverflow, GeeksforGeeks, Instagram, etc.
- **Play Music:** Plays a predefined local music file.
- **Tell Time:** Speaks out the current time.
- **Open VS Code:** Launches VS Code via command.
- **Send Email:** Can send emails through a predefined Gmail account.
- **Personalized Greetings:** Wishes user based on time of day.

***

## Requirements

Python libraries required:

- pyttsx3
- SpeechRecognition
- wikipedia
- datetime
- webbrowser
- os
- smtplib

***

## Usage

1. Configure your email credentials in the script (`yourname@gmail.com`, `yourpassword`).
2. Run the script and interact by speaking your commands.

**Examples of supported commands:**
- Wikipedia [topic]
- Open YouTube
- Open Google
- Play music
- What is the time?
- Open code
- Email to Aman

***

## Code Structure

- Greets user based on current time.
- Listens and returns voice input as text.
- Sends an email via Gmail.
- Continuously receives user commands and executes matching actions.

***

## Notes

- Update hardcoded file paths and email credentials before using.
- Voice recognition is optimized for English (India).
- Ideal for learning about speech interfaces and automation with Python.

***

## License

Include your preferred license here.

***

Feel free to modify or add your author information or custom notes to this README!
