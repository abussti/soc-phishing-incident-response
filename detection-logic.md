# Phishing Detection Logic

This document outlines detection logic derived from a phishing email investigation.
The goal is to identify similar phishing attempts proactively in a SOC environment.

---

## 1. Email Authentication Failures

### Detection Idea
Flag emails where sender authentication fails.

### Logic
- SPF result = Fail
- Reason: Domain does not designate the sending IP address

### Rationale
SPF failures indicate that the sending server is not authorized to send email on behalf
of the claimed domain, a common indicator of spoofed phishing emails.

---

## 2. From vs Reply-To Mismatch

### Detection Idea
Alert when the Reply-To address does not match the From address domain.

### Logic
- From domain ≠ Reply-To domain

### Example
- From: billjobs[@]microapple[.]com  
- Reply-To: negeja3921[@]pashter[.]com  

### Rationale
Legitimate emails typically use consistent sender and reply domains.
A mismatch is a strong phishing indicator.

---

## 3. Typosquatted or Lookalike Domains

### Detection Idea
Detect domains that impersonate well-known brands.

### Logic
- Domain contains brand-like keywords with minor spelling changes
- Newly registered or low-reputation domains

### Rationale
Attackers often register lookalike domains to deceive users and bypass basic filters.

---

## 4. Abuse of Public Email-Sending Services

### Detection Idea
Monitor emails sent via public or anonymous email-sending services.

### Logic
- Sending service identified as a public bulk email provider (e.g., emkei[.]cz)

### Rationale
Public email services are frequently abused for phishing campaigns and should be
monitored or restricted in enterprise environments.

---

## 5. Correlated Phishing Detection (High Confidence)

### Detection Idea
Increase alert severity when multiple phishing indicators occur together.

### Correlation Conditions
- SPF failure
- Reply-To mismatch
- External sender domain
- Suspicious or typosquatted domain

### Outcome
- Classify alert as **High Confidence Phishing**
- Trigger SOC analyst review or automated response

---

## 6. Recommended Response Actions

- Quarantine email
- Block sender and reply-to domains
- Alert SOC analysts
- Notify affected users
- Update email filtering rules

---

## 7. Future Improvements

- Automate enrichment of sender domains
- Integrate detections into SIEM rules
- Add user click telemetry for impact confirmation
