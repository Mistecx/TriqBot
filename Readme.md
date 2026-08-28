# 🚀 TRIQ BOT — Windows AI PC Assistant & Remote Controller

<p align="center">
  <img src="https://i.postimg.cc/jdppJRM3/icon.png" width="120" height="120" alt="TRIQ BOT Logo" />
</p>

<p align="center">
  <strong>An ultra-fast, local-first PC assistant and remote controller powered by Google Gemini & OpenRouter LLMs.</strong><br>
  <em>Manage, automate, inspect, and interact with your Windows PC seamlessly from a desktop Command Center or anywhere on the go via Telegram.</em>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Windows%2010%20%7C%2011-0078D6?style=for-the-badge&logo=windows&logoColor=white" />
  <img src="https://img.shields.io/badge/Framework-Electron%20%2B%20Express-47848F?style=for-the-badge&logo=electron&logoColor=white" />
  <img src="https://img.shields.io/badge/AI%20Engines-Gemini%20%7C%20OpenRouter-8E75B2?style=for-the-badge&logo=google&logoColor=white" />
  <img src="https://img.shields.io/badge/Remote-Telegram%20Bot-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white" />
  <img src="https://img.shields.io/badge/Made%20by-Mistecx-a78bfa?style=for-the-badge" />
</p>

---

## ⚡ What is TRIQ BOT?

**TRIQ BOT** is a private, lightweight, and token-efficient desktop assistant built by **Mistecx**. It transforms natural conversational prompts into safe, structured system operations on your Windows machine using native LLM tool calling.

Whether you're sitting in front of your desktop using the glassmorphic Command Center or away from home messaging your private Telegram bot, TRIQ BOT executes tasks on demand with zero latency and complete privacy.

---

## 🌟 Core Highlights

### 🖥️ Native Windows Command & Control
- **PowerShell & CLI Execution**: Execute scripts, launch installed apps, inspect network status, manage processes, and handle administrative commands.
- **File System Management**: Read, write, search, transfer, and download files directly via chat or Telegram.
- **Live Desktop Snapshots**: Snap real-time desktop screenshots on demand and preview them directly in chat or receive high-res images in Telegram.
- **System Metrics Monitoring**: Live tracking of CPU load, RAM usage, and multi-disk partition capacities with zero layout-reflow performance.

### 📱 Secure Telegram Remote Gateway
- **Remote On-The-Go Control**: Message your bot from anywhere to run commands, check PC health, lock the workstation, or fetch documents.
- **Single-User Lock Security**: Strict authorization whitelist (`TELEGRAM_AUTHORIZED_USER_ID`) rejects unauthorized access attempts automatically.
- **Bi-directional File Transfers**: Send files to your PC or receive files generated on your computer directly in your Telegram chat.

### 🧠 Dual AI Engine Architecture
- **Google Gemini Direct**: Native high-speed function calling with `gemini-2.0-flash` or `gemini-2.5-flash` via Google AI Studio.
- **OpenRouter Multi-Model Gateway**: Connect to hundreds of open/closed models (Claude, Llama 3.1, Mistral, Qwen, DeepSeek, Nemotron).
- **Auto-Route Free Models**: Smart fallback toggle to route queries to verified free-tier models on OpenRouter to save API costs.
- **Custom System Instructions**: Inject custom personas, operational rules, or output formatting guidelines.

### 💎 Ultra-Smooth Glassmorphic Command Center
- **Performance Optimized**: GPU-composited tab transitions (`visibility: hidden` / `opacity`) with zero layout reflows and low-power background idling.
- **Interactive Execution Trace**: Expandable real-time trace log of CLI operations, function parameters, and status codes executed by the agent.
- **Adaptive Background Polling**: Automatic throttle & pause when minimized to system tray or running in the background.

### 🪟 Windows Integration & Background Silent Mode
- **System Tray Resident**: Starts cleanly in the Windows notification area tray with quick right-click controls.
- **Single-Instance Protection**: Prevents duplicate background processes when double-clicking desktop shortcuts.
- **Silent Boot Option**: One-click **Startup: ON / OFF** sidebar button to launch automatically on Windows boot silently without popping up on screen.

---

## 📸 Architecture & Design

```mermaid
graph TD
    UserLocal[Desktop User] -->|Local UI / 127.0.0.1| ExpressServer[Express Local Backend]
    UserRemote[Remote User via Phone] -->|Telegram Bot API| TgService[Telegram Bot Service]
    
    TgService --> ExpressServer
    ExpressServer --> ToolRouter{Tool Calling Router}
    
    ToolRouter -->|PowerShell & CLI| SysExec[System & Process Execution]
    ToolRouter -->|Screenshot Desktop| ScreenCap[Screen Capture Engine]
    ToolRouter -->|File IO / Registry| FileMgr[File & History Manager]
    ToolRouter -->|Resource Probes| Metrics[CPU / RAM / Disk Metrics]
    
    ExpressServer -->|HTTPS API| Gemini[Google Gemini Direct]
    ExpressServer -->|HTTPS API| OpenRouter[OpenRouter API]
```

## 📥 Download & Installation

TRIQ BOT is distributed as a standalone Windows Desktop application by **Mistecx**.

### 1. Download the Installer
Download the latest Windows Setup (`.exe`) from the official release channels:
- **Installer**: `TRIQ BOT Setup 1.0.0.exe` (Windows 10 / 11 64-bit)

### 2. Install & Launch
1. Run the installer and choose your preferred installation directory.
2. The installer will create a **Desktop Shortcut** and **Start Menu entry**.
3. Launch **TRIQ BOT** from your desktop or start menu.

### 3. Quick Initial Configuration
1. Open the in-app **Settings** modal via the sidebar button.
2. Enter your **Google Gemini** or **OpenRouter API Key**.
3. (Optional) Paste your **Telegram Bot Token** to enable remote control.
4. Click **Save Settings** — your credentials are encrypted and stored 100% locally on your device.

---

## 🎮 Telegram Remote Commands

| Command / Message | Action |
|---|---|
| `What is my CPU and RAM load?` | Queries hardware counters and returns formatted usage stats. |
| `Take a screenshot` | Captures current desktop screen and sends the photo to Telegram. |
| `Open Notepad and write hello` | Launches application and performs automated tasks. |
| `Run ipconfig /all` | Runs PowerShell command safely and streams output back. |
| `List files in C:\Downloads` | Lists directory contents with file sizes and dates. |
| `/status` | Direct hardware and uptime health check. |
| `/clear` | Clears conversation memory and resets session context. |

---

## 🔒 Security & Privacy Architecture

- **100% Localhost Bound**: The internal engine binds exclusively to `127.0.0.1` — no public ports are opened.
- **Zero Third-Party Telemetry**: Your prompts, traces, and files stay strictly between your computer, your private Telegram bot, and your selected AI provider.
- **Encrypted Local Storage**: API credentials and bot tokens are stored locally on your machine.
- **Single-User Lockout**: Any unauthorized Telegram user attempting to interact with your bot is immediately blocked and logged.

---

## 👨‍💻 Developer & Company

Built with ❤️ by **Mistecx**

- 👨‍💻 **Creator**: **Jayesh**
- 🌐 **Portfolio**: [lostxjayesh.netlify.app](https://lostxjayesh.netlify.app/)
- 🐙 **GitHub**: [@LostxJayesh](https://github.com/LostxJayesh)
- 📸 **Instagram**: [@lostxjayesh](https://www.instagram.com/lostxjayesh)
- 🐦 **Twitter / X**: [@jayesh__6z](https://x.com/jayesh__6z)
- 💬 **Discord**: [Join Community](https://discord.gg/bMrmBdctB)

---

## 📄 License & Copyright

**Copyright © 2026 Mistecx. All Rights Reserved.**

This software is proprietary and confidential. Unauthorized copying, distribution, modification, public display, reverse engineering, or decompilation of this software or any portion thereof is strictly prohibited.

*Disclaimer: TRIQ BOT executes native commands on your operating system based on LLM reasoning. Always verify system instructions and maintain active backups of critical data.*

