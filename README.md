# # NightFall Project — Suspicious Network Connection Scanner (Python)

## Overview
NightFall Case 001 **“The Quiet Beacon”**  
This project is a lightweight Python-based network analysis tool designed to help analysts quickly identify suspicious or abnormal network behavior on a Windows system. It performs a single-shot scan, analyzes patterns, and generates a clean JSON report suitable for SOC triage, threat hunting, or incident documentation.

This tool reflects the NightFall philosophy and the ǃGURA tracking mindset:  
**observe movement → identify patterns → understand behavior → track deviations → act decisively.**

---

## Features
- Collects active TCP/UDP network connections  
- Parses and structures netstat output  
- Flags:
  - Unusual ports  
  - Repeated outbound connections (possible beaconing)  
  - Unexpected listeners  
- Whitelisting to reduce noise  
- Outputs a JSON report for documentation or further analysis  
- No admin rights required  
- No external libraries needed  

---

## Use Cases
- SOC triage  
- Threat hunting  
- Baseline creation  
- Early-stage anomaly detection  
- Lightweight IR support  
- Training and portfolio demonstration  

---

## How It Works
1. The script calls `netstat -ano` to collect all active connections.  
2. It parses the output into structured Python dictionaries.  
3. It applies simple behavioral rules to identify anomalies.  
4. It filters out known-noise IPs (0.0.0.0, 127.0.0.1, ::).  
5. It prints suspicious findings to the console.  
6. It saves a JSON report named `nightfall_network_report.json`.

---

## Running the Tool
```powershell
python scanner.py
Custom python scanner
