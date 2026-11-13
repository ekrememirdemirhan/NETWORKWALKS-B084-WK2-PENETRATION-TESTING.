# W2-PM5 — Network Scanning with Zenmap

## Project Information
- **Internship:** Networkwalks Cybersecurity Internship
- **Batch:** B084
- **Week:** 2
- **Module:** W2-PM5
- **Tools:** Nmap 7.993, Zenmap
- **Operating System:** Windows 11
- **Date:** November 13, 2026

## Objective
The objective of this project was to discover active devices on an authorized local network using Zenmap and document the network topology.

## Tasks Completed

1. Installed Nmap and Zenmap on Windows.
2. Identified the local IPv4 address and subnet mask using `ipconfig`.
3. Performed a Ping Scan using Zenmap.
4. Identified the number of active hosts.
5. Collected the IP addresses of active hosts.
6. Examined MAC addresses using Zenmap and `ipconfig /all`.
7. Generated and saved the network topology as a PDF.

## Scan Configuration

- **Scan Type:** Ping Scan
- **Command:** `nmap -sn <authorized-LAN-subnet>`
- **Subnet Mask:** /24
- **IP Addresses Scanned:** 256
- **Active Hosts Discovered:** 10
- **Scan Duration:** 12.97 seconds

## Results

The scan identified 10 active hosts, including the scanning computer.

Zenmap provided information about responding devices, including IP addresses, available MAC addresses, and hostnames.

A graphical network topology was generated to visualize the discovered hosts.

## Security and Privacy

The scan was performed on an authorized local network.

Private IP addresses, MAC addresses, and identifying device names are excluded from the publicly shared documentation.

The network topology was anonymized before publication.

## Limitations

A Ping Scan identifies responding hosts but does not establish whether those devices contain security vulnerabilities.

No exploitation, vulnerability assessment, or unauthorized access was performed.

## Conclusion

This project provided practical experience in network discovery, host identification, and network topology visualization using Nmap and Zenmap.

These skills are relevant to network administration, asset discovery, and cybersecurity operations.

**Disclaimer:** This exercise was performed for educational purposes on an authorized network.
