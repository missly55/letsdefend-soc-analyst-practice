## SOC Alert Investigation:  SOC114 - Malicious Attachment Detected - Phishing Alert

**Date:** 14 September 2025  
**Platform:** LetsDefend  
**Type of Alert:** Phishing  
**Difficulty:** Beginner/Intermediate

**Initial Observation:**  
On letsdefend the SIEM tool used to view alerts indicated that there was a possible phishing incident involving a malicious attachment was detected. The severity listed on this alert is High. The email subject states Invoice. The email was NOT flagged by the system; it was delivered to the user’s inbox.  Which the device action indicates it was allowed.

The message was short and harmless:
> "Dear customer, Your invoice for the shopping you have done is attached. Regards." 

There was an an attachment with a file hash value of: 
`c9ad9506bcccfaa987ff9fc11b91698d`
So VirusTotal indicates that the file hash was flagged as malicious. 34/61 security vendors, threat labeled as trojan and  Cve-2017-11882. 
”SMTP: `49.234.43.39` listed as country CHINA

**Investigation Steps:**

To understand the alert, I followed these steps:

1. Searched for the email using the sender's `accounting@cmail.carleton.ca` address inside the Let’s Defend platform.
2. Checked the attachments file hash value using VirusTotal — came back clean
3. Check the sender’s email `accounting@cmail.carleton.ca` using WHOIS — came back clean registrar to Carleton University.

**Tools Used:**
- VirusTotal
- WHOIS
- LetsDefend Email Gateway

**Conclusion:**
It was confirmed that the email  was a phishing attempt based on these indicators:
The attachment had a file hash “c9ad9506bcccfaa987ff9fc11b91698d” that was flagged as malicious and linked to a known vulnerability: CVE-2017-11882.


The SMTP IP address was located in China.


**What I Learned:**
This was a great hands-on learning experience. Where I practiced:

- Email header analysis.
- Using VirusTotal to evaluate suspicious files.
- Performing WHOIS lookups to check sender legitimacy.
- Using a SIEM platform (LetsDefend) to triage a phishing alert.

This write-up is part of my growing cybersecurity portfolio as I work toward landing my first role as a Security Analyst. I’m currently working at Amazon in a physical role, but I'm eager to break into cybersecurity and apply what I’ve been learning through platforms like LetsDefend and guidance from the community.
