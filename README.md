============================================================

REAL-WORLD PHISHING EMAIL INVESTIGATION - SOC LAB

============================================================



PROJECT TYPE:

SOC / Phishing Email Investigation



PROJECT PURPOSE:

This project demonstrates a SOC-style investigation of a

suspicious phishing email impersonating Microsoft Account

Security.



The investigation was performed using a publicly available

.raw email sample and focused on email headers, email

authentication, IOC extraction, URL investigation,

domain/DNS investigation, IP investigation, threat

intelligence, and incident reporting.





============================================================

1\. CASE INFORMATION

============================================================



CASE ID:

PHISH-GH-001



CASE TITLE:

Microsoft Account Phishing Email Investigation



CASE TYPE:

Phishing Email Investigation



ALERT TYPE:

Suspicious Email / Possible Phishing



EVIDENCE SOURCE:

Public GitHub Phishing Analysis Lab



SAMPLE:

sample2.eml



IMPERSONATED ORGANIZATION:

Microsoft



FINAL VERDICT:

PHISHING



CONFIDENCE:

HIGH





============================================================

2\. INVESTIGATION OBJECTIVE

============================================================



The objective of this investigation was to determine whether

the suspicious email was legitimate or a phishing attempt.



The investigation focused on:



\- Identifying the sender

\- Analyzing email headers

\- Identifying the sending infrastructure

\- Checking SPF, DKIM and DMARC

\- Extracting Indicators of Compromise (IOCs)

\- Investigating the suspicious URL

\- Investigating the sender domain

\- Performing DNS investigation

\- Investigating the sending IP

\- Performing threat-intelligence checks

\- Documenting the evidence

\- Producing a final incident assessment





============================================================

3\. EMAIL DETAILS

============================================================



FROM:

"Microsoft Account Team"

<noreply@microsoftonline-verify.com>



TO:

jacobcookofficial@gmail.com



SUBJECT:

\[Action Required] Unusual sign-in activity on your account



DATE:

Thu, 06 Feb 2026 17:14:18 +0000



RETURN-PATH:

noreply@microsoftonline-verify.com



SENDING HOST:

mail.microsoftonline-verify.com



UPSTREAM HOST:

vps-291847.contabo.net



SENDING IP:

178.238.225.91





============================================================

4\. EMAIL HEADER ANALYSIS

============================================================



The email headers were examined to identify the sender,

routing information and sending infrastructure.



IMPORTANT FINDINGS:



Sender Domain:

microsoftonline-verify.com



Sending Host:

mail.microsoftonline-verify.com



Upstream Host:

vps-291847.contabo.net



Sending IP:

178.238.225.91



The Received header was used to identify the sending

infrastructure associated with the email.





============================================================

5\. EMAIL AUTHENTICATION

============================================================



SPF:

FAIL



DKIM:

FAIL



DMARC:

FAIL



The email failed SPF, DKIM and DMARC authentication checks.



These authentication failures increased the suspicion

surrounding the email and supported further phishing

investigation.





============================================================

6\. IOC EXTRACTION

============================================================



The following indicators were extracted from the email:



SENDER EMAIL:

noreply@microsoftonline-verify.com



SENDER DOMAIN:

microsoftonline-verify.com



SENDING IP:

178\[.]238\[.]225\[.]91



SENDING HOST:

mail.microsoftonline-verify.com



UPSTREAM HOST:

vps-291847.contabo.net



SUSPICIOUS URL:

hxxps://bit\[.]ly/3vF9xKz



IP MENTIONED IN EMAIL:

91\[.]234\[.]99\[.]42



MESSAGE-ID:

<8c4f2e91.a03b7d44.1f2e8a@microsoftonline-verify.com>





============================================================

7\. URL INVESTIGATION

============================================================



INVESTIGATED URL:

https://bit.ly/3vF9xKz



THREAT INTELLIGENCE SOURCE:

VirusTotal



RESULT:

1/91



DETECTION:

Phishing Database - Phishing



CURRENT URL STATUS:

404



The URL received a phishing detection from one security

vendor during the investigation.



The 404 status indicated that the resource was unavailable

at the time of investigation.



The 404 status was not treated as standalone proof of

maliciousness.





============================================================

8\. DOMAIN AND DNS INVESTIGATION

============================================================



INVESTIGATED DOMAIN:

microsoftonline-verify.com



DNS INVESTIGATION TOOL:

MXToolbox



DNS RESULTS:



A Record:

Not Found



AAAA Record:

Not Found



MX Record:

Not Found



NS Record:

Not Found



CNAME Record:

Not Found



SOA Record:

Not Found



SPF Record:

Not Found



DMARC Record:

Not Found



GENERAL DNS:

No Results Found



These DNS findings were treated as supporting evidence

rather than standalone proof of malicious activity.





============================================================

9\. SENDING IP INVESTIGATION

============================================================



INVESTIGATED IP:

178.238.225.91



ASN:

AS51167



ORGANIZATION:

Contabo GmbH



NETWORK:

178.238.224.0/20



CURRENT PTR:

vmi3247644.contaboserver.net



VIRUSTOTAL RESULT:

0/91



The IP was not currently flagged as malicious by the

VirusTotal vendors checked.



The IP was identified as infrastructure associated with

Contabo GmbH.



The hosting provider attribution alone was not treated as

proof of malicious activity.





============================================================

10\. IP MENTIONED IN THE EMAIL

============================================================



IP:

91.234.99.42



PURPOSE IN EMAIL:

The IP address appeared inside the email body as the alleged

IP address associated with unusual sign-in activity.



VIRUSTOTAL RESULT:

0/91



The IP was treated as an investigation artifact because

its presence in the email does not independently prove

that it was the attacker's infrastructure or that an

actual account login occurred.





============================================================

11\. SOCIAL ENGINEERING INDICATORS

============================================================



The email contained multiple characteristics commonly

associated with phishing:



\- Microsoft impersonation

\- Urgent subject line

\- Account-security theme

\- Unusual sign-in warning

\- Suspicious sender domain

\- Shortened URL

\- Failed SPF authentication

\- Failed DKIM authentication

\- Failed DMARC authentication





============================================================

12\. THREAT INTELLIGENCE SUMMARY

============================================================



URL:



https://bit.ly/3vF9xKz



VirusTotal:

1/91



Detection:

Phishing Database - Phishing





SENDING IP:



178.238.225.91



VirusTotal:

0/91



ASN:

AS51167



Organization:

Contabo GmbH





EMAIL-MENTIONED IP:



91.234.99.42



VirusTotal:

0/91





============================================================

13\. FINAL ASSESSMENT

============================================================



FINAL VERDICT:



PHISHING



CONFIDENCE:



HIGH



REASON:



The email combined multiple phishing indicators including

Microsoft impersonation, an urgent account-security theme,

failed SPF/DKIM/DMARC authentication, a suspicious sender

domain, and a shortened URL that received a phishing

detection during threat-intelligence analysis.



The final verdict was based on the combined evidence rather

than relying on a single indicator.





============================================================

14\. RECOMMENDED SOC RESPONSE

============================================================



1\. Do not click the suspicious URL.



2\. Quarantine or remove the phishing email.



3\. Search the environment for other emails containing the

&#x20;  identified IOCs.



4\. Check whether the recipient interacted with the URL.



5\. If the user interacted with the phishing page, investigate

&#x20;  possible credential exposure.



6\. Review relevant identity-provider and endpoint logs.



7\. Reset credentials if compromise is confirmed or suspected.



8\. Verify MFA protection.



9\. Block or monitor identified IOCs where appropriate.



10\. Preserve the original email and investigation evidence.



11\. Document the incident and escalate according to the

&#x20;   organization's incident-response process.





============================================================

15\. TOOLS USED

============================================================



\- Windows Notepad

\- GitHub

\- VirusTotal

\- MXToolbox

\- RIPE WHOIS

\- DNS Lookup

\- PTR Lookup

\- ASN Lookup

\- Email Header Analysis





============================================================

16\. SKILLS DEMONSTRATED

============================================================



\- Phishing Email Analysis

\- Email Header Analysis

\- SPF Analysis

\- DKIM Analysis

\- DMARC Analysis

\- IOC Extraction

\- URL Investigation

\- Domain Investigation

\- DNS Investigation

\- IP Investigation

\- Threat Intelligence

\- Social Engineering Analysis

\- Incident Documentation

\- SOC Incident Reporting





============================================================

17\. PROJECT STRUCTURE

============================================================



Real-World-Phishing-SOC-Lab

|

+-- 01-Case-Intake

|   +-- Case-Intake.txt

|

+-- 02-Raw-Email

|   +-- sample2.eml

|

+-- 03-Header-Analysis

|   +-- Header-Analysis.txt

|

+-- 04-Email-Authentication

|   +-- SPF-DKIM-DMARC-Analysis.txt

|

+-- 05-IOC-Extraction

|   +-- IOC-List.txt

|

+-- 06-URL-Investigation

|   +-- URL-Investigation.txt

|

+-- 07-Threat-Intelligence

|   +-- IP-178.238.225.91.txt

|   +-- IP-91.234.99.42.txt

|

+-- 08-Final-Report

|   +-- Final-Incident-Report.txt

|

+-- 09-Screenshots

&#x20;   +-- 01-Email.png

&#x20;   +-- 02-URL-VirusTotal.png

&#x20;   +-- 03-IP-VirusTotal.png





============================================================

18\. INVESTIGATION WORKFLOW

============================================================



EMAIL

&#x20; |

&#x20; v

HEADER ANALYSIS

&#x20; |

&#x20; v

SPF / DKIM / DMARC

&#x20; |

&#x20; v

IOC EXTRACTION

&#x20; |

&#x20; v

URL INVESTIGATION

&#x20; |

&#x20; v

DOMAIN / DNS INVESTIGATION

&#x20; |

&#x20; v

IP INVESTIGATION

&#x20; |

&#x20; v

THREAT INTELLIGENCE

&#x20; |

&#x20; v

FINAL ASSESSMENT

&#x20; |

&#x20; v

INCIDENT REPORT





============================================================

19\. CONCLUSION

============================================================



The investigated email was classified as PHISHING based on

the combined evidence collected during the investigation.



The investigation demonstrated a SOC-style workflow starting

from the original email evidence and progressing through

header analysis, email authentication, IOC extraction,

URL investigation, domain/DNS investigation, IP analysis,

threat intelligence and final incident assessment.



The investigation also demonstrated an important SOC

principle: individual indicators should not automatically be

treated as proof of malicious activity. The final verdict

should be based on the overall evidence and context.





============================================================

20\. DISCLAIMER

============================================================



This project was performed for cybersecurity learning and

portfolio purposes using a publicly available phishing email

sample.



No real user account was accessed or compromised as part of

this investigation.





============================================================

END OF PROJECT

============================================================

