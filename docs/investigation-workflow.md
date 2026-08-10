# Phishing Investigation Workflow

## Phase 1 — Preserve Evidence

Record the original email and basic artifacts before beginning analysis.

Recommended fields:

```text
Sending Address:
Subject Line:
Recipients:
Sending Server IP:
Reverse DNS:
Reply-To:
Date and Time:
Attachment:
SHA256:
Full URL (sanitized):
Root Domain:
```

Avoid changing the original email or opening suspicious content directly.

---

## Phase 2 — Analyze the Email

Review:

- Sender display name
- Actual sending address
- Reply-To
- Subject
- Urgency
- Threats
- Requests for credentials
- Requests for payment
- Brand impersonation
- Grammar or formatting anomalies
- Link text versus actual destination

State observable facts before making conclusions.

---

## Phase 3 — Analyze URLs

Start with passive sources.

```text
VirusTotal
→ PhishTank
→ URLhaus
→ urlscan.io
→ URL2PNG / Wannabrowser
→ WHOIS
```

Collect screenshots and record timestamps.

---

## Phase 4 — Analyze Attachments

```text
Calculate SHA256
→ VirusTotal
→ Talos File Reputation
→ Hybrid Analysis
→ CyberChef if needed
```

Do not run a suspicious attachment locally.

---

## Phase 5 — Check Internal Telemetry

In an authorized enterprise environment, check available controls such as:

- Email gateway
- SIEM
- EDR
- DNS logs
- Web proxy
- Firewall logs
- Identity provider logs

Questions to answer:

- Did anyone receive the message?
- Did anyone reply?
- Did anyone click?
- Did any endpoint resolve or connect to the domain?
- Were credentials submitted?
- Was a payload downloaded?
- Did a suspicious process execute?

---

## Phase 6 — Reach a Verdict

Possible classifications:

```text
Benign
Spam
Suspicious
Phishing
Credential Phishing
Malware Delivery
Business Email Compromise
Unknown / Insufficient Evidence
```

Use multiple independent observations where possible.

---

## Phase 7 — Recommend Actions

Recommendations should be tied to evidence.

Examples:

- Block sender
- Block URL
- Block domain
- Remove messages
- Search for additional recipients
- Reset credentials
- Revoke sessions
- Isolate endpoint
- Escalate malware
- Add detections
- Notify affected users

---

## Phase 8 — Write the Report

A strong investigation report should answer:

1. What happened?
2. What evidence was collected?
3. What did each tool show?
4. What is the analyst's assessment?
5. Was there user interaction?
6. What actions should be taken?
