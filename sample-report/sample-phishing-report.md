# Sample Phishing Investigation Report

> This is a portfolio example based on sanitized training data. Replace the placeholders and add your own screenshots before publishing.

## 1. Executive Summary

A suspicious email was reported after recipients received a message claiming that their email accounts would be locked unless they immediately verified their identities. The email used Outlook-related branding and directed users to a non-Microsoft domain. Reputation and webpage analysis supported classification of the message as credential phishing. Available internal telemetry showed no evidence that recipients visited the malicious domain at the time of investigation.

**Final Classification:** Credential Phishing  
**Severity:** Medium  
**User Interaction Identified:** No evidence identified in reviewed telemetry

---

## 2. Email Artifacts

**Sending Address:** `emailsecalert1@gmail.com`  
**Subject Line:** `Your Email Will be Locked! Act NOW!`  
**Sending Server IP:** `209.85.222.173`  
**Reverse DNS:** `mail-qk1-f173.google.com`  
**Reply-To:** `emailsecalert1@gmail.com`  
**Date and Time:** `3:21 PM, Monday, June 1, 2020`

### Recipients

```text
john.smith@dicksonunited.co.uk
alice.cooper@dicksonunited.co.uk
jacon.long@dicksonunited.co.uk
fred.johnson@dicksonunited.co.uk
pickle.rick@dicksonunited.co.uk
```

---

## 3. Web Artifacts

**Full URL (sanitized):**

```text
hxxps://outlook-security.emailsecalerts[.]net/index/2020/OWA.php
```

**Root Domain:**

```text
emailsecalerts[.]net
```

---

## 4. Email Analysis

The reported message presented itself as an Outlook security alert and used branding intended to make the message appear legitimate. It warned recipients that their mailboxes would be closed unless they confirmed their identities. The urgency and requested account-verification action are consistent with credential-phishing social engineering.

### Evidence Placeholder

```markdown
![Figure 1 - Original phishing email](../screenshots/01-original-email.png)
```

**Figure 1.** Reported email using Outlook-related branding and urgent account-lock language.

---

## 5. Sender Infrastructure

A reverse DNS lookup of the sending server IP resolved to a Gmail mail server. This does not match the Microsoft/Outlook identity presented in the email and supports the conclusion that the message did not originate from the organization it attempted to impersonate.

### Evidence Placeholder

```markdown
![Figure 2 - Reverse DNS result](../screenshots/02-reverse-dns.png)
```

---

## 6. Webpage Analysis

Remote webpage analysis showed that the linked page presented an Outlook-style credential form asking the user to enter an email address and password. This behavior is consistent with a credential-harvesting page.

### Evidence Placeholder

```markdown
![Figure 3 - Rendered credential phishing page](../screenshots/03-phishing-page.png)
```

---

## 7. VirusTotal Reputation

A VirusTotal search of the domain showed malicious and phishing classifications from security vendors at the time of analysis. This reputation result supports the malicious assessment but is not used as the sole basis for the verdict.

### Evidence Placeholder

```markdown
![Figure 4 - VirusTotal result](../screenshots/04-virustotal.png)
```

---

## 8. Internal Telemetry Review

The email gateway showed no outgoing messages to the sending address, indicating that no reviewed recipient replied to the sender.

SIEM and EDR telemetry did not show connections from organizational systems to the malicious domain during the reviewed period. Based on the available telemetry, no recipient click was identified at the time of investigation.

### Evidence Placeholders

```markdown
![Figure 5 - Email gateway search](../screenshots/05-email-gateway.png)

![Figure 6 - SIEM domain search](../screenshots/06-siem.png)

![Figure 7 - EDR review](../screenshots/07-edr.png)
```

---

## 9. Findings

### Finding 1 — Brand Impersonation

The message imitated an Outlook security notification while originating through unrelated Gmail infrastructure.

### Finding 2 — Credential-Harvesting Page

Remote webpage analysis showed a fake Outlook login page requesting email credentials.

### Finding 3 — Malicious Reputation

Threat-intelligence results supported classification of the domain as malicious or phishing-related.

### Finding 4 — No Confirmed User Interaction

The reviewed email, SIEM, and EDR telemetry did not identify replies or network connections to the malicious domain.

---

## 10. Final Assessment

Based on the social-engineering content, sender mismatch, credential-harvesting webpage, and supporting reputation evidence, the email is assessed as a credential-phishing attempt. Multiple independent observations support this conclusion. At the time of investigation, the reviewed internal telemetry did not identify successful user interaction with the phishing infrastructure.

---

## 11. Suggested Defensive Measures

### Email Control

Block the confirmed malicious sender address to prevent additional messages from the same mailbox.

```text
emailsecalert1@gmail.com
```

### Web Control

Block the malicious root domain because the analysis identified it as phishing infrastructure and no legitimate business requirement was established.

```text
emailsecalerts[.]net
```

### Additional Actions

- Search the email environment for additional copies of the message.
- Remove matching phishing emails from user mailboxes.
- Continue monitoring for connections to the domain.
- Add the domain and URL to relevant threat-intelligence or detection workflows.
- If later evidence identifies credential submission, reset the affected password and revoke active sessions.

---

## 12. Indicators of Compromise

```text
Sender: emailsecalert1@gmail.com
Sending Server IP: 209.85.222.173
Root Domain: emailsecalerts[.]net
URL: hxxps://outlook-security.emailsecalerts[.]net/index/2020/OWA.php
```

---

## 13. Limitations

This sample does not include original message headers, complete WHOIS records, live threat-intelligence timestamps, or screenshots. Those should be added when completing the portfolio investigation.

---

## 14. Conclusion

The available evidence supports classification of the reported message as credential phishing. Defensive blocking and message removal are appropriate, while continued monitoring should be used to identify any delayed or previously missed user interaction.
