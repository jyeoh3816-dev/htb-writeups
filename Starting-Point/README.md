# Hack The Box Starting Point

## Machine Information
- Machine name: Meow
- Difficulty: Very Easy
- Date completed: 2026-10-20
- Machine status: Started
- Target IP: 10.129.96.175

## Objective
Describe what this lab teaches.

## Enumeration
Connectivity Test

Tool: ping

Purpose: Check whether the target machine responds over the network.

Command: ping -c 4 10.129.96.175

Result: Received replies from the Meow target.

Learning point: The AttackBox can communicate with the target over the network.
Nmap Service Scan

Tool: Nmap 7.95

Command: nmap -sV 10.129.96.175

Host status: Up

Open port: TCP 23

Service: Telnet

Service version: Linux telnetd

Other scanned ports: 999 closed TCP ports

Finding: Telnet is exposed on the target machine.

Security relevance: Telnet does not encrypt session traffic, so credentials and other transmitted data may be exposed.

Learning point: Port scanning helps identify exposed services and potential security risks.

### Nmap Results

| Port | Protocol | State | Service | Version |
|---|---|---|---|---|
| 23 | TCP | Open | Telnet | Linux telnetd |

**Scan summary**
- **Tool:** Nmap 7.95
- **Scan option:** `-sV`
- **Result:** One open TCP port was identified among the 1,000 default scanned ports.
- **Security observation:** Telnet does not encrypt session traffic, unlike SSH.

**Analysis**

The scan identified Telnet as an exposed remote-access service. This finding helped guide further investigation during the authorised lab. An open port alone does not establish a vulnerability; the security impact depends on the service configuration and authentication controls.



## Findings
Access and Flag Retrieval

Initial access: Telnet on TCP port 23

User account: root

Privilege level: Root

Flag location: /root/flag.txt

Flag submission: Accepted by Hack The Box

Key learning: Enumeration helps identify exposed services. Telnet provides remote terminal access but does not encrypt session traffic.

Reflection: I practised Nmap service detection, Telnet connectivity, Linux navigation, and documenting findings in Markdown.

## Lessons Learned
Use Nmap to identify open ports and running services.

Understand the security risks of unencrypted protocols such as Telnet.

Practise Linux commands such as whoami, cd, ls, and cat.

Record findings clearly and never publish flags, credentials, or other restricted information.

## Methodology

### 1. Connectivity Verification
Used `ping` to check whether the assigned target responded over the network.

### 2. Service Enumeration
Used Nmap with service-version detection (`-sV`) to identify exposed TCP services.

### 3. Service Investigation
Investigated the Telnet service identified on TCP port 23, following the authorised HTB lab instructions.

### 4. Linux Exploration
Used basic Linux commands to identify the current account, navigate directories, and inspect the target file.

### 5. Objective Verification
Retrieved the lab flag and confirmed that Hack The Box accepted the submission.

## Security Takeaways

- Exposed services should be reviewed and secured appropriately.
- Telnet does not encrypt communication, so secure alternatives such as SSH are generally preferred.
- Access control and authentication are essential for protecting privileged accounts.
- Clear documentation makes technical findings easier to review and reproduce.

## Ethical Considerations

All testing was performed against the assigned Hack The Box lab machine. The techniques documented here are intended for authorised security testing and education.
