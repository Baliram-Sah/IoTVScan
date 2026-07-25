# IoTVScan
IoT-VScan, a lightweight and modular vulnerability scanner that integrates multiple modules for IoT devices vulnerability scanning. The tool perform the common port scanning, web fingerprinting, device discovery and default credentials checking. The tool perform common port scanning to detects the running services and versions of services.

---
## Installation Prerequisites
Make sure you have installed:
Python 3.8+
WhatWeb installed on your system
The following Python dependencies:
```
pip install -r requirements.txt
Example: argparse
         jinja2
         paramiko
         beautifulsoup4
         requests
```

## Project Structure
```
smap/
├── __main__.py          # Entry point
├── banner.py            # ASCII logo and intro banner
├── scanner.py           # Core scanning logic
├── port_scanner.py      # TCP/UDP port scanning module
├── vulnerability.py     # Vulnerability assessment module
├── utils.py             # Helper functions and color utilities
├── results.py           # JSON & HTML report generator
└── creds/               # Default credential JSONs (optional)
```
Scan Sample Output:
```
[SCAN] Starting scan of 192.168.1.10
[INFO] Scanning 1000 common ports
Host: 192.168.1.10
Hostname: router.local
OS Guess: Linux
Device Type: Router/Gateway

Open Ports:
PORT    PROTO   STATE     SERVICE    VERSION
22      tcp     open      SSH        OpenSSH_8.9
80      tcp     open      HTTP       nginx/1.18.0

Vulnerabilities Found:
Port 23: Telnet service is insecure
Severity: HIGH
Recommendation: Disable Telnet and use SSH instead
```
# Installation

## Clone Repository

```bash
git clone https://github.com/yourusername/SMAP.git
cd SMAP
```

## Install Dependencies

```bash
pip install -r requirements.txt
```

### Install WhatWeb

Ubuntu/Debian

```bash
sudo apt install whatweb
```

---

# Usage

## Scan a Single Host

```bash
python main.py 192.168.1.1
```

---

## Scan Common Ports

```bash
python main.py 192.168.1.1 -p common
```

---

## Scan Specific Ports

```bash
python main.py 192.168.1.1 -p 22,80,443
```

---

## Scan Port Range

```bash
python main.py 192.168.1.1 -p 1-1000
```

---

## Scan Entire Network

```bash
python main.py 192.168.1.0/24
```

---

## UDP Scan

```bash
python main.py 192.168.1.1 -sU
```

---

## TCP Scan

```bash
python main.py 192.168.1.1 -sT
```

---

## Use Default Credential File

```bash
python main.py 192.168.1.1 -d default_cred.json
```

---

## Generate HTML Report

```bash
python main.py 192.168.1.1 --html
```

---

## Save JSON Report

```bash
python main.py 192.168.1.1 -o results.json
```

---

# Example

```bash
python main.py 192.168.1.0/24 \
-p common \
-d default_cred.json \
--html \
-o results.json
```

---

# Supported Protocols

- HTTP
- HTTPS
- SSH
- FTP
- Telnet
- SMTP
- DNS
- MQTT
- SNMP
- RTSP
- Modbus
- CoAP
- IMAP
- POP3

---

# Security Checks

SMAP can identify:

- Open Ports
- Running Services
- Banner Information
- Service Versions
- Default Credentials
- Weak SSH Configuration
- Insecure Telnet Services
- Default Web Interfaces
- SNMP Exposure
- UPnP Exposure
- Potential IoT Misconfigurations

---

# Output

## Terminal Output

- Open Ports
- Service Information
- Banner Information
- Device Type
- Operating System Guess
- Vulnerability Summary

## JSON Report

Contains structured scan results for automation and further analysis.

## HTML Report

Generates a professional report including:

- Scan Summary
- Host Information
- Open Ports
- Service Details
- Vulnerabilities
- Severity Levels
- Security Recommendations

---

# Future Improvements

- CVE Integration
- CVSS Severity Scoring
- SSL/TLS Security Checks
- SMB Enumeration
- HTTP Security Header Analysis
- PDF Report Generation
- Plugin-Based Vulnerability Detection
- Docker Support
- Export to CSV
- Scheduled Scans

---

# Contributing

Contributions are welcome!

1. Fork the repository.
2. Create a feature branch.

```bash
git checkout -b feature/new-feature
```

3. Commit your changes.

```bash
git commit -m "Add new feature"
```

4. Push to your branch.

```bash
git push origin feature/new-feature
```

5. Open a Pull Request.

---

# License

This project is licensed under the MIT License.

---

# Author

**Baliram Sah**

- GitHub: https://github.com/yourusername
- LinkedIn: https://linkedin.com/in/yourprofile
- Email: your.email@example.com

---

## ⭐ Support

If you found this project helpful, consider giving it a **⭐ Star** on GitHub.
Suggestions before uploading to GitHub
Replace the placeholder GitHub, LinkedIn, and email links with your own.
Add screenshots of the CLI output and generated HTML report in a screenshots/ folder and reference them in the README. This makes the repository much more attractive.
Include a requirements.txt file so users can install dependencies easily with pip install -r requirements.txt.
Add a LICENSE file (MIT is a common choice for open-source projects).
