# Tool Reference

## VirusTotal

Use VirusTotal to check whether a suspicious URL, file hash, domain, or IP has already been identified by security vendors.

Useful evidence:

- Detection counts
- Vendor classifications
- Relationships
- Historical reputation
- Associated URLs or domains

**Caution:** A clean result does not prove an artifact is safe.

---

## urlscan.io

Use urlscan.io to safely render a suspicious webpage and review:

- Screenshot
- Redirect chain
- HTTP requests
- Contacted domains
- IP addresses
- Technologies
- Page title
- DOM or page behavior

Useful for demonstrating what a victim would see and identifying related infrastructure.

---

## URLhaus

Use URLhaus when a URL may be involved in malware distribution.

Useful for:

- Malware-delivery URLs
- Payload hosting
- Loader pages
- Known malicious infrastructure

Absence from URLhaus does not prove a URL is benign.

---

## PhishTank

Use PhishTank for phishing-specific URL reputation.

It is especially useful when investigating:

- Fake login pages
- Credential harvesting
- Brand impersonation

---

## Cisco Talos File Reputation

Use Talos File Reputation when you have a SHA256 hash.

Document:

- Reputation
- Threat classification
- Available score or verdict

Do not rely on a score alone.

---

## Hybrid Analysis

Use Hybrid Analysis to observe suspicious file behavior in a sandbox.

Possible evidence:

- Spawned processes
- Dropped files
- DNS requests
- Network connections
- Registry changes
- Behavioral indicators

Behavioral evidence can be stronger than reputation alone.

---

## URL2PNG

Use URL2PNG to remotely capture a webpage screenshot.

Useful for documenting:

- Fake login pages
- Brand impersonation
- Download prompts
- Credential forms

A screenshot demonstrates appearance, not complete behavior.

---

## Wannabrowser

Use Wannabrowser to inspect webpage content with different user agents.

Possible uses:

- Review HTML
- Compare mobile and desktop behavior
- Identify user-agent-based cloaking
- Inspect returned content without normal browsing

---

## WHOIS / ICANN Lookup

Use WHOIS or ICANN Lookup to identify:

- Registration date
- Registrar
- Name servers
- Domain status
- Public registrant information when available

Recent registration can be a supporting indicator but is not proof of maliciousness.

---

## CyberChef

Use CyberChef for transformations such as:

- Base64 decoding
- URL decoding
- Hex decoding
- Deobfuscation
- Hashing
- Parsing
- Decompression
- Header cleanup

Record both input and output so the analysis can be reproduced.
