---
name: bug-bounty-ctf-playbook
description: Bug Bounty Methodology, Vulnerability Reporting (CVSS), and CTF Playbook skill distilled from Awesome-Hacking (Bug Bounty, Bug Bounty Reference, CTF, Hacker101). Use when hunting bugs in authorized programs, writing high-impact vulnerability reports, or solving CTF challenges.
---

# Bug Bounty & CTF Playbook

## 1. Bug Bounty Metodologiyasi (High-ROI Strategy)
- **Scope & Rules:** Dastur qoidalarini (In-Scope / Out-of-Scope) o'qish. Hech qachon Out-of-Scope domenlarga so'rov yubormang.
- **Duplicate dan qochish:** Hamma skanerlaydigan asosiy domen (`www.target.com`) o'rniga yangi sotib olingan kompaniyalar, unutilgan subdomenlar, mobil API lar va murakkab biznes-mantiq (Business Logic) zaifliklariga e'tibor qarating.
- **Chaining (Zanjirlash):** Past darajadagi zaifliklarni (masalan: Open Redirect + SSRF yoki Self-XSS + CSRF) birlashtirib, High/Critical impact ko'rsatish.

## 2. High-Impact Hisobot Yozish (HackerOne / Bugcrowd)
Har bir hisobotda quyidagi 5 ta qism aniq bo'lishi shart:
1. **Summary & Severity (CVSS 3.1):** Muammo nima va qanchalik xavfli.
2. **Steps to Reproduce:** Qadam-baqadam, nusxalab ishlatish mumkin bo'lgan aniq ko'rsatma.
3. **Proof of Concept (PoC):** Skrinshot, HTTP request/response yoki qisqa video.
4. **Impact:** Biznesga real zarari (masalan: "Istalgan foydalanuvchi ma'lumotini o'qish mumkin").
5. **Remediation:** Muammoni tuzatish bo'yicha aniq tavsiya.

## 3. CTF (Capture The Flag) Tezkor Yondashuv
- **Web:** Source code, cookies/JWT, robots.txt, LFI/SQLi.
- **Crypto:** Base64/Hex/ROT13 (CyberChef), zaif RSA (`RsaCtfTool`), ECB padding oracle.
- **Pwn / Rev:** `file`, `strings`, `checksec`, `gdb`, `pwntools`.
