# Offline Multimodal MedAi Console
<strong>A truly offline text and voice medical Ai console powered by MedGemma</strong>
> 
> Prototype - For demonstration, education and inspiration

<img src="images/image1.png" alt="App screenshot" height="300">


<br>

The MedAi Console is a transparent, offline-first and privacy-first multimodal Ai console where clinicians can talk, type, show images, adjust parameters and create Ai tools. Uses Flask for the backend, Whisper for Speech-to-Text (STT), Kokoro for Text-to-Speech (TTS), and Ollama to serve the Large Language Model (LLM).

The app, powered by Google's MedGemma 4B model, is a multi-disciplinary and multi-lingual virtual colleague that can help clinicians review documents, brainstorm ideas, generate hypotheses, challenge assumptions, and learn fast. It gives clinicians a private and secure place to think clearly and quickly about difficult problems.

In other words, instead of taking the MedGemma model and using it to create a single task application, like an x-ray classification app, what I’ve done is take the model and put it into the hands of the user. The MedAi Console is an offline platform that  gives clinicians the privacy and flexibility to experiment with MedGemma and use it to create their own Ai tools. This could lead to some novel applications that programmers could never have imagined.

<br>

YouTube Video:<br>
myOfflineAi - A Local Text and Voice Chat Ai Console powered by Ollama, Whisper and Kokoro<br>
https://www.youtube.com/watch?v=LOndd7MpdCs

<br>


<img src="images/image1x.png" alt="App screenshot" height="500">
<p>Minimalist UI</p>

<br>


<br>

## Key Features

<br>

- <strong>100% Offline and Private:</strong> Your conversations and data never leave your local machine.
- <strong>Multimodal:</strong> Chat using text and images (supports JPG, PNG, WebP, and multi-page PDFs).
- <strong>Voice Chat:</strong> Have a conversation with your Ai.
- <strong>Create Ai Tools:</strong> Create specialized assistants with unique personas, tailored for specific tasks (e.g. code generation, text summarization, creative writing).
- <strong>Advanced Model Controls:</strong> Tune the performance of models with adjustable parameters like temperature, context size, and top_p.
- <strong>Webcam Photos:</strong> Use the webcam to send photos of hand drawn diagrams and homework problems directly to the chat.
- <strong>Chat History:</strong> All conversations are saved in a portable file that can be moved to a secure location or deleted.
- <strong>Supports math notation and code rendering:</strong> Ideal for use as an Ai tutor.
- <strong>Single-file architecture:</strong> Code is easy to audit because HTML, CSS, JS and Python are all in one file. HIPAA compliance thinking is built into the design.

<br>

## Key Innovations

<br>

The innovation is not in creating new technologies but in combining and optimizing existing technologies:

- <strong>Self-Contained Single-File Architecture:</strong> The entire application logic is contained in a single file. This design offers two major benefits: it provides a low barrier for tinkering and Ai modification, and more importantly, it makes the codebase easy to audit for security and privacy.
- <strong>"Double-Click to Run" Accessibility:</strong> Through simple .bat (Windows) and .command (macOS) scripts, the application can be launched without needing to use the command line, making it accessible to non-programmers and enthusiasts alike.
- <strong>High-Performance Hybrid Network:</strong> The app intelligently uses both HTTP and WebSockets. HTTP provides robust handling for file uploads, while WebSockets enable a real-time, low-latency connection for streaming AI responses and audio.
- <strong>Instant Audio with Sentence-by-Sentence TTS:</strong> Instead of waiting for the AI to generate its full response, text-to-speech audio begins playing sentence by sentence, creating a much more fluid and natural conversational experience.
- <strong>Ephemeral Data Processing:</strong> User-uploaded images and PDFs are processed entirely in-memory and are never permanently saved to your disk.


<br>

<img src="images/image2.png" alt="App screenshot" height="500">
<p>Supports images and pdf files</p>

<br>

<img src="images/image3.png" alt="App screenshot" height="500">
<p>Supports math notation and code rendering</p>

<br>

<img src="images/image4.png" alt="App screenshot" height="500">
<p>Settings panel hidden</p>

<br>

## Why does this app only support MacOS?

- Privacy is critical in medical applications. MacOS inspires trust because it's reliable and supports both privacy and user agency.
- Base spec silicon Macs (256 GB storeage, 16 GB RAM, 1000 USD cost) are able to run the MedGemma model at a token speed that's fast enough to be useful.
- Silicon Macs have battery life that's greater than 12 hours. This is important for a good user exerience, because running Ollama locally uses alot of battery power.

<br>


## How to Install and Run

<br>

In this section you will do the following:
- Install the Ollama desktop app
- Download an Ollama model
- Install the UV Python package manager
- Install ffmeg
- Start the app by double clicking a file

<br>

```
--------------------------------------------------------------
System Requirements
--------------------------------------------------------------

Operating System: macOS
Computer: Apple Silicon Mac (M1, M2, M3, M4)
RAM: 16GB
Free disk Space: 10 GB

--------------------------------------------------------------
Step-by-Step Setup
--------------------------------------------------------------

If you already have Ollama, UV and ffmeg installed then please skip those steps.


1. Download and install the Ollama desktop application
--------------------------------------------------------------

This is the link to download Ollama. After downloading, please install it on your computer.
Then launch it. A white chat window will open.
https://ollama.com/

Ollama launches automatically when you start your computer.


2. Download the MedGemma-1 GGUF model from Huggingface (7.77 GB)
----------------------------------------------------------------

1. Open the terminal on your Mac
2. Paste in this line and press Enter:
ollama run hf.co/unsloth/medgemma-4b-it-GGUF:BF16


Optional:
If you also want to download MedGemma-1.5 GGUF (7.77 GB), use this command:
ollama run hf.co/unsloth/medgemma-1.5-4b-it-GGUF:BF16

3. Install ffmpeg
--------------------------------------------------------------

# Use Homebrew (https://brew.sh/)

1. Open the terminal on your Mac
2. Paste in this line and press Enter:
brew install ffmpeg


4. Install UV
--------------------------------------------------------------

Paste this command into the terminal and press Enter:
wget -qO- https://astral.sh/uv/install.sh | sh


5. Download the project folder and place it on your desktop
--------------------------------------------------------------

1. On GitHub click on "<> Code". The select "Download Zip"
2. Download the project folder and unzip it.
3. Inside you will find a folder named: MedAi-Console-v1.0
4. Place MedAi-Console-v1.0 on your desktop.


5. Install the App
--------------------------------------------------------------

1. cd into MedAi-Console-v1.0 folder:
cd Desktop
cd MedAi-Console-v1.0

7. Paste this command into the terminal and press Enter
cat start-mac-app.command > temp && mv temp start-mac-app.command && chmod +x start-mac-app.command

8. Open the MedAi-Console-v1.0 folder
9. Double click this file: start-mac-app.command
10. The app will auto download all requirements and then open in your browser.


--------------------------------------------------------------
Using the App
--------------------------------------------------------------

The name of the model you downloaded will appear in the dropdown menu in the top left.
You can submit images and pdf documents in addition to text.

You can also talk to the Ai model by clicking on the Mic icon.
The Ai voice is turned off by default. You can turn it on in Voice Settings.
Any changes you make to the settings will be automatically saved.

The app does not stop running when you close the browser tab.
To shut down the app, close the terminal window.
You can also close the terminal by selecting it and typing Ctrl+C on Mac.


--------------------------------------------------------------
Future startup
--------------------------------------------------------------

Now that the setup is complete, in future simply double-click the start-mac-app.command file to launch the app.
The project folder must be placed on your desktop before the app is launched.

You could start the app and leave it running in the background all day.
Then whenever you want to use it, enter the following url in your browser:

http://127.0.0.1:5000/

Your browser will remember this local address so you won't have to.


--------------------------------------------------------------
Troubleshooting
--------------------------------------------------------------

If the app doesn't start, make sure Ollama is running (look for its icon in your menu bar)
If you see "connection refused", restart Ollama
Inference time will increase as you increase the context size setting.
Inference time will be longer when submitting large images or pdf files.
For the voice (TTS) to work Kokoro needs two files: kokoro-v1.0.onnx, and voices-v1.0.bin. These files are auto downloaded during the setup process. However, if the voice is not working then please download these files manually and place them in the project folder:

kokoro-v1.0.onnx: https://github.com/thewh1teagle/kokoro-onnx/releases/download/model-files-v1.0/kokoro-v1.0.onnx

voices-v1.0.bin: https://github.com/thewh1teagle/kokoro-onnx/releases/download/model-files-v1.0/voices-v1.0.bin


--------------------------------------------------------------
Notes
--------------------------------------------------------------

When creating agents/tools that will generate math notation, you need to tell the agent to use LaTeX when generating math notation. Please add this note to the system message: Use LaTeX notation for mathematical or scientific expressions only.
For best results when using your voice - use a headset or earphones with a mic. This reduces background noise. It also allows for a more relaxed chat because you won't have to constantly focus on being clearly heard by the speech to text system.
Because MedGemma-1.5 is a reasoning model, I've set up the app to disable voice output when the MedGemma-1.5 model is selected.

```
<br>

## Detailed writeup

A detailed writeup for a similar project, including trouble-shooting info, is available here:<br>
https://github.com/vbookshelf/myOfflineAi-PrivacyFirst

<br>

## What Files are Created during operation?

<br>

The application is designed to be self-contained and stores all its configuration and data in the same directory it is run from.

### Persistent Configuration and Data Files
These files store your settings and history and remain on your disk between sessions.

1. agents.json<br>
- <strong>Purpose:</strong> This is a crucial file that stores all the custom "AI Tools" (or agents) that you create. It saves their names, titles, system personas, conversation type (single-turn/multi-turn), and any model settings you've specifically configured for them.<br>
- <strong>Lifecycle:</strong> It is automatically created on the first run if it doesn't exist, pre-populated with the default "Ai Assistant." It is read on startup and written to whenever you create, edit, reorder, or delete an AI Tool.

2. conversations.json.<br>
- <strong> Purpose:</strong> This file saves your complete chat history. Each conversation is stored as a separate entry, linked to the specific AI Tool you were using at the time..<br>
- <strong> Lifecycle:</strong> This file is created after your first conversation is completed. It is updated at the end of every chat session to save the new messages.

3. user_settings.json.<br>
- <strong>Purpose:</strong> This file stores your global settings. This includes the default model parameters (temperature, context size, etc.), your voice preferences (language, voice, speed), and other UI-related settings like the PDF page limit. These are the settings that apply to the default "Ai Assistant" and serve as the base for new AI Tools..<br>
- <strong>Lifecycle:</strong> It is created on the first run if it doesn't exist, populated with the application's default values. It is updated any time you change these settings in the sidebar.

3. last_model.txt.<br>
- <strong>Purpose:</strong> A very simple text file that contains only the name of the last Ollama model you selected from the dropdown menu..<br>
- <strong>Lifecycle:</strong> It is created or overwritten every time you select a different model. This ensures the application remembers your preferred model for your next session.

### Temporary Files
This category includes files that are created for a specific, brief task and are deleted automatically.

temp_recording.wav.<br>
- <strong>Purpose:</strong> To temporarily store the raw audio data from your microphone when using the speech-to-text feature..<br>
- <strong>Lifecycle:</strong> This file is ephemeral. It is created the moment you stop speaking, is immediately fed to the Whisper model for transcription, and is then instantly and automatically deleted. It only exists on your disk for a fraction of a second during the transcription process.

### What is Not Saved to Disk
Uploaded Images and PDFs: All user-uploaded files (.jpg, .png, .pdf, etc.) are processed entirely in-memory. They are converted to a Base64 format, sent to the model, and are never written to or saved on your hard drive.

### Agent profile pictures
The agent profile pictures that you upload are stored in a folder named agent_avatars. The profile image is deleted when an agent is deleted.


<br>

## Technologies Used

<strong>Backend:</strong> Flask (HTTP), Flask-SocketIO (WebSockets), Ollama Python<br>
<strong>Frontend:</strong> HTML, Tailwind CSS, JavaScript<br>
<strong>File Processing:</strong> PyMuPDF (for PDFs)<br>
<strong>Speech-to-Text:</strong> OpenAI Whisper<br>
<strong>Text-to-Speech:</strong> Kokoro TTS


<br>

## Notes

- When using the voice chat it helps to wear a headset or use earphones with a mic. The voice detection system is quite simple so it won't work well if there's alot of background noise.
- When setting up a tool (specialized assistant) that uses voice, it helps to tell it (in the system message) not to use markdown - or else the Ai will speak the markdown symbols out loud. 
- Whisper is an LLM, and it can hallucinate. It sometimes generates random text like "Thank you for watching!". This text then gets converted in to speech.
- Not all parameters are supported by all models. I found that Qwen3 Ollama models would not work if a repeat_penalty parameter was passed to the model. To make the app more robust I've only used parameters that are likely to be supported by the vast majority of models - temperature, context size, top_p.
- Small quantized local models are not yet trustworthy enough to be used for mission critical tasks. They are good for tasks that don't require precise answers like brainstorming and creative writing, or for tasks where a user can quickly check the accuracy of the output.
- I found that the gemma3:12b 4 bit quantized model (8.1 GB) works well. It's fast, has a high level of intelligence and can handle both text and images. 
- At first glance the single-file architecture may look like a naive simplification created for non-technical users and for easy auditing - but it's much more. It's an architecture pattern that's optimized for AI-assisted development - a "see the entire picture at once" pattern that supports fast and efficient Human + Ai collaboration.



<br>

## App Family - Offline-First, Privacy-First, Transparent

- myOfflineAi-PrivacyFirst<br>(Maximum security. No chat history is saved.)<br>
  https://github.com/vbookshelf/myOfflineAi-PrivacyFirst<br>
- myOfflineAi-ChatHistory<br>(Saves chats to a local file you control.)<br>
  https://github.com/vbookshelf/myOfflineAi-ChatHistory<br>
- Chat-Image-Marker<br>(A simple, offline tool for marking up images.)<br>
  https://github.com/vbookshelf/Chat-Image-Marker<br>
- myOfflineAi-VoiceAssistant<br>(An offline full-featured Ai voice assistant.)<br>
  https://github.com/vbookshelf/myOfflineAi-VoiceAssistant<br>
-  myOfflineAi-ChatConsole<br>(Desktop multimodal chat console that supports both text chat and voice chat.)<br>
  https://github.com/vbookshelf/myOfflineAi-ChatConsole


<br>

## Revision History

Version 3.0<br>
28-Oct-2025<br>
Changed the UI.<br>
Added a toolbox.<br>
Added agent profile picture feature.

Version 2.0<br>
26-Oct-2025<br>
Implemented a more robust hybrid network architecture - HTTP and WebSockets.<br>
Fixed error with Qwen models.<br>
Removed model parameters that are not supported by all models.

Version 1.1<br>
21-Oct-2025<br>
Enabled flash attention and q_8 context caching to speed up inference.

Version 1.0<br>
17-Oct-2025<br>
Prototype. Released for testing and education.

<br>


