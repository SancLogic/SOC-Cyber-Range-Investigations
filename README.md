<p align="center">
  <img src="https://img.shields.io/badge/-Microsoft_Sentinel-0078D4?style=for-the-badge&logo=Microsoft&logoColor=white" />
  <img src="https://img.shields.io/badge/-Microsoft_Defender_for_Endpoint-00A4EF?style=for-the-badge&logo=Microsoft&logoColor=white" />
  <img src="https://img.shields.io/badge/-Threat_Intelligence-FF4500?style=for-the-badge&logo=VirusTotal&logoColor=white" />
  <img src="https://img.shields.io/badge/-KQL-000000?style=for-the-badge&logo=codeforces&logoColor=white" />
</p>

<h1 align="center">SOC Cyber Range Investigations</h1>

<p align="center">
  Real-world threat activity investigated through hands-on detection and response inside a student cyber range environment.
</p>

---

<img src="https://img.shields.io/badge/REPOSITORY_STRUCTURE-24292e?style=for-the-badge&logo=github&logoColor=white" />

- `Reports/` – Full Incident Reports  
- `Iocs/` – IOC Lists Extracted  
- `Detections/` – KQL Rules/Alerts (Coming Soon)

---

<img src="https://img.shields.io/badge/INCIDENT_LIBRARY-0078D4?style=for-the-badge&logo=azuredevops&logoColor=white" />

### Incident-2400: Azure Abuse – Crypto-Mining & Brute-Force  
<a href="./Reports/incident-2400-azure-abuse-crypto-mining-brute-force.pdf"><img src="https://img.shields.io/badge/-Full_Report-grey?style=for-the-badge&logo=readthedocs&logoColor=white" /></a>
<a href="#incident-2400-summary"><img src="https://img.shields.io/badge/-Summary-blue?style=for-the-badge&logo=markdowngit&logoColor=white" /></a>
<a href="./Iocs/incident-2400-iocs.csv"><img src="https://img.shields.io/badge/-IOCs-orange?style=for-the-badge&logo=virustotal&logoColor=white" /></a>
<a href="./Detections/incident-2400-detections.kql"><img src="https://img.shields.io/badge/-Detections-purple?style=for-the-badge&logo=microsoft&logoColor=white" /></a>

---

### Incident-2401: Linux VM Compromise – XorDDoS Malware  
<a href="./Reports/incident-2401-linux-vm-xorddos-compromise.pdf"><img src="https://img.shields.io/badge/-Full_Report-grey?style=for-the-badge&logo=readthedocs&logoColor=white" /></a>
<a href="#incident-2401-summary"><img src="https://img.shields.io/badge/-Summary-blue?style=for-the-badge&logo=markdowngit&logoColor=white" /></a>
<a href="./Iocs/incident-2401-iocs.csv"><img src="https://img.shields.io/badge/-IOCs-orange?style=for-the-badge&logo=virustotal&logoColor=white" /></a>
<a href="./Detections/incident-2401-detections.kql"><img src="https://img.shields.io/badge/-Detections-purple?style=for-the-badge&logo=microsoft&logoColor=white" /></a>

---

### Incident-2402: Password Spray (No Compromise)  
<a href="./Reports/incident-2402-password-spray-finallabscott.pdf"><img src="https://img.shields.io/badge/-Full_Report-grey?style=for-the-badge&logo=readthedocs&logoColor=white" /></a>
<a href="#incident-2402-summary"><img src="https://img.shields.io/badge/-Summary-blue?style=for-the-badge&logo=markdowngit&logoColor=white" /></a>
<a href="./Iocs/incident-2402-iocs.csv"><img src="https://img.shields.io/badge/-IOCs-orange?style=for-the-badge&logo=virustotal&logoColor=white" /></a>
<a href="./Detections/incident-2402-detections.kql"><img src="https://img.shields.io/badge/-Detections-purple?style=for-the-badge&logo=microsoft&logoColor=white" /></a>



&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp; 
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp; 
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp; 


## Incident 2400 Summary  
# Incident 2400 – Azure Abuse, Crypto-Mining & Brute-Force  
**Incident ID:** 2400  
**Date Investigated:** March 18, 2025  
**Environment:** LOG(N) Pacific | Cyber Range

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

&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp; 
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp; 
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp; 

### Incident 2401 Summary  
# Incident 2401 – Linux VM Compromise: XorDDoS Malware  
**Incident ID:** 2401  
**Date Investigated:** March 24, 2025  
**Environment:** LOG(N) Pacific | Cyber Range

---

<img src="https://img.shields.io/badge/-WHO-000000?style=for-the-badge&logo=github&logoColor=white" />

- Compromised host: `jr-linux-vm-test`  
- Attacker: XorDDoS malware operators using SSH brute force  
- Root account (`root`) compromised via weak credentials

---

<img src="https://img.shields.io/badge/-WHAT-000000?style=for-the-badge&logo=github&logoColor=white" />

- SSH brute-force → XorDDoS malware deployed  
- Persistence via cron jobs and fake system binaries  
- Log wiping, system abuse, and crypto mining observed  
- C2 communication to IP `169.239.130.12`

---

<img src="https://img.shields.io/badge/-WHEN-000000?style=for-the-badge&logo=github&logoColor=white" />

- Initial compromise: Jan 30, 2025  
- Cleanup attempt: Mar 18–20  
- Re-entry & persistence: Mar 24–25

---

<img src="https://img.shields.io/badge/-WHERE-000000?style=for-the-badge&logo=github&logoColor=white" />

- Azure-hosted Linux VM (`jr-linux-vm-test`)  
- External origin IPs from botnets and C2 infrastructure  
- C2 traffic over HTTP (port 80)

---

<img src="https://img.shields.io/badge/-WHY-000000?style=for-the-badge&logo=github&logoColor=white" />

- Crypto-mining and lateral movement via SSH  
- Weak SSH security allowed re-entry post-cleanup  
- Evasion through renamed binaries, cron jobs, and fake services

&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp; 
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp; 
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  
&nbsp; 

### Incident 2402 Summary  
# Incident 2402 – Password Spray Attempt (No Compromise)  
**Incident ID:** 2402  
**Date Investigated:** March 30, 2025  
**Environment:** LOG(N) Pacific | Cyber Range

---

<img src="https://img.shields.io/badge/-WHO-000000?style=for-the-badge&logo=github&logoColor=white" />

- Targeted host: `finallabscott` (internet-facing, no MDE)  
- Attacker IPs from China & Russia (e.g. `218.92.0.186`, `5.178.87.180`)  
- Account targeted: `guest`

---

<img src="https://img.shields.io/badge/-WHAT-000000?style=for-the-badge&logo=github&logoColor=white" />

- Detected password spray attack  
- 1,000+ failed logon attempts from multiple IPs  
- No successful authentication or shell activity

---

<img src="https://img.shields.io/badge/-WHEN-000000?style=for-the-badge&logo=github&logoColor=white" />

- Alert triggered: Mar 29, 2025 – 3:30 PM  
- Extended review: past 7 days of logs

---

<img src="https://img.shields.io/badge/-WHERE-000000?style=for-the-badge&logo=github&logoColor=white" />

- Device `finallabscott` (unmanaged, exposed to internet)  
- Logon attempts from China, Russia, and global botnet IPs

---

<img src="https://img.shields.io/badge/-WHY-000000?style=for-the-badge&logo=github&logoColor=white" />

- Guest account was active and accessible  
- No compromise occurred  
- Weak external posture + lack of MDE made it a soft target


