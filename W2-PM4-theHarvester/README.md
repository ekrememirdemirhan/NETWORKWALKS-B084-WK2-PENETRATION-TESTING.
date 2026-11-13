# W2-PM4 — Footprinting & Reconnaissance with theHarvester

## Project Information
- **Internship:** Networkwalks Cybersecurity Internship
- **Batch:** B084
- **Week:** 2
- **Module:** W2-PM4
- **Tool:** theHarvester 4.10.1
- **Operating System:** Kali Linux 2026.2
- **Target Domain:** microsoft.com

## Objective
The objective of this module was to practice passive reconnaissance using theHarvester to collect publicly available information, including email addresses, hosts, and subdomains.

## Task 1 — Baidu Reconnaissance

**Command:**
`theHarvester -d microsoft.com -l 1000 -b baidu`

**Results:**
- Hosts discovered: 6
- Emails discovered: 0
- IP addresses discovered: 0

The scan successfully retrieved publicly indexed hostnames.

## Task 2 — Multiple-Source Reconnaissance

**Command:**
`theHarvester -d microsoft.com -l 50 -b all`

**Results:**
- Multiple hostnames and subdomains were discovered.
- Some sources returned missing API key warnings.
- Results were saved for documentation and further analysis.

## Challenges and Limitations
Some data sources required API keys, which were not configured. Therefore, not every supported source returned results.

The absence of results from a particular source does not necessarily mean that the information does not exist.

## Evidence
Screenshots and command outputs were collected during both tasks. Publicly shared evidence will be reviewed to avoid unnecessary exposure of sensitive information.

## Conclusion
This project provided practical experience with passive reconnaissance, OSINT tools, and documenting reconnaissance results.

The exercise demonstrated how publicly available information can help security analysts understand an organization's external exposure.

**Disclaimer:** This project was completed for educational purposes using publicly available information. No exploitation or unauthorized access was performed.
