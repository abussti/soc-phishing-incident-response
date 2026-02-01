# Indicators of Compromise (IOCs)

## Email Infrastructure

### Sending Service
- Email sending service: emkei[.]cz  
  - Used to send spoofed phishing emails
  - Commonly abused for mass phishing campaigns

### From Address
- billjobs[@]microapple[.]com  
  - Impersonates a well-known brand using typosquatting
  - Domain does not belong to a legitimate organization

### Reply-To Address
- negeja3921[@]pashter[.]com  
  - Mismatch between sender and reply-to address
  - Strong indicator of phishing

---

## Domains

- microapple[.]com  
- pashter[.]com  
- emkei[.]cz  

---

## Email Authentication Failures

### SPF
- SPF result: **Fail**
- Reason: Domain does not designate the sending IP address

This indicates the sending mail server was **not authorized** to send emails on behalf of the claimed domain.

---

## Tactics Observed

- Email spoofing
- Brand impersonation (typosquatting)
- Abuse of public email-sending service
- Mismatch between From and Reply-To headers

## Detection Notes

- Flag emails where the Reply-To domain differs from the From domain
- Alert on SPF failures combined with external sender domains
- Monitor use of public email-sending services in phishing campaigns
