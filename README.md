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

## Incident Library

### Incident-2400: Azure Abuse – Crypto-Mining & Brute-Force  
<a href="./Reports/incident-2400-azure-abuse-crypto-mining-brute-force.pdf"><img src="https://img.shields.io/badge/-Full_Report-grey?style=for-the-badge&logo=readthedocs&logoColor=white" /></a>
<a href="#incident-2400-summary"><img src="https://img.shields.io/badge/-Summary-blue?style=for-the-badge&logo=markdowngit&logoColor=white" /></a>
<a href="./IOCs/incident-2400-iocs.md"><img src="https://img.shields.io/badge/-IOCs-orange?style=for-the-badge&logo=virustotal&logoColor=white" /></a>
<a href="./Detections/incident-2400-detections.md"><img src="https://img.shields.io/badge/-Detections-purple?style=for-the-badge&logo=microsoft&logoColor=white" /></a>

---

### Incident-2401: Linux VM Compromise – XorDDoS Malware  
<a href="./Reports/incident-2401-linux-vm-xorddos-compromise.pdf"><img src="https://img.shields.io/badge/-Full_Report-grey?style=for-the-badge&logo=readthedocs&logoColor=white" /></a>
<a href="#incident-2401-summary"><img src="https://img.shields.io/badge/-Summary-blue?style=for-the-badge&logo=markdowngit&logoColor=white" /></a>
<a href="./IOCs/incident-2401-iocs.md"><img src="https://img.shields.io/badge/-IOCs-orange?style=for-the-badge&logo=virustotal&logoColor=white" /></a>
<a href="./Detections/incident-2401-detections.md"><img src="https://img.shields.io/badge/-Detections-purple?style=for-the-badge&logo=microsoft&logoColor=white" /></a>

---

### Incident-2402: Password Spray (No Compromise)  
<a href="./Reports/incident-2402-password-spray-finallabscott.pdf"><img src="https://img.shields.io/badge/-Full_Report-grey?style=for-the-badge&logo=readthedocs&logoColor=white" /></a>
<a href="#incident-2402-summary"><img src="https://img.shields.io/badge/-Summary-blue?style=for-the-badge&logo=markdowngit&logoColor=white" /></a>
<a href="./IOCs/incident-2402-iocs.md"><img src="https://img.shields.io/badge/-IOCs-orange?style=for-the-badge&logo=virustotal&logoColor=white" /></a>
<a href="./Detections/incident-2402-detections.md"><img src="https://img.shields.io/badge/-Detections-purple?style=for-the-badge&logo=microsoft&logoColor=white" /></a>



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

<img src="https://img.shields.io/badge/-HOW-000000?style=for-the-badge&logo=github&logoColor=white" /> 
- The attacker gained entry using brute force attacks and was able to gain entry due to weak credentials  
- They hid their activity using scripts and scheduled tasks.

---

<img src="https://img.shields.io/badge/-RECOMMENDATIONS-228B22?style=for-the-badge&logo=vercel&logoColor=white" />

1. **Secure Remote Access**  
   Limit who can connect to systems remotely and require strong, unique passwords or authentication methods.

2. **Block Malicious Traffic**  
   Prevent compromised systems from connecting to known hacker servers or mining networks by controlling outbound network traffic.

3. **Update Credentials**  
   Immediately change all passwords on affected systems and avoid using shared or reused credentials going forward.

4. **Monitor for Suspicious Behavior**  
   Set up security alerts to catch unusual logins or hidden programs that could signal another attack.

5. **Clean Up and Reset**  
   Remove all infected systems, restore from clean backups, and do not reuse compromised virtual machines or images.

---

<img src="https://img.shields.io/badge/-TIMELINE-4169E1?style=for-the-badge&logo=clockify&logoColor=white" />

| Date       | Event                                      |
|------------|--------------------------------------------|
| Feb 18     | Attacker gained access via weak credentials |
| Feb 20–22  | Crypto-mining tools installed and active    |
| Mar 14–17  | Outbound brute-force attacks launched       |
| Mar 18     | Microsoft abuse alert triggered             |
| Mar 20     | Incident fully contained and cleaned        |

<br>
<a href="#incident-library"><img src="https://img.shields.io/badge/-Back_to_Incident_Library-555?style=for-the-badge&logo=homeassistant&logoColor=white" /></a>


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

## Incident 2401 Summary  
# Incident 2401 – Linux VM Compromise: XorDDoS Malware  
**Incident ID:** 2401  
**Date Investigated:** March 24, 2025  
**Environment:** LOG(N) Pacific | Cyber Range

---

<img src="https://img.shields.io/badge/-INCIDENT_SUMMARY-0078D4?style=for-the-badge&logo=bookstack&logoColor=white" />

A Linux VM exposed to the internet was compromised through brute-force SSH attacks. The attacker deployed XorDDoS malware, maintained access over time using hidden cron jobs and SSH keys, and communicated with a known command-and-control (C2) server. Attempts were also made to move laterally and hide their presence using renamed system binaries.

---

<img src="https://img.shields.io/badge/-WHO-000000?style=for-the-badge&logo=github&logoColor=white" />

- Compromised host: `jr-linux-vm-test`  
- Attacker used public SSH scanning infrastructure  
- C2 IP observed: `169.239.130.12`

---

<img src="https://img.shields.io/badge/-WHAT-000000?style=for-the-badge&logo=github&logoColor=white" />

- Malware: XorDDoS variant deployed post-compromise  
- Persistence via cron jobs, fake system binaries  
- C2 communication and botnet control attempts

---

<img src="https://img.shields.io/badge/-WHEN-000000?style=for-the-badge&logo=github&logoColor=white" />

- Initial access: Jan 30, 2025 - Feb 28, 2025  
- Malware activity re-detected: Mar 24, 2025  
- Previous cleanup done: Mar 18–20  

---

<img src="https://img.shields.io/badge/-WHERE-000000?style=for-the-badge&logo=github&logoColor=white" />

- Azure-hosted VM: `jr-linux-vm-test`  
- C2 communication over HTTP (port 80)  
- External origin IPs associated with botnet activity

---

<img src="https://img.shields.io/badge/-WHY-000000?style=for-the-badge&logo=github&logoColor=white" />

- Maintain access for malware deployment and system abuse  
- Resource hijacking (CPU/traffic) and possible lateral movement  
- Weak SSH configuration enabled multiple compromises

---

<img src="https://img.shields.io/badge/-HOW-000000?style=for-the-badge&logo=github&logoColor=white" />

- Gained root access via SSH brute-force  
- Injected SSH keys and set up malicious cron jobs  
- Used renamed Linux binaries to evade detection  
- Connected to known XorDDoS C2 infrastructure

---

<img src="https://img.shields.io/badge/-RECOMMENDATIONS-228B22?style=for-the-badge&logo=vercel&logoColor=white" />

1. **Harden SSH Access**  
   Restrict access to known IPs and use key-based authentication.

2. **Rotate Credentials**  
   Change all passwords and keys, especially for root and shared users.

3. **Rebuild Systems**  
   Don’t reuse infected machines — Delete the VMs.

4. **Block Malicious Infrastructure**  
   Use threat intel to block known C2 servers like `169.239.130.12`.

5. **Increase Monitoring**  
   Watch for signs of persistence (cron jobs, SSH key changes, renamed binaries).

---

<img src="https://img.shields.io/badge/-TIMELINE-4169E1?style=for-the-badge&logo=clockify&logoColor=white" />

| Date       | Event                                      |
|------------|--------------------------------------------|
| Jan 30     | Initial SSH brute-force compromise         |
| Feb–Mar    | Dormant persistence (no alerts)            |
| Mar 18–20  | Cleanup attempt performed                  |
| Mar 24     | Malware re-detected and C2 communication observed |
| Mar 25     | Host isolated and deleted                |

<br>
<a href="#incident-library"><img src="https://img.shields.io/badge/-Back_to_Incident_Library-555?style=for-the-badge&logo=homeassistant&logoColor=white" /></a>


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

## Incident 2402 Summary  
# Incident 2402 – Password Spray Attempt (No Compromise)  
**Incident ID:** 2402  
**Date Investigated:** March 30, 2025  
**Environment:** LOG(N) Pacific | Cyber Range

---

<img src="https://img.shields.io/badge/-INCIDENT_SUMMARY-0078D4?style=for-the-badge&logo=bookstack&logoColor=white" />

A high-severity alert flagged suspicious logon activity targeting an internet-facing lab VM. Investigation confirmed a password spray attempt from external IPs, focused on the built-in `guest` account. No successful authentication or system compromise occurred. The device was not enrolled in endpoint protection and was publicly exposed at the time of the attack.

---

<img src="https://img.shields.io/badge/-WHO-000000?style=for-the-badge&logo=github&logoColor=white" />

- Targeted device: `finallabscott`  
- Attacker IPs from: China, Russia, and global scanning infrastructure  
- Account targeted: `guest` (built-in, enabled)

---

<img src="https://img.shields.io/badge/-WHAT-000000?style=for-the-badge&logo=github&logoColor=white" />

- Password spray attack (1,000+ failed attempts)  
- Attempted remote login via "Network Logon"  
- No successful authentication or shell activity observed

---

<img src="https://img.shields.io/badge/-WHEN-000000?style=for-the-badge&logo=github&logoColor=white" />

- Alert triggered: Mar 29, 2025  
- Logs reviewed: Mar 23–30, 2025

---

<img src="https://img.shields.io/badge/-WHERE-000000?style=for-the-badge&logo=github&logoColor=white" />

- Device: `finallabscott`  
- Exposure: Internet-facing with no Defender for Endpoint  
- Remote IPs: `218.92.0.186`, `5.178.87.180` (VT: known scanners)

---

<img src="https://img.shields.io/badge/-WHY-000000?style=for-the-badge&logo=github&logoColor=white" />

- External actors targeting public systems with weak/default credentials  
- Guest account was accessible and lacked protections  
- Likely part of a mass credential stuffing campaign

---

<img src="https://img.shields.io/badge/-HOW-000000?style=for-the-badge&logo=github&logoColor=white" />

- Automated spray tools attempted login to `guest` account  
- No lateral movement, persistence, or malware seen  
- Failed authentication logs confirmed across multiple time windows

---

<img src="https://img.shields.io/badge/-RECOMMENDATIONS-228B22?style=for-the-badge&logo=vercel&logoColor=white" />

1. **Disable Unused Accounts**  
   Remove or disable default/guest accounts across all VMs.

2. **Limit Exposure**  
   Avoid exposing unmanaged devices directly to the internet.

3. **Enable Endpoint Protection**  
   Enroll all devices in Defender for Endpoint or equivalent tools.

4. **Geo-Block Suspicious IPs**  
   Block known malicious ranges from untrusted regions where possible.

5. **Enforce Lockout Policies**  
   Implement lockout after failed login attempts to prevent enumeration.

---

<img src="https://img.shields.io/badge/-TIMELINE-4169E1?style=for-the-badge&logo=clockify&logoColor=white" />

| Date       | Event                                        |
|------------|----------------------------------------------|
| Mar 23–29  | Multiple failed logons targeting `guest`     |
| Mar 29     | Alert triggered by Sentinel (Password Spray) |
| Mar 30     | Incident triaged, no compromise confirmed    |

<br>
<a href="#incident-library"><img src="https://img.shields.io/badge/-Back_to_Incident_Library-555?style=for-the-badge&logo=homeassistant&logoColor=white" /></a>
