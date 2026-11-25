---
name: mobile-app-security
description: Mobile Application Security (Android & iOS) auditing skill distilled from Awesome-Hacking (Android Security, OSX and iOS Security). Use when auditing APK/IPA binaries, bypassing SSL pinning in authorized tests, analyzing mobile storage, or running MobSF/Frida.
---

# Mobile Application Security (Android & iOS)

> [!CAUTION]
> **Authorized Scope Only:** Ushbu texnikalar faqat ruxsat etilgan ilovalar va Bug Bounty dasturlari doirasida qo'llaniladi.

## 1. Static Analysis (Statik Tahlil)
- **Automated Scanning:** `MobSF` (Mobile Security Framework) orqali APK/IPA ni tezkor skanerlash.
- **Android Decompilation:** `jadx-gui` yoki `apktool d app.apk` orqali `AndroidManifest.xml`, hardcoded API kalitlar, Firebase URL lar va `exported="true"` komponentlarni (Activity, Service, BroadcastReceiver) tekshirish.
- **iOS:** `class-dump` / `otool` orqali binary himoyalarini (PIE, ARC, Stack Canary) tekshirish.

## 2. Dynamic Analysis & Instrumentation (Frida / Objection)
- **SSL Pinning Bypass (Authorized Testing):**
  ```bash
  # Objection orqali SSL pinning va Root detection ni chetlab o'tish
  objection -g com.target.app explore --startup-command "android sslpinning disable"
  ```
- **Local Storage Auditi:** `SharedPreferences`, SQLite bazalar, Keychain (iOS) va loglarda (`adb logcat`) maxfiy tokenlar yoki parollar ochiq holda saqlanmasligini tekshirish.
- **Deep Links & WebViews:** `javascript:alert(1)` va `setJavaScriptEnabled(true)` orqali WebView XSS / File Theft xavfini tekshirish.
