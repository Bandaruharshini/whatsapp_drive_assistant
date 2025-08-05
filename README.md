# WhatsApp-Driven Google Drive Assistant

##  Objective
Control your Google Drive using WhatsApp messages via an n8n workflow.

##  Tools Used
- n8n
- Twilio (WhatsApp Sandbox)
- Google Drive API (OAuth2)
- OpenAI GPT-4o (for summaries – extendable)

##  Supported Commands
Send any of the following to your Twilio WhatsApp number:
- `LIST /ProjectX` – list files in `/ProjectX`
- `DELETE /ProjectX/file.pdf`
- `MOVE /ProjectX/file.pdf /Archive`
- `SUMMARY /ProjectX`

##  Setup Instructions

### 1. Twilio WhatsApp Sandbox
- Create a [Twilio account](https://www.twilio.com/)
- Enable WhatsApp Sandbox
- Note your Sandbox number (e.g., `+14155238886`)

### 2. Google OAuth2 Setup
- Enable Google Drive API from [Google Console](https://console.cloud.google.com/)
- Create OAuth2 credentials and add them to n8n

### 3. Import Workflow
- Open n8n
- Import `workflow.json`
- Set credentials for:
  - Twilio
  - Google Drive

### 4. Run with Docker (Optional)
```bash
docker run -it --rm   -p 5678:5678   -v ~/.n8n:/home/node/.n8n   n8nio/n8n
```

##  Logs
You can add a Google Sheet node to log actions (LIST, DELETE, etc.).

## ✅ Optional Extras
- AI summaries with GPT-4o using OpenAI node
- Confirmation prompts for DELETE/MOVE# whatsapp_drive_assistant
