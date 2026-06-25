# SOC Analyst Notes

## SOC Levels

SOC analysts are divided into three levels, each handling progressively more complex work.

- **L1** - Entry level
  - Monitors the network.
  - If anything malicious is found, forwards it to L2 after initial analysis.
- **L2** - Handles deeper investigation and analysis.
- **L3** - Handles advanced incidents, threat hunting, and complex investigations.

## Tools Used

### SIEM (Security Information and Event Management)

Common SIEM tools:

- Splunk
- Wazuh
- Microsoft Sentinel
- IBM QRadar

SIEM is used for:

- Collecting logs
- Analyzing logs and events
- Detecting threats
- Alerting analysts

## VirusTotal

File checking using VirusTotal:

1. Get the sample file.
2. Navigate to VirusTotal.
3. Upload the file.
4. Analyze the results.

## Skills Required

- OS knowledge
- Security knowledge
- Problem-solving skills
- Communication skills

## SOC Best Practices

- Never ignore alerts.
- Don't delete logs.
- Don't escalate without analysis.
- Don't panic.
- Document everything.

## SOC Career Progression

- Junior SOC Analyst
- Senior SOC Analyst
- SOC Analyst
- SOC Manager
- SOC Director

## Certifications to Look Out For

- Security+
- CySA+
- CCNA
- GCIH
- GCIP

# Cybersecurity Basics

## What is Cybersecurity?

- Protection of data and digital systems.
- A SOC analyst monitors, detects, and responds to real-time threats.

### Risk Formula

```text
Threat × Vulnerability = Risk
```

## Domains of Cybersecurity

- Network Security
- Application Security
- Endpoint Security
- Cloud Security
- Identity and Access Management (IAM)
- Security Operations

## CIA Triad

- Confidentiality
- Integrity
- Availability

## Cyber Threats

### Malware (Malicious Software)

- Virus
- Ransomware
- Trojan
- Worm
- Spyware

Other threats:

- Phishing
- Insider threats
- APTs (Advanced Persistent Threats)

## Common Attack Types

- Brute force
- DDoS
- SQL Injection
- Zero-day attacks

### Example

- WannaCry ransomware (2017)

## Cyber Kill Chain

1. Reconnaissance
2. Weaponization
3. Delivery
4. Exploitation
5. Installation
6. Command and Control (C2)
7. Actions on Objectives

## Defense in Depth

Onion-like security using multiple layers:

- Perimeter
- Network
- Endpoint
- Application
- Data
- Human

## Basics to Learn

- IP
- Ports
- Protocols
- Firewalls
- Network Segmentation

## Endpoint Security

- Antivirus
- Hardening (disable unused services and apply security configurations)
- Patching

## Email Security

- Phishing protection
- URL filtering
- Sandboxing

## Log Sources

- Windows Event Logs
- Firewall logs
- DNS logs
- VPN logs

## Practice Labs

- TryHackMe rooms
- Hack The Box (HTB) rooms
- Safe home labs

## General Best Practices

- Strong passwords
- Regular software updates
- Avoid public Wi-Fi
- Use antivirus and firewalls
- User awareness training

## Practice Tasks

- Scan a file and a URL using VirusTotal.
- Perform WHOIS lookup and IP reputation checks.
- Check the strength of a password.

## Resources

- https://www.virusshare.com — Website where malware samples are shared.
