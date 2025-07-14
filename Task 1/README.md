# Nmap Network Scan Report

## Objective
Perform a network scan to identify open ports and running services on a target system using Nmap. The goal is to assess the system's exposed services and understand their significance from a cybersecurity perspective.

---

## 🛠Tools Used
- **Nmap** (Network Mapper) - Version 7.95
- **Operating System**: Kali Linux
- **Target IP Address**: 192.168.29.147

---

## Scan Command Used
```bash
nmap -sS -sV 192.168.29.147 -oN nmap_scan_results.txt
```
-sS: Stealth TCP SYN scan
-sV: Service version detection
-oN: Save output to a file in normal format


