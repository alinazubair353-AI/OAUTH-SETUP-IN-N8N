# OAUTH-SETUP-IN-N8N
# 📊 Auto Create Google Spreadsheet | n8n Workflow

> Manually trigger n8n to automatically create a new Google Spreadsheet — built with **OAuth2 authentication** as part of the **Learn AI Automation** course.

---

## 🔥 What This Workflow Does

| Step | Node | Action |
|------|------|--------|
| 1️⃣ | **Manual Trigger** | Click "Execute Workflow" to start |
| 2️⃣ | **Create Spreadsheet** | Automatically creates a new Google Sheet via API |

One click → New Google Spreadsheet created instantly in your Google Drive! ✅

---

## 📤 Output Result (Test Run)

```
✅ Success in 1.915s

Spreadsheet Created:
  - spreadsheetId : 1srlGrwokNOpYc-zJT5JUsKaNEpzxfGCxNPXJnY3wk3o
  - title         : SHEET 1
  - locale        : en_US
  - sheets        : 0 (default sheet)
  - spreadsheetUrl: https://docs.google.com/spreadsheets/...
```

---

## 🔐 OAuth2 Setup (Google Cloud Console)

This workflow uses **Google OAuth2** for secure API access. Here's how it was configured:

### Step 1 — Google Cloud Console
1. Go to [console.cloud.google.com](https://console.cloud.google.com)
2. Create a new project (or select existing)
3. Enable **Google Sheets API**:
   - APIs & Services → Library → Search "Google Sheets API" → Enable

### Step 2 — Create OAuth2 Credentials
1. Go to **APIs & Services → Credentials**
2. Click **+ Create Credentials → OAuth 2.0 Client ID**
3. Application type: **Web Application**
4. Add Authorized Redirect URI:
   ```
   http://localhost:5678/rest/oauth2-credential/callback
   ```
5. Copy **Client ID** and **Client Secret**

### Step 3 — Add Credentials in n8n
1. Open n8n → **Settings → Credentials**
2. Click **+ Add Credential → Google Sheets OAuth2 API**
3. Paste Client ID and Client Secret
4. Click **Connect** → Sign in with Google → Allow permissions
5. Credential saved ✅

---

## ⚙️ Workflow Setup

### Nodes Used
| Node | Type | Config |
|------|------|--------|
| Manual Trigger | Built-in | No config needed |
| Create Spreadsheet | Google Sheets | Operation: `Create Spreadsheet` |

### How to Run
1. Open workflow in n8n (`localhost:5678`)
2. Click orange **"Execute Workflow"** button
3. New spreadsheet appears in your Google Drive instantly!


<img width="1363" height="639" alt="Screenshot 2026-06-26 125339" src="https://github.com/user-attachments/assets/22173a19-2a5d-4a7b-b073-d41443f1fa4a" />


---

## 🛠️ Tech Stack

- **n8n** (local — `localhost:5678`)
- **Google Sheets API** (v4)
- **Google Cloud Console** (OAuth2)
- **Windows** (local n8n instance)

---

## 📁 Project Structure

```
📦 n8n-create-spreadsheet
 ┣ 📄 README.md         ← You are here
 ┣ 📄 workflow.json     ← n8n workflow export
 ┗ 📄 screenshot.png    ← Workflow canvas screenshot
```

---

## 💡 Use Cases

- **Auto-generate reports** — create a fresh sheet every day/week
- **Project setup** — one click creates a new tracking spreadsheet
- **Dynamic data storage** — create sheet then fill it with other nodes
- **Template duplication** — extend this to copy template sheets automatically

---

## 🎓 Course Context

This project is part of my **Learn AI Automation** journey using n8n.

**Skills practiced:**
- Google Cloud Console setup
- OAuth2 credential configuration
- Google Sheets API integration
- Manual trigger workflows

---

## 👩‍💻 Author

Alina Zubair
----
