<!-- spell-checker:words CUDA LMStudio Qwen GGUF -->

# LM Studio Starter Guide
### Install it, download a model, chat with a private AI on your own machine

LM Studio is a free desktop app that lets you run open AI chat models (like Llama, Gemma, Qwen and Mistral) **entirely on your own computer**. No account, no subscription, and your conversations never leave your machine. It's point-and-click — no command line needed. This sheet takes you from nothing to your first chat.

---

## ⚠️ Step 0 — Check your hardware first

Chat models are limited mainly by **RAM** (your computer's memory). A graphics card (GPU) makes things faster but isn't essential. On Apple Silicon Macs, the unified memory counts as both.

| Your RAM | What you can run comfortably | Notes |
|---|---|---|
| 8 GB | Small models (3B–4B) | Fine for a first try |
| 16 GB | 7B–8B models — the sweet spot for most people | Recommended starting point |
| 32 GB | 13B–14B models | Noticeably smarter answers |
| 64 GB+ | 30B and larger | Power-user territory |

A few hardware notes:
- **NVIDIA GPU** (CUDA) gives the biggest speed boost; **Apple Silicon** (M1 or newer) is excellent; AMD has partial support.
- **No dedicated GPU?** It still works on the processor alone — just slower. A small model is the way to go.
- You don't have to memorise model sizes — LM Studio checks your specs for you and flags which models will fit (see Step 2).

To check RAM: **Windows** → Task Manager (`Ctrl+Shift+Esc`) → Performance → Memory. **Mac** →  menu → About This Mac.

---

## Step 1 — Install LM Studio

1. Go to [**lmstudio.ai** ](https://lmstudio.ai/)and click **Download** — the site automatically offers the right version for your operating system (Windows, macOS, or Linux).
2. Install it:
   - **Windows:** double-click the `.exe` and follow the prompts (~1–2 minutes).
   - **Mac:** open the `.dmg` and drag LM Studio into your **Applications** folder.
   - **Linux:** make the `.AppImage` executable and run it.
1. Open LM Studio. 

> **Requirements:** Windows 10 or newer, macOS 14+ (Apple Silicon only), or Linux.

---

## Step 2 — Download your first model

When you open LM Studio the model library starts empty. You pick a model and download it from inside the app.

1. Click the **Model Search** tab — the **magnifying-glass icon** in the left sidebar.
2. Search for a beginner-friendly model, like Gemma 4 E2B.
3. Select that item from the search result and click Download.
4. Once the model is downloaded click on "Use in New Chat"

---

## Step 3 — Have your first chat.

1. Type a message in the box at the bottom and hit enter. That's it — you're talking to an AI running entirely on your computer, even with the Wi-Fi off. 🎉


**A few settings worth knowing**:
- Configuration menu:
	- Open the side panel by clicking the following button on the top right of the chat window:
		![Side panel button](images/Screenshot%202026-06-26%20at%2012.47.40.png)
	- Inside this paper you can configure model parameters: 
		- **System prompt** — a standing instruction that shapes how the model behaves (e.g. *"You are a concise study tutor."*).
		- **Custom Fields** - In there you can enable or disable the "Thinking" feature. While "thinking", enables the model to engage in "deep-thought" before producing a final a answer, disabling it can lead to quicker generation of answers.
		- **Settings** - In this section we can find the "Temperature" parameter. A higher temperature leads to more create/random answers, while lower lead to more focused and deterministic answers. ~0.7 is a sensible default. Another parameter is this section is Limit Response Length, which allows setting a maximum token response length.
- Modal Load Setting Menu:
	- Open the model load setting menu ![Modal load setting menu](images/Screenshot%202026-06-26%20at%2013.11.15.png)
	- In here you can change the **Context length**, which how much text the model can "remember" at once. Different models have different capacities, reducing this number lead to quicker answer but leads to model "forgetting" parts of the conversation.
- Change currently loaded model menu:
	- Open the model menu by clicking here:
		![Model menu](images/Screenshot%202026-06-26%20at%2013.17.20.png)
	- In this menu you can select another model you have on your local machine.
---

## Step 4 — Useful things to try next

- Drag an image into the message box and ask to the model what it sees in the image.
- **Chat with your own documents (offline).** Click the **+** in the chat box and attach a **PDF, DOCX or TXT** file — lecture notes, a paper, a reading. The model can then answer questions about it, and the file never leaves your machine.
- **Try different models** and feel the difference — a 3B vs an 8B model on the same question is a genuinely interesting comparison.
- **Set a system prompt** to turn the model into a specific helper: a coding tutor, an essay feedback bot, a translator.
- **(Advanced) Local API server.** Under the **Developer** tab you can start a server on `localhost:1234` that mimics the OpenAI API, so your own code or scripts can call the local model. Useful if anyone's building a project.

---

**Where your models live** (if you ever need to find or delete them to free space):
- **Windows:** `C:\Users\YourName\.lmstudio\models`
- **Mac / Linux:** `~/.lmstudio/models`

---

## Mini glossary

- **LLM** — Large Language Model; the AI that generates text replies.
- **Model** — a single downloadable AI "brain," usually a `.gguf` file.
- **GGUF** — the file format LM Studio uses to run models efficiently on normal hardware.
- **Quantisation (Q4, Q8…)** — how much a model is compressed; lower numbers are smaller and faster but slightly less capable.
- **RAM** — your computer's memory; the main limit on which models you can run.
- **Context length** — how much conversation/text the model can keep in mind at once.
- **System prompt** — a hidden instruction that sets the model's role and behaviour.
- **RAG** — the feature that lets the model read documents you attach and answer questions about them.
