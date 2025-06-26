# Task 3: Vulnerability Assessment

## Overview

This task focuses on conducting a **vulnerability assessment** of a personal Windows system using industry-standard tools. It aims to provide real-world exposure to identifying, analyzing, and documenting security risks through an automated scan using **Nessus Essentials**.

**Tools**: OpenVAS Community Edition (free vulnerability scanner) or Nessus Essentials.
**Deliverables**: Vulnerability scan report with identified issues.

This exercise simulates the initial steps of professional risk assessment and builds familiarity with CVEs, CVSS scores, and vulnerability mitigation techniques.

---

## Objective

- Install and configure a vulnerability scanner.
- Scan the local system for known vulnerabilities.
- Analyze the findings based on severity and type.
- Document observations and remediation strategies.
- Develop an introductory understanding of system hardening.

---

## Tools & Environment

| Tool              | Details |
|------------------|---------|
| **Scanner**       | Nessus Essentials (Tenable) – Free version |
| **System Scanned**| Windows 10 Home Edition |
| **Interface**     | Web UI (`https://localhost:8834`) |
| **Scan Type**     | Basic Network Scan |
| **Target**        | `127.0.0.1` (localhost) |

---

## ⚙️ Step-by-Step Execution

### 1. Nessus Setup
- Registered on [Tenable's website](https://www.tenable.com/products/nessus/nessus-essentials) to receive a free activation key.
- Downloaded and installed Nessus Essentials for Windows.
![Screenshot 2025-06-26 124254](https://github.com/user-attachments/assets/b37b7a69-22b9-42ec-a8c7-a4a08fba3995)
- Accessed the Nessus web interface at `https://localhost:8834`.
- Created a local Nessus user and initialized the plugin download.
![Screenshot 2025-06-26 141328](https://github.com/user-attachments/assets/bc9b55a1-7311-456b-b950-157ab04c91ea)

### 2. Scan Configuration
- Created a **New Scan** > Selected **Basic Network Scan**.
![Screenshot 2025-06-26 143936](https://github.com/user-attachments/assets/1b21674a-615e-41e9-98d4-a19883b8999b)
- Named the scan `New_Scan`.
- Defined target IP as `192.168.31.182` to scan the host system.
- Saved and launched the scan.
![image](https://github.com/user-attachments/assets/80a2176b-b16d-4fc6-8b20-f1513a4c6b0a)

### 3. Scan Results
- The scan completed in ~40 minutes.
- Discovered multiple vulnerabilities across medium, and low severity.
- Captured key details and screenshots for documentation.
![image](https://github.com/user-attachments/assets/cd4dd976-cd1a-4f81-b953-642a7eef7f98)

---

## Summary of Findings

| Severity | Total Issues | Vulnerabilities                          |
|----------|--------------|------------------------------------------|
| Medium   | 4            | SMB Signing not required                 |
| Low      | 10+          | Missing Headers, Deprecated Services     |

> All vulnerability descriptions were cross-referenced with [NIST NVD](https://nvd.nist.gov/) and CVSS scoring methodology.
![image](https://github.com/user-attachments/assets/677a3232-7d1b-45a5-932f-79657a602852)
![image](https://github.com/user-attachments/assets/66b71ba9-1dad-49d0-bbbf-35d468c15d8d)
![image](https://github.com/user-attachments/assets/726cf453-6243-4dd9-98a5-b197409be7f6)

---

## Remediation Strategy

### Medium & Low:
- Enforce message signing in the host's configuration. On Windows, this is found in the policy setting 'Microsoft network server: Digitally sign communications (always)'. On Samba, the setting is called 'server signing'. See the 'see also' links for further details.
- Purchase or generate a proper SSL certificate for this service.

---

## Key Takeaways

- Gained practical exposure to Nessus and automated scanning techniques.
- Learned to interpret vulnerability metadata: **Plugin ID**, **CVE ID**, **CVSS**, and **solution references**.
- Differentiated between vulnerability scanning and manual penetration testing.
- Understood the role of periodic scans in maintaining system hygiene.
- Experienced hands-on remediation planning based on technical documentation.

---

## Repository Structure
```
├── Nessus-Report (exported report)
├── README.md
```

---

## Final Thoughts

This task strengthened my foundational skills in vulnerability management and gave me insight into how enterprise security tools help reduce risk through automated detection and proactive remediation.

> 🧠 *Cybersecurity is not a one-time action, but an ongoing process of identifying, understanding, and mitigating threats.*
