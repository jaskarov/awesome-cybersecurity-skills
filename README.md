# Awesome Cybersecurity AI Skills

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![Skills](https://img.shields.io/badge/AI%20Skills-10%20Modules-blue.svg)](#included-skills)
[![Compatible](https://img.shields.io/badge/Compatible-Antigravity%20%7C%20Claude%20%7C%20Cursor%20%7C%20Windsurf-green.svg)](#how-to-use)

**Universal, production-ready AI Agent Skills (`SKILL.md`) for Ethical Hacking, Penetration Testing, OSINT, Red Teaming, DevSecOps, AI/LLM Security, and Incident Response.**

Distilled from the [Awesome-Hacking](https://github.com/Hack-with-Github/Awesome-Hacking) ecosystem into structured, actionable playbooks that any AI coding agent can load and execute.

> [!CAUTION]
> **Authorized Scope Only:** All techniques, commands, and methodologies in these skills are strictly for authorized security assessments, Bug Bounty programs, CTF challenges, and defensive hardening.

---

## Included Skills

| # | Skill | Domain & Capabilities | Link |
|---|---|---|---|
| 1 | **cyber-recon-osint** | Subdomain/Asset Discovery (`subfinder`, `amass`, `naabu`), OSINT (`trufflehog`, `gitleaks`), `.pcap` analysis (`tshark`), IoT/RF recon | [SKILL.md](skills/cyber-recon-osint/SKILL.md) |
| 2 | **web-api-appsec-pentest** | OWASP Top 10, API Security (BOLA/IDOR, SQLi/NoSQLi, SSTI, SSRF, JWT, Race Conditions), `ffuf` fuzzing, Node.js/PHP, Web3 | [SKILL.md](skills/web-api-appsec-pentest/SKILL.md) |
| 3 | **red-team-exploitation** | Linux/Windows PrivEsc (`GTFOBins`, `BloodHound`, Kerberoasting), CI/CD attacks, `hashcat`, Persistence auditing | [SKILL.md](skills/red-team-exploitation/SKILL.md) |
| 4 | **devsecops-cloud-hardening** | Shift-Left SAST/SCA (`semgrep`, `trivy`, `checkov`), Suricata IDS/IPS, Honeypots, Cryptography (`Argon2id`, `AES-256-GCM`), `Vulhub` | [SKILL.md](skills/devsecops-cloud-hardening/SKILL.md) |
| 5 | **ai-llm-security-defense** | LLM OWASP Top 10, Direct/Indirect Prompt Injection defense, Agentic Tool Misuse (HITL), RAG Multi-Tenant ACL | [SKILL.md](skills/ai-llm-security-defense/SKILL.md) |
| 6 | **incident-response-forensics** | 6-Step IR Protocol, Live Triage, RAM Forensics (`Volatility 3`), Malware Analysis (`Ghidra`, `CyberChef`), YARA & Threat Hunting | [SKILL.md](skills/incident-response-forensics/SKILL.md) |
| 7 | **mobile-app-security** | Android & iOS static/dynamic analysis (`MobSF`, `jadx`, `Frida`, `objection`), SSL Pinning bypass, Deep Links | [SKILL.md](skills/mobile-app-security/SKILL.md) |
| 8 | **exploit-dev-fuzzing** | Coverage-guided fuzzing (`AFL++`, `libFuzzer`), ASan/UBSan, `checksec`, `gdb` crash triage, Packer detection | [SKILL.md](skills/exploit-dev-fuzzing/SKILL.md) |
| 9 | **hardware-iot-ics-security** | Firmware extraction (`binwalk`), UART/JTAG, MQTT/BLE, ICS/SCADA (Modbus/S7comm), Vehicle CAN-bus | [SKILL.md](skills/hardware-iot-ics-security/SKILL.md) |
| 10 | **bug-bounty-ctf-playbook** | Bug Bounty ROI strategy, Vulnerability Chaining, CVSS 3.1 reporting, CTF quick-start | [SKILL.md](skills/bug-bounty-ctf-playbook/SKILL.md) |

---

## How to Use

These skills follow the universal `SKILL.md` standard (YAML frontmatter + Markdown instructions) and work with **Antigravity**, **Claude Code**, **Cursor**, **Windsurf**, and other AI agents.

### Quick Install
Clone this repository and copy the `skills/` folders into your agent's skills directory:

```bash
git clone https://github.com/jaskarov/awesome-cybersecurity-skills.git
cp -r awesome-cybersecurity-skills/skills/* .agents/skills/
```

Once installed, your AI agent will automatically load the relevant skill whenever you ask it to audit an API, analyze a `.pcap` file, harden a CI/CD pipeline, or investigate an incident.
