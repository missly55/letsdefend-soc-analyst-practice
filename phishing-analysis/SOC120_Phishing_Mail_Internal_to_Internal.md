## SOC Alert Investigation:  SOC120 - Phishing Mail Detected - Internal to Internal

**Date:** 25 November 2025  
**Platform:** LetsDefend  
**Type of Alert:** Exchange   
**Difficulty:** Beginner/Intermediate

**Initial Observation:**  

Within the letsdefend platform on the simulated SIEM tool used to view the alerts  it indicated that there was a possible phishing incident involving an internal exchange was detected. The severity listed on this alert is medium. The email subject Meeting. The email was NOT flagged by the system; it was delivered to the user’s inbox.  Since the device action indicates it was allowed.


**Investigation Steps:**

To identify it  the alert was a false positive or a true positive, I followed these steps:

1. I gathered information from the alert  SMTP Address `172.16.20.3`, Source address `john@letsdefend.io`, destination address `susie@letsdefend.io`
2. For each artifact stated within the email search tools (VirusTotal) to identify indicators of compromise and gather more information about the alert in question. Used VirusTotal to inspect the SMTP Address `172.16.20.3` since there was  no other indicators in the email. 
3. In the Email security tab on Letsdefend search using the email address `john@letsdefend.io` identifying the right date stated in the alert `Feb, 07, 2021, 04:24 AM`.
 The message was short and harmless:
> "Hi Susie, Can we arrange a meeting today if you are available?"

- [Email](Email.png)


**Tools Used:**
- VirusTotal
- LetsDefend Email Gateway

**Conclusion:**

The SMTP Address `172.16.20.3`came back clean when entered in VirusTotal, no sign of malicious content. And device action was allowed since both email address are internal to the company. The message in the email was harmless no attachments or links to investigate. 


**What I Learned:**
