# FIREWALL-CONFIGURATION-WITH-UFW-
TASK 4
Firewall Configuration with UFW - Task Report
Introduction
This repository documents the completion of Task 4: Setup and Use a Firewall for Elevate Labs, demonstrating firewall configuration using UFW (Uncomplicated Firewall) on Linux. UFW is a user-friendly interface for managing Linux's built-in netfilter firewall system, providing simplified command-line management while maintaining robust security capabilities.

Objective
Configure and test basic firewall rules to:

Allow SSH access (port 22)

Block Telnet access (port 23)

Test firewall rule effectiveness

Document the configuration process

Tools Used
UFW (Uncomplicated Firewall): Simplified firewall management tool for Linux

Telnet: For testing port connectivity

Terminal: Command-line interface for executing firewall commands

Steps Performed
1. Check Initial Firewall Status
bash
sudo ufw status verbose
Output:

text
Status: inactive
2. Enable UFW & Allow SSH Access
bash
sudo ufw allow 22
sudo ufw enable
Output:

text
Rules updated
Rules updated (v6)
Firewall is active and enabled on system startup
3. Block Telnet Port (23)
bash
sudo ufw deny 23
Output:

text
Rule added
Rule added (v6)
4. Test Telnet Block
bash
telnet localhost 23
Output:

text
Trying ::1 ...
Connection failed: Connection refused
Trying 127.0.0.1...
telnet: Unable to connect to remote host: Connection refused
5. Remove Test Rule
bash
sudo ufw delete deny 23
sudo ufw reload
Output:

text
Rule deleted
Rule deleted (v6)
Firewall reloaded
Firewall Rules Documentation
Command	Description
sudo ufw status verbose	Check firewall status
sudo ufw allow 22	Allow SSH traffic
sudo ufw enable	Activate firewall
sudo ufw deny 23	Block Telnet traffic
telnet localhost 23	Test Telnet block
sudo ufw delete deny 23	Remove Telnet block
sudo ufw reload	Apply configuration changes
How Firewalls Filter Traffic
Firewalls act as network gatekeepers using:

Rules-Based Filtering: Explicit ALLOW/DENY rules based on:

Port numbers

IP addresses

Network protocols

Stateful Inspection: Tracks connection states to:

Allow reply traffic for established sessions

Prevent unsolicited incoming connections

Default Policies:

UFW: DENY all incoming, ALLOW all outgoing

Windows: Allow common services (DHCP, DNS)

Direction Control: Manages both:

Inbound (ingress) traffic

Outbound (egress) traffic

Key Takeaways
Principle of Least Privilege: Firewalls enforce "block everything by default, allow only essential services"

Administrative Access First: Always allow SSH/management ports before enabling firewall

Immediate Testing: Verify rules immediately after implementation

UFW Simplicity: Provides easy yet powerful firewall management through:

Intuitive commands

IPv4/IPv6 dual-stack support

Application profiles

Screenshots
https://screenshot.png
Actual terminal output showing UFW configuration steps

Author
Harsh Gupta
Elevate Labs Intern
Date: 30-06-2025
