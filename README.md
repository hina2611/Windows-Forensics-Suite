# Windows Digital Forensics & Malware Assessment Tool

A Python-based Windows Digital Forensics and Incident Response (DFIR) tool designed to collect system artifacts, detect suspicious indicators, perform malware assessment, build forensic timelines, and generate investigation reports.

## Features

### Evidence Collection
- Installed software inventory
- Running processes monitoring
- Windows services enumeration
- Startup programs and Autoruns analysis
- Scheduled tasks collection
- User account discovery
- USB device history
- Browser artifact collection
- Windows Event Log analysis
- Active network connections
- Recent files tracking
- Downloads folder inspection

### Malware Assessment
- Suspicious executable detection
- MD5 and SHA256 hashing
- IOC (Indicators of Compromise) matching
- YARA rule scanning (optional)
- VirusTotal hash reputation lookup (optional)
- Digital signature verification

### Email Investigation
- Outlook data file discovery
- Email client configuration analysis
- Attachment metadata extraction
- Phishing indicator detection

### Reporting
- JSON Report
- HTML Report
- PDF Report
- Executive Summary
- Risk Scoring
- Evidence Tables
- Timeline Analysis
- Investigation Recommendations

### GUI Dashboard
- Modern Tkinter-based interface
- Case management workflow
- One-click evidence collection
- Automated reporting

---

## Project Structure

```text
win_forensic_assessor/
│
├── analysis/
│   ├── hashing.py
│   ├── ioc.py
│   ├── timeline.py
│   ├── yara_scan.py
│   ├── virustotal.py
│   └── signature.py
│
├── collectors/
│   └── windows.py
│
├── reports/
│   ├── html_report.py
│   ├── json_report.py
│   └── pdf_report.py
│
├── core/
│   └── case.py
│
├── gui.py
├── cli.py
├── requirements.txt
└── README.md
```

---

## Installation

### Clone Repository

```bash
git clone https://github.com/yourusername/win-forensic-assessor.git
cd win-forensic-assessor
```

### Create Virtual Environment

```bash
python -m venv .venv
```

### Activate Environment

Windows:

```powershell
.\.venv\Scripts\activate
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

---

## Running the GUI

```bash
python -m win_forensic_assessor.gui
```

Run as Administrator for maximum artifact visibility.

---

## Command Line Usage

```bash
python -m win_forensic_assessor.cli \
--case-name "IR-Case-001" \
--output ./cases \
--iocs ./iocs.json \
--yara ./rules.yar
```

---

## IOC Format

```json
{
  "hashes": [
    "44d88612fea8a8f36de82e1278abb02f"
  ],
  "paths": [
    "C:\\Users\\Public\\bad.exe"
  ],
  "domains": [
    "example-phish.test"
  ],
  "ips": [
    "203.0.113.10"
  ],
  "filenames": [
    "invoice.scr"
  ]
}
```

---

## VirusTotal Integration

Set your API key:

```powershell
$env:VT_API_KEY="YOUR_API_KEY"
```

---

## Generated Outputs

After execution the tool generates:

- evidence.json
- report.json
- report.html
- report.pdf

---

## Recommended Workflow

1. Create a new case.
2. Collect host artifacts.
3. Run IOC and YARA analysis.
4. Review suspicious findings.
5. Generate reports.
6. Preserve evidence according to DFIR procedures.

---

## Technology Stack

- Python 3.10+
- Tkinter
- Psutil
- ReportLab
- Requests
- YARA (Optional)
- VirusTotal API (Optional)

---

## Use Cases

- Incident Response
- Malware Triage
- Windows Forensics
- Security Audits
- Threat Hunting
- IOC Validation

---

## Disclaimer

This project is intended strictly for authorized defensive security, digital forensics, and incident response activities. Users are responsible for complying with all applicable laws and organizational policies.

---

## License

MIT License
