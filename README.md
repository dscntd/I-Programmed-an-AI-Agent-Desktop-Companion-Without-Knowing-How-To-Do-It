# R08 – Desktop KI-Agent

> *"Ich wollte ChatGPT in einem Winamp-Skin. Jetzt baue ich einen echten Agenten."*

R08 ist ein lokaler Desktop-KI-Agent für Windows – gebaut mit PyQt6, Claude API und Ollama.
Kein Cloud-Abo, keine monatlichen Kosten, keine Datenweitergabe. Läuft auf deinem PC.

---

## Was R08 aktuell kann

### 🧠 Intelligenz
- **Dual-AI System** – Claude API (R08) für komplexe Aufgaben, Ollama/Qwen lokal (Q5) für Smalltalk
- **Automatisches Routing** – der Router entscheidet wer antwortet: Command Layer (0 Tokens), Q5 lokal, oder Claude API
- **TRIGGER_R08** – wenn Q5 eine Frage nicht beantworten kann, übergibt er automatisch an Claude
- **Semantisches Memory** – R08 erinnert sich an Facts, Gespräche und Notizen via Embeddings (sentence-transformers)
- **Northstar** – persönliche Konfigurationsdatei die R08 mitteilt wer du bist und was er darf

### 👁️ Vision
- **Screen-Analyse** – R08 kann den Desktop sehen und beschreiben
- **"Was siehst du?"** – macht einen Screenshot (960x540), schickt ihn an Claude, antwortet direkt im Chat
- **Koordinaten-Skalierung** – vorbereitet für Maus/Tastatur-Steuerung in v3.0

### 🎵 Musik
- **0-Token Musiksuche** – YouTube Audio direkt via yt-dlp + VLC, Cloud wird nie erreicht
- **Genre-Erkennung** – findet echten Dubstep statt Schlager 😄
- **Stop/Start** – direkt aus dem Chat steuerbar

### 🖥️ Windows-Steuerung
- Notepad, Browser, Explorer öffnen
- Lautstärke setzen
- Timer starten
- Papierkorb leeren
- Alle Aktionen per Spracheingabe im Chat

### 📅 Reminder System
- Termine speichern mit oder ohne Uhrzeit
- Vortags-Erinnerung um 21:00 Uhr
- Stündlicher Background-Check (0 Tokens)
- "Erinnere mich am 20.03. an Herrn Kukulies" → funktioniert

### 📁 Datei-Management
- Notizen speichern, lesen, archivieren, kombinieren
- RAG-System – R08 durchsucht gespeicherte Notizen semantisch
- Logs und Chat-Exporte
- Eigener Home-Ordner: `r08_home/`

### 💬 Persönlichkeit
- **R08** – selbstsicherer Desktop-Agent, trockener Humor, kurze Antworten
- **Q5** – nervöser lokaler Praktikant, ehrlich wenn er etwas nicht weiß
- Ausdrucks-Animationen: neutral, happy, sad, angry, loved, confused, surprised, joking, crying, loading
- Witz-Erkennung → zeigt Witz-Gesicht mit 5 Minuten Cooldown
- Idle-Messages wenn du zu lange nichts schreibst

### 🏗️ Workspace
- Großes dunkles Fenster mit 5 Tabs: Notizen, Memory, LLM Routing, Agents, Code
- Memory-Verwaltung direkt im UI (Facts + Kontext-Einträge)
- LLM Routing Log – zeigt live wer was beantwortet hat und was es kostet
- Timer-Anzeige, Shortcuts, Datei-Browser
- **Freeze / Clear Context** Button – löscht Chat-Verlauf, spart massiv Tokens

---

## Token-Kosten

| Aktion | Tokens | Kosten |
|--------|--------|--------|
| Musik abspielen | 0 | gratis |
| Lautstärke ändern | 0 | gratis |
| Timer setzen | 0 | gratis |
| Erinnerung prüfen | 0 | gratis |
| Normale Chat-Nachricht | ~600 | ~$0.0005 |
| Screen-Analyse (Vision) | ~1.000 | ~$0.0008 |
| Komplexe Frage | ~1.500 | ~$0.001 |

> Gesamtkosten der kompletten Entwicklung bis jetzt: ~1,30€

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

## Roadmap v3.0

- [ ] Maus & Tastatur Steuerung (pyautogui)
- [ ] Agenten-Loop mit Feedback (max 5 Steps)
- [ ] ThreadPool + Request-ID System
- [ ] Tool Registry vollständig (bereits gestartet ✅)

---

## Start

```bat
# r08_start.bat ausführen
# Aktiviert venv + setzt alle env vars automatisch
```

---

## Warum R08?

Weil ich einen Assistenten wollte der **auf meinem PC läuft**, meine Dateien kennt, 
meine Gewohnheiten versteht – und nicht jeden Monat ein Abo kostet.

Und weil "ChatGPT in einem Winamp-Skin" irgendwie zu einem echten Projekt geworden ist. 😄
