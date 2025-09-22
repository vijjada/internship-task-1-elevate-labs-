# internship-task-1-elevate-labs-
objective : Learn to discover open ports on devices in your local network to understand network exposure.
# Local Network Port Scanning Report

## Overview
This project documents the process and findings of a network reconnaissance exercise to identify open, filtered, and closed TCP ports of devices in a local subnet (192.168.12.0/24). The purpose is to assess potential security risks and network exposure.

## Tools Used
- **Nmap**: For scanning network hosts and enumerating port status.
- **Wireshark** (optional): Used optionally for capturing and analyzing packets (not used in this task).

## Methodology
1. Identified the local subnet IP range.
2. Conducted a TCP SYN scan for top 100 ports on the subnet with:
nmap -sS -Pn --top-ports 100 -T4 192.168.12.0/24 -oN nmap_quick_192.168.12.0-24.txt
3. Collected results in standard output and screenshots.
4. Analyzed port states and services across discovered hosts for security insights.

## Scan Results Summary

| Host           | Vendor                     | Open Ports                  | Filtered Ports                                                                 | Closed Ports                          |
|----------------|----------------------------|-----------------------------|--------------------------------------------------------------------------------|-------------------------------------|
| 192.168.12.139 | Apple                      | None                        | Ports such as 26(rsftp), 81(hosts2-ns), 144(news), 465(smtps), 5432(postgresql) | N/A                                 |
| 192.168.12.1   | Hewlett Packard Enterprise | 22 (SSH), 23 (Telnet), 80 (HTTP) | N/A                                                                            | N/A                                 |
| 192.168.12.52  | Unknown                    | None                        | N/A                                                                            | Common ports like SSH, Telnet, SMTP, HTTP, HTTPS, MySQL, etc. |

## Security Observations
- Hosts with filtered or closed ports show effective firewall and security configurations.
- Open legacy ports like Telnet present security risks and should preferably be disabled.
- Open web and remote access ports require continuous monitoring and strong authentication controls.

## Recommendations
- Disable unnecessary or legacy services such as Telnet.
- Regularly scan network ports to monitor unexpected exposure.
- Harden firewall rules to maintain robust network security posture.

## Author
Vijjada Prem Sai  
BTech CSE (Cybersecurity), GD Goenka University

---

This README provides a clear summary of the approach, results, and recommendations for the network port scanning project.



