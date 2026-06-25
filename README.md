# CloudEFS — Cloud-Based Encrypted File System

A zero-knowledge, client-side encrypted file system prototype built with vanilla HTML, CSS, and the Web Crypto API. No backend, no server — all encryption happens in your browser.

## 🔐 Crypto Stack

| Layer | Implementation |
|---|---|
| Encryption | AES-256-GCM |
| Key Derivation | PBKDF2 / SHA-256 / 600,000 iterations |
| IV | 96-bit random per file |
| Auth Tag | 128-bit GCM tag |
| Storage | Browser IndexedDB (simulated cloud) |

## 🚀 Deploy to Vercel

### Option 1 — Vercel CLI
```bash
npm i -g vercel
vercel
```

### Option 2 — Vercel Dashboard
1. Push this folder to a GitHub repo
2. Go to [vercel.com](https://vercel.com) → New Project
3. Import the repo → Deploy (no build settings needed)

## 🛠️ Run Locally

```bash
# Using Python
python -m http.server 8766

# Using npx serve
npx serve . -p 8766
```

Then open [http://localhost:8766](http://localhost:8766).

## 📁 Project Structure

```
cloud-efs-proto/
├── index.html      # Full app (HTML + CSS + JS)
├── vercel.json     # Vercel deployment config + security headers
├── package.json    # Project metadata
└── README.md       # This file
```

## ✨ Features

- 🔒 Real AES-256-GCM encryption via Web Crypto API
- 🗝️ PBKDF2 key derivation from passphrase
- 📁 Multi-vault support with isolated namespaces
- ⬆️ Drag & drop file upload with instant encryption
- ⬇️ Decrypt & download with one click
- 📋 Audit log for all operations
- 🔑 Key fingerprint viewer
- 💾 Persistent storage via IndexedDB
- 🎨 Dark UI with animated particle background

## ⚠️ Note

This is a **prototype**. IndexedDB is local to the browser — it simulates the cloud store. For a real deployment, replace IndexedDB reads/writes with API calls to your cloud storage backend (S3, GCS, etc.).
