# 🔐 My Vault

A private, offline password manager for Chrome and Edge.
Your passwords are encrypted on your own device — nothing is uploaded anywhere.

**Developed by Arafat Ahmed** · © 2026 Arafat Ahmed. All rights reserved.

## Features

- AES-256-GCM encrypted vault, unlocked with your master password (PBKDF2-SHA256, 600,000 iterations)
- Add / edit / search entries, strong password generator with strength meter
- Autofill icon inside login fields, and "Save this login?" prompts after you sign in
- Built-in 2FA (TOTP) code generator
- Import (My Vault backup, or CSV/JSON from Chrome, LastPass, Bitwarden, 1Password) and export (encrypted backup or CSV)
- Backup reminders and optional automatic encrypted backups
- Auto-lock, light & dark theme

## Install

1. Open the **[Releases](../../releases/latest)** page and download `my-vault-extension.zip`.
2. Extract the zip into a folder you will **keep** (for example `Documents/MyVault`). Do not delete this folder — Chrome loads the extension from it.
3. Open `chrome://extensions` (Edge: `edge://extensions`) and switch on **Developer mode**.
4. Click **Load unpacked** and choose the folder that contains `manifest.json`.
5. Pin the My Vault icon to your toolbar, open it, and enter your **16-digit activation key**.

> Need a key? Contact the developer, Arafat Ahmed.

## Activation keys

- A key looks like `1234-5678-9012-3456`.
- **One key works on one device at a time.** To move to another computer, open **Settings → Deactivate** first, then enter the same key on the new device. If you lost access to the old device, ask the developer to reset your key.
- Activation sends only your key and a random device ID to the license server. **Your passwords and vault never leave your device.**
- After activating, My Vault keeps working offline; it re-checks the license in the background and tolerates up to 14 days without internet.

## Updating

Download the new zip and copy its files over the **same folder**, then click the reload icon on `chrome://extensions`. Your vault is kept.
Loading a *different* folder creates a brand-new, empty copy of the extension — export an encrypted backup first and deactivate the old one.

## Backups — important

Your vault lives only in this browser. If you remove the extension or clear browser data it is gone, and there is no way to recover a forgotten master password. Use **Backup → Export encrypted backup** regularly (or turn on automatic backups in Settings).

## For the developer

See [`docs/OWNER-GUIDE-bn.md`](docs/OWNER-GUIDE-bn.md) for deploying the license server, creating keys and publishing releases.

```
extension/   the Chrome/Edge extension (Manifest V3)
worker/      license server (Cloudflare Worker + KV)
tools/       admin.js — create / list / revoke / reset keys
```

## License

Proprietary — see [LICENSE](LICENSE). Not for redistribution; use requires a valid activation key.
