
# SOC Analyst Simulation – SSH Brute Force Detection using Splunk SIEM

![Splunk](https://img.shields.io/badge/SIEM-Splunk-orange)
![Linux](https://img.shields.io/badge/OS-Ubuntu-purple)
![Kali Linux](https://img.shields.io/badge/Attacker-Kali%20Linux-blue)
![Security](https://img.shields.io/badge/Domain-SOC%20Analysis-green)

## 1. Project Overview

This project demonstrates a hands-on Security Operations Center (SOC) analyst simulation focused on detecting and investigating SSH brute-force attacks using Splunk SIEM.

The lab simulates suspicious SSH authentication activity from a Kali Linux machine against an Ubuntu system. Authentication logs are collected and analyzed in Splunk to identify repeated failed login attempts, investigate source IP addresses, and monitor targeted user accounts.

## 2. Project Objectives

- Simulate SSH brute-force activity in an authorized lab environment.
- Generate authentication failure events.
- Collect and analyze Linux authentication logs using Splunk.
- Develop SPL queries for suspicious login detection.
- Identify attacker IP addresses and targeted usernames.
- Build dashboards for security event visualization.
- Configure alerts for suspicious authentication activity.

## 3. Lab Architecture

| Component | Description |
|---|---|
| Attacking Machine | Kali Linux |
| Target Machine | Ubuntu Linux |
| Attack Technique | SSH Brute Force |
| Attack Tool | Hydra |
| Log Source | Linux auth.log |
| SIEM Platform | Splunk |
| Query Language | SPL |
| Protocol | SSH |

### Lab Workflow

1. Kali Linux generates SSH authentication attempts against the Ubuntu host.
2. Ubuntu records authentication failures in auth.log.
3. Authentication logs are ingested into Splunk.
4. SPL queries identify failed login activity.
5. Dashboards visualize suspicious events.
6. Alerts help identify repeated authentication failures.

## 4. Attack Simulation

An SSH brute-force simulation was performed using Hydra in a controlled lab environment.

**Simulation details:**

- Tool: Hydra
- Parallel tasks: 16
- Wordlist: rockyou.txt
- Wordlist size: 14M+ passwords
- Generated failed-login events: 857

The simulation generated authentication failure records in the Ubuntu auth.log file.

## 5. Log Analysis and Detection

The collected authentication logs were ingested into Splunk using the linux_secure source type.

SPL queries were developed to:

- Identify failed SSH login attempts.
- Extract source IP addresses.
- Identify targeted usernames.
- Analyze repeated authentication failures.
- Track suspicious login activity over time.

See the `queries/` directory for the detection queries.

## 6. Dashboard Development

A three-panel Splunk dashboard was developed.

### Dashboard Components

1. Attack Timeline – Visualizes SSH authentication failures over time.
2. Top Attacker IPs – Identifies source IP addresses generating failed logins.
3. Targeted Users – Identifies usernames targeted during authentication attempts.

## 7. Findings and Results

| Metric | Result |
|---|---:|
| Failed-login events | 857 |
| Hydra parallel tasks | 16 |
| Wordlist size | 14M+ |
| Identified attacker IPs | 1 |
| Targeted account | ubuntu |
| Dashboard panels | 3 |

The investigation identified repeated failed SSH authentication attempts originating from one source IP and targeting the Ubuntu account.

## 8. Skills Demonstrated

- SIEM Monitoring
- Linux Log Analysis
- SSH Authentication Monitoring
- Brute Force Detection
- SPL Query Development
- Security Dashboard Creation
- Alert Configuration
- Incident Investigation

## 9. Repository Structure

```text
SOC-Analyst-Simulation-Splunk/
├── README.md
├── screenshots/
├── queries/
├── reports/
└── documentation/
```

## 10. Screenshots

Screenshots of the attack simulation, authentication logs, Splunk dashboard, and alert configuration are available in the `screenshots/` directory.

## 11. Key Learnings

This project provided practical experience in understanding authentication attacks, analyzing Linux security logs, developing SIEM detection queries, visualizing suspicious activities, and investigating potential security incidents.

## 12. Disclaimer

This project was conducted in a controlled lab environment using systems under my control. It is intended solely for educational and defensive cybersecurity purposes.
