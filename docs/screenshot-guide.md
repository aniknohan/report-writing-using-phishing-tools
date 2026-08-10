# Screenshot Guide

Place screenshots in this folder using numbered names.

Recommended naming convention:

```text
01-original-email.png
02-email-header.png
03-virustotal-url.png
04-phishtank.png
05-urlhaus.png
06-urlscan-render.png
07-urlscan-redirects.png
08-whois.png
09-talos-file-reputation.png
10-hybrid-analysis.png
11-cyberchef-decoding.png
12-siem-search.png
13-edr-search.png
```

## What Every Screenshot Should Show

When possible, include:

- Tool name
- Indicator being analyzed
- Verdict or relevant result
- Date/time
- Relevant detection or behavior

Crop out unrelated information.

Redact:

- API keys
- Authentication tokens
- Personal information
- Internal company names
- Private IPs when disclosure is not appropriate
- Usernames when not needed
- Confidential email content

Use captions in the report.

Example:

```markdown
![Figure 3 - VirusTotal detections for sanitized phishing domain](../screenshots/03-virustotal-url.png)

**Figure 3.** VirusTotal showed multiple vendors classifying the domain as malicious or phishing at the time of analysis.
```
