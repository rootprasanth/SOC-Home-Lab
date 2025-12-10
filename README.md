# 🛡️ SOC Home Lab — Splunk + Wazuh + Sysmon + Atomic Red Team + Kali (AWS Cloud)

This repository showcases my personal **SOC & Detection Engineering Home Lab**, built using **AWS Cloud infrastructure** and a physical **Windows endpoint**.The goal of this project is to replicate a real-world SOC environment to practice log analysis, detection engineering, MITRE ATT&CK mapping, and incident investigation.

---

## 🚀 Overview

This home lab simulates an enterprise detection environment where I can emulate meaningful attacks and engineer detections in real-time.

* **Attack Simulation:** A Windows 10 Victim Laptop generates real attacker telemetry.
* **Telemetry:** Visibility provided by **Sysmon**, **PowerShell Logging**, and **Windows Security Logs**.
* **Log Ingestion:** Logs are forwarded simultaneously to:
    * **Splunk SIEM** (Hosted on AWS Ubuntu)
    * **Wazuh XDR + SIEM** (Hosted on AWS Ubuntu)
* **Adversary:**
    * A **Kali Linux machine** (AWS) performs real external attacks.
    * **Atomic Red Team** executes MITRE-mapped adversary techniques locally.

---

## 🏗️ Architecture

### 🔧 Components

| Component | Platform | Purpose |
| :--- | :--- | :--- |
| **Splunk Server** | AWS Ubuntu | SIEM log analytics, dashboards, and custom detections. |
| **Wazuh Manager** | AWS Ubuntu | MITRE ATT&CK alerts, XDR analysis, and file integrity monitoring. |
| **Kali Linux Attacker** | AWS Ubuntu | External adversary simulation (C2, Scanning, Exploits). |
| **Windows 10 Laptop** | Physical | Endpoint telemetry source + Atomic Red Team execution target. |

---

## 🧪 What I Perform in This Lab

### ✔ External Attacks (Kali Linux)
* **Port Scanning:** Nmap scans to identify open services.
* **Enumeration:** Service version detection and OS fingerprinting.
* **Brute Force:** Hydra/Medusa simulations against RDP/SSH.
* **Exploit Attempts:** Metasploit framework execution.
* **Reverse Shells:** Testing C2 connectivity and payload delivery.

### ✔ Internal Attacks (Atomic Red Team)
* **PowerShell Execution:** Obfuscated commands and script block logging (T1059).
* **Process Injection:** Mimicking malware behavior (T1055).
* **Persistence:** Registry run keys and scheduled tasks (T1547).
* **Discovery:** Network and system information discovery (T1082).

---

## 📊 Detection & Analysis

### 🦅 Splunk
* **Sysmon Monitoring:** Analysis of Event ID 1 (Process Create) and Event ID 3 (Network Connection).
* **PowerShell Activity:** Hunting for base64 encoded commands and suspicious downloads.
* **Brute Force:** Correlating multiple failed login attempts (Event ID 4625).
* **MITRE Alignment:** Building correlation searches mapped to specific TTPs.

### 🐺 Wazuh
* **MITRE ATT&CK Mapping:** Automated alerts mapped to the MITRE framework.
* **Real-time Alerts:** Triggering on file changes, configuration assessment, and malware detection.
* **Threat Intel:** Correlation with integrated threat intelligence feeds.
* **Log Ingestion:** Unified collection of Sysmon and WinEventLogs.

---

### 📬 Contact
Feel free to reach out if you have questions about the configuration or detection rules used in this lab!
