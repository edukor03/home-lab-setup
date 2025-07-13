# Windows 10 Setup
## Objectives
In this lab setup the windows 10 will be representing a regular workstation. The objectives that are set for windows 10 setup are listed below:
* Download Windows 10 ISO image.
* Configure VM settings before installation.
* Perform windows insallation and any configurations that are needed.
* Setup static IP address for the lab.
* Check if windows 10 can ping Kali linux.

## VM Overview
|            |            |
|------------|------------|
| OS Name    | Windows 10 |
| Purpose    | Workstation |
| Base OS    | Windows |
| Installed On | VirtualBox 7.1.4 |
| Resources Allocated | 2 CPUs, 4 GB RAM, 50 GB Disk |
| Network Node | Internal Network (LabNet), NAT |

## Installation Process
### File Download
* Source: [Download Windows 10](https://www.microsoft.com/en-gb/software-download/windows10)
* ISO File: Windows10.iso

### Virtual Machine Configuration
* Hypervisor: VirtualBox
* Name: Windows10
* Type: Windows
* Base Memory: 4096 MB
* CPUs: 2
* Network Adaptor: NAT (For updating and installing additional packages) | Internal Network (For LabNet network)
* Hard Disk: 50 GB VDI (dynamically allocated)

### Screenshots
#### 1. Creating ISO file
<img src="screenshots/windows10-setup_1.png" width="400px">
<p>Windows 10 ISO file can be created by downloading installation media from official Microsoft website. The link is provided above.</p>
<img src="screenshots/windows10-setup_2.png" width="400px">
<p>Once the installation media is downloaded. Open it and accept the license terms to start the process.</p>
<img src="screenshots/windows10-setup_3.png" width="400px">
<p>The installation media provides two options:</p>
<ul>
  <li>Upgrade the PC.</li>
  <li>Create ISO, USB flash drive or DVD media.</li>
</ul>
<p>Since we require ISO image, choose the second option and click next.</p>
<img src="screenshots/windows10-setup_4.png" width="400px">
<p>If unsure what options to choose from, click on "use recommended options for this PC". Click next.</p>
<img src="screenshots/windows10-setup_5.png" width="400px">
<p>In this section it allows to choose either to create a USB flash drive, or ISO file. As we are going to use it as a VM, choose ISO file. Press next.</p>

#### 2. Installation and Configuration
<img src="screenshots/windows10-setup_7.png" width="400px">
<img src="screenshots/windows10-setup_8.png" width="400px">
<img src="screenshots/windows10-setup_9.png" width="400px">
<p>Windows 10 system is very resource intensive so allocating more processors and memory can improve performance significantely.</p>
<p>Recommendation is to use at least 2 CPUs and 4 GB of memory. It will lag a little but still will be in working condition.</p>
<p>Also make sure that main system has enough storage since it will take up around 50 GB of your storage.</p>
<img src="screenshots/windows10-setup_10.png" width="400px">
<p>In addition, in the windows 10 VM settings go to system and then for paravirtualization interface use Hyper-V option as it works well with windows OS.</p>
<p>Once all configuration is done in your virtualisation software, the windows 10 VM can be started.</p>
<img src="screenshots/windows10-setup_11.png" width="400px">
<p>The next configurations are quite easy and straightforward. First select the language you want, then press next.</p>
<img src="screenshots/windows10-setup_12.png" width="400px">
<p>Since we don't have a product key, we need to click on "I don't have a product key" option at the bottom.</p>
<img src="screenshots/windows10-setup_13.png" width="400px">
<p>In here you can choose any windows version you want. For my lab I will be choosing Windows 10 Pro.</p>
<img src="screenshots/windows10-setup_14.png" width="400px">
<p>On these step, choose custom install.</p>
<img src="screenshots/windows10-setup_15.png" width="400px">
<p>Select the drive that was created by our virtualisation software and click next.</p>
<p>After this step it should restart the windows 10 VM and open another configuration menu which is used to customise the experience of the windwos.</p>
<img src="screenshots/windows10-setup_16.png" width="400px">
<p>Once the system is restarted, the following configurations are based on your liking.</p>
<img src="screenshots/windows10-setup_18.png" width="400px">
<p>Choose offline account, unless you want to connect your microsoft account.</p>
<img src="screenshots/windows10-setup_19.png" width="400px">
<p>Click on limited experience since we don't want to create a new account.</p>
<p>Then next steps will require to enter a new username and password.</p>
<p>After that its just personalisation configurations, so there is no need for guidance.</p>
<img src="screenshots/windows10-setup_29.png" width="400px">
<p>When the configuration is done, it will prompt you to log into the created user. If you can see desktop screen when you have done everything correctly.</p>

#### 3. Static IP Address
<img src="screenshots/windows10-setup_30.png" width="400px">
<p>To change static IP address, firstly navigate to control panel.</p>
<img src="screenshots/windows10-setup_31.png" width="400px">
<p>Inside the control panel navigate to Network and Internet. Then navigate to Network and Sharing Centre.</p>
<img src="screenshots/windows10-setup_32.png" width="400px">
<p>Inside the Network and Sharing, click on the change adapter settings on the side menu.</p>
<img src="screenshots/windows10-setup_33.png" width="400px">
<img src="screenshots/windows10-setup_34.png" width="400px">
<p>Click on the ethernet option. It will open the window called Ethernet Status. Inside this window click on properties.</p>
<p>Another window will be opened. Inside Ethernet properties window select Internet Protocol Version 4 (TCP/IPv4) and then click properties.</p>
<img src="screenshots/windows10-setup_35.png" width="400px">
<p>Another window will pop up. Inside this window change settings to "use the following IP address" and eneter your IP address you use for Lab.</p>
<p>Then click on OK and close all other windows since we don't need it anymore.</p>
<img src="screenshots/windows10-setup_36.png" width="400px">
<p>Windows has a similar command to "ifconfig", its called "ipconfig". It basically performs similar function.</p>
<p>In windows terminal type "ipconfig" and run the command.</p>
<p>This should display information about current IP address, if it shows the address you setup then change was successful.</p>

#### 4. Test Connection
<img src="screenshots/windows10-setup_37.png" width="400px">
<img src="screenshots/windows10-setup_38.png" width="400px">
<p>Last time I created a Kali Linux VM, and now I will run both VMs and try to ping one another.</p>
<p>Both Windows and Linux use ping command. In windows you can use windows terminal to do so.</p>
<p>If both machines can ping each other then the network setup is correctly done.</p>
<p>In this case both machines can successfuly ping each other.</p>




