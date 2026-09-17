# W2-PM-FINAL — Week 2 Cybersecurity Project Report

## 1. Project Overview

This final report summarizes the completed Week 2 practical modules selected for the cybersecurity project.

### Completed Modules

- **W2-PM1:** Footprinting with Multiple Kali Tools
- **W2-PM2:** Footprinting & Reconnaissance with GHDB-style Search Operators
- **W2-PM5:** Zenmap Based Network Scanning

The selected practicals cover two major areas of reconnaissance: **footprinting/OSINT** and **local network discovery/scanning**.

---

# 2. W2-PM1 — Footprinting with Multiple Kali Tools

## Objective

The practical used multiple Kali Linux reconnaissance tools to collect publicly observable information about `networkwalks.com`.

## Tools Used

| Tool | Purpose |
|---|---|
| WHOIS | Domain registration information |
| WhatWeb | Web technology fingerprinting |
| NSLookup | DNS resolution |
| cURL | HTTP response/header analysis |
| WAFW00F | WAF detection |
| DNSRecon | DNS record enumeration |

## Commands Performed

```bash
whois networkwalks.com
whatweb networkwalks.com
nslookup networkwalks.com
curl -I https://networkwalks.com
wafw00f https://networkwalks.com
dnsrecon -d networkwalks.com
```

## Key Findings

- WHOIS returned publicly available domain registration information.
- WhatWeb identified observable web technologies and server information.
- NSLookup resolved the domain to `192.232.216.135` during the practical.
- cURL was used to inspect HTTP response headers.
- WAFW00F was used to check for an identifiable Web Application Firewall.
- DNSRecon identified multiple DNS records, including NS, A, MX, TXT and SRV records.

## Evidence

The detailed PM1 documentation and screenshots are maintained in the dedicated module folder:

`W2-PM1-Footprinting/`

---

# 3. W2-PM2 — GHDB-Based Footprinting

## Objective

The practical demonstrated search-engine-based information discovery using operators such as `filetype:pdf`, `site:edu`, and quoted search phrases.

## Safety Scope

For this project, the documented results were limited to **public, non-sensitive mathematics educational PDFs**. No exposed cameras, private systems, credentials, or sensitive resources were included.

## Search Operators Used

```text
filetype:pdf mathematics
site:edu filetype:pdf mathematics
site:edu filetype:pdf mathematics "lecture notes"
site:edu filetype:pdf mathematics "lecture notes" calculus
site:edu filetype:pdf mathematics "linear algebra" lecture notes
site:edu filetype:pdf mathematics "probability" "lecture notes"
site:edu filetype:pdf mathematics "differential equations" "lecture notes"
site:edu filetype:pdf mathematics "number theory" "lecture notes"
site:edu filetype:pdf mathematics "abstract algebra" "lecture notes"
```

## Results

Ten publicly accessible academic mathematics resources were documented, including material from Alagappa University, Carnegie Mellon University, MIT, University of Wisconsin–Madison, NJIT, UC Davis, and Loyola University Chicago.

Topics included:

- Nature of Mathematics
- Calculus
- Mathematics for Computer Science
- Linear Algebra
- Probability
- Differential Equations
- Number Theory
- Abstract Algebra

No usernames or passwords were required for the listed public educational resources.

## Key Learning

- Search operators can narrow information discovery results.
- `filetype:pdf` searches for PDF documents.
- `site:edu` focuses searches toward educational domains.
- Quoted phrases make searches more specific.
- Reconnaissance activities should remain within authorized and non-sensitive scope.

## Evidence

The detailed PM2 documentation is maintained in:

`W2-PM2-GHDB/`

---

# 4. W2-PM5 — Zenmap Based Network Scanning

## Objective

The practical used Zenmap/Nmap to discover live hosts on the local Wi-Fi subnet.

## Network Information

- Local IPv4: `10.208.175.92`
- Subnet Mask: `255.255.255.0`
- Target Network: `10.208.175.0/24`

## Scan Profile

**Ping Scan**

## Command

```bash
nmap -sn 10.208.175.0/24
```

## Scan Result

The scan checked 256 IP addresses and identified two hosts as up:

| No. | IP Address | Status |
|---:|---|---|
| 1 | `10.208.175.103` | Up |
| 2 | `10.208.175.215` | Up |

## ARP/MAC Information

The local ARP table showed the following IP-to-MAC mappings:

| IP Address | MAC Address |
|---|---|
| `10.208.175.103` | `c6-4c-2f-29-e1-f7` |
| `10.208.175.215` | `0e-ea-b8-d5-83-cf` |

## Topology

Zenmap's Topology view displayed the local host together with the two discovered hosts. A topology PDF was saved as:

`PM5-Zenmap-Topology.pdf`

## Key Learning

- A `/24` network contains 256 IPv4 addresses.
- `nmap -sn` performs host discovery without a conventional port scan.
- ARP can provide local IP-to-MAC mappings.
- Zenmap provides a graphical interface for Nmap results and topology visualization.

## Evidence

The detailed PM5 documentation is maintained in:

`W2-PM5-Zenmap/`

---

# 5. Comparison of the Completed Practicals

| Module | Main Area | Primary Tools/Methods | Main Output |
|---|---|---|---|
| W2-PM1 | Footprinting | WHOIS, WhatWeb, NSLookup, cURL, WAFW00F, DNSRecon | Domain/web/DNS information |
| W2-PM2 | Search-based Reconnaissance | Search operators / GHDB-style queries | Public academic resources |
| W2-PM5 | Network Scanning | Zenmap / Nmap / ARP | Live hosts and topology |

---

# 6. Overall Skills Demonstrated

Through these modules, the project demonstrated practical understanding of:

1. Passive and publicly observable reconnaissance concepts.
2. Domain and DNS information gathering.
3. Web technology fingerprinting.
4. HTTP header inspection.
5. Search-engine reconnaissance techniques.
6. Network host discovery.
7. IP-to-MAC mapping using ARP information.
8. Graphical network topology analysis with Zenmap.
9. Evidence collection and technical documentation.

---

# 7. Security and Ethical Considerations

All practical activities documented in this final report were performed for educational cybersecurity learning. Network scanning was limited to the local network used for the practical, and the GHDB/search-based exercise was documented using non-sensitive public educational resources.

Reconnaissance and scanning should only be performed against systems and networks where appropriate authorization has been obtained.

---

# 8. Conclusion

The Week 2 project provided hands-on exposure to reconnaissance, OSINT-style information discovery, and network scanning. The combination of Kali Linux tools, search operators, Nmap/Zenmap, and structured evidence collection helped build a practical foundation for further cybersecurity work.

**Status: Week 2 selected modules completed and documented.**
