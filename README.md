<p align="center">
  <img src="https://img.shields.io/badge/-Microsoft_Sentinel-0078D4?style=for-the-badge&logo=Microsoft&logoColor=white" />
  <img src="https://img.shields.io/badge/-Microsoft_Defender_for_Endpoint-00A4EF?style=for-the-badge&logo=Microsoft&logoColor=white" />
  <img src="https://img.shields.io/badge/-Threat_Intelligence-FF4500?style=for-the-badge&logo=VirusTotal&logoColor=white" />
  <img src="https://img.shields.io/badge/-KQL-000000?style=for-the-badge&logo=codeforces&logoColor=white" />
</p>

<h1 align="center">🔎 SOC Cyber Range Investigations</h1>

<p align="center">
  Real-world threat hunting, detections, and incident response simulations performed in a student cyber range environment.
</p>

---

<img src="https://img.shields.io/badge/REPOSITORY_STRUCTURE-24292e?style=for-the-badge&logo=github&logoColor=white" />

- `Reports/` – Full Incident Reports
- `Summaries/` – Case Summaries  
- `Iocs/` – IOC Lists Extracted
- `Detections/` – KQL Rules/Alerts (Coming Soon)

---

<img src="https://img.shields.io/badge/INCIDENT_LIBRARY-0078D4?style=for-the-badge&logo=azuredevops&logoColor=white" />

### Incident-2400: Azure Abuse – Crypto-Mining & Brute-Force  
- [📄 Full Report](./Reports/incident-2400-azure-abuse-crypto-mining-brute-force.pdf)  
- [📝 Summary](#incident-2400-summary)  
- [📌 IOCs] *(coming soon)*

---

### Incident-2401: Azure Abuse – Crypto-Mining & Brute-Force  
- [📄 Full Report](./Reports/incident-2400-azure-abuse-crypto-mining-brute-force.pdf)  
- [📝 Summary](#incident-2401-summary)  
- [📌 IOCs] *(coming soon)*

---

### Incident-2402: Azure Abuse – Crypto-Mining & Brute-Force  
- [📄 Full Report](./Reports/incident-2400-azure-abuse-crypto-mining-brute-force.pdf)  
- [📝 Summary](#incident-2402-summary)


## Incident 2400 Summary

# Incident 2400 – Azure Abuse, Crypto-Mining & Brute-Force  
**Incident ID:** 2400  
**Date Investigated:** March 23, 2025  
**Environment:** Pacific | Cyber Range

---

<img src="https://img.shields.io/badge/-INCIDENT_SUMMARY-0078D4?style=for-the-badge&logo=bookstack&logoColor=white" />

A suspicious Azure abuse report led to the discovery of crypto-mining and external brute-force attacks originating from internal lab VMs. The attacker exploited weak SSH credentials, deployed miner payloads, and used compromised systems to launch outbound brute-force attacks to external services.

---

<img src="https://img.shields.io/badge/-WHO-000000?style=for-the-badge&logo=github&logoColor=white" />

- Initial compromised host: `linux-vulnmgmt-kobe`  
- Laterally moved to: `levi-linux-vulnerability`, `sakel-lunix-2`  
- External targets included YouTube, Twitter, etc.

---

<img src="https://img.shields.io/badge/-WHAT-000000?style=for-the-badge&logo=github&logoColor=white" />

- Miner binaries: `.diicot`, `.balu`, `.bisis`  
- Downloaded via `wget` and `curl`  
- 240K+ outbound brute-force attempts via SSH

---

<img src="https://img.shields.io/badge/-WHEN-000000?style=for-the-badge&logo=github&logoColor=white" />

- Initial compromise: Feb 18, 2025  
- Mining activity: Feb 20–22  
- Outbound abuse: Mar 14–17

---

<img src="https://img.shields.io/badge/-WHERE-000000?style=for-the-badge&logo=github&logoColor=white" />

- Internal lab: Azure-hosted Linux VMs  
- Public IP involved: `20.81.228.191`

---

<img src="https://img.shields.io/badge/-WHY-000000?style=for-the-badge&logo=github&logoColor=white" />

- Crypto-mining for financial gain  
- Platform abuse through brute-force  
- No outbound egress restrictions + weak SSH creds

