# Evidence Guidelines

## Make a Point, Then Provide Evidence

Weak:

> This is definitely phishing.

Better:

> The email directs recipients to a login page that imitates Microsoft 365. urlscan.io rendered a credential-entry form, while reputation sources independently flagged the domain. These findings support classification as credential phishing.

---

## Separate Observation From Interpretation

### Observation

> WHOIS showed that the domain was registered recently.

### Interpretation

> The recent registration is consistent with infrastructure commonly used in short-lived phishing campaigns, but it is not independently conclusive.

---

## Record Timestamps

Threat-intelligence results can change.

For important evidence, record:

```text
Tool:
Indicator:
Result:
Date/Time Checked:
Screenshot:
Analyst Note:
```

---

## Avoid Overclaiming

### VirusTotal

Bad:

> VirusTotal proves this URL is safe.

Good:

> No vendors detected the URL at the time of analysis. Additional investigation is required before considering it benign.

### Screenshot

Bad:

> The screenshot proves the website steals passwords.

Good:

> The screenshot shows a credential-entry form imitating the legitimate brand. Additional behavioral or network evidence is needed to determine how submitted data is handled.

### WHOIS

Bad:

> The domain is malicious because it is only two days old.

Good:

> The recent registration is a supporting risk indicator when correlated with the impersonation and reputation findings.

---

## Preserve Reproducibility

A reader should be able to understand:

- What artifact was checked
- What tool was used
- What result was observed
- When it was observed
- How it influenced the conclusion
