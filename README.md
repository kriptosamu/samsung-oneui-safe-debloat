# 🚀 Smart Samsung One UI Debloater

A lightweight, safe, and transparent guide to debloating Samsung Galaxy devices (including the A-series like A35 5G, and S-series) without rooting or breaking Knox security features.

This repository is designed to be fully compatible with **Claude Code**, AI agents, or traditional ADB terminal commands.

---

## 🧠 Why this approach?
Instead of using complex scripts that blindly delete system apps, this project focuses on a **conservative debloat method**. It uses the `pm disable-user --user 0` command, which puts annoying background apps to sleep without tripping Samsung Knox. Your banking apps, Samsung Wallet, and secure folder will keep working perfectly.

## 📋 Safe to Remove Packages
The packages listed in `debloat_list.txt` target:
* **Bixby Suite:** Samsung's virtual assistant and its home screen feeds.
* **AR Features:** Augmented reality emoji editors and camera stickers.
* **Bloatware:** Pre-installed apps like Game Launcher or Kids Mode.

---

## 🤖 How to use with Claude Code (Recommended)

1. Clone this repository to your computer:
   ```bash
   git clone https://github.com
   cd smart-samsung-debloater
   ```
2. Connect your Samsung phone to your PC via USB with **USB Debugging** enabled.
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
* **Do NOT touch** packages containing `knox`, `securitylogagent`, or `biometrics`. Doing so might lock you out of your device.
* Always backup your important data before performing any system modifications.

---

*Disclaimer: This project is independent and not affiliated with Samsung Electronics.*
