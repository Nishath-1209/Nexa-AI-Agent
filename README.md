# Nexa-AI-Agent  
🚀 30 Days of Voice Agents Challenge  

Welcome to the repository for my **30 Days of Voice Agents Challenge**!  
This project documents the journey of building a sophisticated, voice-activated conversational AI from scratch.  
Over the course of this challenge, a simple web page evolved into a **fully interactive voice agent** capable of holding context-aware conversations.  

---

## 🤖 About The Project
This project is a hands-on guide to building a **voice-based conversational AI** using modern web technologies and powerful AI APIs.  

- Engage in **voice-to-voice conversation** with an AI powered by Google’s **Gemini LLM**.  
- The agent **remembers context** of your conversation, enabling natural follow-ups.  
- Each day of the challenge represents a progressive step — from setting up the server to implementing **full conversational memory** and special skills.  

---

## ✨ Key Features
- 🎤 **Voice-to-Voice Interaction** – Speak to the agent and receive a spoken response.  
- 🧠 **Contextual Conversations** – Maintains chat history for intelligent follow-ups.  
- ⚡ **End-to-End AI Pipeline** – Integrates STT → LLM → TTS seamlessly.  
- 🎨 **Modern & Intuitive UI** – Single-button control with visual feedback for states (ready, recording, thinking).  
- 🛡️ **Robust Error Handling** – Fallback audio ensures smooth user experience on API failure.  
- 🌦️ **Weather Updates** – Ask the agent for live weather information.  
- 📰 **Latest News Headlines** – Get quick updates on trending news.  
- 🤣 **Pirate Jokes Mode** – Switch persona for fun & engaging conversations.  

---

## 🛠️ Tech Stack

### Backend
- **FastAPI** – High-performance asynchronous API server  
- **Uvicorn** – ASGI server for FastAPI  
- **Python-Dotenv** – Secure environment variable management  

### Frontend
- **HTML, CSS, JavaScript** – Structure, styling, and logic  
- **TailwindCSS** – Modern, responsive styling  
- **MediaRecorder API** – Capture audio in-browser  

### AI & Voice APIs
- **Murf AI** – High-quality Text-to-Speech (TTS)  
- **AssemblyAI** – Fast Speech-to-Text (STT)  
- **Google Gemini** – Large Language Model for responses  

---

## ⚙️ Architecture
The application follows a **client-server architecture**:

1. Client captures user's voice using **MediaRecorder API**.  
2. Server (**FastAPI**) receives audio.  
3. Audio → **AssemblyAI** → Transcribed text.  
4. Chat history + transcript → **Google Gemini LLM** for response.  
5. LLM response → **Murf AI** → Speech output.  
6. Client plays the audio → UI updates to ready state.  

---

## 🚀 Getting Started

### Prerequisites
- Python 3.8+  
- API keys for:  
  - Murf AI  
  - AssemblyAI  
  - Google Gemini  

### Installation
```bash
git clone https://github.com/your-username/Nexa-AI-Agent.git
cd Nexa-AI-Agent
pip install -r requirements.txt
Environment Variables
Create a .env file in the project root:

bash
Copy code
MURF_API_KEY="your_murf_api_key_here"
ASSEMBLYAI_API_KEY="your_assemblyai_api_key_here"
GEMINI_API_KEY="your_gemini_api_key_here"
Running the App
bash
Copy code
uvicorn main:app --reload
Open your browser at: http://localhost:8000

⚠️ Important: Grant microphone permissions when prompted.

🎤 How to Use
Click Start Recording.

Speak naturally – ask questions, tell jokes, or request weather/news.

Click Stop when done.

Wait a few seconds while the AI processes your input.

Listen to the AI’s spoken response.

Continue chatting – the AI remembers context!

📡 API Endpoints
Endpoint	Method	Description
/	GET	Main web interface
/transcribe/file	POST	Upload audio for transcription
/agent/chat/{session_id}	POST	Full conversation pipeline
/agent/history/{session_id}	GET	Retrieve conversation history
/agent/history/{session_id}	DELETE	Clear conversation history
/generate-audio	POST	Convert text to speech
/llm/query	POST	Query AI with audio input
/health	GET	Check system status & API availability

☁️ Deployment (Render Free Tier)
Steps:

Push repo to GitHub.

In Render, create a Web Service from the repo.

Configure:

Build Command: pip install -r requirements.txt

Start Command: uvicorn main:app --host 0.0.0.0 --port $PORT

Runtime: Python 3.11

Add environment variables from .env file.

Health check path: /health

WebSocket Endpoints:

/ws/turn-detection (primary)

/ws/streaming (optional / advanced)

🔮 Roadmap / Future Work
🌍 Multi-language support.

🗣️ Real-time translation mode (English ↔ Hindi, etc.).

⏰ Reminder & task management (alarms, to-do lists).

🎵 Music playback integration.

📱 Package as a PWA for mobile-friendly use.

🙌 Acknowledgements
Murf AI – High-quality TTS (#BuildwithMurf).

AssemblyAI – Fast & accurate STT.

Google Gemini – Contextual conversational power.

30 Days of Voice Agents Challenge – For inspiring this journey.

📌 Challenge Progress
This project is part of the #30DaysofVoiceAgents challenge.
Check out my LinkedIn updates where I share daily progress 🚀.

---

✅ This is a **ready-to-use final README.md**.  
