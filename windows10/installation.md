# Windows 10 Installation
Windows 10 machine will act as a workstation in this lab environment setup, used for simulated attacks, OS hardening and testing services run by Ubuntu Server machine.

## Objectives
- Download installation file and create Windows 10 ISO image.
- Setup Windows 10 virtual machine.
- Configure static IP address.

## VM Overview and Configuration
| Sections         | Description       |
|------------------|-------------------|
| Purpose          | Workstation       |
| Base OS          | Windows           |
| Processor        | 3 CPUs            |
| Memory           | 4096 MB           |
| Hard Disk        | 50 GB             |
| Network Adaptor  | NAT               |
| Installed On     | VirtualBox 7.1.4  |
| Hypervisor       | VirtualBox        |
| Name             | Windows10         |

## Installation Process
The Windows 10 installation file can be downloaded from official website: [Download Windows 10](https://www.microsoft.com/en-gb/software-download/windows10). Under 'Create Windows 10 installation media' click on 'download now'. It will start downloading Installation media which gives serveral options.

![Downloading Installation Media](screenshots/windows10-setup_1.png)

The Windows 10 installation media file allows to install Windows 10 directly onto users computer and create ISO, DVD and USB stick copies of Windows 10. For this lab environment choose ISO file and proceed to next steps. The process of creating ISO file is shown below: 

![Creating Windows 10 ISO file](screenshots/windows10-setup_3.png)
![Creating Windows 10 ISO file](screenshots/windows10-setup_4.png)
![Creating Windows 10 ISO file](screenshots/windows10-setup_5.png)

In VirtualBox press Add New VM. Select the file and perform necessary pre installation configurations. Make sure to allocate enough CPUs and Memory because Windows 10 is a recource intensive OS. The configurations for the machine in this lab environment are shown below:

![Pre Installation Configuration](screenshots/windows10-setup_7.png)
![Pre Installation Configuration](screenshots/windows10-setup_8.png)
![Pre Installation Configuration](screenshots/windows10-setup_9.png)

Before starting the VM, navigate to settings -> systems. Go to Acceleration section and for 'Paravirtualisation Interface' choose 'Hyper-V'. The 'Hyper-V' option is great for running Windows operating systems VM. 

![Hyper-V setting](screenshots/windows10-setup_10.png)

When booting up Windows 10 for the frist time, it will go through installation process and then it will reboot and move onto configuration process. Once installation process begins choose prefered language and keyboard settings.

![Upgrade](screenshots/windows10-setup_11.png)

It will prompt for a product key. Press 'I don't have a product key'. Then it will allow to choose which version of Windows 10 to install. Select Windows 10 Pro version and click next. The steps are shown bellow.

![Product key](screenshots/windows10-setup_12.png)
![Version](screenshots/windows10-setup_13.png)

Now it will ask the type of installation to perform, select the 'Custom: Install Windows...'. In the next step it will ask to choose storage space, the space is automatically created by VirtualBox so select the only option that is available. By clicking next it will reboot the system and move to configuration stage. The steps are shown below.

![Custom install](screenshots/windows10-setup_14.png)
![Storage space](screenshots/windows10-setup_15.png)

The configuration stage for Windows 10 is straight forward. When it asks to add an existing account, select 'Offline account' option located in the bottom left corner.

![Add account](screenshots/windows10-setup_18.png)

At the end it will prompt to enter a new Username and Password. Afterwards it will open a login screen and use those credentials to login into the account that has been created.

![Windows view](screenshots/windows10-setup_29.png)

### Configuring static IP address
To configure static IP address on Windows 10, search for 'Control Panel' and open it. Inside it click on 'Network and Sharing Centre'. Then on the left side menu, click on the second option called 'Change adapter settings'. Click on ethernet and it will open configuration window.
Click on properties inside configuration window, this should open a properties window. Inside this window find 'Network Protocol Version 4 (TCP/IPv4), select it, and click properties. Inside it the static IP address can be configured. The steps are shown bellow.

![](screenshots/windows10-setup_30.png)
![](screenshots/windows10-setup_31.png)
![](screenshots/windows10-setup_32.png)
![](screenshots/windows10-setup_33.png)
![](screenshots/windows10-setup_34.png)
![](screenshots/windows10-setup_35.png)

Open command prompt and enter 'ipconfig' command to check if static IP address was set. For IPv4 Address it should display the choosen static IP address. Inside the Windows 10 VM network settings select the Internal Network adaptor to allow the machine to communicate with other VM on the same subnet.

![](screenshots/windows10-setup_36.png)
