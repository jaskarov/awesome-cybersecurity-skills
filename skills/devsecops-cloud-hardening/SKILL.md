---
name: devsecops-cloud-hardening
description: DevSecOps, Static Analysis, Detection Engineering, Cryptography, and Network Defense skill distilled from Awesome-Hacking (DevSecOps, Detection Engineering, Static Analysis, Suricata, Honeypots, Cryptography, Vulhub). Use when securing CI/CD pipelines, writing SIEM/Suricata detection rules, auditing cryptography, or deploying vulnerable labs safely.
---

# DevSecOps, Detection Engineering & Cloud Hardening

## 1. Shift-Left Security & Static Analysis (SAST / SCA / Secret Scanning)
Har bir commit va PR da avtomatik xavfsizlik darvozalari (Quality Gates) o'rnatilishi shart:
- **SAST (Kod tahlili):** `semgrep --config=auto`, `bandit` (Python), `eslint-plugin-security` (JS/TS).
- **SCA (Kutubxonalar auditi):** `trivy fs .`, `npm audit --audit-level=high`, `pip-audit`.
- **Container & IaC Security:** `trivy image myapp:latest`, `checkov -d .` (Terraform/Dockerfile). Docker konteynerlarida `USER nonroot` va `--read-only` rootfs ishlatish.

## 2. Detection Engineering & Network IDS/IPS (Suricata)
- **Suricata qoidalari:** Tarmoq darajasida C2 trafik, SQLi/XSS urinishlari va anomaliyalarni ushlash.
- **Detection Lab & Honeypots:** Hujumchilarni chalg'itish va ularning TTP (Tactics, Techniques, Procedures) larini o'rganish uchun izolyatsiyalangan Honeypot (Cowrie SSH, T-Pot) larni DMZ da joylashtirish.
- **SIEM / Logging:** Barcha auth urinishlari, `sudo` buyruqlari, API 401/403/500 xatolari markazlashgan log tizimiga (ELK / Wazuh / Loki) yuborilishi shart.

## 3. Cryptography & Zero-Leakage Standards
- **Parollar:** Faqat `Argon2id` yoki `bcrypt` (cost >= 12). MD5, SHA1, SHA256 parol saqlash uchun QAT'IY TAQIQLANADI.
- **Shifrlash:** `AES-256-GCM` yoki `ChaCha20-Poly1305` (authenticated encryption). ECB rejimi taqiqlanadi.
- **Randomness:** Token va OTP lar uchun faqat CSPRNG (`secrets` moduli Python-da, `crypto.randomBytes` Node.js-da).
- **TLS:** Faqat TLS 1.2 / 1.3, HSTS yoqilgan.

## 4. Safe Testing Environments (Vulhub)
- Yangi eksploit yoki himoya qoidalarini sinash uchun hech qachon production serverdan foydalanmang. Lokal Docker-Compose asosidagi `Vulhub` muhitida izolyatsiyalangan holda test qiling.
