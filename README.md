<div align="center">

```
 ██████╗ ███████╗███╗   ██╗████████╗███████╗███████╗████████╗
 ██╔══██╗██╔════╝████╗  ██║╚══██╔══╝██╔════╝██╔════╝╚══██╔══╝
 ██████╔╝█████╗  ██╔██╗ ██║   ██║   █████╗  ███████╗   ██║   
 ██╔═══╝ ██╔══╝  ██║╚██╗██║   ██║   ██╔══╝  ╚════██║   ██║   
 ██║     ███████╗██║ ╚████║   ██║   ███████╗███████║   ██║   
 ╚═╝     ╚══════╝╚═╝  ╚═══╝   ╚═╝   ╚══════╝╚══════╝   ╚═╝   
```

**Universal Penetration Testing Framework**

[![Version](https://img.shields.io/badge/version-4.0-red?style=for-the-badge)](https://github.com/Darksystem-01/desktop-tutorial)
[![License](https://img.shields.io/badge/license-MIT-blue?style=for-the-badge)](LICENSE)
[![Shell](https://img.shields.io/badge/shell-bash-green?style=for-the-badge&logo=gnu-bash)](https://www.gnu.org/software/bash/)
[![Platform](https://img.shields.io/badge/platform-Linux-orange?style=for-the-badge&logo=linux)](https://linux.org)
[![Lines](https://img.shields.io/badge/lines-3200%2B-purple?style=for-the-badge)]()
[![Functions](https://img.shields.io/badge/functions-77-cyan?style=for-the-badge)]()

> ⚠️ **For authorized penetration testing and educational purposes ONLY.**

</div>

---

## 📖 About

**PenTest Framework v4.0** is a comprehensive, professional-grade penetration testing bash script. It automates everything from full network scanning, service enumeration, web application testing, to exploit searching — all in one command.

**What's new in v4.0:**
- 🔕 **Zero error output** — all tool errors are completely suppressed, only clean results shown
- 📋 **Smart Wordlist Manager** — automatically prompts you for the wordlist path if default is not found; skip by pressing Enter
- 🎯 **Clean result boxes** — findings displayed in concise, formatted summary boxes
- 🔑 **Wordlist asked once per session** — remembered for the whole scan
- 📊 **Enhanced HTML report** — professional dark-theme report with CSS styling
- 🔍 **77 functions** across 28 sections
- 🗃️ **Auto MSF resource file** generation
- 🖥️ **Improved interactive menu** with box UI

---

## ✨ Features

### 🔍 Port Scanning
| Type | Description | Time |
|------|-------------|------|
| `Quick` | Top-1000 ports (fast) | ~15s |
| `Port` | **ALL 65535 ports** (masscan + nmap) | ~1-5m |
| `Script` | Service/version detection | ~5m |
| `Full` | All ports + deep `-A` scan | ~15-30m |
| `UDP` | UDP port scanning (requires sudo) | ~5m |

### 🌐 Web Application Testing
- **Nikto** — web vulnerability scanner
- **ffuf / Gobuster / Dirb** — directory & file brute-force (wordlist prompted)
- **WhatWeb** — technology fingerprinting
- **SQLMap** — automated SQL injection testing
- **WPScan** — WordPress security audit
- **SSL/TLS** — sslscan / testssl analysis
- **HTTP Headers** — security headers check
- **robots.txt / sitemap.xml** — automatic discovery

### 🗂️ Service Enumeration
| Service | Capabilities |
|---------|-------------|
| **SMB** | smbmap, smbclient, enum4linux, nbtscan, MS17-010/EternalBlue check, share access test |
| **FTP** | Anonymous login, vsFTPd 2.3.4 backdoor, directory listing |
| **SSH** | Auth methods, weak algorithms, ssh-audit, banner grab |
| **DNS** | Zone transfer (AXFR), dnsrecon, dnsenum, subdomain brute (wordlist prompted) |
| **SMTP** | smtp-user-enum (VRFY/RCPT), open relay check |
| **SNMP** | Community string brute (onesixtyone, wordlist prompted), full MIB walk, user/port enum |
| **RDP** | MS12-020, BlueKeep (CVE-2019-0708) check |
| **MySQL** | Anonymous login, empty root password, DB enumeration |
| **MSSQL** | xp_cmdshell, NTLM info, empty password |
| **Oracle** | SID brute, user enum |
| **PostgreSQL** | DB enum, brute force |
| **Redis** | Unauthenticated access, CONFIG dump |

### 🔐 Vulnerability Scanner
- CVE detection via **vulners.nse** (min CVSS 7.0)
- Nmap `--script vuln` suite
- Safe discovery scripts

### 💣 Exploit Search
- **Searchsploit** — service, version, and CVE-based search
- **Metasploit resource file** — auto-generated for found ports
- Per-port MSF module suggestions

### 🔑 Brute Force
- **Hydra / Medusa** — SSH, FTP, HTTP, SMB, MySQL, RDP, SMTP, PostgreSQL, Telnet
- **Wordlist prompted once** — reused for all services in the session
- Configurable threads and timeout

### 🚀 Post-Exploitation
- **LinPEAS / WinPEAS** — auto-downloaded to `post/`
- **linux-exploit-suggester** — kernel exploit suggestions
- **pspy64** — process monitoring without root
- **PowerUp.ps1** — Windows privilege escalation
- Full Linux & Windows enumeration command reference
- Shell stabilization guide
- Reverse shell quick reference (Bash, Python, PHP, PowerShell)
- Persistence & lateral movement commands

### 📊 Reporting
- **HTML** — professional dark-theme report with CSS styling, metadata grid, findings sections
- **Markdown** — GitHub-compatible, structured report
- **Metasploit `.rc`** resource file per target
- All results saved to organized subdirectories

---

## 🛠️ Installation

### Prerequisites

```bash
# Core tools
sudo apt update
sudo apt install -y nmap masscan nikto sqlmap gobuster dirb \
    hydra medusa smbclient smbmap enum4linux nbtscan \
    onesixtyone snmp smtp-user-enum dnsrecon dnsenum \
    exploitdb whatweb ffuf sslscan curl wget netcat-openbsd

# Metasploit Framework
curl https://raw.githubusercontent.com/rapid7/metasploit-omnibus/master/config/templates/metasploit-framework-wrappers/msfupdate.erb | sudo sh

# WPScan
sudo gem install wpscan

# vulners NSE script (for CVE scanning)
cd /usr/share/nmap/scripts
sudo wget https://raw.githubusercontent.com/vulnersCom/nmap-vulners/master/vulners.nse
```

### Download & Setup

```bash
# Clone the repository
git clone https://github.com/Darksystem-01/desktop-tutorial.git
cd desktop-tutorial

# Make executable
chmod +x pentest.sh

# Check all tools
./pentest.sh   # then select option 21 (Tools)
```

---

## 🚀 Usage

### Interactive Mode (Recommended)
```bash
./pentest.sh
```
You'll be prompted for a target and then shown the full menu.

### Direct Command Mode
```bash
./pentest.sh -H <TARGET> -t <TYPE>

# Examples:
./pentest.sh -H 192.168.1.1 -t Quick
./pentest.sh -H 10.10.10.10 -t Full
./pentest.sh -H 10.0.0.5 -t Web
./pentest.sh -H 192.168.1.100 -t All
./pentest.sh -H target.com -t DNS
```

### Options
```
-H, --host         Target IP or hostname
-t, --type         Scan type (Quick/Port/Script/Full/UDP/Vulns/Web/SMB/FTP/SSH/DNS/SMTP/SNMP/RDP/SQL/Brute/Exploit/Post/Recon/Network/Report/All)
-d, --dns          Custom DNS server
-o, --output       Output directory (default: <host>/)
-T, --threads      Thread count (default: 10)
-r, --rate         masscan packet rate (default: 1000)
-y, --yes          Skip confirmation prompts
-v, --verbose      Show raw tool output
-s, --static-nmap  Path to static nmap binary
-h, --help         Show help
```

---

## 📁 Output Structure

```
<target>/
├── nmap/
│   ├── Port_<target>.nmap      — Port scan results
│   ├── Script_<target>.nmap    — Service/version scan
│   ├── Full_<target>.nmap      — Full -A scan
│   ├── CVEs_<target>.nmap      — CVE detection
│   ├── Vulns_<target>.nmap     — Vuln scripts
│   └── UDP_<target>.nmap       — UDP scan
├── web/
│   ├── nikto_*.txt             — Nikto scan
│   ├── gobuster_*.txt          — Directory brute
│   ├── whatweb_*.txt           — Technologies
│   ├── sslscan_*.txt           — SSL analysis
│   └── wpscan_*.txt            — WordPress audit
├── recon/
│   ├── smb/                    — SMB enumeration
│   ├── ftp/                    — FTP enumeration
│   ├── ssh/                    — SSH audit
│   ├── dns/                    — DNS enumeration
│   ├── smtp/                   — SMTP enum
│   ├── snmp/                   — SNMP walk
│   ├── rdp/                    — RDP scan
│   ├── db/                     — Database enum
│   └── brute/                  — Brute force results
├── exploits/
│   ├── searchsploit_*.txt      — Exploit search
│   └── msf_*.rc                — Metasploit resource file
├── post/
│   ├── linpeas.sh              — Linux PrivEsc
│   ├── winpeas.exe             — Windows PrivEsc
│   ├── pspy64                  — Process monitor
│   └── PowerUp.ps1             — Windows PrivEsc PS
├── analysis/
├── report_<target>.md          — Markdown report
├── report_<target>.html        — HTML report
└── pentest_<target>_<type>.log — Full scan log
```

---

## 🔕 Error Suppression

**v4.0** completely suppresses all tool errors — no stderr, no warnings from external tools.  
Only **meaningful findings** are displayed in clean summary boxes:

```
┌─[ Services Detected ]
│   22/tcp    open  ssh     OpenSSH 7.4
│   80/tcp    open  http    Apache 2.4.6
│   445/tcp   open  netbios Microsoft Windows SMB
└─────────────────────────────────────────────
```

---

## 📋 Wordlist Manager

When a tool needs a wordlist, the script:
1. **Checks the default path** — if found, uses it silently
2. **If not found** — prompts you with a clear box:
```
┌─[ WORDLIST REQUIRED ]───────────────────────────────────────┐
│  Tool       : Gobuster (directory brute-force)
│  Default    : /usr/share/wordlists/dirb/common.txt
│  Status     : Not found
└─────────────────────────────────────────────────────────────┘
  Enter wordlist path (leave empty to skip this tool): _
```
3. **Leave empty** → tool is skipped, no error shown
4. **Path remembered** for the entire session

---

## 📜 License

```
MIT License

Copyright (c) 2025 DarkSystem-01

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

> ⚠️ **DISCLAIMER:** This tool is intended for **authorized security testing only**.  
> Using this tool against systems without explicit permission is **illegal**.  
> The author is not responsible for any misuse or damage caused by this tool.

---

<div align="center">

Made with ❤️ by **DarkSystem-01**

[![GitHub](https://img.shields.io/badge/GitHub-DarkSystem--01-181717?style=for-the-badge&logo=github)](https://github.com/Darksystem-01)

*"Hack the planet — but only with permission."*

</div>
