# 🎯 MITRE ATT&CK Fundamentals

**Master the MITRE ATT&CK Framework** - Understand Adversary Tactics, Techniques, and Detection Strategies for Security Operations and Penetration Testing.

## 📋 Table of Contents

- [What is MITRE ATT&CK?](#what-is-mitre-attck)
- [Framework Overview](#framework-overview)
- [Core Concepts](#core-concepts)
- [Tactics & Techniques](#tactics--techniques)
- [Detection Strategies](#detection-strategies)
- [Hands-On Labs](#hands-on-labs)
- [Resources](#resources)

## 🔍 What is MITRE ATT&CK?

The **MITRE Adversarial Tactics, Techniques, and Common Knowledge (ATT&CK)** framework is a globally-accessible knowledge base of adversary tactics and techniques based on real-world observations.

**Key Points:**
- **14 Tactics**: Categories of adversary behavior
- **700+ Techniques**: Specific methods to achieve tactical goals
- **Real-world data**: Based on actual threat actor behaviors
- **Detection focus**: How to identify and defend against attacks

## 📊 Framework Overview

### The 14 Tactics (ATT&CK for Enterprise)

| # | Tactic | Focus Area |
|---|--------|------------|
| 1 | **Reconnaissance** | Gather information about targets |
| 2 | **Resource Development** | Establish capabilities for attack |
| 3 | **Initial Access** | Get into target network |
| 4 | **Execution** | Run malicious code |
| 5 | **Persistence** | Maintain presence |
| 6 | **Privilege Escalation** | Gain higher access levels |
| 7 | **Defense Evasion** | Avoid detection |
| 8 | **Credential Access** | Steal login credentials |
| 9 | **Discovery** | Find available systems/resources |
| 10 | **Lateral Movement** | Move through network |
| 11 | **Collection** | Gather data |
| 12 | **Command & Control** | Control compromised systems |
| 13 | **Exfiltration** | Steal data |
| 14 | **Impact** | Disrupt/damage systems |

## 🛠️ Core Concepts

### Tactics
- **Definition**: Broader categories of attacker behavior
- **Purpose**: Why an attacker performs an action
- **Example**: "Privilege Escalation" - gaining higher access

### Techniques
- **Definition**: Specific methods used to execute tactics
- **Sub-techniques**: More granular variations of techniques
- **Example**: "Exploit system software" - T1068

### Mitigations
- **Definition**: Actions to reduce likelihood of technique success
- **Categories**: 
  - Operational mitigations
  - Technical mitigations
  - Architecture/design mitigations

## 🎓 Key Techniques by Tactic

### Initial Access (T1xxx)
- **T1189**: Drive-by Compromise
- **T1200**: Hardware Additions
- **T1566**: Phishing

### Execution (T1xxx)
- **T1059**: Command and Scripting Interpreter
- **T1106**: Native API
- **T1053**: Scheduled Task

### Persistence (T1xxx)
- **T1547**: Boot or Logon Autostart Execution
- **T1547.001**: Registry Run Keys
- **T1098**: Account Manipulation

### Privilege Escalation (T1xxx)
- **T1548**: Abuse Elevation Control Mechanism
- **T1548.003**: Sudo and Sudo Caching
- **T1134**: Access Token Manipulation

### Defense Evasion (T1xxx)
- **T1197**: BITS Jobs
- **T1036**: Masquerading
- **T1207**: Rogue Domain Controller

## 🛡️ Detection Strategies

### Detection Process
```
1. Understand the Tactic → Define Detection Goal
2. Map Techniques → Know Adversary Methods
3. Identify Indicators → What to look for (IOCs/TTPs)
4. Select Tools → SIEM, EDR, Network tools
5. Monitor & Alert → Continuous observation
6. Investigate → Response and remediation
```

### Detection Methods by Layer

| Layer | Tools | Signals |
|-------|-------|----------|
| **Endpoint** | EDR, AV | Process creation, registry changes, file access |
| **Network** | IDS/IPS, Firewall | Network connections, DNS queries, protocols |
| **Application** | Logging, APM | API calls, auth failures, data access |
| **Cloud** | Cloud logs, CASB | Account activity, API usage, data movement |

## 💻 Hands-On Labs

### Lab 1: Map Tactics to Real Breach
- **Scenario**: Analyze a real threat actor (e.g., APT28)
- **Task**: Document tactics used in their campaigns
- **Outcome**: Build threat profile using ATT&CK

### Lab 2: Build Detection Rules
- **Scenario**: Detect T1059 (Command Line)
- **Task**: Write YARA/SIGMA rules
- **Outcome**: Operational detections for your environment

### Lab 3: Incident Response Mapping
- **Scenario**: Analyze logs from breached system
- **Task**: Map observed activity to ATT&CK techniques
- **Outcome**: Understand attack chain and impact

## 📚 Learning Objectives

✅ Understand MITRE ATT&CK framework structure
✅ Know all 14 tactics and common techniques
✅ Map adversary behavior to ATT&CK
✅ Develop detection strategies
✅ Build threat intelligence profiles
✅ Improve incident response capabilities

## 🔗 Resources

- **Official Site**: https://attack.mitre.org/
- **Navigator Tool**: https://mitre-attack.github.io/attack-navigator/
- **Mobile ATT&CK**: https://attack.mitre.org/mobile/
- **Cloud ATT&CK**: https://attack.mitre.org/cloud/

## 👤 Who Should Use This?

- 🔐 **Security Analysts** - Threat detection and hunting
- 🔴 **Penetration Testers** - Attack planning and simulation
- 🛡️ **Blue Teamers** - Defense strategy development
- 📊 **SOC Analysts** - Incident investigation
- 👨‍💼 **Security Leaders** - Risk assessment and prioritization

## 📈 Progression Path

**Beginner** → Learn the 14 tactics → Understand common techniques → Map to real threats

**Intermediate** → Deep dive into specific tactics → Learn mitigations → Build detections

**Advanced** → Threat actor profiling → Campaign analysis → Threat intelligence

## 💡 Tips for Success

1. **Start with one tactic** - Don't try to learn everything at once
2. **Use the Navigator** - Visual tool helps understanding relationships
3. **Map real breaches** - Apply framework to actual threat intel
4. **Build detections** - Create rules for techniques in your environment
5. **Stay updated** - MITRE regularly adds new techniques

## 📝 License

MIT License - Free to use and distribute

---

⭐ **If this helps your security journey, please star this repository!**

**Questions?** Open an issue or reach out on LinkedIn: [in/rohith-d-a46aaa288](https://www.linkedin.com/in/rohith-d-a46aaa288/)
