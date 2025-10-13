# IoTVScan
IoT-VScan, a lightweight and modular vulnerability scanner that integrates multiple modules for IoT devices vulnerability scanning. The tool perform the common port scanning, web fingerprinting, device discovery and default credentials checking. The tool perform common port scanning to detects the running services and versions of services.

Installation Prerequisites
Make sure you have:
Python 3.8+
WhatWeb installed on your system
The following Python dependencies:
pip install -r requirements.txt
Example: argparse
         jinja2
         paramiko
         beautifulsoup4
         requests

# Run directly from the command lile.
Go to directory path
command: python3 -m smap.main <target>
Examples:
# Scan a single host for common ports
python -m smap 192.168.1.1

# Scan an entire subnet with default credential checks
python -m smap 192.168.1.0/24 -p common -d creds/default_creds.json

# Scan specific TCP ports and export results
python -m smap 192.168.1.0/24 -p 22,80,443 -o results.json

# Perform a UDP scan
python -m smap 192.168.1.0/24 -p 53,161 -sU


Project Structure
smap/
├── __main__.py          # Entry point
├── banner.py            # ASCII logo and intro banner
├── scanner.py           # Core scanning logic
├── port_scanner.py      # TCP/UDP port scanning module
├── vulnerability.py     # Vulnerability assessment module
├── utils.py             # Helper functions and color utilities
├── results.py           # JSON & HTML report generator
└── creds/               # Default credential JSONs (optional)


Scan Sample Output:

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


