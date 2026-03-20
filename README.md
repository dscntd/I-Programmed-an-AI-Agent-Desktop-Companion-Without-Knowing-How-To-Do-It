# R08 AI Agent (Learning Project)

This is my journey of building an AI desktop agent from scratch – without knowing Python at the start.

## What this is
A personal experiment where I document everything I learn while building an AI agent that can control my computer.

## Status: Work in progress 🚧
---

> *"I wanted ChatGPT in a Winamp skin. Now I'm building a real agent."*

On day 1 I didn't know how to open a .py script on Windows.
On day 13 I wrote my own .bat file and it WORKS! :D

R08 is a local desktop AI agent for Windows – built with PyQt6, Claude API and Ollama.
No cloud subscription, no monthly costs, no data sharing. Runs on your PC.

For info: I do NOT think I'm a great programmer, etc. It's about
HOW FAR I've come with 0% Python experience. And that's only because of AI :)

---

## What R08 can currently do

### 🧠 Intelligence
- **Dual-AI System** – Claude API (R08) for complex tasks, Ollama/Qwen local (Q5) for small talk
- **Automatic Routing** – the router decides who responds: Command Layer (0 Tokens), Q5 local, or Claude API
- **TRIGGER_R08** – when Q5 can't answer a question, it automatically hands over to Claude
- **Semantic Memory** – R08 remembers facts, conversations and notes via embeddings (sentence-transformers)
- **Northstar** – personal configuration file that tells R08 who you are and what it's allowed to do

### 👁️ Vision
- **Screen Analysis** – R08 can see the desktop and describe it
- **"What do you see?"** – takes a screenshot (960x540), sends it to Claude, responds directly in chat
- **Coordinate Scaling** – prepared for mouse/keyboard control in v3.0

### 🎵 Music
- **0-Token Music Search** – YouTube Audio directly via yt-dlp + VLC, cloud never reached
- **Genre Recognition** – finds real dubstep instead of Schlager 😄
- **Stop/Start** – controllable directly from chat

### 🖥️ Windows Control
- Open Notepad, Browser, Explorer
- Set volume
- Start timers
- Empty recycle bin
- All actions via voice input in chat

### 📅 Reminder System
- Save appointments with or without time
- Day-before reminder at 9:00 PM
- Hourly background check (0 Tokens)
- "Remind me on 20.03. about Mr. XY" → works

### 📁 File Management
- Save, read, archive, combine, delete notes
- RAG system – R08 searches stored notes semantically
- Logs and chat exports
- Own home folder: `r08_home/`

### 💬 Personality
- **R08** – confident desktop agent, dry humor, short answers
- **Q5** – nervous local intern, honest when it doesn't know something
- Expression animations: neutral, happy, sad, angry, loved, confused, surprised, joking, crying, loading
- Joke detection → shows joke face with 5 minute cooldown
- Idle messages when you don't write for too long

- Reason for this? You can't get rid of the noticeable transition from Haiku 4.5 to Ollama 7b!
Now that Ollama acts as an intern, it's at least funny instead of frustrating :D

### 🏗️ Workspace
- Large dark window with 5 tabs: Notes, Memory, LLM Routing, Agents, Code
- Memory management directly in the UI (Facts + Context entries)
- LLM Routing Log – shows live who answered what and what it cost
- Timer display, shortcuts, file browser
- **Freeze / Clear Context** button – deletes chat history, saves massive amounts of tokens

---

## Token Costs

| Action | Tokens | Cost |
|--------|--------|------|
| Play music | 0 | free |
| Change volume | 0 | free |
| Set timer | 0 | free |
| Check reminder | 0 | free |
| Normal chat message | ~600 | ~$0.0005 |
| Screen analysis (Vision) | ~1,000 | ~$0.0008 |
| Complex question | ~1,500 | ~$0.001 |

> Total cost of complete development so far: ~€1.30

---

## Tech Stack

```
Frontend:     PyQt6 (Windows Desktop UI)
KI Cloud:     Claude Haiku 4.5 via OpenRouter
KI Lokal:     Qwen2.5:7b via Ollama
Embeddings:   sentence-transformers (all-MiniLM-L6-v2)
Musik:        yt-dlp + VLC
Vision:       mss + Pillow + Claude Vision
Suche:        DuckDuckGo (kein API Key nötig)
Storage:      JSON (memory.json, reminders.json, settings.json)
```

---

Roadmap v3.0

    [ ] Mouse & Keyboard Control (pyautogui)
    [ ] Agent Loop with Feedback (max 5 Steps)
    [ ] ThreadPool + Request-ID System
    [ ] Tool Registry complete (already started ✅)

---

## 📺 Series on YouTube
- [Part 1 – Der Anfang](https://www.youtube.com/watch?v=CIJat1l2EJU)
- [Part 5 – R08 sieht meinen Desktop](https://www.youtube.com/watch?v=1H37PCjip40)

Why R08?
Because I wanted an assistant that runs on my PC, knows my files,
understands my habits – and doesn't cost a subscription every month.
And because "ChatGPT in a Winamp skin" somehow became a real project. 😄
