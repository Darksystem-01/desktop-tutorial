# Universal Penetration Testing Script

A comprehensive bash script that integrates nmap scanning, web application testing, exploitation search, and post-exploitation tools for complete penetration testing workflows.

## Features

### Scanning Capabilities
- **Network Scan**: Discover live hosts in the target network
- **Port Scan**: Identify open ports on target
- **Script Scan**: Run NSE scripts on open ports
- **Full Scan**: Comprehensive port scan with script analysis
- **UDP Scan**: UDP port scanning (requires sudo)
- **Vulns Scan**: CVE and vulnerability detection
- **Recon**: Automated reconnaissance recommendations

### Web Application Testing
- **SQLMap Integration**: Automated SQL injection testing
- **Nikto**: Web server vulnerability scanning
- **Gobuster/Dirb**: Directory and file enumeration
- **SSL Testing**: SSL/TLS configuration analysis

### Exploitation
- **Searchsploit**: Automated exploit database search
- **Metasploit**: Module suggestions and resource file generation
- **CVE-based Exploit Search**: Search exploits for found vulnerabilities

### Post-Exploitation
- **LinPEAS**: Linux privilege escalation automation
- **WinPEAS**: Windows privilege escalation automation
- **Enumeration Scripts**: Custom scripts for both Linux and Windows
- **Post-Exploitation Guide**: Comprehensive guide for next steps

### Analysis & Reporting
- **Automated Reports**: Markdown format analysis reports
- **Manual Analysis Guidance**: Structured approach to findings
- **Result Organization**: Organized directory structure

## Installation

### Prerequisites
```bash
# Install required tools
sudo apt update
sudo apt install -y nmap nikto sqlmap gobuster dirb searchsploit

# Optional: Install Metasploit Framework
sudo apt install -y metasploit-framework

# Optional: Install additional recon tools
sudo apt install -y enum4linux smbclient smtp-user-enum dnsrecon
```

### Script Setup
```bash
# Download the script
wget https://your-repo/pentest.sh

# Make it executable
chmod +x pentest.sh

# (Optional) Move to PATH
sudo cp pentest.sh /usr/local/bin/
```

## Usage

### Basic Syntax
```bash
./pentest.sh -H <TARGET> -t <TYPE>
```

### Parameters
- `-H, --host`: Target IP address or hostname (required)
- `-t, --type`: Scan type (required)
- `-d, --dns`: Custom DNS server (optional)
- `-o, --output`: Output directory (optional)
- `-s, --static-nmap`: Path to static nmap binary (optional)

### Scan Types

#### Network Scanning
```bash
./pentest.sh -H 192.168.1.1 -t Network
./pentest.sh -H 192.168.1.1 -t Port
./pentest.sh -H 192.168.1.1 -t Script
./pentest.sh -H 192.168.1.1 -t Full
./pentest.sh -H 192.168.1.1 -t UDP
```

#### Vulnerability Assessment
```bash
./pentest.sh -H 192.168.1.1 -t Vulns
./pentest.sh -H 192.168.1.1 -t Recon
```

#### Web Application Testing
```bash
./pentest.sh -H 192.168.1.1 -t Web
```

#### Exploitation & Post-Exploitation
```bash
./pentest.sh -H 192.168.1.1 -t Exploit
./pentest.sh -H 192.168.1.1 -t Post
```

#### Analysis
```bash
./pentest.sh -H 192.168.1.1 -t Analysis
```

#### Complete Assessment
```bash
./pentest.sh -H 192.168.1.1 -t All
```

## Output Structure

The script creates an organized directory structure:

```
<OUTPUT_DIR>/
├── nmap/              # Nmap scan results
│   ├── Port_HOST.nmap
│   ├── Script_HOST.nmap
│   ├── Full_HOST.nmap
│   ├── UDP_HOST.nmap
│   └── Vulns_HOST.nmap
├── web/               # Web application testing
│   ├── nikto_HOST_80.txt
│   ├── sqlmap_HOST_80/
│   └── gobuster_HOST_80.txt
├── exploits/          # Exploit search results
│   ├── search_OS_HOST.txt
│   ├── search_services_HOST.txt
│   └── msf_suggestions_HOST.rc
├── post/              # Post-exploitation tools
│   ├── linux_enum_HOST.sh
│   ├── windows_enum_HOST.txt
│   └── post_exploitation_guide_HOST.txt
├── analysis/          # Analysis reports
│   └── analysis_report_HOST.md
├── recon/             # Reconnaissance results
│   ├── smbmap_HOST.txt
│   └── enum4linux_HOST.txt
└── pentest_HOST_TYPE.txt  # Full scan log
```

## Examples

### Vulnyx Machine Example
```bash
# Initial reconnaissance
./pentest.sh -H 192.168.1.100 -t Network

# Port and service discovery
./pentest.sh -H 192.168.1.100 -t Port

# Vulnerability scanning
./pentest.sh -H 192.168.1.100 -t Vulns

# Web application testing (if web ports found)
./pentest.sh -H 192.168.1.100 -t Web

# Search for exploits
./pentest.sh -H 192.168.1.100 -t Exploit

# Post-exploitation (after gaining access)
./pentest.sh -H 192.168.1.100 -t Post

# Generate analysis report
./pentest.sh -H 192.168.1.100 -t Analysis
```

### Complete Assessment
```bash
# Run everything at once
./pentest.sh -H 192.168.1.100 -t All
```

## Tool Integration Details

### SQLMap
- Automatically detects HTTP/HTTPS ports
- Interactive confirmation before scanning
- Results saved in organized directories
- Batch mode for automated testing

### LinPEAS/WinPEAS
- Automatic download if not present
- Transfer instructions provided
- Usage guidance included
- Custom enumeration scripts included

### Searchsploit
- OS-based exploit search
- Service-based exploit search
- CVE-based exploit search
- Results organized by category

### Metasploit
- Module suggestions based on findings
- Resource file generation
- Quick search commands
- Common exploit modules listed

## Important Notes

### Legal Disclaimer
This tool is for **educational purposes and authorized security testing only**. Always obtain proper authorization before testing any systems. Unauthorized access to computer systems is illegal.

### Usage Guidelines
1. Only test systems you own or have permission to test
2. Use responsibly and ethically
3. Respect privacy and data protection laws
4. Document all findings properly
5. Report vulnerabilities responsibly

### Limitations
- Some features require root/sudo privileges
- Web testing may be intrusive - use with caution
- Post-exploitation tools require manual transfer to target
- Not a replacement for manual testing and analysis
- Some tools may not be available on all systems

### Best Practices
1. Start with Network and Port scans
2. Review results before proceeding
3. Use specific scan types when possible
4. Always review automated findings manually
5. Keep detailed notes and documentation
6. Test in a controlled environment first

## Troubleshooting

### Nmap not found
```bash
sudo apt install nmap
```

### SQLMap not found
```bash
sudo apt install sqlmap
```

### Permission denied
```bash
chmod +x pentest.sh
```

### UDP scan requires sudo
```bash
sudo ./pentest.sh -H <TARGET> -t UDP
```

### LinPEAS/WinPEAS download fails
Manual download from: https://github.com/carlospolop/PEASS-ng/releases

## Contributing

Contributions are welcome! Please feel free to submit issues or pull requests.

## License

This script is provided as-is for educational purposes. Use responsibly and legally.

## Acknowledgments

- nmapAutomator for the scanning framework
- PEASS-ng for LinPEAS/WinPEAS
- Offensive Security for Metasploit
- All the open-source security tools integrated

## Support

For issues or questions, please refer to the documentation of individual tools used in this script.
