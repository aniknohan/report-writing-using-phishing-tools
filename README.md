# Report Writing Using Phishing Tools

A hands-on cybersecurity portfolio project demonstrating how phishing-analysis tools can be used to collect evidence, validate indicators, document findings, and write a professional phishing incident report.

> **Purpose:** Defensive security training and report-writing practice only.  
> Do not interact with live malicious infrastructure from a personal or production system. Use sanitized indicators, passive intelligence sources, screenshots, and approved sandbox environments.

---

## Project Objectives

This project demonstrates how to:

- Triage suspicious phishing indicators.
- Analyze URLs, domains, and attachments using reputable security tools.
- Collect evidence suitable for an incident report.
- Separate strong evidence from supporting evidence.
- Sanitize malicious URLs and domains before documenting them.
- Write clear findings without overstating what a tool proves.
- Recommend practical defensive actions.
- Present the investigation as a professional GitHub portfolio project.

---

## Tools Covered

| Tool | Primary Use |
|---|---|
| VirusTotal | Multi-engine reputation checks for URLs, domains, IPs, hashes, and files |
| urlscan.io | Website rendering, screenshots, redirects, requests, and contacted infrastructure |
| URLhaus | Threat intelligence for malware-delivery URLs |
| PhishTank | Phishing URL reputation |
| Cisco Talos File Reputation | SHA256 file reputation |
| Hybrid Analysis | Sandbox behavior analysis of suspicious files |
| URL2PNG | Remote screenshot capture of suspicious webpages |
| Wannabrowser | Inspect webpage behavior, HTML, and user-agent differences |
| WHOIS / ICANN Lookup | Domain registration and registrar information |
| CyberChef | Decode, deobfuscate, normalize, transform, and inspect artifacts |

---

## Repository Structure

```text
report-writing-using-phishing-tools/
├── README.md
├── DISCLAIMER.md
├── docs/
│   ├── investigation-workflow.md
│   ├── tool-reference.md
│   ├── evidence-guidelines.md
│   └── screenshot-guide.md
├── templates/
│   ├── phishing-investigation-template.md
│   └── findings-language-cheatsheet.md
├── sample-report/
│   └── sample-phishing-report.md
├── screenshots/
│   └── README.md
└── assets/
    └── README.md
```

---

# Investigation Workflow

## 1. Collect Email Artifacts

Record the basic email evidence first.

- Sending address
- Subject line
- Recipients
- Sending server IP
- Reverse DNS
- Reply-To
- Date and time
- Suspicious URLs
- Root domain
- Attachment filename
- SHA256 hash, if applicable

Never modify the original evidence.

---

## 2. Initial Reputation Triage

Start with passive reputation checks.

### Suspicious URL

Suggested order:

1. VirusTotal
2. PhishTank
3. URLhaus
4. urlscan.io
5. URL2PNG or Wannabrowser
6. WHOIS / ICANN Lookup

### Suspicious Attachment

Suggested order:

1. Calculate SHA256
2. VirusTotal
3. Cisco Talos File Reputation
4. Hybrid Analysis
5. CyberChef if encoded or obfuscated content is involved

---

## 3. Visual and Web Analysis

Use tools such as urlscan.io, URL2PNG, and Wannabrowser to determine:

- What the victim would see
- Whether a legitimate brand is being impersonated
- Whether the page contains a credential form
- Whether redirects occur
- Whether the page contacts third-party infrastructure
- Whether different content is shown to different user agents

Add screenshots to the `screenshots/` directory and reference them in the report.

---

## 4. Infrastructure Analysis

Use WHOIS / ICANN Lookup, VirusTotal, and urlscan.io to examine:

- Domain age
- Registrar
- Name servers
- Hosting information
- Associated IP addresses
- Redirect infrastructure
- Related domains

A recently registered domain can support suspicion, but domain age alone does not prove maliciousness.

---

## 5. Attachment or Payload Analysis

For suspicious files:

- Record filename and file type.
- Calculate the SHA256 hash.
- Check reputation.
- If authorized, analyze the file in a sandbox.
- Document spawned processes, dropped files, DNS requests, and network connections.

Do not execute suspicious attachments directly on your workstation.

---

## 6. Decode or Deobfuscate Artifacts

CyberChef can help with:

- Base64
- URL encoding
- Hex
- Obfuscated strings
- Hashing
- Compression
- Header normalization
- Extracting hidden URLs

Always record both the original value and the decoded result.

---

# Evidence Strength

## Strong Evidence

Examples include:

- Hybrid Analysis behavioral observations
- urlscan.io page render and redirect chain
- Talos malicious reputation on a SHA256 hash
- Multiple independent VirusTotal detections

## Supporting Evidence

Examples include:

- PhishTank listing
- URLhaus listing
- Recently registered domain
- Remote screenshot
- CyberChef-decoded destination

No single signal should automatically determine the final verdict.

---

# Important Reporting Rules

### Do not say:

> VirusTotal has zero detections, so the URL is safe.

### Better:

> VirusTotal did not show detections at the time of analysis. This does not prove the URL is benign, so additional evidence was reviewed.

### Do not say:

> The domain is malicious because it is new.

### Better:

> WHOIS data indicates that the domain was registered recently. This is a supporting indicator and is consistent with short-lived phishing infrastructure when considered alongside the other findings.

---

# Sanitizing Indicators

Do not publish clickable malicious indicators.

Use:

```text
hxxps://example[.]com/login
```

Instead of:

```text
https://example.com/login
```

You can also sanitize IP addresses if desired:

```text
192[.]0[.]2[.]10
```

---

# Example Screenshot References

Later, after adding your screenshots:

```markdown
![Figure 1 - Suspicious phishing email](screenshots/01-phishing-email.png)

![Figure 2 - VirusTotal domain reputation](screenshots/02-virustotal.png)

![Figure 3 - urlscan.io rendered phishing page](screenshots/03-urlscan.png)

![Figure 4 - WHOIS registration information](screenshots/04-whois.png)
```

---

# Sample Conclusion

> Based on the email content, sender infrastructure, phishing-page behavior, domain reputation, and supporting threat-intelligence results, the message is assessed as a phishing attempt designed to obtain user credentials. No single tool was used as the sole basis for the verdict. The conclusion was reached by correlating multiple independent indicators.

---

# Recommended Defensive Actions

Depending on the evidence collected:

- Block the confirmed malicious sender.
- Block the malicious root domain.
- Block confirmed malicious URLs.
- Remove the phishing message from affected mailboxes.
- Search mail logs for additional recipients.
- Search proxy, DNS, SIEM, and EDR telemetry for user interaction.
- Reset credentials if a user submitted them.
- Revoke active sessions when credential compromise is suspected.
- Escalate confirmed malicious attachments for malware response.
- Document all actions and evidence.

---

# What This Project Demonstrates to Employers

This repository demonstrates practical ability in:

- Phishing triage
- Security investigation
- Threat intelligence
- URL analysis
- Domain analysis
- File reputation analysis
- Sandbox analysis
- Evidence preservation
- Indicator sanitization
- Technical report writing
- Defensive recommendations
- SOC-style communication

---

## Disclaimer

This repository is for defensive cybersecurity education, portfolio demonstration, and authorized analysis only. Never submit confidential organizational data to public third-party services without permission.

## Author

**Anik Nohan**

Cybersecurity | SOC Analysis | Blue Team | Report Writing
