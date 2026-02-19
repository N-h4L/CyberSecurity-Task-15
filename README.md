# Task 15: Vulnerability Assessment & Risk Prioritization

## Overview

This task focuses on performing a Vulnerability Assessment (VA) and understanding risk prioritization using OpenVAS (Greenbone Vulnerability Manager). The objective was to identify security weaknesses, analyze CVE and CVSS scores, classify risks, and prioritize remediation.

Although the OpenVAS scan could not be fully executed due to a VirtualBox network configuration issue, the vulnerability assessment workflow, risk classification process, and troubleshooting methodology were thoroughly analyzed and documented.

---

## Objective

- Install and configure OpenVAS (GVM)
- Perform vulnerability scan on target system
- Analyze vulnerabilities using CVE and CVSS
- Classify risks based on severity
- Prioritize remediation steps
- Document findings professionally

---

## Environment

- Host OS: Windows 11
- Virtualization: Oracle VirtualBox
- Guest OS: Kali Linux
- Vulnerability Scanner: OpenVAS (Greenbone Vulnerability Manager)

---

## Tool Overview: OpenVAS (GVM)

OpenVAS is an open-source vulnerability scanning framework used to detect security weaknesses in systems and networks.

It relies on:

- NVT (Network Vulnerability Tests)
- SCAP Data
- CERT Advisories
- CVE database
- CVSS scoring system

---

## Installation & Setup Attempt

Commands executed:

```bash
sudo apt update
sudo apt install gvm -y
sudo gvm-setup
sudo greenbone-feed-sync
sudo gvm-start
```

Web Interface:

```
https://127.0.0.1:9392
```

Attempted Target:

```
127.0.0.1
```

---

## Issue Encountered

During feed synchronization, the following error occurred:

```
Temporary failure in name resolution
rsync: getaddrinfo: feed.community.greenbone.net:873
```

Network testing revealed:

```
Destination Host Unreachable
100% packet loss
```

---

## Root Cause Analysis

The Kali Linux VM had no internet connectivity due to a VirtualBox network configuration issue.

Because OpenVAS requires external vulnerability feeds:

- SCAP data was not downloaded
- CERT data was not synchronized
- Default port lists were not created
- Scan target creation failed
- Vulnerability scan could not be executed

---

## Troubleshooting Performed

- Checked network connectivity using:
  ```bash
  ping 8.8.8.8
  ping google.com
  ```
- Identified DNS resolution failure
- Diagnosed VirtualBox network adapter misconfiguration

---

## Vulnerability Assessment Methodology

Even though the scan was not completed, the vulnerability assessment process was studied and structured:

### Steps in Vulnerability Assessment:

1. Define scan scope
2. Configure scanner
3. Execute scan
4. Analyze findings
5. Map vulnerabilities to CVE
6. Review CVSS scores
7. Classify severity
8. Prioritize remediation

---

## CVE & CVSS Explained

### CVE (Common Vulnerabilities and Exposures)

A unique identifier assigned to publicly disclosed vulnerabilities.

Example:

```
CVE-2023-12345
```

---

### CVSS (Common Vulnerability Scoring System)

A severity scoring system ranging from 0.0 to 10.0.

| Score Range | Severity |
|-------------|----------|
| 9.0 – 10.0  | Critical |
| 7.0 – 8.9   | High |
| 4.0 – 6.9   | Medium |
| 0.1 – 3.9   | Low |

---

## Risk Prioritization Framework

| Severity | Priority | Action |
|----------|----------|--------|
| Critical | P1 | Immediate remediation |
| High | P2 | Urgent fix |
| Medium | P3 | Scheduled remediation |
| Low | P4 | Monitor / improve |

Prioritization is important because organizations may have hundreds or thousands of vulnerabilities and must address the highest-risk issues first.

---

## VA vs Penetration Testing

| Vulnerability Assessment | Penetration Testing |
|--------------------------|--------------------|
| Identifies weaknesses | Exploits weaknesses |
| Broad automated scan | Targeted attack simulation |
| Risk identification | Proof of exploitability |

---

## Key Learning Outcomes

- Understood vulnerability management lifecycle
- Learned CVE and CVSS scoring system
- Studied risk prioritization framework
- Gained experience troubleshooting security tool deployment
- Improved understanding of real-world lab environment limitations

---

## Conclusion

The OpenVAS vulnerability assessment setup was initiated but could not be completed due to a VirtualBox network connectivity issue. Despite this limitation, the vulnerability assessment methodology, risk classification model, and CVE/CVSS prioritization framework were thoroughly studied and documented.

This task strengthened understanding of vulnerability management processes and practical troubleshooting — essential skills for SOC Analysts, Security Analysts, and Vulnerability Management roles.

---

## Author

Mohammed Nihal  
Cyber Security Intern  
Vulnerability Management | CVE | CVSS | OpenVAS
