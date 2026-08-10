# Phishing Investigation Report

## 1. Executive Summary

**Case ID:**  
**Analyst:**  
**Date:**  
**Final Classification:**  
**Severity:**  

### Summary

[Write 3–5 sentences explaining what was reported, the major findings, whether user interaction occurred, and the final assessment.]

---

## 2. Email Artifacts

**Sending Address:**  
**Display Name:**  
**Subject Line:**  
**Recipients:**  
**Sending Server IP:**  
**Reverse DNS:**  
**Reply-To:**  
**Date and Time:**  
**Message-ID:**  
**Attachment(s):**  
**SHA256:**  

---

## 3. Web Artifacts

**Full URL (sanitized):**  
**Root Domain:**  
**Resolved IP:**  
**Redirect Destination:**  
**Domain Registration Date:**  
**Registrar:**  

---

## 4. Initial Email Analysis

[Describe the email's appearance, language, urgency, impersonation, requested action, and suspicious characteristics.]

### Screenshot

```markdown
![Figure 1 - Original phishing email](../screenshots/01-original-email.png)
```

---

## 5. URL Reputation Analysis

### VirusTotal

**Indicator:**  
**Result:**  
**Analysis Date:**  

[Explain what VirusTotal showed without treating it as the sole verdict.]

### PhishTank

**Indicator:**  
**Result:**  
**Analysis Date:**  

### URLhaus

**Indicator:**  
**Result:**  
**Analysis Date:**  

---

## 6. Webpage Analysis

### urlscan.io

**Observed Page:**  
**Redirects:**  
**Contacted Domains:**  
**Notable Requests:**  
**Brand Impersonated:**  

[Explain what the page looked like and what infrastructure was observed.]

### URL2PNG / Wannabrowser

[Document screenshot or page-source findings.]

---

## 7. Domain and Infrastructure Analysis

### WHOIS / ICANN Lookup

**Registration Date:**  
**Registrar:**  
**Name Servers:**  
**Domain Status:**  

[Explain why the findings are relevant.]

---

## 8. Attachment Analysis

If there is no attachment, write:

> No attachment was present in the reported message.

If an attachment exists:

**Filename:**  
**File Type:**  
**SHA256:**  

### VirusTotal / Talos

[Record reputation findings.]

### Hybrid Analysis

[Record behavioral findings.]

---

## 9. Decoding / Deobfuscation

### CyberChef

**Original Value:**  
**Recipe Used:**  
**Decoded Value:**  

[Explain why decoding was necessary and what was revealed.]

---

## 10. Internal Telemetry Review

### Email Gateway

[Did other users receive or reply to the message?]

### SIEM

[Were there DNS, proxy, authentication, or network events?]

### EDR

[Did any endpoint open, download, or execute content?]

---

## 11. Findings

### Finding 1

**Statement:**  
**Evidence:**  
**Assessment:**  

### Finding 2

**Statement:**  
**Evidence:**  
**Assessment:**  

### Finding 3

**Statement:**  
**Evidence:**  
**Assessment:**  

---

## 12. Final Assessment

[Explain the final classification and correlate multiple independent observations.]

Suggested structure:

> Based on [email evidence], [webpage evidence], [reputation evidence], and [internal telemetry], the message is assessed as [classification]. [State whether any recipient clicked, submitted credentials, or executed a file if that information is available.]

---

## 13. Suggested Defensive Measures

- [ ] Block sender
- [ ] Block URL
- [ ] Block root domain
- [ ] Remove email from affected mailboxes
- [ ] Search for additional recipients
- [ ] Check DNS/proxy/SIEM logs
- [ ] Check EDR telemetry
- [ ] Reset affected credentials
- [ ] Revoke sessions
- [ ] Isolate affected endpoint
- [ ] Escalate malware analysis
- [ ] Create detection rule
- [ ] Notify users

### Justification

[Explain why each recommended action is appropriate.]

---

## 14. Indicators of Compromise

```text
Sender:
Domain:
URL:
IP:
SHA256:
Filename:
```

All malicious indicators should be sanitized before publication.

---

## 15. Evidence Index

```text
Figure 1:
Figure 2:
Figure 3:
Figure 4:
Figure 5:
```

---

## 16. Limitations

[Document missing evidence, unavailable logs, incomplete WHOIS information, or tools that returned no results.]

---

## 17. Conclusion

[Provide a concise final conclusion.]
