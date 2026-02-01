# SOC Phishing Incident Response

This project documents a phishing email investigation performed using SOC analyst methodologies.
The investigation follows a real-world incident response workflow, from triage to recommendations.

## Objectives
- Analyze a phishing email sample
- Extract and enrich indicators of compromise (IOCs)
- Assess potential impact to users and systems
- Document response actions and prevention strategies
- Design detection logic for future prevention

## Skills Demonstrated
- Phishing email analysis
- IOC extraction and enrichment
- Static attachment analysis
- Incident response documentation
- MITRE ATT&CK mapping
- SOC detection thinking

## Tools Used
- CyberChef – decoding, data transformation, and artifact analysis
- Notepad++ – raw email and artifact inspection
- Gary Kessler’s File Signature Table – file type verification
- HxD Hex Editor – low-level file and header inspection
- ExifTool – metadata extraction and analysis
- VirusTotal – indicator enrichment and reputation checks
- Domain reputation and WHOIS analysis

## Project Structure
- `incident-report.md` – Full phishing incident report  
- `iocs.md` – Indicators of compromise  
- `detection-logic.md` – SIEM detection ideas  
- `mitre-mapping.md` – ATT&CK technique mapping  

## Disclaimer
All samples and indicators are used strictly for educational and defensive security purposes.
