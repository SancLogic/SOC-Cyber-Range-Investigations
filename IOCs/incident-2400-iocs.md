# IOCs – Incident 2400: Azure Abuse, Crypto-Mining & Brute-Force  
**Incident ID:** 2400  
**Environment:** LOG(N) Pacific | Cyber Range  
**Date Investigated:** March 18, 2025  

---

## 🔍 IP Addresses
| IP Address       | Type            | Notes                                      |
|------------------|------------------|---------------------------------------------|
| 85.31.47.99       | External (C2)     | C2, miner payload host (.balu, wget/curl)   |
| 80.76.51.5        | External (Infra) | ELF miner hosting (confirmed via OSINT)     |
| 20.81.228.191     | Internal (Azure) | Outbound brute-force origination IP         |

---

## 🌐 Domains / URLs
| Domain / URL                             | Type    | Notes                           |
|------------------------------------------|---------|----------------------------------|
| dinpasiune[.]com                          | Domain  | Malware delivery, C2 infra      |
| d1npiasuune[.]com                         | Domain  | Variant domain, passive DNS     |
| digital[.]digitaldatainsights[.]org      | Domain  | Known to host `black3` payload  |
| http[:]//85.31.47.99/.NzJOTWxvcs/.balu   | URL     | Miner binary download           |
| http[:]//dinpasiune[.]com/payload        | URL     | Payload staging                 |

---

## 🧪 File Hashes (SHA256)
| Hash                                                                 | File Name     | Notes                      |
|----------------------------------------------------------------------|---------------|-----------------------------|
| 061f2562bf4ad2db25f218e218920aece057024cd2c8826c87f65acc29583191     | `retea`       | Core miner script           |
| 8c2a00409bad8033fec13fc6ffe4aa4732d80400072043b71ceb57db37244129     | `cache`       | Artifact used in staging    |
| 7d48d223d81a0dd8150d27685a7f9808cb59bd9da918f992ce6dac1c387aa16e     | `update`      | Persistence mechanism       |
| 0e13e9e4443102bf5b26396b5319f528642b4f0477feb9c7f536fab379b73074     | `cache` (variant) | Across multiple systems  |

---

## 📁 File Paths / Artifacts
| Path                                     | Description                             |
|------------------------------------------|------------------------------------------|
| `/var/tmp/Documents/.diicot`             | Initial miner binary                     |
| `/var/tmp/Documents/.kuak`               | Secondary payload                        |
| `/var/tmp/cache`                         | Payload staging folder                   |
| `/etc/rc.local`                          | Persistence via startup script           |
| `~/.bash_history`                        | Wiped for evasion                        |
| `/root/.ssh/authorized_keys`            | Backdoor SSH key injection               |
| `/tmp/.tmp/`, `/dev/shm/`, `/var/tmp/`  | Common attacker write locations          |

---

## ⚙️ Commands & Techniques
| Command                         | Description                        |
|----------------------------------|-------------------------------------|
| `curl -O -s -L .../.balu`        | Downloading miner payload           |
| `wget -q .../.balu`              | Alternate miner fetch               |
| `chmod +x cache`                | Making payload executable           |
| `rm -rf .bash_history`          | Anti-forensics                      |
| `crontab -r`                    | Cleanup persistence                 |
| `chattr -iae ~/.ssh/authorized_keys` | Modify SSH auth for persistence |

## Notes
- SSH brute-force originated from infected Azure-hosted Linux VMs.
- Attacker infrastructure reused across incidents and binaries.
- MITRE mappings: T1496, T1027, T1036, T1098, T1564.001, T1053.003
