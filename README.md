# aiml
## Jarvis: Your Personal Desktop Assistant

This is the code for **Jarvis**, a simple yet functional desktop voice assistant built in Python. Jarvis allows you to perform basic tasks using voice commands, such as searching Wikipedia, opening websites, playing music, checking the time, and sending emails.

-----

###  Getting Started

Follow these steps to set up and run Jarvis on your local machine.

####  Prerequisites

You'll need **Python 3** installed. This project relies on several third-party libraries:

  * `pyttsx3`: Text-to-speech conversion.
  * `speechRecognition`: For recognizing voice input using Google's speech recognition API.
  * `wikipedia`: To easily search and summarize Wikipedia articles.

Install the necessary libraries using pip:

```bash
pip install pyttsx3 speechRecognition wikipedia webbrowser datetime os smtplib
```

*(Note: `webbrowser`, `datetime`, `os`, and `smtplib` are standard Python libraries and typically don't require separate installation.)*

####  Configuration

Before running, you need to configure a couple of things, especially for the email functionality and file paths:

1.  **Email Setup:**
    In the `sendEmail` function, you need to replace the placeholders with your actual email credentials.

      * **Gmail Security:** If you are using Gmail, you may need to enable "Less secure app access" in your Google account security settings or, preferably, use an **App Password** instead of your main password, as per Google's security recommendations.

    <!-- end list -->

    ```python
    def sendEmail(to, content):
        server = smtplib.SMTP('smtp.gmail.com', 587)
        server.ehlo()
        server.starttls()
        # Replace with your actual email and password/App Password
        server.login('yourname@gmail.com', 'yourpassword') 
        server.sendmail('youremail@gmail.com', to, content) # Replace 'youremail@gmail.com'
        server.close()
    ```

2.  **Music Directory:**
    Update the `music_dir` variable to the location where your songs are stored.

    ```python
    elif 'play music' in query:
        music_dir = 'D:\\Non Critical\\songs\\Favorite Songs2' # <-- Update this path
        # ... rest of the code
    ```

3.  **VS Code Path (or any application):**
    If you use the 'open code' command, make sure `codePath` points to the correct executable path for your VS Code installation.

    ```python
    elif 'open code' in query:
        codePath = "D:\VS Code\Microsoft VS Code\Code.exe" # <-- Update this path
        os.startfile(codePath)
    ```

####  Running Jarvis

1.  Save the code as `jarvis.py`.

2.  Open your terminal or command prompt.

3.  Navigate to the directory where you saved the file.

4.  Run the script:

    ```bash
    python jarvis.py
    ```

Jarvis will greet you, and the console will show "Listening...". You can now start issuing commands\!

-----

### 🗣️ Available Commands

Here are the commands Jarvis is currently programmed to understand:

| Command Phrase | Action |
| :--- | :--- |
| **"Wikipedia [query]"** | Searches Wikipedia for the query and speaks the summary. |
| **"Open YouTube"** | Opens YouTube in your default web browser. |
| **"Open Google"** | Opens Google in your default web browser. |
| **"Open Stack Overflow"** | Opens Stack Overflow. |
| **"Open GeeksforGeeks"** | Opens GeeksforGeeks. |
| **"Open Instagram"** | Opens Instagram. |
| **"Play Music"** | Starts playing the first song (`songs[0]`) from the configured `music_dir`. |
| **"What is the time"** | Tells you the current time. |
| **"Open code"** | Opens the application located at `codePath` (e.g., VS Code). |
| **"Email to Aman"** | Prompts you for the content, then attempts to send an email to a predefined recipient (`amanyourEmail@gmail.com`). |

-----

###  Project Notes

  * **Voice:** Jarvis is configured to use the second voice available in your system's SAPI5 text-to-speech engine (`voices[1].id`), which is often a female voice on Windows systems.
  * **Listening:** The assistant uses a `pause_threshold = 1` which means it will wait for 1 second of non-speech before concluding a phrase.
  * **Error Handling:** Basic error handling is in place for email sending and speech recognition failures.
