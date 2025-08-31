# 🎧 Personal Audiobook Studio

**Turn any PDF into an audiobook in *your own voice*.**  
OCR ➜ Text Extraction ➜ Chunking ➜ **Deepgram TTS** ➜ **OpenVoice** voice conversion ➜ MP3 in a minimal **Gradio** UI.

> Live Demo : [https://huggingface.co/spaces/your-username/personal-audiobook-studio  ](https://huggingface.co/spaces/ZainabEman/Personal_Audiobook_Studio/tree/main)
> Blog : [https://medium.com/@your-handle/personal-audiobook-studio](https://medium.com/@zainabeman976/personal-audiobook-studio-turn-any-pdf-into-an-audiobook-in-your-own-voice-745ce97ac805)

---

<img width="1115" height="647" alt="Image" src="https://github.com/user-attachments/assets/fd997357-0809-4417-b083-290da3df1cb7" />

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
- **Deploy**: Hugging Face Spaces (`requirements.txt`, `packages.txt`)


<img width="1536" height="1024" alt="Image" src="https://github.com/user-attachments/assets/ea999eab-2b64-425b-845c-22b3248aef1f" />
---

