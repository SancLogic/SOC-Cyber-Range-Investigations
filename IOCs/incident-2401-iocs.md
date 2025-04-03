# IOCs – Incident 2401: Linux VM Compromise – XorDDoS Malware  
**Incident ID:** 2401  
**Environment:** LOG(N) Pacific | Cyber Range  
**Date Investigated:** March 24, 2025  

---

## 🔍 IP Addresses
| IP Address         | Type            | Notes                                  |
|--------------------|------------------|-----------------------------------------|
| 169.239.130.12      | C2 (HTTP)        | XorDDoS outbound beacon (port 80)       |
| 185.81.134.79       | Payload host     | Hosted payloads and miner scripts       |
| 196.251.114.67      | Payload host     | Downloaded black3 & variants            |
| 85.31.47.99         | C2 & downloader  | Shared miner infra with other cases     |

---

## 🌐 Domains / URLs
| Domain / URL                                 | Notes                                 |
|----------------------------------------------|----------------------------------------|
| dinpasiune[.]com                              | Miner C2 domain (multi-campaign)       |
| d1npiasuune[.]com                             | Variant domain, passive DNS matches    |
| digital[.]digitaldatainsights[.]org/.x/black3 | Hosted miner ELF payload               |
| http[:]//185.81.134.79/payload                | XorDDoS payload                        |
| http[:]//85.31.47.99/.NzJjOTYwxx5/.balu       | Related downloader URL                 |

---

## 🔐 SSH Keys (Encoded)
| Notes                             |
|----------------------------------|
| `K0FNWFaWn7k7XfYP6Cm1p6WEnB4...`  |
| `KOFVwMxV7k7XjP7fwXPY6Cmp16v...` |
| `rpvnAU...`                      |

---

## 📁 File Paths / Dropped Artifacts
| Path / File                            | Description                          |
|----------------------------------------|---------------------------------------|
| `/usr/bin/ygljglkjgfg0`                | XorDDoS persistence binary            |
| `/usr/bin/skhqwensw`, `ezxtzyenqc`     | Obfuscated malware binaries           |
| `/var/tmp/update-logs/`               | Persistence log / setup               |
| `/root/.bash_history`, `/var/log/wtmp`| Wiped for anti-forensics              |
| `/root/.ssh/authorized_keys`          | SSH backdoor key injection            |

---

## 🧪 SHA256 Hashes (XorDDoS / Miner Samples)
| Hash (SHA256)                                                       | Notes                        |
|----------------------------------------------------------------------|------------------------------|
| 74d31cac40d98ee64df2a0c29ceb229d12ac5fa699c2ee512fc69360f0cf68c5     | `.payload`                   |
| 8f5ebb5b1c09744b4bb0087dca66360530533a1913151eaa04f17b691aae5a6b     | `.balu` variant              |
| afe2db673f80d3db25f3219f27c49684f0c4f2da84bcd3459f0a0022626bde0a     | `update` binary              |
| 32a0a7ae4949e744a0508c9de404e73070c112979eb8f10d5fac9bf657018256     | `black3` ELF file            |
| b71111326ea431a855ba5b5c1b15af54adb7f0c526517d22477410faba887b78     | Fake cron utility            |

---

## ⚙️ Commands / Techniques
| Command / Behavior                      | Description                          |
|-----------------------------------------|---------------------------------------|
| `chattr -iae ~/.ssh/authorized_keys`    | Persist SSH key silently              |
| `rm -rf ~/.bash_history`                | Log wipe, anti-forensics              |
| `curl/wget ...payload`                  | Binary download                       |
| `crontab -r`                            | Disable existing cron jobs            |
| `chmod +x`                              | Payload executable setup              |
| `ulimit`, `sshpass`, `pkill`            | Miner tweaks and service kill         |

---

## 🎭 Obfuscated Binary Names
| Filename       | Purpose                              |
|----------------|---------------------------------------|
| `rmrjxqexeg`    | Fake system binary, persistence       |
| `fvsciqfcyy`    | Dropped ELF payload                   |
| `ntwgkmbdti`    | Masqueraded in `/usr/bin/`            |
| `yoviypjqdj`    | Likely launched at boot via fake init |

---

## Notes
- C2 over HTTP (port 80) with passive beaconing
- Multiple custom-named ELF binaries created in `/usr/bin`
- Attack leveraged SSH brute-force, log wipe, and persistence via renamed cron/init binaries
- MITRE TTPs: T1021, T1053.003, T1070, T1036.005, T1496, T1090, T1071.001

