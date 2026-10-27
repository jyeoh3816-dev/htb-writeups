# Hack The Box — Meow Writeup

## 1. Machine Information

| Information | Details |
|---|---|
| Machine Name | Meow |
| Platform | Hack The Box |
| Category | Starting Point |
| Difficulty | Very Easy |
| Operating System | Linux |
| Target IP | 10.129.96.175 |
| Primary Protocol | Telnet |
| Open Port | 23/TCP |
| Completion Date | 20 October 2026 |
| Status | Completed |

## 2. Introduction

On 20 October 2026, I successfully completed Meow, my first Hack The Box Starting Point machine.

As a Year 2 student pursuing a 3-Year Higher Nitec in Cyber & Network Security at ITE College West, I undertook this challenge to strengthen my practical knowledge of Linux, network enumeration, and remote-access security.

This writeup documents my methodology, commands, observations, findings, and key learning outcomes.

## 3. Learning Objectives

The objectives of this exercise were to:

- Verify network connectivity to the target machine.
- Identify open ports and running services using Nmap.
- Understand the functionality and security risks of Telnet.
- Practise basic Linux command-line operations.
- Understand Linux user privileges.
- Develop professional technical documentation skills.

## 4. Network Connectivity Testing

Before conducting network enumeration, I verified that the target machine was reachable from my Hack The Box AttackBox.

### Command Executed

```bash
ping -c 4 10.129.96.175
```

### Observed Results

The target responded successfully to the ICMP echo requests.

This confirmed that the target machine was reachable from the AttackBox.

### Key Learning Point

Network connectivity testing helps verify that communication with a target is possible before beginning service enumeration.

However, a machine that does not respond to ICMP may still have accessible network services.

## 5. Network Enumeration

After confirming connectivity, I performed an Nmap scan to identify open ports and running services.

### Command Executed

```bash
nmap -sV 10.129.96.175
```

### Command Explanation

- `nmap`: Performs network discovery and port scanning.
- `-sV`: Attempts to identify the services and versions running on open ports.
- `10.129.96.175`: The target IP address assigned by Hack The Box.

### Nmap Findings

| Port | State | Service | Version |
|---|---|---|---|
| 23/tcp | Open | Telnet | Linux telnetd |

The scan also reported that the remaining 999 default-scanned TCP ports were closed.

### Analysis

The scan revealed that TCP port 23 was open and running a Telnet service.

Telnet is a remote-access protocol that allows users to interact with another computer through a command-line interface.

Unlike SSH, traditional Telnet does not encrypt communication.

This presents security risks when the protocol is used across untrusted networks.

### Key Learning Point

Network enumeration is an important early stage of penetration testing because it helps identify exposed services and potential security weaknesses.

## 6. Telnet Investigation

After identifying the Telnet service, I investigated the remote-access functionality within the authorised HTB environment.

### Command Executed

```bash
telnet 10.129.96.175 23
```

### Command Explanation

- `telnet`: Launches the Telnet client.
- `10.129.96.175`: Specifies the target machine.
- `23`: Specifies the Telnet service port.

### Observed Results

I successfully established a Telnet connection to the target machine and accessed the Linux environment using the lab's intended authentication configuration.

After establishing the session, I verified the account's privileges.

### Command Executed

```bash
whoami
```

### Observed Output

```text
root
```

### Analysis

The output confirmed that the session was operating as the Linux root user.

The root account has extensive administrative privileges over the operating system.

This demonstrated the importance of controlling remote administrative access and ensuring that users receive only the permissions necessary for their responsibilities.

## 7. Flag Discovery and Machine Completion

After establishing remote access, I continued investigating the Linux environment.

During the exercise, I located the designated Hack The Box flag file in the root user's directory.

### File Location

```text
/root/flag.txt
```

### Command Executed

```bash
cat /root/flag.txt
```

### Command Explanation

The `cat` command displays the contents of a file in the terminal.

I used it to retrieve the designated lab flag and subsequently submitted the flag through the Hack The Box platform.

### Result

**Machine completed successfully.**

The flag value and authentication details have been intentionally omitted from this public writeup.

## 8. Security Analysis

### 8.1 Insecure Remote-Access Protocol

The target exposed a Telnet service on TCP port 23.

Traditional Telnet does not encrypt transmitted data, creating confidentiality risks on untrusted networks.

### 8.2 Authentication Security

The lab demonstrated how insecure remote-access configurations can create opportunities for unauthorised system access.

Secure authentication controls are essential for protecting administrative interfaces.

### 8.3 Excessive User Privileges

The `whoami` command confirmed that the remote session was operating with root privileges.

Administrative privileges should be carefully controlled because excessive permissions increase the potential impact of a security compromise.

### 8.4 Exposed Network Services

Open network ports provide access to running services.

Organisations should ensure that externally accessible services are necessary, securely configured, and regularly reviewed.

## 9. Security Recommendations

Based on the concepts demonstrated during this exercise, I identified several security improvements.

**1. Replace Telnet with SSH**

Use encrypted remote-access protocols to protect communications and authentication information.

**2. Strengthen Authentication**

Implement secure authentication methods and restrict access to authorised users.

**3. Apply the Principle of Least Privilege**

Limit administrative access and avoid unnecessary use of highly privileged accounts.

**4. Reduce the Attack Surface**

Disable unused network services and restrict access to administrative ports.

**5. Implement Security Monitoring**

Maintain appropriate logging and review remote-access activity for suspicious behaviour.

## 10. Key Learning Outcomes

Completing Meow strengthened my understanding of the following technical concepts:

| Skill | Practical Experience |
|---|---|
| Network Connectivity | Tested target reachability using Ping |
| Network Enumeration | Identified an open port using Nmap |
| Service Identification | Identified Linux telnetd on TCP port 23 |
| Network Protocols | Investigated Telnet functionality and security risks |
| Linux Fundamentals | Used Linux terminal commands |
| User Privileges | Verified root access using `whoami` |
| File Operations | Retrieved the designated lab file using `cat` |
| Technical Documentation | Recorded commands, findings, analysis, and recommendations |

## 11. Personal Reflection

Completing Meow on 20 October 2026 was an important milestone in my cybersecurity learning journey.

Although Meow is classified as Very Easy, the challenge allowed me to apply theoretical networking concepts in a practical environment.

One of my biggest takeaways was understanding how an exposed remote-access service and insecure configurations can affect system security.

I also learned the importance of following a structured methodology, beginning with connectivity testing, followed by enumeration, service investigation, and documentation.

This experience strengthened my interest in penetration testing and motivated me to continue developing my Linux, networking, and cybersecurity skills through more challenging Hack The Box machines.

## 12. Conclusion

The Meow machine provided valuable introductory experience in network enumeration, Telnet, Linux command-line operations, and basic security analysis.

Through this exercise, I successfully identified an exposed network service, established authorised remote access, examined user privileges, and completed the designated Hack The Box challenge.

Moving forward, I aim to strengthen my technical foundations and develop the analytical and documentation skills required for a future career in penetration testing and offensive security.

## Disclaimer

All activities described in this writeup were performed within the authorised Hack The Box training environment for educational purposes.

No unauthorised systems were targeted. Flags and authentication credentials have been omitted.
