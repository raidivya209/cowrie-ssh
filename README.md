# Cowrie SSH Honeypot Lab – Multi-Attacker Simulation & Threat Analysis

## 📄 Full Project Report
👉 [Download Full PDF Report](Report/Cowrie_Honeypot_REPORT.pdf)

## Overview
This project demonstrates the deployment and analysis of a Cowrie SSH honeypot to simulate real-world brute-force attacks, unauthorized login attempts, and post-compromise attacker behavior. The goal of this lab was to observe attacker techniques, collect telemetry, analyze logs, and map observed activity to the MITRE ATT&CK framework. The honeypot was deployed on Kali Linux, and multiple attacker identities were simulated using Linux network namespaces to generate traffic from different IP addresses. This setup allowed realistic attack behavior to be recorded and analyzed without exposing any real infrastructure.

## Objective
• Deploy and configure Cowrie SSH honeypot • Simulate brute-force and interactive SSH attacks • Capture attacker behavior and credentials • Analyze JSON logs using jq • Identify attack patterns • Map activity to MITRE ATT&CK • Extract Indicators of Compromise (IOCs) • Produce a professional incident-style report

## Lab Environment
| Component         | Description              |
| ----------------- | ------------------------ |
| Attacker OS       | Kali Linux               |
| Honeypot          | Cowrie SSH Honeypot      |
| Attack Tool       | Hydra                    |
| Log Format        | JSON                     |
| Analysis Tool     | jq                       |
| Simulation Method | Linux network namespaces |
 
## 🔧 Cowrie Installation
This section demonstrates the setup of Cowrie and its dependencies on Kali Linux.
![Cowrie Install](Screenshots/cowrie install 4.png)
![Python Install](Screenshots/python install 1.png)
![Git Clone](Screenshots/cowrie git 3.png)

## 🔐 SSH Login Simulation
![SSH Login](Screenshots/ssh login 9.png)
![SSH Logs](Screenshots/ssh login log 9.2.png)

## ⚔️ Hydra Brute Force Attacks
![Hydra Attack](Screenshots/multiple attacks 10.png)
![Multiple IPs](Screenshots/multiple attacks 10.1.png)

## 💻 Commands
All commands used during installation, attack simulation, and log analysis:
👉 [View Commands](commands-used.md)

## 📊 Logs
![Data Analysis](Screenshots/data analysis.png)
![10.0.1.1 Logs](Screenshots/10.0.1.1 log 12.2.png)
![10.0.2.1 Logs](Screenshots/10.0.2.1 log 12.3.png)

## Disclaimer
This project was conducted in a controlled lab environment for educational and research purposes only.
