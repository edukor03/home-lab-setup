# Kali Linux Setup
## Objectives
Setting up Kali Linux VM is a part of setting a cyber security lab. It will be used to simulate an attacker/offensive security. In this document it will show the process of installing Kali Linux VM and how to boot it up. In addition, at the end of the document it will show how to configure static IP address.
* Download Kali Linux VM file
* Configure VM before installing and booting up the Kali Linux
* Update the systems packages using update & upgrade
* Configure lab network (static IP address)

## VM Overview
|            |            |
|------------|------------|
| OS Name    | Kali Linux 2025.02 |
| Purpose    | Attacker/Offensive Security |
| Base OS    | Debian-based Linux |
| Installed On | VirtualBox 7.1.4 |
| Resources Allocated | 2 CPUs, 2 GB RAM, 30 GB Disk |
| Network Node | Internal Network (LabNet), NAT |

## Installation Process
### File Download
* Source: [Download Kali Linux](https://www.kali.org/get-kali/#kali-virtual-machines)
* VIM File: kali-linux-2025.2-virtualbox-amd64.vim

### Virtual Machine Configuration
* Hypervisor: VirtualBox
* Name: Kali_Linux_2025.2
* Type: Linux -> Debian (64-bit)
* Base Memory: 2048 MB
* CPUs: 2
* Network Adaptor: NAT (For updating and installing additional packages) | Internal Network (For LabNet network)
* Hard Disk: 30 GB VDI (dynamically allocated)

### Screenshots
...
