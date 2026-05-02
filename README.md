## 🧠 Architecture Overview

This system is a real-time AI voice agent designed to handle live phone conversations with low latency. It uses a streaming pipeline over WebSockets to process audio, generate responses, and return synthesized speech in near real-time.

---

## ⚙️ How It Works

1. **Call Initiation**

   * A user calls via Twilio
   * Twilio streams live audio to the backend via WebSockets

2. **Speech-to-Text (STT)**

   * Audio stream is forwarded to AssemblyAI
   * Real-time transcription is generated continuously

3. **LLM Processing**

   * Transcribed text is sent to Groq (LLM)
   * The model generates contextual responses with low latency

4. **Text-to-Speech (TTS)**

   * Response text is converted to speech using ElevenLabs
   * Audio is streamed back instantly

5. **Response Delivery**

   * Synthesized voice is sent back through Twilio
   * User hears the AI response in real time

---

## 🔄 Data Flow

User Voice
→ Twilio (Call Handling)
→ WebSocket Stream
→ AssemblyAI (STT)
→ Groq (LLM Processing)
→ ElevenLabs (TTS)
→ Twilio
→ User

---

## 🧩 System Design

* **Streaming-first architecture** for minimal latency
* **WebSocket-based communication** for real-time audio flow
* **Modular pipeline** (STT → LLM → TTS)
* Easily extensible for multi-agent or tool-using systems

---

## 🚀 Key Features

* Real-time, bidirectional voice interaction
* Low-latency response pipeline
* Scalable design (can support multiple concurrent calls)
* Clean separation of services (STT, LLM, TTS)

---

## 🛠️ Tech Stack

* **Backend:** FastAPI
* **Realtime Transport:** WebSockets
* **Telephony:** Twilio
* **STT:** AssemblyAI
* **LLM:** Groq
* **TTS:** ElevenLabs

---

## 📌 Notes

* Optimized for speed using streaming instead of batch processing
* Designed to simulate natural conversation flow
* Can be extended with memory, tools, or agent workflows

---
