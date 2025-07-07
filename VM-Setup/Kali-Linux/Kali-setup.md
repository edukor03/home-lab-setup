# ⚔️ Kali Linux Setup (Cybersecurity Lab)

This document outlines the installation, configuration, and tools used on the Kali Linux virtual machine acting as the primary **attacker node** in the cybersecurity lab environment.

---

## 🔹 Overview

| Setting            | Value                    |
|--------------------|--------------------------|
| Hostname           | kali-attacker            |
| IP Address         | 192.168.56.10            |
| OS Version         | Kali Linux 2024.2 (64-bit) |
| Role               | Offensive security / attacker box |
| Network Type       | Host-only (vboxnet0)     |

---

## 🔧 Installation Summary

### ISO Download:
- [https://www.kali.org/get-kali/#kali-virtual-machines](https://www.kali.org/get-kali/#kali-virtual-machines)

### VM Configuration:
| Resource   | Value                    |
|------------|--------------------------|
| RAM        | 2–4 GB                   |
| CPUs       | 2                        |
| Disk       | 40 GB (dynamically allocated) |
| Network    | Host-only Adapter (Static IP) |

---

## ⚙️ Static IP Configuration

A new ethernet connection has been created. The method is set from dhcp to manual to have a static IP address. IP address for this machine is 192.168.56.10. 
