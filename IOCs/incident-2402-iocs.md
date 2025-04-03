# IOCs – Incident 2402: Password Spray (No Compromise)  
**Incident ID:** 2402  
**Environment:** LOG(N) Pacific | Cyber Range  
**Date Investigated:** March 30, 2025  

---

## 🌐 IP Addresses

| IP Address       | Country | Notes                       |
|------------------|---------|------------------------------|
| 218.92.0.186     | China   | ~896 attempts on guest       |
| 218.92.0.187     | China   | Repeated use, 616+ attempts  |
| 61.177.172.244   | China   | Brute-force activity         |
| 5.178.87.180     | Russia  | Known abuse, password spray  |
| 190.181.24.50    | Unknown | Failed access attempt        |
| 77.223.118.28    | Unknown | Failed access attempt        |

---

## 🧠 Notes

- Attack was unsuccessful — no valid logon events observed  
- All events were `LogonFailed` with `Network` logon type  
- Targeted account was `guest` on `finallabscott` VM  
- No persistence, shells, or lateral movement confirmed  
- IPs match known password spray and botnet behavior

---

## 📌 MITRE Technique
- **T1110.003 – Brute Force: Password Spraying**  
  https://attack.mitre.org/techniques/T1110/003/
