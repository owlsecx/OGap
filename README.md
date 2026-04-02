# 📜 OGap

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-informational?style=flat-square&logo=linux&logoColor=white&color=0a0c10"/>
  <img src="https://img.shields.io/badge/Category-OCore%20%2F%20DFIR%20%2F%20Log%20Forensics-cyan?style=flat-square"/>
  <img src="https://img.shields.io/badge/Dependencies-None%20(Standalone)-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Proprietary-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-v2.0-cyan?style=flat-square"/>
</p>

> **OGap** is a Linux log integrity checker. It detects gaps, tampering, truncation, suspicious time jumps, and anti-forensic activity in systemd journal, syslog, auth.log, and other log files.

---

## 📌 Overview

OGap performs deep forensic analysis on Linux logs to identify integrity issues:
- Sequence gaps in journald / syslog / auth.log
- Log clear / truncation events
- Large time jumps between entries
- Reboot / shutdown markers near gaps
- Anti-forensic indicators (shred, history -c, etc.)

It produces SIEM-ready JSON reports and clear severity ratings.

---

## 🖥️ Modules

| # | Module                  | Description |
|---|-------------------------|-------------|
| **[1]** | **Journal Scan**        | Scan systemd journald logs |
| **[2]** | **Syslog Scan**         | Scan /var/log/syslog or messages |
| **[3]** | **Auth Log Scan**       | Scan /var/log/auth.log or secure |
| **[4]** | **Custom Log Scan**     | Scan any user-specified log file |
| **[5]** | **Full Audit**          | Scan all sources in one pass |
| **[6]** | **Export Report**       | Save session results as JSON |

---

## 📊 Key Features

- **Gap Detection** — Time jumps and missing sequence gaps
- **Tampering Indicators** — Log clear, truncation, anti-forensic commands
- **Context Correlation** — Reboot/shutdown markers near gaps
- **Integrity Scoring** — CONFIRMED_CLEAR, LIKELY_TAMPER, SUSPICIOUS_GAP, BENIGN_REBOOT, BENIGN_ROTATION
- **Severity Levels** — Critical, High, Medium, Low with confidence scores
- **Anti-Forensic Detection** — shred, history -c, rm -rf on logs, etc.
- **JSON Export** — SIEM-ready structured report

---

## ⚙️ Requirements

- **Linux** (systemd recommended)
- **Root privileges** (for full journal and auth.log access)

---

## 🚀 Usage

```bash
sudo ./OGap

📁 Output

Live Terminal — Color-coded gaps with severity and reasons
Detailed Gap Analysis — Time gap, line gap, confidence, markers
Anti-Forensic Alerts — Direct indicators of tampering
JSON Report — Full structured output with all findings

Integrity States:

CONFIRMED_CLEAR — Log was intentionally cleared
LIKELY_TAMPER — High suspicion of tampering
SUSPICIOUS_GAP — Unexplained gap detected
BENIGN_REBOOT — Gap explained by reboot
BENIGN_ROTATION — Gap explained by log rotation


📦 Part of OwlSec Toolkit
This tool is part of the OwlSec suite — a collection of 300+ security and privacy tools.
🔗 owlsec.org

©️ License
Proprietary — © Khaled S. Haddad
Tools are distributed as pre-built executables. Source code is proprietary.

AUTHORISED DIGITAL FORENSICS & INCIDENT RESPONSE USE ONLY
