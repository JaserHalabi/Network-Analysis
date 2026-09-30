# Network Traffic and Protocol Analysis Portfolio

[![Platform](https://img.shields.io/badge/Tool-Wireshark%204.x-blue?style=flat-square)](https://www.wireshark.org/)
[![Focus](https://img.shields.io/badge/Focus-Packet%20Inspection%20%26%20Security-informational?style=flat-square)](#overview)
[![Status](https://img.shields.io/badge/Labs%20Completed-1%20Documented-success?style=flat-square)](#lab-execution-matrix)
[![Analyst](https://img.shields.io/badge/Analyst-Jaser%20Halabi-lightgrey?style=flat-square&logo=github)](https://github.com/JaserHalabi)

> A practical portfolio of packet capture analyses, protocol inspections, and network security investigations using **Wireshark**, **tcpdump**, and traffic filtering techniques.

---

## Overview

This repository documents hands-on network traffic analysis, packet inspection, and vulnerability discovery. Rather than purely theoretical study, each lab focuses on capturing live data, dissecting packet headers across the TCP/IP stack, and applying display filters and logical operators to detect anomalies and isolate critical traffic.

### Core Focus Areas

- **Protocol Inspection:** Analyzing packet structure and headers across Ethernet, IP, ARP, ICMP, TCP, UDP, and application-layer protocols (HTTP, DNS).
- **Traffic Filtering:** Using Wireshark display filters and boolean logic to isolate relevant sessions from high-volume captures.
- **Traffic Troubleshooting:** Identifying retransmissions, latency, malformed packets, and abnormal connection teardowns.
- **Security Analysis:** Detecting reconnaissance scans, cleartext credential transmission, and spoofing attempts in controlled environments.

---

## Lab Execution Matrix

| # | Lab Module | Protocols / Tools | Highlights | Status |
|---|---|---|---|:---:|
| 01 | **[Wireshark Packet Capture & Filtering Basics](./labs/lab-01-wireshark-packet-filtering/)** | Wireshark, TCP, UDP, HTTP, Ethernet | Interface capture, packet columns, display filters, and logical operators | Complete |
| 02 | **TCP Handshake & Teardown Analysis** | TCP, Wireshark | 3-way handshake (SYN, SYN-ACK, ACK), sequence numbers, and FIN/RST flags | In Progress |
| 03 | **ARP Traffic & Spoofing Detection** | ARP, Scapy | ARP request/reply flows and identifying duplicate MAC conflicts | Planned |
| 04 | **Port Scan Reconnaissance Signatures** | Nmap, TCP/UDP | Distinguishing SYN stealth, Xmas, and UDP scans in packet dumps | Planned |
| 05 | **Cleartext Protocols & Credential Exposure** | HTTP, FTP, Telnet | Extracting unencrypted credentials and session data from raw streams | Planned |

---

## Quick Reference: Wireshark Display Filters

Frequently used filters across these labs:

| Filter Syntax | Description |
|---|---|
| `ip.addr == <IP>` | Matches any packet containing the target IP as source or destination |
| `ip.src == <IP>` | Isolates traffic originating from a specific source IP |
| `ip.dst == <IP>` | Isolates traffic destined to a specific target IP |
| `tcp.port == 80` | Filters for TCP traffic on port 80 (HTTP) |
| `udp.port == 53` | Filters for UDP traffic on port 53 (DNS) |
| `eth.addr == <MAC>` | Matches Layer 2 frames by hardware (MAC) address |
| `tcp.flags.syn == 1 && tcp.flags.ack == 0` | Filters for initial TCP connection requests (SYN) |
| `tcp.flags.ack == 1` | Isolates TCP acknowledgment packets |
| `tcp.analysis.retransmission` | Identifies packet retransmissions from packet loss or network issues |
| `not <protocol>` or `!<protocol>` | Excludes a protocol from the view (e.g. `not udp`) |

### Boolean Logic Operators

| Operator | Syntax | Description | Example |
|---|---|---|---|
| AND | `and` or `&&` | All conditions must be true | `ip.src == 198.199.14.10 and ip.dst == 192.168.0.54` |
| OR | `or` or `\|\|` | At least one condition must be true | `ip.src == 198.199.14.10 or ip.src == 192.168.0.54` |
| NOT | `not` or `!` | Condition must NOT match | `not udp` |
| XOR | `xor` or `^^` | Only one condition must match, not both | `ip.addr == 10.0.0.1 xor ip.addr == 10.0.0.2` |

---

## Repository Structure

```text
wireshark/
├── README.md                               ← Main portfolio dashboard (this file)
├── .gitignore                              ← Ignored temporary and binary files
├── labs/
│   ├── README.md                           ← Labs index and overview
│   └── lab-01-wireshark-packet-filtering/  ← Lab 01 report and annotated screenshots
│       ├── README.md
│       └── screenshots/
├── captures/                               ← Raw and filtered .pcap / .pcapng files
├── screenshots/                            ← Additional diagrams and reference captures
├── scripts/                                ← Python (Scapy) and Bash helper scripts
│   ├── README.md
│   └── requirements.txt
└── resources/                              ← Reference notes and filter cheat sheets
```

---

## Tools and Environment

- **Packet Analyzer:** [Wireshark](https://www.wireshark.org/) 4.x
- **Command-Line Capture:** tcpdump
- **Network Scanner:** Nmap
- **Packet Crafting / Automation:** Python 3 (Scapy)
- **Lab Environment:** Isolated virtual network / host-only adapters

---

## How to Use

1. **Clone the repository:**
   ```bash
   git clone https://github.com/JaserHalabi/Network-Analysis.git
   cd Network-Analysis
   ```

2. **Explore the labs:**
   Browse to any lab inside the `labs/` directory to read the full step-by-step write-up and view supporting screenshots.

3. **Inspect capture files:**
   Any `.pcap` or `.pcapng` files in `captures/` can be opened directly in Wireshark for hands-on analysis.

---

## Disclaimer

All packet captures and analysis activities in this repository were conducted on local test hosts, virtual machines, or networks where explicit authorization was granted. This repository is strictly for academic and defensive network security education.

---

_Maintained by **[Jaser Halabi](https://github.com/JaserHalabi)**_