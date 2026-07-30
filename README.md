# IoTVScan
SMAP (**Security Mapping and Assessment Platform**) is a **Python-based Command-Line Interface (CLI) IoT Vulnerability Scanner** designed to automate network reconnaissance and security assessments of IoT devices. It performs host discovery, TCP/UDP port scanning, service detection, banner grabbing, default credential detection, and vulnerability identification while generating professional JSON and HTML reports.

> **Disclaimer:** This tool is intended for educational purposes and authorized security assessments only. Do not scan systems without proper authorization.

---

## ✨ Features

- 🔍 Host Discovery
- 🌐 Scan Single IP, IP Range, and CIDR Networks
- ⚡ Multi-threaded TCP & UDP Port Scanning
- 📡 Service Detection and Version Fingerprinting
- 🏷️ Banner Grabbing
- 🌍 WhatWeb Integration for Web Technology Detection
- 🔑 Default Credential Detection
  - HTTP
  - HTTPS
  - FTP
  - SSH
  - Telnet
- 🖥️ Operating System Guessing
- 📱 IoT Device Type Detection
- 📊 JSON Report Generation
- 📄 Professional HTML Report Generation
- 🎨 Interactive Colored CLI Output

---

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
git clone https://github.com/Baliram-Sah/IoTVScan.git &
cd IoTVScan
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
python3 -m smap.main 192.168.1.1
```

---

## Scan Common Ports

```bash
python3 -m smap.main 192.168.1.1 -p common
```

---

## Scan Specific Ports

```bash
python3 -m smap.main 192.168.1.1 -p 22,80,443
```

---

## Scan Port Range

```bash
python3 -m smap.main 192.168.1.1 -p 1-1000
```

---

## Scan Entire Network

```bash
python3 -m smap.main 192.168.1.0/24
```

---

## UDP Scan

```bash
python3 -m smap.main 192.168.1.1 -sU
```

---

## TCP Scan

```bash
python3 -m smap.main 192.168.1.1 -sT
```

---

## Use Default Credential File

```bash
python3 -m smap.main 192.168.1.1 -d default_cred.json
```

---

## Generate HTML Report

```bash
python3 -m smap.main 192.168.1.1 --html
```

---

## Save JSON Report

```bash
python3 -m smap.main 192.168.1.1 -o results.json
```

---

# Example

```bash
python3 -m smap.main 192.168.1.0/24 \
-p common \
-d default_cred.json \
--html \
-o results.json
```

---

# Supported Protocols

- HTTP, HTTPS, SSH, FTP, Telnet
- SMTP, DNS, MQTT, SNMP, RTSP
- Modbus, CoAP, IMAP, POP3

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

- GitHub: https://github.com/Baliram-Sah
- LinkedIn: https://linkedin.com/in/baliram-sah1432
- Email: sahb455@gmail.com

---

## ⭐ Support

If you found this project helpful, consider giving it a **⭐ Star** on GitHub.
