
# Home SOC Lab - SSH Brute Force Detection

This project demonstrates a real-world SOC workflow by simulating and detecting an SSH brute-force attack in a controlled lab environment. The attack was generated using Kali Linux and analyzed using Splunk SIEM in Ubuntu.

## 🧰Tools Used
- Splunk Enterprise
- Kali Linux
- Ubuntu Server
- Hydra
## ⚙️Lab Setup
- Target Machine: Ubuntu (running SSH service)
- Attacker Machine: Kali Linux
- SIEM: Splunk (log ingestion from /var/log/auth.log)
## 🚨Attack Simulation
- Conducted SSH brute-force attack using Hydra
- Targeted a user account with multiple password attempts
- Generated high-frequency failed login events
## 🔍 Detection & Analysis

- Monitored logs in Splunk using:

```bash
  index=main "Failed password"
```
- Identified attacker IP and attack timeline
- Created visualizations using timechart
- Calculated:
  - Total attempts
  - Attack duration
  - Attempts per minute

## 📊 Key Findings
- Attack Type: SSH Brute Force
- Service: SSH (port 22)
- Behavior: Multiple password attempts on single user
- Source: Single attacker IP
- No successful compromise observed
## 🧠 MITRE ATT&CK Mapping
- T1110 – Brute Force
- T1110.001 – Password Guessing
## 🛡️ Mitigation Strategies
- Disable password-based SSH authentication
- Implement Fail2Ban for automated blocking
- Restrict SSH access to trusted IPs
- Configure Splunk alerts for failed login spikes
## 📸Screenshots

![App Screenshot](https://github.com/raiaman35/soc-splunk-lab/blob/180b68cb67c85213e64d029397c460fa038783b0/Screenshots/VirtualBox_Ubuntu%20_23_04_2026_18_27_17.png)


## 📄Report

[incident-report.pdf](https://github.com/raiaman35/soc-splunk-lab/blob/1920d0815cf9c4cd00a1cf2feff42fd5ab7886f2/SOC_Incident_Report_INC-2026-01.pdf)

