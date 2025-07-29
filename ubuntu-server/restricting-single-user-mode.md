# Single User Mode
Single user mode, also known as recovery mode, is a boot option that allows operating system (OS) to start with a single superuser account, bypassing multiuser access.
On Ubuntu Server recovery mode does not require a password by defult. This poses a security risk as an attacker with physical or virtual access to the system can modify a kernel line in GRUB boot menu to boot in a recovery mode. Once inside recovery mode, user can perform password resets, modifying configurations and troubleshooting system issues.

## Changing Root Password Through Recovery Mode
It is possible to change a Root password inside Recovery Mode due to forgetting root password or trying to gain access to the root user. Intentions can be both legitimate and malicious. The following example is only for educational purpose only.

To enter into GRUB boot menu, press 'ESC' or 'F12' keys as soon as machine starts booting up. Once the GRUB boot menu is visible, select the first option and press 'E' to modify GRUB boot parameters. Go to line that starts with 'linux' at the end add the following parameter:
> systemd.unit=rescue.target

To make sure when booting into recovery mode there are not errors, enter the following parameter after systemd:
> nomodeset

Once its done press 'Ctrl+X' or 'F10' to boot with this parameters. Example is shown below:

![GRUB boot parameters]()

First, remount the root directory to read and write mode which allows to change root users password. Enter the following command:
> mount -o remount,rw /

The 'mount' is a Linux command that allows to attach file systems to directory tree. Allowing access to external storage devices like USB drives and Hard Drive. The parameter '-o' stands for options allowing to set additional options to mount. In this case, remount option is used to change options for a file system without unmounting it first. Another option 'rw' defines that the directory needs to me remounted to read and write mode which is root directory '/'

To change the password, enter the following command:
> passwd

To boot into a default mode enter:
> exec /sbin/init

![Changing Root Password]()

Now try logging into a root user. It will require to enter a newly created password. This way if single user mode is not protected it can allow a hackers to gain access to the system, also it can be used to recover the account after forgeting the password.

## Securing Single User Mode
Securing a recovery mode is not complicated, however if not careful it can lock you out from the system. First step is to encrypt the password using the following command:
> grub-mkpasswd-pbkdf2

![Encrypting Password]()

After entering a desired password, it will output a code which needs to be saved somewhere or copied for the next step.
Navigate to '/etc/grub.d' directory and modify 40_custom file, using editors like nano or vim (it requires escalated privilages, use sudo command). Enter the following parameters:
> set superusers="Admin"

> password_pbkdf2 Admin grub.pbkdf2.sha512.1....

An example of the complete file is shown below:

![Setting a Password]()

To update the changes for grub, enter the following command:
> sudo update-grub

Everytime user tries to access GRUB boot menu, it will prompt to enter username and password before allowing access to it.
