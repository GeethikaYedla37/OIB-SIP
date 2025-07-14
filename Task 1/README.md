# Nmap Network Scan Report

## Objective
Perform a network scan to identify open ports and running services on a target system using Nmap. The goal is to assess the system's exposed services and understand their significance from a cybersecurity perspective.

---

## Tools Used
- **Nmap** (Network Mapper) - Version 7.95
- **Operating System**: Kali Linux
- **Target IP Address**: 192.168.29.147

---

## Scan Command Used
```bash
nmap -sS -sV 192.168.29.147 -oN nmap_scan_results.txt
```
- -sS: Stealth TCP SYN scan
- -sV: Service version detection
- -oN: Save output to a file in normal format


## Summary of Open Ports and Services

| Port  | State | Service         | Description                                 |
|-------|-------|------------------|---------------------------------------------|
| 135   | open  | msrpc            | Microsoft RPC                               |
| 139   | open  | netbios-ssn      | NetBIOS Session Service                     |
| 445   | open  | microsoft-ds     | SMB over TCP                                |
| 554   | open  | rtsp?            | Possibly Real-Time Streaming Protocol       |
| 2869  | open  | http             | Microsoft HTTPAPI httpd 2.0 (UPnP)          |
| 5357  | open  | http             | Microsoft HTTPAPI httpd 2.0 (UPnP)          |
| 10243 | open  | http             | Microsoft HTTPAPI httpd 2.0 (UPnP)          |
| 5040  | open  | unknown          | Possibly VirtualBox Virtual NIC             |

