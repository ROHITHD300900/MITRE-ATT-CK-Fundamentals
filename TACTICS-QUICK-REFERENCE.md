# 🞯 MITRE ATT&CK - Tactics Quick Reference

A concise guide to the 14 tactics in the MITRE ATT&CK framework with common techniques and detection points.

---

## 1. 🔍 RECONNAISSANCE (TA0043)
**Adversary gathers information about the target**

| Technique | ID | Description | Detection |
|-----------|----|-----------|-----------|
| Active Scanning | T1595 | Probe networks for vulnerabilities | Monitor network scans, firewall logs |
| Gather Victim Info | T1589 | Collect target organization data | Monitor data broker sites, OSINT tools |
| Search Public Resources | T1598 | Search for info in public sources | Monitor forums, job listings |

**Key Point**: This phase happens BEFORE attack - hard to detect but important for intel gathering

---

## 2. 🔨 RESOURCE DEVELOPMENT (TA0042)
**Adversary establishes capabilities for attack**

| Technique | ID | Description | Detection |
|-----------|----|-----------|-----------|
| Acquire Infrastructure | T1583 | Rent servers, domains, or services | DNS monitoring, IP reputation |
| Develop Capabilities | T1586 | Create malware or tools | Malware analysis, threat intel |
| Obtain Capabilities | T1588 | Buy or steal tools | Monitor underground forums |

**Key Point**: Pre-attack preparation phase - critical for understanding threat actors

---

## 3. ✍ INITIAL ACCESS (TA0001)
**Adversary gains entry into the network**

| Technique | ID | Description | Detection |
|-----------|----|-----------|-----------|
| Phishing | T1566 | Malicious emails/messages | Email filtering, user training |
| Supply Chain Compromise | T1195 | Target through vendor | Software verification, updates |
| Exploit Public-Facing App | T1190 | Attack web applications | WAF logs, vulnerability scanning |

**Key Point**: This is the breach moment - focus detection here!

---

## 4. ⚡ EXECUTION (TA0002)
**Adversary runs code/commands**

| Technique | ID | Description | Detection |
|-----------|----|-----------|-----------|
| Command Line | T1059 | Execute commands | EDR, command logging |
| PowerShell | T1059.001 | Use PowerShell | PowerShell logging, script block logging |
| Scheduled Task | T1053 | Create scheduled jobs | Task scheduler logs |

**Key Point**: Heavy monitoring required - most detections here

---

## 5. 🏘️ PERSISTENCE (TA0003)
**Adversary maintains presence**

| Technique | ID | Description | Detection |
|-----------|----|-----------|-----------|
| Boot/Logon Autostart | T1547 | Run at startup | Registry monitoring, startup folders |
| Scheduled Task/Job | T1053 | Persistence via tasks | Task scheduler, cron logs |
| Account Manipulation | T1098 | Modify user accounts | User audit logs, account changes |

**Key Point**: Prevents eviction - important for long-term intrusions

---

## 6. 🕓 PRIVILEGE ESCALATION (TA0004)
**Adversary gains higher access**

| Technique | ID | Description | Detection |
|-----------|----|-----------|-----------|
| Abuse Elevation Control | T1548 | Bypass privilege restrictions | User access logs, UAC bypasses |
| Exploit System Software | T1068 | Vulnerability exploitation | Patch management, EDR |
| Token Impersonation | T1134 | Use other user tokens | Process access logs |

**Key Point**: Critical escalation point - high-value detection target

---

## 7. 🚎 DEFENSE EVASION (TA0005)
**Adversary avoids detection**

| Technique | ID | Description | Detection |
|-----------|----|-----------|-----------|
| Masquerading | T1036 | Disguise files/processes | File properties, process analysis |
| Disable Tools | T1562 | Disable security tools | Security tool logs, alerts |
| Obfuscate Code | T1027 | Hide malicious code | Behavioral analysis, memory scanning |

**Key Point**: Hardest to detect - requires behavioral and advanced monitoring

---

## 8. 🔐 CREDENTIAL ACCESS (TA0006)
**Adversary steals login credentials**

| Technique | ID | Description | Detection |
|-----------|----|-----------|-----------|
| Brute Force | T1110 | Guess passwords | Failed login attempts, account lockouts |
| Credential Dumping | T1003 | Extract hashes | LSASS memory access, SAM extraction |
| Input Capture | T1056 | Keylogging/Screen capture | EDR, network monitoring |

**Key Point**: Gateway to lateral movement - critical defense point

---

## 9. 🔍 DISCOVERY (TA0007)
**Adversary finds available resources**

| Technique | ID | Description | Detection |
|-----------|----|-----------|-----------|
| System Info Discovery | T1082 | Gather system details | Process execution logs |
| Account Discovery | T1087 | Find user accounts | Active Directory queries |
| Network Share Discovery | T1135 | Find shared folders | Network monitoring |

**Key Point**: Reconnaissance within network - watch for discovery patterns

---

## 10. 🛌 LATERAL MOVEMENT (TA0008)
**Adversary moves through network**

| Technique | ID | Description | Detection |
|-----------|----|-----------|-----------|
| Remote Services | T1570 | Use RDP/SSH/WinRM | Network logs, authentication logs |
| Pass-the-Hash | T1550.002 | Use stolen hashes | Authentication event logs |
| Windows Admin Shares | T1570 | Access C$ shares | Network monitoring, share access logs |

**Key Point**: Critical for containment - block lateral movement!

---

## 11. 📄 COLLECTION (TA0009)
**Adversary gathers target data**

| Technique | ID | Description | Detection |
|-----------|----|-----------|-----------|
| Data Staged | T1074 | Prepare data for exfil | File access logs, staging directories |
| Archive Collected Data | T1560 | Zip/compress files | Process monitoring, file creation |
| Screen Capture | T1113 | Take screenshots | EDR, clipboard monitoring |

**Key Point**: Data theft objective - focus on sensitive data access

---

## 12. 📡 COMMAND & CONTROL (TA0011)
**Adversary controls compromised systems**

| Technique | ID | Description | Detection |
|-----------|----|-----------|-----------|
| Application Layer Protocol | T1071 | Use HTTPS/DNS for C2 | Network analysis, traffic inspection |
| Remote Access Software | T1219 | TeamViewer, AnyDesk | Network monitoring, process analysis |
| Data Encoding | T1001 | Hide C2 communications | Network behavioral analysis |

**Key Point**: Backbone of attack - detect C2 communications!

---

## 13. 📄 EXFILTRATION (TA0010)
**Adversary steals data**

| Technique | ID | Description | Detection |
|-----------|----|-----------|-----------|
| Exfil Over C2 Channel | T1041 | Send data via C2 | Network monitoring, DLP |
| Data Compressed | T1002 | Compress before transfer | Process monitoring, network analysis |
| Exfil Over HTTPS | T1020 | Use HTTPS for theft | SSL inspection, network monitoring |

**Key Point**: Point of no return - prevent data loss!

---

## 14. 💣 IMPACT (TA0040)
**Adversary disrupts/damages systems**

| Technique | ID | Description | Detection |
|-----------|----|-----------|-----------|
| Data Destruction | T1485 | Delete/wipe data | File deletion monitoring, recovery tools |
| Defacement | T1491 | Modify websites/systems | Integrity monitoring, backups |
| Denial of Service | T1499 | Disrupt availability | Network monitoring, threshold alerts |

**Key Point**: Final damage phase - ensure backups and recovery plans!

---

## 📈 Detection by Tactic Priority

**HIGHEST Priority** (Easiest to detect, most impactful)
1. Initial Access
2. Execution
3. Lateral Movement
4. Exfiltration

**MEDIUM Priority**
1. Privilege Escalation
2. Persistence
3. Credential Access

**CHALLENGING** (Requires advanced detection)
1. Defense Evasion
2. Discovery
3. Collection

**DIFFICULT** (Pre-attack)
1. Reconnaissance
2. Resource Development
3. Command & Control (need network insights)

---

## 💡 Quick Win Detections

✅ Enable process execution logging
✅ Monitor failed login attempts
✅ Setup network flow monitoring
✅ Enable PowerShell logging
✅ Monitor scheduled task creation
✅ Alert on admin group changes
✅ Track lateral movement patterns
✅ Monitor data staging locations
