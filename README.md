# 🚀 Smart Samsung One UI Debloater

A lightweight, safe, and transparent guide to debloating Samsung Galaxy devices (including the A-series like A35 5G, and S-series) without rooting or breaking Knox security features.

This repository is designed to be fully compatible with **Claude Code**, AI agents, or traditional ADB terminal commands.

---

## 🧠 Why this approach?
Instead of using complex scripts that blindly delete system apps, this project focuses on a **conservative debloat method**. It uses the `pm disable-user --user 0` command, which puts annoying background apps to sleep without tripping Samsung Knox. 

Your banking apps, Samsung Wallet, Secure Folder, and OTA software updates will keep working perfectly.

## 📋 What is being disabled?
The packages listed in `debloat_list.txt` target non-essential features:
* **Bixby Suite:** Samsung's virtual assistant, voice wakeup, and home screen feeds.
* **AR Features:** Augmented reality emoji editors, avatars, and camera stickers.
* **Ecosystem Overlap:** Pre-installed apps and features that overlap with Google services (e.g., Game Launcher, Kids Mode, Link to Windows).

---

## 🤖 How to use with Claude Code (Recommended)

1. **Clone this repository** to your computer:
   ```bash
   git clone https://github.com
   cd samsung-oneui-safe-debloat
   ```
   *(Note: Remember to replace `YOUR_GITHUB_USERNAME` with your actual GitHub username, or simply download the ZIP file using the green "Code" button above).*

2. Connect your Samsung phone to your PC via USB with **USB Debugging** enabled in the Developer Options.
3. Launch **Claude Code** inside the repository folder and ask:
   > *"Read the debloat_list.txt file, detect my connected Samsung device via ADB, and disable the safe packages listed there. Do not touch Knox or biometric services."*

---

## 💻 Manual Method (Via Standard ADB)

If you prefer using standard terminal commands, you can disable apps individually:

```bash
# Example: Disabling Bixby Assistant
adb shell pm disable-user --user 0 com.samsung.android.bixby.agent

# Example: How to restore an app if you change your mind
adb shell pm enable com.samsung.android.bixby.agent
```

---

## ⚠️ Safety Warning
* **Do NOT touch** packages containing `knox`, `securitylogagent`, or `biometrics`. Doing so might trigger safety locks or cause a bootloop.
* Always backup your important data before performing any system modifications.

---

## 🇮🇹 Nota per la community Italiana
Questo repository raccoglie tutti i pacchetti superflui della One UI di Samsung che possono essere disattivati in sicurezza tramite ADB (senza permessi di root). Usando il comando `pm disable-user`, le app vengono semplicemente "congelate". Ciò significa che l'operazione è sicura al 100%, reversibile e **non invalida la garanzia né blocca Knox (Samsung Pay e app bancarie continueranno a funzionare)**. Ottimo da usare in accoppiata con Claude Code o tramite terminale classico.

---

*Disclaimer: This project is independent and not affiliated with Samsung Electronics.*
q