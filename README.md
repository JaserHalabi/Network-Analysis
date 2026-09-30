# Network Analysis and Security Portfolio

Hands-on network analysis, packet inspection, and vulnerability labs. This repository contains packet capture files (.pcap/.pcapng), lab write-ups, analysis scripts, and traffic breakdowns created during coursework and self-study.

## Overview

The primary focus of this repository is analyzing network protocols, identifying misconfigurations, and detecting malicious traffic patterns in controlled lab environments.

Key focus areas:
- Protocol Analysis: Deep packet inspection of TCP/IP stack protocols (ARP, IP, ICMP, TCP, UDP, DNS, HTTP, TLS).
- Traffic Troubleshooting: Diagnosing latency, packet loss, retransmissions, and abnormal packet flows.
- Attack Signatures: Identifying scans (SYN scan, Xmas scan), spoofing (ARP/DNS spoofing), brute force attacks, and cleartext credential leaks.
- Automation: Writing Python scripts with Scapy to parse captures, craft packets, and automate repetitive analysis.

## Repository Layout

```text
├── labs/
│   └── (individual lab folders with reports and findings)
├── captures/
│   └── (raw and filtered .pcap / .pcapng files)
├── screenshots/
│   └── (annotated packet diagrams and Wireshark captures)
├── scripts/
│   ├── requirements.txt
│   └── (Python and Bash helper scripts)
└── resources/
    └── (filter cheatsheets, reference notes, and study guides)
```

## Labs and Case Studies

| ID | Topic | Protocols / Tools | Description |
|---|---|---|---|
| [Lab 01](labs/lab-01-wireshark-packet-filtering/) | Wireshark Packet Capture and Filtering Basics | Wireshark, TCP, UDP, HTTP, Ethernet | Getting started with Wireshark, packet list columns, display filters, and logical operators |
| Lab 02 | TCP Handshake and Connection Teardown | TCP, Wireshark | Analyzing sequence numbers, window sizing, flags (SYN, ACK, FIN, RST) |
| Lab 03 | ARP Spoofing and Mitigation | ARP, Scapy | Demonstrating ARP cache poisoning in a local virtual network |
| Lab 04 | Port Scanning and Reconnaissance | Nmap, TCP/UDP | Detecting various Nmap scan types (SYN stealth, UDP, NULL scan) from PCAP data |
| Lab 05 | Cleartext Protocol Vulnerabilities | HTTP, FTP, Telnet | Extracting credentials and unencrypted sensitive data from packet streams |

*(Lab write-ups and captures are added as experiments are completed.)*

## Tools and Environment

- Wireshark: Protocol decoding, packet inspection, and stream following
- tcpdump: Headless traffic captures on Linux test hosts
- Nmap: Network mapping and port state analysis
- Python (Scapy, pyshark): Automated packet parsing and analysis
- Virtualization: VirtualBox / VMware host-only network topology for safe experimentation

## Useful Wireshark Display Filters

Common filters used throughout these labs:

| Filter | Description |
|---|---|
| `tcp.flags.syn == 1 && tcp.flags.ack == 0` | Identify initial TCP connection requests (SYN packets) |
| `tcp.analysis.retransmission` | Highlight packet retransmissions indicating packet loss or network congestion |
| `dns.flags.response == 0` | View DNS queries |
| `http.request.method == "POST"` | Filter for HTTP POST requests (often containing form or login submissions) |
| `arp.duplicate-address-frame` | Spot potential IP/ARP conflicts or ARP poisoning attempts |
| `icmp.type == 8 || icmp.type == 0` | Track ICMP Echo requests and replies |

## Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/JaserHalabi/Network-Analysis.git
cd Network-Analysis
```

### 2. Inspect Captures
Open any `.pcap` or `.pcapng` file from the `captures/` folder directly in Wireshark. Each lab folder also contains the relevant capture slice used in its report.

### 3. Setup Python Environment
To run the analysis scripts:
```bash
python -m venv venv
# On Windows:
.\venv\Scripts\activate
# On Linux/macOS:
source venv/bin/activate

pip install -r scripts/requirements.txt
```

## Disclaimer

All packet captures, port scans, and security tests were conducted in isolated lab environments on local virtual machines or on networks where explicit authorization was granted. This repository is intended strictly for academic, educational, and defensive security learning.