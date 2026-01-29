# Offline MedAi Console
<strong>A multimodal Ai collaborator for clinicians. Powered by MedGemma.</strong>
> 
> Prototype - For demonstration, education and inspiration

YouTube Video:<br>
Introducing the Offline MedAi Console | Powered by MedGemma<br>
https://youtu.be/X3-6MpZp89s?si=y8ZHe_BfaoL8VA1E

<br>

<img src="images/image1.png" alt="App screenshot" height="300">


<br>

The MedAi Console is a transparent, offline-first and privacy-first multimodal AI console where clinicians can talk, type, show images, adjust parameters and create AI tools. Uses Flask for the backend, Whisper for Speech-to-Text (STT), Kokoro for Text-to-Speech (TTS), and Ollama to serve the Large Language Model (LLM).

The console is powered by Google's MedGemma 4B model. MedGemma is a multi-skilled medical model.<br>
It can interpret medical images in four specialities: 

- Radiology (X-rays, CT scans)
- Digital Pathology (Tissue slides)
- Dermatology (Skin conditions)
- Ophthalmology (Retinal scans)

The model can also understand medical documents. Moreover, it has the general purpose capabilities of the Gemma3 model.

<br>

## Example Use Cases

- An X-ray shows a 'sail sign' in a pediatric patient. Please explain the clinical significance of this finding and what the next diagnostic step should be.

- I'm a midwife. A pregnant woman in her third trimester has a headache and blurry vision. What questions can I ask that will help me differentiate between tension headache and pre-eclampsia?

- I'm a GP. I need to explain Atrial Fibrillation to a 75 year old patient without using medical jargon. Please give me a one paragraph summary. The patient doesn't understand English. He only speaks Spanish.

<br>

## UI

<img src="images/image2.png" alt="App screenshot" height="500">
<p>Minimalist UI</p>

<br>


<br>

## Key Features

<br>

- <strong>100% Offline and Private:</strong> Can run anywhere care is delivered. Your data never leaves your device.
- <strong>Fully Transparent:</strong> All code files accessible for review. No black-box executables. No proprietary wrappers.
- <strong>Multimodal:</strong> Chat using text and images (supports JPG, PNG, dicom, dcm and multi-page PDFs).
- <strong>Supports dicom files:</strong> Dicom files (.dicom and .dcm) are converted into png images and stored in the persistent_uploads folder.
- <strong>Voice Chat:</strong> Talk to your AI.
  
- <strong>Create Ai Tools:</strong> Create specialized assistants for specific tasks (e.g. x-ray analysis, text summarization, text extraction).
- <strong>Advanced Model Controls:</strong> Tune the performance of models with adjustable parameters like temperature, context size, and top_p.
- <strong>Webcam Photos:</strong> Use the webcam to send photos of prescriptions and hand drawn diagrams directly to the chat.

- <strong>Chat History:</strong> All conversations are saved in a portable file that can be moved to a secure location or deleted.
- <strong>Supports LaTeX notation and code rendering:</strong> Can be used as a medical AI tutor for chemistry and math.
- <strong>Single-file architecture:</strong> Code is easy to audit because HTML, CSS, JS and Python are all in one file.

<br>

## Key Innovations

<br>

The innovation is not in creating new technologies but in combining and optimizing existing technologies:

- <strong>Self-Contained Single-File Architecture:</strong> The frontend and backend code is contained in a single app.py file. This "see the entire picture at once" design makes the codebase easy to audit for security and privacy. It also makes the code highly maintainable through AI collaboration. Developers can share the entire codebase with an AI assistant in a single prompt. This enables them to add features or fix bugs immediately rather than logging GitHub issues and waiting for responses.

- <strong>"Double-Click to Run" Accessibility:</strong> Through a simple .command MacOS script, the application can be launched without needing to use the command line, making it accessible to non-programmers.

- <strong>High-Performance Hybrid Network:</strong> The app intelligently uses both HTTP and WebSockets. HTTP provides robust handling for file uploads, while WebSockets enable a real-time, low-latency connection for streaming AI responses and audio.

- <strong>Fast Audio with Sentence-by-Sentence TTS:</strong> Instead of waiting for the AI to generate its full response, text-to-speech audio begins playing sentence by sentence, creating a fast conversational experience.


<br>

<img src="images/image3.png" alt="App screenshot" height="500">
<p>Supports images</p>

<br>

<img src="images/image6.png" alt="App screenshot" height="500">
<p>Supports pdf files</p>

<br>

<img src="images/image4.png" alt="App screenshot" height="500">
<p>Supports LaTeX notation and code rendering</p>

<br>

<img src="images/image7.png" alt="App screenshot" height="500">
<p>Create AI tools</p>

<br>

## Why does this console only support MacOS?

- Base-spec Macs (256GB Storage, 16GB RAM, built in GPU) are able to run the BF16 MedGemma model at a token speed that's fast enough to be useful (approx. 13 tokens/sec).
- Macs are reliable and privacy focused.
- Silicon Macs have battery life that's greater than 12 hours. This is important for a good user exerience, because local inference uses a lot of battery power.
- The low cost of a base-spec Silicon Mac ($669 USD for a M4 Mac Mini, $999 USD for a M4 Macbook Air) makes local AI accessible to ordinary people.

<br>


## How to Install and Run

<br>

In this section you will do the following:
- Install the Ollama desktop app
- Download the MedGemma GGUF BF16 model from HuggingFace
- Install the uv Python package manager
- Install ffmeg
- Start the app by double clicking a file

<br>

```
--------------------------------------------------------------
System Requirements
--------------------------------------------------------------

Operating System: MacOS
Computer: Apple Silicon Mac (M1, M2, M3, M4)
RAM: 16GB
Free disk Space: 10GB

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

Now that the setup is complete, in future simply double-click the start-mac-app.command file
to launch the app.
The project folder must be placed on your desktop before the app is launched.

You could start the app and leave it running in the background all day.
Then whenever you want to use it, enter the following url in your browser:

http://127.0.0.1:5000/

Your browser will remember this local address so you won't have to.


--------------------------------------------------------------
Troubleshooting
--------------------------------------------------------------

1. It will take a few seconds to get a response to your first message because Ollama needs to load the model.
Subsequent responses will be much faster.

2. If the app doesn't start, make sure Ollama is running (look for its icon in your menu bar)

3. If you see "connection refused", restart Ollama

4. Inference time will increase as you increase the context size setting.

5. Expect inference time to be longer when submitting large images or pdf files.

6. For the voice (TTS) to work Kokoro needs two files: kokoro-v1.0.onnx, and voices-v1.0.bin.
These files are auto downloaded during the setup process.
However, if the voice is not working then please download these files manually and
place them in the project folder:

kokoro-v1.0.onnx: https://github.com/thewh1teagle/kokoro-onnx/releases/download/model-files-v1.0/kokoro-v1.0.onnx

voices-v1.0.bin: https://github.com/thewh1teagle/kokoro-onnx/releases/download/model-files-v1.0/voices-v1.0.bin


```


<br>

## Technologies Used

<strong>Backend:</strong> Flask (HTTP), Flask-SocketIO (WebSockets), Ollama Python<br>
<strong>Frontend:</strong> HTML, Tailwind CSS, JavaScript<br>
<strong>File Processing:</strong> PyMuPDF (for PDFs)<br>
<strong>Speech-to-Text:</strong> OpenAI Whisper<br>
<strong>Text-to-Speech:</strong> Kokoro TTS

<br>

## Legal Note (U.S. Only)

While this tool removes the need for Business Associate Agreements (BAAs) by keeping data off the cloud, clinicians remain "Covered Entities" under HIPAA. Using an offline tool shifts the responsibility for data protection from a cloud provider to the local practice.


<br>

## Notes

- Because MedGemma-1.5 is a reasoning model, I've set up the app to disable voice output when the MedGemma-1.5 model is selected.
- For best results when using your voice - use a headset or earphones with a mic. This reduces background noise. It also allows for a more relaxed chat because you won't have to constantly focus on being clearly heard by the speech to text system.

- When setting up an AI tool that uses voice, it helps to tell it (in the system message) not to use markdown - or else the AI will speak the markdown symbols out loud.
- When creating tools that will generate math notation, you need to tell the model to use LaTeX when generating math notation. Please add this note to the system message: Use LaTeX notation for mathematical or scientific expressions.

- Whisper is an LLM, and it can hallucinate. It sometimes generates random text like "Thank you for watching!". This text then gets converted in to speech.

<br>

## References

- Ollama: Running Hugging Face GGUF models just got easier!<br>
  Learn Data with Mark<br>
  https://www.youtube.com/watch?v=-iJMVIT4PYE

- unsloth/medgemma-4b-it-GGUF model on HuggingFace<br>
ollama run hf.co/unsloth/medgemma-4b-it-GGUF:BF16<br>
https://huggingface.co/unsloth/medgemma-4b-it-GGUF/tree/main

- unsloth/medgemma-1.5-4b-it-GGUF on HuggingFace<br>
ollama run hf.co/unsloth/medgemma-1.5-4b-it-GGUF:BF16<br>
https://huggingface.co/unsloth/medgemma-1.5-4b-it-GGUF/tree/main

- ollama<br>
  https://github.com/ollama/ollama

- ollama-python<br>
  https://github.com/ollama/ollama-python

- flask<br>
  https://github.com/pallets/flask

- kokoro-onnx<br>
  https://github.com/thewh1teagle/kokoro-onnx

- whisper<br>
  https://github.com/openai/whisper

- PyMuPDF<br>
  https://github.com/pymupdf/PyMuPDF


<br>

## Revision History

Version 1.0<br>
22-Jan-2026<br>
Prototype. Released for demonstration.

<br>


> <strong> There is no patent. Could you patent the sun?</strong><br>
> <i>Jonas Salk<br>
> (Creator of the first polio vaccine)</i>


