## SOC Alert Investigation:  SOC176 - Brute Force Detected 

**Date:** 26 December 2025  
**Platform:** LetsDefend  
**Type of Alert:** Brute Force Detected
**Severity:** Medium
**Difficulty:** Beginner/Intermediate

**Initial Observation:**  

An alert was generated in the Letsdefend dashboard indicating a brute force activity. 
The alert description stated:
`“Login failure from a single source with different non-existing accounts.”`
The alert timestamp showed activity dated `March 7, 2024`, with repeated authentication failures.

**Investigation Steps:**

To help in identifying whether the alert was a false positive or a true positive, follow these steps:
1. Gather evidence from the alert dashboard. The alert was triggered with the message `
2. Login failure from a single source with different non-existing accounts`.
3. Identify Indicators of Compromise (IOC) using various tools. Tool Virustotal is appropriate since the alerts have both destination and source IP address. 
Navigated to the Log Management Tab using destination IP address `172.16.17.148`. 
* Multiple log entries were observed with the message:
 `Unknown user name or bad password`
* All failed login attempts originated from the same source IP address:
 `218.92.0.56`
4. Submitted both IP addresses to VirusTotal for reputation analysis.


**Tools Used:**
- VirusTotal
- LetsDefend Alert Dashboard
- Log Management Tab

**Findings:**
The Destination IP Address: `172.16.17.148`
No detections from security vendors
Considered clean


Source IP Address: `218.92.0.56` 
Flagged by 7/95 security vendors
Classified as: SSH Brute Force Attacker
Country of origin: China


**Conclusion:**
Based on log evidence and IOC reputation analysis, this alert was determined to be a true positive brute force attempt.

**What I Learned:**

* I learned that multiple failed login attempts from the same IP address targeting different accounts can indicate a brute force attack.
* I learned how to clearly document investigation steps and findings so the alert can be escalated or responded to properly.
* I learned how to confirm an alert by checking the reputation of the IP addresses to see if they are known for malicious activity.
