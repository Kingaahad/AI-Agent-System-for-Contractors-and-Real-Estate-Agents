````markdown
<h1 align="center">🔊🤖 AI Contact-Verification Agent<br>for Contractors & Real-Estate Pros</h1>

<p align="center">
  <img alt="Python" src="https://img.shields.io/badge/Python-3.8%2B-blue?logo=python">
  <img alt="Twilio"  src="https://img.shields.io/badge/Twilio-voice%20&%20sms-ff3533?logo=twilio">
  <img alt="OpenAI"  src="https://img.shields.io/badge/OpenAI-GPT-powered-25c47e?logo=openai">
  <img alt="License" src="https://img.shields.io/badge/License-MIT-lightgrey">
</p>

> **One call, zero friction:**  
> This agent picks up the phone, verifies the caller with AI-powered voice recognition, captures their details, and logs everything straight to Google Sheets—no manual data entry, no missed leads.

---

## ✨ Key Features

| Area | Highlights |
|------|------------|
| **📞 Phone Verification** | • AI speech-to-text & text-to-speech<br>• Multi-step identity checks<br>• Auto-retry on failure |
| **📇 Contact Capture** | • Name, email, phone, address grabbed in call<br>• Instant write-back to Google Sheets<br>• Full contact-history timeline |
| **🤖 AI Intelligence** | • GPT-analysis for confidence scoring<br>• Fraud / spam detection<br>• Natural-language dialog in multiple languages |
| **🎙️ Voice Interface** | • Customizable voice & speed<br>• Human-like pauses and confirmations<br>• Supports multilingual callers |
| **🔒 Security** | • Env-based secrets, no hard-coding<br>• Encrypted traffic end-to-end<br>• Rate-limiting & input sanitization |

---

## 🗺️  Table of Contents
1. [Prerequisites](#-prerequisites)    
2. [Quick Start](#-quick-start)    
3. [Configuration](#-configuration)    
4. [Project Structure](#-project-structure)    
5. [Usage](#-usage)    
6. [Error Handling](#-error-handling)    
7. [Security & Compliance](#-security--compliance)    
8. [Contributing](#-contributing)    
9. [License](#-license)

---

## 🛠️  Prerequisites
* **Python 3.8+**  
* **Twilio** voice-enabled phone number  
* **OpenAI** API key  
* **Google Cloud** project with **Sheets API** enabled  

---

## 🚀 Quick Start

```bash
# 1  Clone the repo
git clone https://github.com/<your-org>/real-estate-ai-agent.git
cd real-estate-ai-agent

# 2  Install deps
pip install -r requirements.txt

# 3  Add secrets
cp .env.example .env   # then paste your keys & IDs

# 4  Run the agent
python run.py
````

The server boots on **`http://localhost:5000`** and Twilio webhooks will hit `/voice`.

---

## ⚙️  Configuration (`.env`)

| Key                       | Description                      |
| ------------------------- | -------------------------------- |
| `TWILIO_ACCOUNT_SID`      | Your Twilio Account SID          |
| `TWILIO_AUTH_TOKEN`       | Twilio Auth Token                |
| `TWILIO_PHONE_NUMBER`     | Incoming call number             |
| `OPENAI_API_KEY`          | GPT access key                   |
| `GOOGLE_CREDENTIALS_FILE` | Service-account JSON             |
| `SPREADSHEET_ID`          | Target Google Sheet              |
| `PORT`                    | Local server port (default 5000) |

---

## 🗂️  Project Structure

```
real-estate-ai-agent/
├── src/
│   ├── agents/            # Business logic per role
│   ├── utils/             # Sheets, voice, verification helpers
│   └── main.py            # Flask / FastAPI endpoints
├── config/                # Central settings
├── run.py                 # Entrypoint
└── requirements.txt
```

---

## ▶️  Usage

1. **Incoming calls** hit `/voice` → agent greets and starts verification.
2. Answers are analysed by GPT; on success, contact data is pushed to Google Sheets in real time.
3. **Outbound calls** can be triggered with a simple POST to `/call`.
4. Query all verified contacts at `/contacts`.

---

## 🧰 Error Handling

* Auto-retry up to **3 times** if caller fails a step.
* Graceful fallbacks for Twilio / OpenAI / Sheets outages.
* Structured logs for every call & API request.

---

## 🔐 Security & Compliance

* Secrets live only in environment variables.
* All HTTP traffic served over **TLS** in production.
* Input sanitization prevents prompt & SQL injection.
* GDPR-ready: easy data export / deletion on request.

---

## 🤝 Contributing

1. **Fork** → `git switch -c feature/my-feature`
2. **Commit** with [Conventional Commits](https://www.conventionalcommits.org).
3. **Push** & open a Pull Request—CI will run tests automatically.

---

## 📝 License

Released under the **MIT License** – see [`LICENSE`](LICENSE) for full text.

---

> **Need help or a custom feature?**  Open an issue or drop us a line—let’s build something amazing together! 🚀

```
