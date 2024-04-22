# Kali Linux


## Download Kali
Download from the following link:<br>
`https://www.kali.org/get-kali/#kali-installer-images`<br>
Make sure the  **64-bit**  option has been toggled near the top of the page.<br>
You should see a list of downloads for various hypervisors.<br>
Choose  **VirtualBox**.


## Install Kali
Open  **VirtualBox**.<br>
Select  **New**.<br>

### Virtual machine Name and Operating System
**Name**: `Kali`<br>
**Folder**: **leave as default**<br>
**ISO Image**: `<not selected>`<br>
**Type**: `Linux`<br>
**Version**: `Debian (64-bit)`
NOTE: leave ISO image as default \<not selected>. Otherwise it will crash and produce an error during installation.

Click  **Next**.


You should be safe with the following resource allocations:<br>
4GB RAM<br>
2 cores<br>
32GB hard disk<br>

Click on  **Settings**.

### Settings
**General** tab  ->  **Advanced** tab<br>
**Shared Clipboard**:  `Bidirectional`

This will allow clipboard sharing between your host machine and the virtual machine.

**Display** tab  ->  **Screen** tab<br>
**Video Memory**: 64MB<br>
**Graphics Controller**: VMSVGA<br>
**Extended Features**: Enable 3D Acceleration<br>
This allows the Guest machine (VM) to use the Host machine GPU (Graphics Processing Unit) to render 3D graphics based on OpenGL.

**Storage** tab  ->  **Controller: IDE**<br>  ->  **Empty**  ->  **Attributes**  ->  **Optical Drive**<br>
Click on the CD icon to the right of the  **Optical Drive**.

**Network** tab  ->  **Adapter 1**<br>
**Attached to**: `Bridged Adapter`<br>
This allows the VM to be accessed by other devices in the network, via various methods including SSH. It gives the VM its own IP address.

**Choose a disk file...**, then select the Kali ISO you just downloaded.
Click  **OK**.

Click  **Start**  in the VirtualBox top panel.

An Installation window should pop up, diplaying a menu.<br>
A message will also pop up, verbosely explaining that the mouse and keyboard are bound within the window. To release it, press the  `right ctl`  key **twice** on your Windows keyboard. The Host machine should then regain focus of the mouse and keyboard.

Select  **Graphical Install**.<br>
Press  **Enter**.

Set the system language, country, keyboard setup.

**Configure the network**
Hostname: Kali<br>
Domain name: \<leave empty><br>
Full name for the new user: \<the wizard suggests using your real full name><br>
User name for your account: <Ex: 'kali-user'><br>
Password: \<select strong password>

**Partition disks**<br>
Partitioning method: **Guided - use entire disk**<br>
Select disk to partition: \<there should only be one virtual disk to choose><br>
Partitioning scheme: **All files in one partition**<br>
Overview:  **Finish partitioning and write changes to disk**<br>
Write the changes to disk? **Yes**


**Software selection**<br>
After a few minutes, you'll be able to choose your graphical desktop environment.<br>
Choose software to install: **GNOME**<br>

The desktop installation might take over 10 minutes.

**Install the GRUB boot loader**
Install the GRUB boot loader to your primary drive?  **Yes**<br>
Device for boot loader installation:  **/dev/sda**

Once installation is complete, press  **Continue**  to reboot.<br>
You shouldn't need to remove the installation media (iso file).<br>
VirtualBox will do it automatically for you.

### Login Screen
Click on the user with your name.<br>
Enter the password.

Congrats! You've just installed Kali Linux.


## Configure Kali
Let's install the VirtualBox Guest Edition tools that will enable 3D acceleration, clipboard sharing, and more functionalities.

The Kali interface Home screen should show you some of the applications that are installed right out of the box.<br>
On the left, there should be a terminal icon.<br>
Open terminal.

Update and upgrade Kali:<br>
`$  sudo apt update`<br>
`$  sudo apt upgrade`

Reboot the system:<br>
`$  sudo reboot now`

After signing back in, open the terminal.<br>
Retry the above process to check if there are any new dependencies which haven't been updated.

Now let's install the Linux Kernel Headers:<br>
`$  sudo apt install linux-headers-$(uname -r)`

This will install the  `linux-header`  header files associated with the Linux kernel.<br>
`$(test_input)`  is a command substitution. The Linux shell will treat this the command `uname -r` as the literal output from the command within it.<br>
`uname -r`  outputs the kernel release information.

Linux headers (kernel headers) are source code files that provide the necessary interfaces and definitions required for building and running kernel modules. These headers are specific to the Linux kernel installed on your system. This is what will allow you to apply the settings that you configured for the VM in the VirtualBox panel before installing Kali.

In the VirtualBox menu at top, select:<br>
**Devices**  ->  **Insert guest additions CD image**

Once it's mounted, open the file manager.<br>
Click the CD icon at the bottom of the left sidebar.<br>
Press  `ctl + a`, then  `ctl + c`  to copy all of the files.<br>
Navigate to the  **Documents**  directory, then press  `ctl + v`  to paste the files.

Open the terminal.<br>
Navigate to the  **Documents**  directory.

Use the following command to find a specific file:<br>
`$  ls *run`<br>
This command will list all of the files that end with the characters `run`.

It should output a file named along the lines of  `VBoxLinuxAdditions.run`.<br>
Installing this file will enable all of the aforementioned extra features.

Change the permissions of the file with:<br>
`$  sudo chmod 777 VBoxLiinuxAdditions.run`

Restart Kali one more time:<br>
`$  sudo reboot now`

The guest additions support should now be added to Kali.<br>
You can test it by trying a few functions.
* `ctl + f` should full screen so that the Kali interface itself takes up the full screen, instead of just the VirtualBox window with a smaller Kali window in the center.
* `ctl + c` to copy an item in terminal, then `ctl + v` to paste it into your Host machine's browser window or text file.

Congrats! You've just installed and configured Kali! 🙌


# Troubleshooting
If upon booting Kali, you come across an error that reads:<br>
`end kernel panic - not syncing: No working init foundTry passing init= option to kernel`<br>
...do not fret!<br>
This might be an error caused by not being able to find  `init`  binary while loading.<br>
This can happen early in the boot process, usually from the `initramfs`, which tracks your errors.<br>
Sometimes, the `initramfs` can become corrupted.

Run the following commands:<br>
`sudo update-initramfs -u -k all`<br>
`sudo update-grub`<br>
`sudo shutdown now`

Start your Kali instance back up, and it should start as normal.

If this doesn't work, then there might be something else seriously wrong with the installation.<br>
It might be worth it to install a fresh instance instead of continuing to troubleshoot.