---
name: cyber-recon-osint
description: Comprehensive Reconnaissance, Asset Discovery, OSINT, and Network Trace Analysis skill distilled from Awesome-Hacking (OSINT, Asset Discovery, Pcaptools, RF/IoT, Cellular). Use when mapping attack surfaces, auditing exposed assets, analyzing network traffic (.pcap), or conducting authorized OSINT investigations.
---

# Cyber Recon, Asset Discovery & OSINT

> [!CAUTION]
> **Authorized Scope Only:** Ushbu skilldagi barcha texnikalar faqat ruxsat etilgan domenlar, shaxsiy/korporativ infratuzilma yoki rasmiy Bug Bounty dasturlari doirasida qo'llanilishi shart.

## 1. Passive & Active Asset Discovery (Hujum Yuzasini Xaritalash)
Har qanday tizimni tekshirishdan oldin uning tashqi ko'rinishini (External Attack Surface) to'liq aniqlash zarur:

### Subdomain & DNS Enumeration
```bash
# Subdomainlarni passiv va aktiv yig'ish
subfinder -d target.com -all -recursive -o subs.txt
amass enum -passive -d target.com -o amass_subs.txt
cat subs.txt amass_subs.txt | sort -u | httpx -silent -status-code -title -tech-detect
```
- **Edge Case (Wildcard DNS):** Agar `*.target.com` barcha so'rovlarga bir xil IP qaytarsa, `puredns` yoki `massdns` orqali wildcard filtrlashni qo'llang.
- **Certificate Transparency:** `crt.sh` orqali SSL sertifikatlar tarixidan unutilgan subdomenlarni (`dev.`, `staging.`, `vpn.`, `internal.`) topish.

### Port & Service Fingerprinting
```bash
# Tezkor port skanerlash va xizmatlarni aniqlash
naabu -list live_hosts.txt -top-ports 1000 -silent | httpx -silent
nmap -sV -sC -T4 -Pn -p- --min-rate 1000 target.com -oA nmap_full
```

## 2. OSINT (Open Source Intelligence)
- **GitHub / GitLab Secret Leak:** `trufflehog`, `gitleaks` yordamida tashkilotning ochiq repozitoriyalarida qolib ketgan `.env`, API kalitlar, SSH kalitlar va ichki URL manzillarni tekshirish.
- **Shodan / Censys / FOFA:** Ochiq qolgan ma'lumotlar bazalari (MongoDB, Elasticsearch, Redis, PostgreSQL), Docker API (`2375`), Kubernetes (`10250`) va kameralar/IoT qurilmalarni aniqlash.
- **Email & Employee Recon:** `theHarvester`, `hunter.io` orqali korporativ pochta formatini aniqlash va sizib chiqqan parollar bazasida (breach data) tekshirish.

## 3. Network Trace & Pcap Analysis (Tarmoq Trafikini Tahlil Qilish)
- **Wireshark / tshark:**
  ```bash
  # HTTP so'rovlar va shifrlanmagan kredensiallarni ajratib olish
  tshark -r capture.pcap -Y "http.request" -T fields -e http.host -e http.request.uri
  # DNS eksfiltratsiya (uzun yoki shubhali subdomenlar) tekshiruvi
  tshark -r capture.pcap -Y "dns.qry.name" -T fields -e dns.qry.name | sort | uniq -c | sort -nr | head -20
  ```
- **Anomaliyalar:** Noma'lum tashqi IP larga doimiy beaconing (C2 trafiki), nostandart portlarda SSH/TLS, yoki katta hajmdagi chiqish (data exfiltration).

## 4. Specialized Recon (IoT, RF, Cellular)
- **IoT / Embedded:** `binwalk` orqali firmware ni ochish, hardcoded parollar va ochiq UART/JTAG portlarni tekshirish.
- **Wireless / RF:** Wi-Fi (WPA2/WPA3 PMKID/Handshake auditi), Bluetooth Low Energy (BLE) va SDR (Software Defined Radio) orqali chastota tahlili.
