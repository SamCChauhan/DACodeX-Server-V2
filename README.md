# DACodeX-Server-V2 🚀

**DACodeX** is a high-performance, multimodal AI Coding Mentor built for the classroom. It utilizes the Google Gemini 2.5 Flash-Lite model to help students debug, understand, and write code through an interactive, teacher-inspired interface. 

This version is optimized to run as a **Local Network Server**, allowing you to host the "brain" on your computer while sharing the "interface" globally.

---

## ✨ Features

* **Multimodal Vision:** Analyze screenshots of code, logic flowcharts, or compiler errors.
* **Teaching Protocols:** Toggle between Socratic (hint-based) and Direct (instruction-based) learning.
* **Curriculum Aware:** Pre-configured for AP CS A, Python, JavaScript, C++, and more.
* **Session Archiving:** Save current chats to a local history and download transcripts as `.txt` files.
* **Isolated User States:** Supports multiple simultaneous connections; every user gets a unique, private chat session.
* **Neon Red UI:** A sleek, developer-focused dark theme built with NiceGUI.

---

## 🛠️ Prerequisites

Before starting, ensure you have the following installed:

* **Python 3.10+**
* **ngrok** (Installed via `winget install Ngrok.Ngrok` or from the [official site](https://ngrok.com/))
* **Google Gemini API Key** (Obtainable from [Google AI Studio](https://aistudio.google.com/))

---

## 🚀 Complete Setup & Execution Guide

### Step 1: Install Dependencies
Open your terminal (PowerShell or Bash) and run:
```bash
pip install nicegui google-genai pillow
```

### Step 2: Configure your API Key
You must set your API key as an environment variable so the code can access it securely.

**Windows (PowerShell):**
```powershell
$env:GOOGLE_API_KEY="your_actual_api_key_here"
```

**Linux / Mac / WSL:**
```bash
export GOOGLE_API_KEY="your_actual_api_key_here"
```

### Step 3: Launch the DACodeX Server
Run the Python script. This starts the backend and the web interface on your local machine.
```bash
python dacodex_server.py
```
> **Note:** The app is configured to run on Port `8081` to avoid common system conflicts.

### Step 4: Open the Global Tunnel (ngrok)
To let friends access the app from outside your Wi-Fi, open a **new** terminal tab and run:
```bash
ngrok http 8081
```

---

## 🌐 Accessing the App

* **On your computer:** Open `http://localhost:8081` in any browser.
* **On your phone/Globally:** Copy the Forwarding URL provided by the ngrok terminal (e.g., `https://hasteful-jennette.ngrok-free.app`).

---

## 🔧 Troubleshooting

**Error: `[Errno 10048] Port already in use`**
* This means another process is still using Port `8081`. Press `Ctrl + C` in all terminal windows to kill old processes and try again.

**Error: Authentication failed (ngrok)**
* Ensure you have added your authtoken to ngrok:
    ```bash
    ngrok config add-authtoken <your-token-from-dashboard>
    ```

---

## 🔒 Privacy & Security

* **API Security:** This project uses Environment Variables. **Never** hardcode your API Key into the `.py` file before pushing to a public repository.
* **Data Handling:** Chat data is stored in volatile memory (RAM) and is cleared once the server script is stopped.
