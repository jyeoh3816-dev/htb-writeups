# Hack The Box Starting Point

## Machine Information
- Machine name: Meow
- Difficulty: Very Easy
- Date completed: In progress
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



## Findings
Summarise your observations and learning points.

## Lessons Learned
Write down what you learned from this lab.
