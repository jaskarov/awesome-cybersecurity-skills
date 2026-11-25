---
name: incident-response-forensics
description: Incident Response, Digital Forensics, Malware Analysis, YARA, and Threat Hunting skill distilled from Awesome-Hacking (Incident Response, Forensics, Malware Analysis, Reversing, YARA, Threat Intelligence, IOC, ThreatHunter-Playbook, CyberChef). Use when investigating security breaches, analyzing suspicious binaries, or hunting threats.
---

# Incident Response, Forensics & Malware Analysis

## 1. Incident Response (IR) 6-Bosqichli Protokoli
Hodisa yuz berganda vahimaga tushmasdan qat'iy tartibda harakatlaning:
1. **Preparation:** Loglar, backup va IR vositalarining tayyorligi.
2. **Identification:** Anomaliyani aniqlash (IOC lar, g'alati jarayonlar, tarmoq ulanishlari).
3. **Containment (Izolyatsiya):**
   - **Qoida:** Serverni darhol o'chirib tashlamang (RAM/operativ xotiradagi dalillar yo'qoladi!). Avval tarmoqdan uzing (network isolate) va RAM dump / disk snapshot oling.
4. **Eradication:** Zararli fayllar, persistence mexanizmlari (cron, SSH keys, systemd) va zaiflikni tozalash.
5. **Recovery:** Tizimni toza backupdan tiklash, barcha parol va API kalitlarni rotatsiya qilish (rotate secrets).
6. **Lessons Learned:** Hodisa sababini hujjatlashtirish va himoyani kuchaytirish.

## 2. Digital Forensics & Live Triage
```bash
# Linuxda shubhali jarayonlar va tarmoq ulanishlarini tezkor tekshirish
ps auxf
ss -tulnp
lsof -i -P -n
find /tmp /dev/shm /var/tmp -type f -executable 2>/dev/null
# Oxirgi 24 soatda o'zgargan fayllar
find / -mtime -1 -ls 2>/dev/null | grep -v "/proc\|/sys"
```
- **Memory Forensics:** `Volatility 3` yordamida RAM dumpdan yashirin jarayonlar, DLL injection va tarmoq soketlarini chiqarish.

## 3. Malware Analysis & Reverse Engineering
- **Static Analysis:** Fayl hashini (`sha256sum`) VirusTotal da tekshirish, `strings`, `file`, `exiftool`, `objdump` / `Ghidra` / `radare2` orqali kod mantiqini o'rganish.
- **Dynamic Analysis:** Faqat izolyatsiyalangan VM/Sandbox (Cuckoo, Any.Run) ichida ishga tushirib, tizim chaqiruvlari (`strace`, `ltrace`, Process Monitor) va tarmoq so'rovlarini kuzatish.
- **Decoding:** Base64, XOR, Hex va obfuskatsiya qilingan payloadlarni **CyberChef** orqali dekodlash.

## 4. YARA & Threat Hunting
- Aniqlangan zararli dastur belgilari (stringlar, bayt ketma-ketligi) asosida **YARA** qoidasi yozish va barcha serverlarda skanerlash.
- **ThreatHunter-Playbook:** Faol ravishda tizimda yashiringan hujumchi izlarini (IOC: IP, domain, file hash) qidirish.
