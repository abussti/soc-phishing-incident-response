# Phishing Incident Report

## Executive Summary
A phishing email was reported by a user and analyzed to determine its legitimacy, intent, and potential impact.
The investigation confirmed the email was malicious and designed to lure users into interacting with a fraudulent domain.

## Timeline
- Email received by user
- Email reported to SOC
- Analysis and IOC extraction performed
- Threat confirmed and contained

## Email Analysis
- Suspicious sender domain
- Social engineering language

Analysis was performed using CyberChef for decoding and artifact extraction,
Notepad++ for raw email inspection, and ExifTool and HxD for metadata and
low-level file analysis. File type validation was cross-checked using
Gary Kessler’s file signature reference.

## Indicators of Compromise
See `iocs.md`

## Enrichment
- VirusTotal analysis
- Domain age and reputation checks

## Impact Assessment
No evidence of user interaction or credential compromise was identified during analysis.

## Response Actions
- Email marked as phishing
- Domain recommended for blocking
- User awareness advised

## Recommendations
- Improve email filtering rules
- User phishing awareness training
- SIEM detection for similar indicators

## Tool Selection Rationale
The tools used in this investigation were selected to ensure safe, static analysis
without executing potentially malicious content. This approach aligns with
SOC best practices for phishing and malware triage.
