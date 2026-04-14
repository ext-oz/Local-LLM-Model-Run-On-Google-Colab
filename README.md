# 🦙 Ollama + Open WebUI on Google Colab

> Run a powerful local LLM on a **free T4 GPU** — no paid API, no data leaks, no subscriptions.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR_USERNAME/YOUR_REPO/blob/main/ollama_openwebui_colab.ipynb)
![GPU](https://img.shields.io/badge/GPU-T4%20Free-76b900?logo=nvidia&logoColor=white)
![Ollama](https://img.shields.io/badge/Ollama-latest-black?logo=ollama)
![Open WebUI](https://img.shields.io/badge/Open%20WebUI-latest-4f8ef7)
![Tunnel](https://img.shields.io/badge/Tunnel-Pinggy-ff6b6b)

---

## 📸 Preview

```
✅ System packages installed.
✅ Ollama installed.
✅ Python packages installed.
✅ All dependencies ready — proceed to Step 2.

✅ Ollama is listening on port 11434.
✅ Model downloaded successfully.
✅ Model 'gemma4-uncensored' registered with Ollama.

🔗 Ollama API  →  https://xxxx.run.pinggy-free.link
🔗 Open WebUI  →  https://yyyy.run.pinggy-free.link

✅ Open WebUI is running — open your tunnel URL now.
```

---

## ✨ Features

- 🆓 **Completely free** — runs on Google Colab's free T4 GPU tier
- 🧹 **Clean output** — no log spam, only colored pass/fail status messages
- 🙈 **Hidden code** — cells show titles only, code is collapsed by default
- 🌐 **Public URL** — Pinggy tunnels expose both the API and the WebUI
- ⚡ **Skip re-downloads** — model download is skipped if already present
- 🔧 **Auto model registration** — GGUF is registered with Ollama automatically

---

## 🧱 Stack

| Tool | Purpose |
|---|---|
| [Ollama](https://ollama.com) | Local LLM runtime |
| [Open WebUI](https://github.com/open-webui/open-webui) | Chat interface |
| [Pinggy](https://pinggy.io) | Public tunnel (no ngrok account needed) |
| [Gemma-4 Uncensored Q8](https://huggingface.co/HauhauCS/Gemma-4-E4B-Uncensored-HauhauCS-Aggressive) | Default GGUF model (~7.5 GB) |

---

## 🚀 Quick Start

1. Click **Open in Colab** badge above
2. Go to **Runtime → Change runtime type → T4 GPU**
3. Run each cell **top to bottom**
4. Copy the **Open WebUI tunnel URL** from Step 5
5. Open it in your browser — done ✅

> ⏳ First run takes ~10 minutes (Ollama install + 7.5 GB model download)  
> ⚡ Subsequent runs are faster — model download is skipped automatically

---

## 📋 Notebook Structure

| Cell | What it does |
|---|---|
| 📦 **Download Dependencies** | Installs `zstd`, `lshw`, `pciutils`, Ollama, `pinggy`, `open-webui` |
| 🚀 **Start Ollama Server** | Launches Ollama and verifies it's listening on port 11434 |
| 📥 **Download Model** | Downloads the GGUF from HuggingFace (~7.5 GB) |
| 🔧 **Register Model** | Creates an Ollama `Modelfile` and registers the GGUF |
| 🔗 **Open Tunnels** | Starts two Pinggy tunnels — one for the API, one for WebUI |
| 🌐 **Launch Open WebUI** | Starts the WebUI server on port 8000 (runs in background) |

---

## 🔄 Using a Different Model

To swap the model, edit these two lines in the notebook:

```python
# Step 3 — change the URL to any GGUF on HuggingFace
MODEL_URL = "https://huggingface.co/YOUR_MODEL/resolve/main/model.gguf"

# Step 4 — change the name Ollama registers it as
MODEL_NAME = "my-model-name"
```

Any GGUF model from HuggingFace will work.

---

## ⚠️ Limitations

- Colab free tier sessions disconnect after **~12 hours** of inactivity
- Pinggy free tunnels have a **1 GB/day** bandwidth cap
- The T4 has **15 GB VRAM** — very large models (70B+) may not load

---

## 📄 License

MIT — free to use, modify, and share.
