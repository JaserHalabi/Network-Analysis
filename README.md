# Network Traffic and Protocol Analysis Portfolio

[![Platform](https://img.shields.io/badge/Tool-Wireshark%204.x-blue?style=flat-square)](https://www.wireshark.org/)
[![Focus](https://img.shields.io/badge/Focus-Packet%20Inspection%20%26%20Security-informational?style=flat-square)](#overview)
[![Status](https://img.shields.io/badge/Labs%20Completed-1%20Documented-success?style=flat-square)](#labs)
[![Analyst](https://img.shields.io/badge/Analyst-Jaser%20Halabi-lightgrey?style=flat-square&logo=github)](https://github.com/JaserHalabi)

> A practical portfolio of packet capture analyses, protocol inspections, and network security labs using **Wireshark**, **tcpdump**, and traffic filtering techniques.

---

## Overview

This repository documents hands-on network traffic analysis, protocol inspection, and security investigations conducted during coursework and self-study. 

Each lab contains a dedicated write-up with step-by-step methodologies, annotated screenshots, and packet analysis.

---

## Labs

Click on a lab below to view its full write-up, procedures, and screenshots:

| # | Lab Module | Key Topics | Status | Link |
|---|---|---|:---:|:---:|
| 01 | **Wireshark Packet Capture & Filtering Basics** | Adapter selection, packet columns, display filters, and logical operators | Complete | [View Lab 01](./labs/lab-01-wireshark-packet-filtering/) |
| 02 | **TCP Handshake & Connection Teardown** | 3-way handshake analysis, sequence/ack numbers, and connection flags | In Progress | Planned |
| 03 | **ARP Traffic & Spoofing Detection** | ARP resolution flows, cache poisoning, and duplicate address detection | Planned | Planned |
| 04 | **Port Scan Reconnaissance Signatures** | Distinguishing SYN stealth, Xmas, and UDP scans from capture data | Planned | Planned |
| 05 | **Cleartext Protocols & Credential Exposure** | Examining unencrypted HTTP, FTP, and Telnet traffic streams | Planned | Planned |

---

## Repository Structure

```text
wireshark/
├── README.md                               ← Main portfolio dashboard (this file)
├── .gitignore
├── labs/
│   ├── README.md                           ← Labs index
│   └── lab-01-wireshark-packet-filtering/  ← Lab 01 write-up and screenshots
├── captures/                               ← Packet capture files (.pcap / .pcapng)
├── screenshots/                            ← Additional diagrams and reference images
├── scripts/                                ← Helper scripts and automation
└── resources/                              ← Reference guides and links
```

---

## Tools Used

- **Wireshark**: Packet capture, protocol inspection, and stream analysis
- **tcpdump**: Command-line packet capture on Linux hosts
- **Nmap**: Network discovery and port scanning
- **Python (Scapy)**: Scripted packet manipulation and parsing

---

## Disclaimer

All packet captures and security tests were conducted in isolated lab environments on local virtual machines or on networks where explicit authorization was granted. This repository is intended strictly for academic and defensive network security education.

---

_Maintained by **[Jaser Halabi](https://github.com/JaserHalabi)**_