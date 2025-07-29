# Ubuntu Server Overview
This folder documents the setup and configuration of the Ubuntu Server virtual machine. It plays the role of internal infrastructure host in the cybersecurity lab environment.

## Contents
- 'installation.md': Contains the steps for installation and configuring the base system.
- 'restricting-single-user-mode.md': Documents the use and how to secure single user mode.
- 'securing-ssh': Configuring SSH
  - Password policies, change SSH default port, allow certain IP addresses 

## Summary of Security Measures
The hardening process includes:
- Restricting single user mode access
- Securing SSH connection
  - Disabling root login over SSH
  - Enforcing strong password policies
- Installing and configuring Fail2ban intrusion prevention tool.
- Closing or disabling unused network ports
- Disabling IPv6 to reduce unnecessary exposure
- Disabling auto mounting of external devices

## Purpose in Lab
This system represents a target host in the lab environment, providing services that other machines can scan, exploit, or interact with during simulated scenarios.

> [!Note]
> Ths directory is a work in progress and will be updated with additional lab activities and configurations as they are developed.
