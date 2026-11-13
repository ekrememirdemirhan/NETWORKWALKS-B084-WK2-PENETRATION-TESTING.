# Week 2 — Final Penetration Testing Report

**Networkwalks Cybersecurity Internship — Batch B084**

**Date:** 13 November 2026  
**Modules Completed:** W2-PM4 and W2-PM5  
**Assessment Type:** Passive Reconnaissance & Authorized Network Discovery

---

## 1. Executive Summary

During Week 2 of the Networkwalks Cybersecurity Internship, two practical cybersecurity modules were completed:

- **W2-PM4:** Footprinting and Reconnaissance with theHarvester
- **W2-PM5:** Network Scanning with Zenmap

The objective was to gain practical experience in Open-Source Intelligence (OSINT), network discovery, host identification, and security reporting.

The exercises demonstrated how publicly available information and authorized network scanning can support cybersecurity assessments.

No exploitation or unauthorized access was performed.

## 2. Scope and Authorization

The assessment consisted of two independent activities.

**Passive Reconnaissance**

- Target domain: `microsoft.com`
- Tool: theHarvester
- Method: Collecting publicly indexed information from supported sources
- No active vulnerability scanning or exploitation was performed against the external domain

**Local Network Discovery**

- Environment: Authorized private local network
- Tool: Zenmap / Nmap
- Scan type: Ping Scan
- Network: Private IPv4 /24 subnet
- Permission: Local network scanning was performed with authorization

Sensitive network identifiers have been excluded from the public report.

## 3. Tools and Environment

| Tool | Purpose | Environment |
|---|---|---|
| theHarvester 4.10.1 | Passive OSINT reconnaissance | Kali Linux 2026.2 |
| Zenmap / Nmap | Network host discovery | Windows 11 |
| ipconfig | Local network configuration | Windows 11 |
| GitHub | Evidence and report documentation | Web |

## 4. W2-PM4 — Footprinting with theHarvester

### 4.1 Objective

The goal was to discover publicly available email addresses, hosts, and subdomains associated with a target organization.

### 4.2 Task 1 — Baidu Search

Command used:

`theHarvester -d microsoft.com -l 1000 -b baidu`

**Observed results:**

| Category | Result |
|---|---|
| Target domain | microsoft.com |
| Data source | Baidu |
| Result limit | 1000 |
| Hosts discovered | 6 |
| Email addresses discovered | 0 |
| IP addresses discovered | 0 |

TheHarvester successfully identified six hostnames through the selected source.

No email addresses or IP addresses were returned in this particular search.

### 4.3 Task 2 — Multiple Data Sources

Command used:

`theHarvester -d microsoft.com -l 50 -b all`

The tool queried multiple supported public information sources.

**Observations:**

- Numerous hostnames and subdomains were returned.
- Some sources required API keys.
- Several sources produced errors or missing API key warnings.
- The complete terminal output was saved as a TXT file for documentation.

The number of results varied by source. A complete, independently verified count of unique hosts was not established.

### 4.4 Limitations

TheHarvester depends on third-party services, public search indexes, API availability, and source-specific restrictions.

Missing results do not necessarily indicate that information is absent.

Discovered subdomains were treated as reconnaissance observations, not confirmed security vulnerabilities.

### 4.5 Supporting Evidence

- [Task 1 — Baidu Results](../W2-PM4-theHarvester/W2-PM4-Task1-Baidu-Results.png)
- [Task 2 — Command and API Warnings](../W2-PM4-theHarvester/W2-PM4-Task2-Command.png)
- [Task 2 — Results Part 1](../W2-PM4-theHarvester/W2-PM4-Task2-Results-1.png)
- [Task 2 — Results Part 2](../W2-PM4-theHarvester/W2-PM4-Task2-Results-2.png)
- [Task 2 — Output Verification](../W2-PM4-theHarvester/W2-PM4-Task2-Output-Verification.png)

## 5. W2-PM5 — Network Scanning with Zenmap

### 5.1 Objective

The objective was to discover active devices within an authorized local network and document the discovered network topology.

### 5.2 Network Configuration

The Windows `ipconfig` command was used to identify the active network adapter's IPv4 configuration and subnet mask.

The target network was a private IPv4 /24 subnet containing 256 total addresses.

### 5.3 Scanning Methodology

Zenmap was configured using the **Ping Scan** profile.

Command structure:

`nmap -sn <authorized-LAN-subnet>`

This method performs host discovery without requesting a TCP or UDP port scan.

### 5.4 Scan Results

| Parameter | Result |
|---|---|
| Scan profile | Ping Scan |
| Subnet prefix | /24 |
| Total IP addresses scanned | 256 |
| Active hosts discovered | 10 |
| Scan duration | 12.97 seconds |
| Scanning environment | Authorized local network |

The scan identified ten active hosts, including the scanning computer.

Available MAC addresses were collected using Zenmap and the Windows `ipconfig /all` command.

### 5.5 Network Topology

Zenmap's Topology feature was used to visualize the discovered devices.

The topology was exported as a PDF file.

For public documentation, IP addresses and identifying device information were replaced with anonymous host labels.

**Evidence:**

[View Anonymized Zenmap Network Topology](../W2-PM5-Zenmap/W2-PM5-Zenmap-Topology-Public.pdf)

### 5.6 Limitations

A Ping Scan identifies hosts that respond to network discovery techniques.

It does not guarantee that every connected device will be detected.

The scan does not establish whether any discovered device contains exploitable vulnerabilities.

No vulnerability exploitation was attempted.

## 6. Security Findings and Risk Assessment

### Finding 1 — Publicly Indexed Host Information

**Observation:** Passive reconnaissance identified publicly indexed subdomains associated with the selected organization.

**Security relevance:** Publicly visible infrastructure information can assist external reconnaissance and attack-surface mapping.

**Assessment:** Informational observation. No confirmed vulnerability was identified.

**Recommendation:** Organizations should maintain an inventory of externally exposed assets and review unnecessary public exposure.

### Finding 2 — Local Network Device Visibility

**Observation:** Ten active hosts were discovered in the authorized local subnet.

**Security relevance:** Host discovery demonstrates the importance of asset inventory and network monitoring.

**Assessment:** Informational observation. No insecure configuration was independently verified.

**Recommendation:** Organizations should maintain accurate asset inventories, monitor unauthorized devices, and apply appropriate network segmentation where required.

### Finding 3 — OSINT Data Source Limitations

**Observation:** Some reconnaissance data sources could not be queried successfully due to API requirements and service errors.

**Impact:** Results may be incomplete.

**Recommendation:** Use several authorized data sources, document tool limitations, and validate findings before drawing security conclusions.

## 7. Challenges Encountered

During the exercises, several technical challenges were encountered:

- Some theHarvester data sources required unavailable API keys.
- TheHarvester returned a large amount of output that required systematic documentation.
- The Kali Linux virtual machine experienced a temporary session issue.
- VirtualBox drag-and-drop file transfer did not work as expected.
- A VirtualBox shared folder was used to transfer saved output files to Windows.
- Zenmap topology labels initially overlapped and required layout adjustments.

These challenges provided practical troubleshooting experience.

## 8. Recommendations

Based on the observations, the following defensive practices are recommended:

1. Maintain an accurate inventory of network devices and public-facing infrastructure.
2. Regularly review publicly accessible organizational information.
3. Monitor newly connected or unauthorized network devices.
4. Protect sensitive infrastructure details in public documentation.
5. Use multiple sources to validate reconnaissance findings.
6. Document limitations and avoid treating unverified observations as confirmed vulnerabilities.

## 9. Conclusion

Week 2 provided practical experience with passive reconnaissance and authorized network discovery.

TheHarvester demonstrated how publicly indexed information can be collected and analyzed.

Zenmap provided hands-on experience with identifying active hosts and visualizing network topology.

The activities strengthened skills in cybersecurity fundamentals, evidence collection, troubleshooting, network analysis, and technical reporting.

**No confirmed exploitable vulnerabilities were established during these exercises.**

---

## 10. Evidence and References

**Project evidence:**

- [W2-PM4 — theHarvester](../W2-PM4-theHarvester/)
- [W2-PM5 — Zenmap](../W2-PM5-Zenmap/)

**Technical references:**

- [Nmap Official Documentation](https://nmap.org/docs.html)
- [theHarvester GitHub Repository](https://github.com/laramies/theHarvester)

**Disclaimer:** This report documents educational cybersecurity exercises. It does not constitute a full penetration test or security certification of the assessed environments.
