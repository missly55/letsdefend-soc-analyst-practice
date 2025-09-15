## SOC Alert Investigation: SOC170 - Passwd Found in Requested URL - Possible LFI Attack

**Date:** 14 September 2025  
**Platform:** LetsDefend  
**Type of Alert:** Web Attack  
**Difficulty:** Beginner/Intermediate  

**Initial Observation:**  
While using the LetsDefend SIEM tool, I investigated an alert where an attacker used the malicious URL (`https://172.16.17.13/?file=../../../../etc/passwd`) to access sensitive system files. If the information was not sanitized where code is used to mask the information then attackers can use `/etc/passwd` to gain access.  
I reviewed the log management tab and found that the device action was permitted and not quarantined and the **HTTP response size was 0** which tells us that the attack was not successful.

**Investigation Steps:**  
Step-by-step, briefly outline what you did. Even if you followed a walkthrough, it still counts.  
1. Reviewed email body for red flags.
2. Checked the source IP address (`106.55.45.162`) using Virustotal:  
   * Flagged as Malicious
   * Originated from China  
4. Checked the destination IP address (`172.16.17.13`) using VirusTotal — came back clean   
5. Analyzed the requested URL (`https://172.16.17.13/?file=../../../../etc/passwd`) — came back clean

**Tools Used:**  

- VirusTotal – to analyze IP addresses and URLs.
- WHOIS –  to gather IP and domain information.
- LetsDefend Email Gateway – for log analysis and investigation.

**Conclusion:**  
Based on the investigation:
- This was a web-based LFI attack aimed at reading the (`/etc/passwd`) file.
- The attack attempt was unsuccessful, as no data was returned and the **HTTP response size was 0**.
- The source IP was confirmed as malicious.

**What I Learned:**  
This alert was different from my previous phishing case and helped me understand web application attacks.
I learned how to use SIEM tools to trace suspicious web requests and how to triage alerts involving URL manipulation.
