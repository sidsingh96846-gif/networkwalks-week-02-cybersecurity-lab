# W2-PM5 — Zenmap Based Network Scanning

## Objective
Perform network discovery on the local Wi-Fi subnet using Zenmap/Nmap and document the discovered live hosts, IP addresses, MAC addresses, and topology.

## Environment
- Tool: Zenmap (Nmap 7.99)
- Scan type: Ping Scan
- Local IPv4: `10.208.175.92`
- Subnet mask: `255.255.255.0`
- Scan target: `10.208.175.0/24`

## Scan Command
```bash
nmap -sn 10.208.175.0/24
```

## Results
The Zenmap ping scan scanned 256 IP addresses and identified **2 hosts up**:

| No. | IP Address | Status |
|---:|---|---|
| 1 | `10.208.175.103` | Up |
| 2 | `10.208.175.215` | Up |

## MAC Address Mapping
MAC mappings observed from the local ARP table:

| IP Address | MAC Address |
|---|---|
| `10.208.175.103` | `c6-4c-2f-29-e1-f7` |
| `10.208.175.215` | `0e-ea-b8-d5-83-cf` |

## Topology
Zenmap Topology view displayed the local host together with the two discovered hosts:
- `localhost`
- `10.208.175.103`
- `10.208.175.215`

## Evidence
The following evidence files are included in this folder:

1. `ipconfig.png` — local IP address and subnet configuration
2. `zenmap-ping-scan.png` — Zenmap/Nmap ping scan results
3. `zenmap-topology.png` — Zenmap topology visualization

## Key Learnings
- `ipconfig` can be used to identify the local IPv4 address and subnet mask.
- A `/24` subnet contains 256 IPv4 addresses.
- `nmap -sn` performs host discovery without a conventional port scan.
- ARP can provide IP-to-MAC mappings for devices visible on the local network.
- Zenmap provides graphical views of Nmap scan results, including topology.

## Safety Note
Scanning was limited to the user's local Wi-Fi subnet identified from the host configuration.
