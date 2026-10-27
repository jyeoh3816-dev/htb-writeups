# Hack The Box — Fawn Writeup

## 1. Machine Information

| Information | Details |
|---|---|
| Machine Name | Fawn |
| Platform | Hack The Box |
| Category | Starting Point |
| Difficulty | Very Easy |
| Operating System | Linux |
| Primary Protocol | FTP |
| Port Associated with FTP | TCP 21 |
| Status | In Progress |

## 2. Introduction

Fawn is a beginner-friendly Hack The Box Starting Point machine designed to introduce fundamental networking concepts, FTP (File Transfer Protocol), and common security risks associated with insecure file-transfer configurations.

The objective of this lab is to strengthen my understanding of network enumeration, service identification, and FTP security through practical experience in an authorised cybersecurity training environment.

## 3. Learning Objectives

- Practise basic network connectivity testing.
- Identify open ports and running services using Nmap.
- Understand how FTP operates.
- Investigate FTP authentication and access controls.
- Recognise the security implications of insecure FTP configurations.
- Develop technical documentation skills.

## 4. Network Connectivity Testing

Before conducting network enumeration, I verified connectivity between the Hack The Box AttackBox and the assigned target machine.

**Command used:**

```bash
ping -c 4 <TARGET_IP>
```

**Observed results:**

- Four ICMP echo requests were sent.
- Four replies were received.
- The target was reachable from the AttackBox.

**Key learning point:**

Connectivity testing helps establish whether a target can be reached before proceeding with further network investigation.

## 5. Network Enumeration

The next stage involves identifying accessible network services.

**Command:**

```bash
nmap -sV <TARGET_IP>
```

**Purpose:**

Nmap is a network scanning tool used to identify open ports and services. The `-sV` option attempts to determine the service and version running on each detected open port.

**My scan findings:**

_To be completed after reviewing the actual Nmap results._

| Port | State | Service | Version |
|---|---|---|---|
| Pending | Pending | Pending | Pending |

## 6. FTP Investigation

FTP is a network protocol used to transfer files between computers.

During this stage, I will investigate the FTP service identified during enumeration and document my observations.

**Topics to investigate:**

- FTP connectivity
- Authentication requirements
- Anonymous access configuration
- Directory listings
- File permissions

**My findings:**

_To be completed after the FTP investigation._

## 7. Security Analysis

FTP presents several potential security concerns depending on its configuration.

These include:

- Transmission of credentials and data without encryption when using traditional FTP.
- Anonymous access that may expose files if improperly configured.
- Excessive file permissions.
- Inadequate access controls.

The actual security findings for Fawn will be documented after completing the lab.

## 8. Security Recommendations

Recommended security measures include:

1. Use encrypted file-transfer protocols such as SFTP or FTPS where appropriate.
2. Disable anonymous FTP access unless specifically required and securely configured.
3. Apply least-privilege access controls.
4. Restrict access to authorised users and networks.
5. Maintain appropriate logging and monitoring.

## 9. Key Learning Outcomes

Through this exercise, I aim to improve my understanding of:

- Network connectivity testing
- Nmap enumeration
- FTP and TCP/IP fundamentals
- Linux networking concepts
- Security misconfigurations
- Technical documentation

## 10. Conclusion

Fawn provides an opportunity to develop practical knowledge of FTP and fundamental network security concepts.

By documenting my methodology, observations, and lessons learned, I aim to strengthen both my technical capabilities and my ability to communicate cybersecurity findings professionally.

This writeup will be updated as I progress through the machine.

## Disclaimer

All activities described in this writeup are conducted within the authorised Hack The Box training environment for educational purposes.
