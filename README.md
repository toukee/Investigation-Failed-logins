# Investigation-Failed-logins

## Objective

To investigate an alert involving multiple failed login attempts across several systems and determine whether the activity represented normal user behavior or malicious brute‑force attempts. This project demonstrates my ability to analyze authentication logs, identify attacker patterns, correlate events across systems, and document findings using a structured SOC investigation workflow

### Skills Learned

- Identifying brute‑force indicators across authentication logs
- Reviewing failed login attempts targeting privileged accounts (Administrator, admin)
- Analyzing geographic anomalies in sign‑in activity (North Korea, Israel)
- Correlating events across multiple systems (SOC‑FW‑RDP, SHIR‑Hive, SHIR‑SAP)
- Understanding attacker intent based on targeted systems (Hive, SAP databases)
- Strengthening triage workflow: who → what → when → where → why → how
- Documenting findings clearly and professionally for SOC reporting
- Recommending security hardening measures such as MFA, lockout policies, and account hygiene


### Tools Used

- Microsoft Defender XDR – alert review, identity insights, geographic sign‑in analysis
- Microsoft Sentinel – log analysis, KQL queries, incident triage
- Azure Portal – reviewing user accounts, sign‑in logs, and resource activity
- Windows Event Viewer – authentication event validation
- CyberChef – decoding and quick data parsing
- VirusTotal – validating suspicious IP addresses
- Notepad++ – investigation notes and documentation


## Steps

🏠  [Back to Portfolio](https://www.notion.so/Toukee-Vang-Portfoilo-29c0c3b8580a803ea4c7e402115d24a2?pvs=21) 

▶️  Next Document 

[Investigating Notes](https://www.notion.so/Investigating-Notes-2a50c3b8580a805e8795c81837192251?pvs=21) 

# You received an alert about multiple failed logins, investigate and document you findings.

# Findings

Attackers where used brute forcing attack to try and login into these accounts. There was more than 10,000 attacks done with in seconds which would refer to script that is ran to brute force access but failed. Main targeted account was the (ADMINISTRATOR, admin, administrator) accounts. The attacker focused their attack on three main computer (SOC-FW-RDP, SHIR-Hive, SHIR-SAP)

# Investigation Summary

## Who

Logs showing two locations ( North Korean, Israel ). IP Address 175.45.176.99 shown to have used North Korean and Israel to connect to Microsoft Azure accounts. There are two users accounts (JohnS, Adele Vance) that are used to access Microsoft applications. User (JohnS) is disable because location is coming from North Korea, while user (Adele Vance) is still accessible from Israel.  ( see fig.1)

## What

Attackers is using brute force attack on the three main computers (SOC-FW-RDP, SHIR-Hive, SHIR-SAP) to gain access to administrator accounts but attack failed to gain access. ( see Fig. 2 & 3)

## When

The attack happen on 4/16/2021 from 8:34 am - 9:33 am UTC and no future logs to detect if attack is still happening. 

## Where

Three main computer (SOC-FW-RDP, SHIR-Hive, SHIR-SAP)

## Why

From the logs the attacker was targeting the database (Hive, SAP). The intent for the attacker should be getting as much data as possible. 

## How

Attacks tried to brute force access to the three main computers. 

# Recommendations:

Suggest recommendation to implementing multi-factor authentication, password time-out, password timeout after 5 failed attempts, password reset after 90 day, no password reused, disable or remove accounts that are not activity in used.

# Appendix:

<img width="1517" height="400" alt="image" src="https://github.com/user-attachments/assets/1585a977-f30d-463d-9aa3-17e6487d251d" />


FIg. 1

<img width="805" height="718" alt="image" src="https://github.com/user-attachments/assets/f66e2702-f349-4574-9fe2-b539607a3720" />


FIg. 2

<img width="649" height="613" alt="image" src="https://github.com/user-attachments/assets/02136cee-d81e-4ec3-adb4-e5f8e73811b4" />


Fig. 3
