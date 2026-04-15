## Enterprise Security Monitoring Lab (DVWA + WAF + Honeypot + ELK)

## Overview

This project simulates a real-world enterprise cybersecurity environment where attacks are launched, detected, and mitigated using modern security tools.
The lab demonstrates both offensive (Red Team) and defensive (Blue Team) techniques.

## 🛠️ Technologies Used
	•	Damn Vulnerable Web Application (DVWA) – Vulnerable web application
	•	Kali Linux – Attacker machine
	•	Metasploit – Exploitation framework
	•	Nmap – Network reconnaissance
	•	Cowrie – Attack monitoring
	•	ModSecurity – Web protection
	•	ELK Stack – Log monitoring & visualization

 ## 🧱 Lab Architecture

    Kali Linux (Attacker)
        |
        |  (Nmap, SQL Injection, SSH Brute Force)
        |
    Ubuntu Server (DVWA + ModSecurity + Cowrie)
        |
        |  (Logs)
        |
    ELK Stack (Monitoring & Visualization)

## ⚔️ Attack Simulation

## 🔍 1. Network Scanning

  Performed using Nmap to identify open ports and services.

  nmap -sV target-ip

## 💉 2. SQL Injection Attack

Executed on DVWA: ' OR 1=1 #

## Result:
	•	Authentication bypass achieved
	•	Demonstrates OWASP Top 10: Injection

## 🧰 3. Metasploit Enumeration

use auxiliary/scanner/http/http_version

## Result:
	•	Web server version discovered

 ## 🔐 4. SSH Brute Force Attack
 ssh root@<target-ip> -p 2222

## Result:
	•	Captured by Cowrie honeypot
	•	Logs show attempted credentials

## 🛡️ Defense Implementation

## 🔥 Web Application Firewall

Configured **ModSecurity with OWASP CRS:
	•	Enabled blocking mode: SecRuleEngine On

## Result:
  •	SQL injection attempts were successfully blocked (403 Forbidden)

## 👁️ Monitoring & Logging

Logs collected using ELK Stack

Monitored Events:

	•	Failed SSH logins
	•	SQL injection attempts
	•	HTTP requests

 ## 📊 Key Findings
 
	•	Weak input validation leads to SQL injection vulnerabilities
	•	Honeypots effectively capture attacker behavior
	•	WAF blocks malicious traffic in real time

## 🧠 MITRE ATT&CK Mapping
  
Activity	Technique:

    Scanning     	T1595
    SQL Injection	T1190
    Brute Force	    T1110
    
## 📌 Conclusion

This lab demonstrates how organizations can:

	•	Detect attacks using logs
	•	Prevent attacks using WAF
	•	Gain visibility into attacker behavior

## 🚀 Future Improvements

	•	Integrate alerting system (SIEM alerts)
	•	Add IDS/IPS (e.g., Suricata)
	•	Automate response
 
