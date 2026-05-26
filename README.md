<div align="center">

<img src="https://img.shields.io/badge/Mica%20CRM-v1.0.0-7c3aed?style=for-the-badge&logoColor=white" />
<img src="https://img.shields.io/badge/Platform-macOS%20Apple%20Silicon-black?style=for-the-badge&logo=apple" />
<img src="https://img.shields.io/badge/Access-@mica.rent%20only-059669?style=for-the-badge" />

# 💬 Mica CRM

**WhatsApp CRM for Mica KAMs** — Kanban pipeline, real-time messaging, Google Sign-In.

[📖 **Open the full setup guide →**](https://stajulian5.github.io/mica-crm-docs/)&nbsp;&nbsp;&nbsp;[⬇️ **Download for Mac (M1/M2/M3)**](https://github.com/stajulian5/mica-crm-docs/releases/latest/download/Mica.CRM-arm64.dmg)

</div>

---

## 👤 For KAMs

> Everything you need to get started in under 5 minutes.

### 1 · Install

Download the `.dmg` above → drag **Mica CRM** to your Applications folder → eject the disk.

> **First launch only:** macOS may block the app. Right-click → **Open** → **Open** to allow it once.

### 2 · Chrome

Mica CRM uses your existing Chrome to power WhatsApp. Make sure it's at its default location:
`/Applications/Google Chrome.app`

### 3 · Sign in

Launch the app and click **Sign in with Google** — use your `@mica.rent` account. Non-Mica accounts are blocked.

### 4 · Connect WhatsApp

Click **Connect WhatsApp** in the top bar. A QR code will appear — scan it from your phone:

| iPhone | Android |
|--------|---------|
| WhatsApp → Settings → Linked Devices → Link a device | WhatsApp → ⋮ → Linked Devices → Link a device |

Your session is saved after the first scan — no re-scanning on relaunch.

### 5 · Use the board

Every contact appears as a card. Drag them across the pipeline as deals progress:

```
New  →  Contacted  →  Open Item  →  Circling Back  →  All Resolved
```

Click any card to open the chat, add notes, or change the stage.

---

## 🛡️ For Admin

> `julian@mica.rent` — admin powers activate automatically on sign-in.

### What you get

| Feature | Details |
|---------|---------|
| **All KAMs overview** | See who's online, WhatsApp status, contact counts, unread badges |
| **Read any conversation** | Full message history for every KAM · read-only (no accidental sends) |
| **Global search** | Find any contact or phone number across all KAMs at once |
| **Aggregate stats** | Total contacts, messages today, connections across the team |
| **Role management** | Promote or demote any user (kam ↔ admin) |

### Accessing the dashboard

Launch the app → sign in → click the purple **Admin** button in the top-right corner.

### One-time setup *(tech team only — KAMs never touch this)*

1. **Create a Google OAuth Client ID**
   Go to [console.cloud.google.com → APIs & Services → Credentials](https://console.cloud.google.com/apis/credentials).
   Create an *OAuth 2.0 Web Client ID* · add `http://localhost:3001` as an authorized redirect URI.

2. **Add it to the config files**
   Paste the Client ID into `backend/.env` and `frontend/.env` (replace the placeholder).

3. **Build & distribute**
   Run `npm run package:mac` → upload the new `.dmg` from `release/` to this GitHub release → share this page with KAMs.

> ⚠️ Never commit `.env` files to a public repo — they contain your Google Client ID.

### Where data is stored

Each KAM's data lives on their own machine:

```
~/Library/Application Support/Mica CRM/data/
├── mica-crm.db        ← SQLite database (contacts, messages, templates)
└── wa_sessions/       ← WhatsApp session (no re-scan needed after first login)
```

---

<div align="center">

**Mica CRM** · Internal tool · Restricted to `@mica.rent` accounts
<br>
[Full styled guide](https://stajulian5.github.io/mica-crm-docs/) · [Releases](https://github.com/stajulian5/mica-crm-docs/releases)

</div>
