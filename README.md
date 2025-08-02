 WhatsApp-Driven-Google-Drive-Assistant-
Here's a complete `README.md` for your **WhatsApp-Driven Google Drive Assistant** project, ready to be added to your GitHub repository:

---

````markdown
# 📁 WhatsApp-Driven Google Drive Assistant (n8n Workflow)

A powerful automation tool built using **n8n**, allowing users to interact with **Google Drive** through simple **WhatsApp messages**. Perform tasks like listing files, deleting, moving documents, and generating AI-powered summaries — all via chat.

---

## 🚀 Features

- ✅ WhatsApp-driven commands (via Twilio or WhatsApp Cloud API)
- 📂 List, delete, and move Google Drive files/folders
- 🧠 AI summaries of PDF, DOCX, and TXT files using GPT-4o
- 🛡️ Logging and confirmation safeguards for sensitive actions
- 📊 Auto-audit to Google Sheets
- 🐳 Easy deployment with Docker
- ⚙️ OAuth2-secured access to user’s Google Drive

---

## 📸 Example Commands

```bash
LIST /ProjectX
DELETE /ProjectX/report.pdf
MOVE /ProjectX/report.pdf /Archive
SUMMARY /ProjectX
````

---

## 🧩 Workflow Overview

```text
[Twilio WhatsApp Message] → [n8n Webhook] → [Command Parser]
                          ↓
                  [Google Drive Operations]
                          ↓
                  [AI Summarizer (GPT-4o)]
                          ↓
                    [Audit & Logging]
```

---

## 🛠️ Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/whatsapp-gdrive-assistant.git
cd whatsapp-gdrive-assistant
```

### 2. Configure `.env`

Create a `.env` file based on the provided `.env.example`:

```env
GENERIC_TIMEZONE=Asia/Kolkata
N8N_BASIC_AUTH_ACTIVE=true
N8N_BASIC_AUTH_USER=admin
N8N_BASIC_AUTH_PASSWORD=yourpassword
N8N_HOST=localhost
N8N_PORT=5678
```

### 3. Set Up Google Drive API

* Go to [Google Cloud Console](https://console.cloud.google.com/)
* Enable Google Drive API
* Create OAuth2 Credentials
* Add Redirect URI: `https://<your-n8n-host>/rest/oauth2-credential/callback`

### 4. Set Up WhatsApp Channel

Use either:

#### Twilio Sandbox

* Signup at [twilio.com/whatsapp](https://www.twilio.com/whatsapp)
* Link Sandbox → Set webhook URL to:

  ```
  https://<your-n8n-domain>/webhook/whatsapp
  ```

#### Meta WhatsApp Cloud API

* Follow [Meta docs](https://developers.facebook.com/docs/whatsapp/cloud-api/) to set up webhook and API credentials.

---

## 🧠 AI Summarization Setup

* Uses **OpenAI GPT-4o**
* Requires OpenAI API Key (you’ll add this in n8n → HTTP Request node)

Prompt Template:

```txt
Summarise the following document into bullet points:

{{DocumentText}}
```

---

## 🐳 Docker Deployment

### 1. Run n8n using Docker Compose

```bash
docker-compose up -d
```

* Access your instance at: [http://localhost:5678](http://localhost:5678)

### 2. Import Workflow

* Open the n8n dashboard
* Click **Import Workflow**
* Select `whatsapp-gdrive-assistant-workflow.json` from this repo

---

## 🛡️ Logging & Safety

* All commands and operations are logged to a Google Sheet (timestamp, user, action)
* DELETE operations require confirmation format:

```bash
CONFIRM DELETE /ProjectX/file.txt
```

---

## 📁 Folder Structure

```
📦 whatsapp-gdrive-assistant/
├── .env.example
├── docker-compose.yml
├── whatsapp-gdrive-assistant-workflow.json
├── README.md
└── docs/
    └── flowchart.png  (optional visuals)
```

---

## 🤖 Tech Stack

* [n8n](https://n8n.io/)
* [Google Drive API](https://developers.google.com/drive)
* [Twilio WhatsApp API](https://www.twilio.com/whatsapp)
* [OpenAI GPT-4o](https://platform.openai.com/)
* Docker

---

## ✍️ Author

**Shubham Namdeo**
AI/ML Intern • Builder • Automation Enthusiast

---

## 📄 License

This project is open source under the [MIT License](LICENSE).

---

> ℹ️ If you like this project, consider giving it a ⭐️ on GitHub!

```

---

Let me know if you'd like me to:
- Generate and send the full project files as a `.zip`
- Deploy it for you on [n8n.cloud](https://n8n.cloud/)
- Include a badge (e.g., Docker ready, OpenAI powered, etc.)

Ready when you are.
```
