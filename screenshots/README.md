# Screenshots

Evidence screenshots for the investigation, numbered in the order they appear in the report.

## Sample Case Evidence

The [sample report](../sample-report/sample-phishing-report.md) references these files as Figures 1–7. Save each screenshot here under exactly this name and the report's figure links will work.

| Figure | File name | What it should show |
|---:|---|---|
| 1 | `01-original-email.png` | The reported email with Outlook branding and account-lock language |
| 2 | `02-reverse-dns.png` | Reverse DNS of `209.85.222.173` resolving to `mail-qk1-f173.google.com` |
| 3 | `03-phishing-page.png` | The rendered fake Outlook login page requesting email and password |
| 4 | `04-virustotal.png` | VirusTotal vendor classifications for `emailsecalerts[.]net` |
| 5 | `05-email-gateway.png` | Email gateway search showing no outgoing messages to the sender |
| 6 | `06-siem.png` | SIEM search showing no connections to the domain |
| 7 | `07-edr.png` | EDR review showing no connections to the domain |

## Other Investigations

For a new investigation, follow the fuller naming convention in the [Screenshot Guide](../docs/screenshot-guide.md).

## Before Uploading

Do not upload screenshots containing credentials, tokens, private customer data, confidential company information, or unsanitized malicious links. See the [Screenshot Guide](../docs/screenshot-guide.md) for what to redact.
