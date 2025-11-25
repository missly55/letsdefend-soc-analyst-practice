## SOC Alert Investigation:  SOC120 - Phishing Mail Detected - Internal to Internal

**Date:** 25 November 2025  
**Platform:** LetsDefend  
**Type of Alert:** Exchange   
**Difficulty:** Beginner/Intermediate

**Initial Observation:**  

Within the letsdefend platform on the simulated SIEM tool used to view the alerts  it indicated that there was a possible phishing incident involving an internal exchange was detected. The severity listed on this alert is medium. The email subject Meeting. The email was NOT flagged by the system; it was delivered to the user’s inbox.  Since the device action indicates it was allowed.


**Investigation Steps:**

To identify it  the alert was a false positive or a true positive, I followed these steps:

I gathered information from the alert  SMTP Address `172.16.20.3`, Source address `john@letsdefend.io`, destination address `susie@letsdefend.io`
For each artifact stated within the email search tools (VirusTotal, UrLScan, Letsdefend Email Gateway) to identify indicators of compromise and gather more information about the alert in question.
In the Email security tab on Letsdefend search using the email address `john@letsdefend.io` identifying the right date stated in the alert `Feb, 07, 2021, 04:24 AM`. 

[Email:](Source.png)



**Tools Used:**
- VirusTotal
- WHOIS
- LetsDefend Email Gateway

**Conclusion:**




**What I Learned:**
