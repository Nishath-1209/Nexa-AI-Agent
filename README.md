# Nexa-AI-Agent



30 Days of Voice Agents Challenge 🚀

Welcome to the repository for my **30 Days of Voice Agents Challenge**! This project documents the journey of building a sophisticated, voice-activated conversational AI from scratch. Over the course of this challenge, a simple web page evolves into a fully interactive voice agent capable of holding context-aware conversations.

## 🤖 About The Project

This project is a hands-on guide to building a voice-based conversational AI using modern web technologies and powerful AI APIs.  

- Engage in **voice-to-voice conversation** with an AI powered by Google's Gemini LLM.  
- The agent **remembers context** of your conversation, enabling natural follow-ups.  
- Each day of the challenge represents a **progressive development step**, from setting up the server to implementing full conversational memory.

---

## ✨ Key Features

- **Voice-to-Voice Interaction:** Speak to the agent and receive a spoken response.  
- **Contextual Conversations:** Maintains chat history for intelligent follow-ups.  
- **End-to-End AI Pipeline:** Integrates STT → LLM → TTS seamlessly.  
- **Modern & Intuitive UI:** Single-button control with visual feedback for different states (ready, recording, thinking).  
- **Robust Error Handling:** Fallback audio ensures smooth user experience on API failure.  

---

## 🛠️ Tech Stack

**Backend:**
- FastAPI – high-performance asynchronous API server  
- Uvicorn – ASGI server for FastAPI  
- Python-Dotenv – secure environment variable management  

**Frontend:**
- HTML, CSS, JavaScript – structure, styling, and logic  
- TailwindCSS – modern, responsive styling  
- MediaRecorder API – capture audio in-browser  

**AI & Voice APIs:**
- **Murf AI:** High-quality TTS  
- **AssemblyAI:** Fast STT transcription  
- **Google Gemini:** Large Language Model (LLM) for responses  

---

## ⚙️ Architecture

The application follows a **client-server architecture**:

1. **Client** captures user's voice using MediaRecorder API.
2. **Server (FastAPI)** receives audio.
3. Audio is sent to **AssemblyAI** → Transcribed text.
4. Chat history is appended → sent to **Google Gemini LLM** for response.
5. LLM response → sent to **Murf AI** → TTS audio.
6. Client plays audio → UI updates ready state.

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
git clone
pip install -r requirements.txt
Environment Variables

Create a .env file in the directory:

MURF_API_KEY="your_murf_api_key_here"
ASSEMBLYAI_API_KEY="your_assemblyai_api_key_here"
GEMINI_API_KEY="your_gemini_api_key_here"

Running the App
uvicorn main:app --reload
Open your browser: http://localhost:8000
```
Important: Grant microphone permissions when prompted.

🎤 How to Use This Thing

1.Click the Start Recording button.

2.Speak naturally – ask questions, tell jokes, or converse freely.

3.Click Stop when done.

4.Wait a few seconds while the AI processes your input.

5.Listen to the AI’s spoken response.

6.Continue conversation; the AI remembers prior context.

| Endpoint                      | Method | Description                              |
| ----------------------------- | ------ | ---------------------------------------- |
| `/`                           | GET    | Main web interface                       |
| `/transcribe/file`            | POST   | Upload audio for transcription           |
| `/agent/chat/{session_id}`    | POST   | Full conversation pipeline               |
| `/agent/history/{session_id}` | GET    | Retrieve conversation history            |
| `/agent/history/{session_id}` | DELETE | Clear conversation history               |
| `/generate-audio`             | POST   | Convert text to speech                   |
| `/llm/query`                  | POST   | Query AI with audio input                |
| `/health`                     | GET    | Check system status and API availability |
☁️ Deploying to Render (Free Tier)

Fast path:

Push repo to GitHub.

In Render, create Web Service from repo.

Set:

Build Command: pip install -r requirements.txt

Start Command: uvicorn main:app --host 0.0.0.0 --port $PORT

Runtime: Python 3.11

Add environment variables from .env file.

Render auto-provisions if using render.yaml.
Health check path: /health.

WebSocket Endpoints:

/ws/turn-detection (primary)

/ws/streaming (optional/advanced)

📝 Notes

Public URL will be HTTPS; static files served at /static.

Ensure your browser allows microphone access.

API keys are stored locally in browser and used only for the current session.
