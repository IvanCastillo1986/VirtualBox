# Windows 10


## Download Windows 10
Download from the following link:<br>
`https://www.microsoft.com/en-us/software-download/windows10ISO`

**Create Windows 10 installation media**  ->  click `Download Now`

This should download the `MediaCreationTool_22H2.exe` file.<br>
This is a tool provided by Microsoft which will assist you with creating installation media for Windows 10.
It creates the ISO file, which you can then use to install the Windows 10 Virtual Machine on VirtualBox.<br>
Open the file.<br>
You can allow this app to make changes, since you know you can trust something you’ve just downloaded from Microsoft.

Go through the creation process.<br>
**Accept the license terms**

What do you want to do?<br>
**Create installation media (USB flash drive, DVD, or ISO file) for another PC**

Select language, architecture, and edition<br>
Language:  \<your language><br>
Edition:  **Windows 10**<br>
Architecture:  **64-bit (x64)**<br>
click `Next`

Choose which media to use<br>
**ISO file**

Name your file.
Ex:  Windows10-image

After the creation process completes, click `Finish`.<br>
You should now have a fresh ISO to install Windows 10 on your Virtual Machine.<br>
The default directory for the creation on a Windows 11 host machine should be:<br>
`Home`  ->  `Documents`


## Install Windows 10
Open VirtualBox.<br>
New  ->  Create Virtual Machine<br>
Name:  windows10-vm<br>
Machine Folder:  directory housing the vm files<br>
Edition:  ___ (autofilled)<br>
Type:  Microsoft Windows (autofilled)<br>
Version:  Windows 10  (64-bit) (autofilled)<br>

Ignore the Unattended Guest OS Install Setup. You won’t be using this.

You should be safe with the following resource allocations:<br>
4GB RAM<br>
2 cores<br>
25GB hard disk<br>

Open Settings before starting Windows iso.<br>
Storage  ->  remove **'Unattended Guest'** floppy disk  ->  Controller: SATA - SATA Port 1  -  `Windows10-image.iso`  ->  **OK**  ->  **Start**

The Windows Setup screen will initialize.

Continue through most of the default settings.<br>
Click on **'I don’t have a product key'**<br>
Choose your preferred version of Windows 10  (for first example, I chose Windows 10 Pro)<br>
Check **'I accept the license terms'**

Which type of installation do you want?<br>
Custom:  **Install Windows only (advanced)**

Where do you want to install Windows?<br>
**Drive 0 Unallocated Space**  ->  **Next**

The installation will begin. The time varies depending on your host machine’s specs. I believe mine takes a rough estimate of 8 minutes.

Choose your Region.<br>
**Skip the second keyboard layout**

How would you like to set up?<br>
**Set up for personal use**

Let’s add your account<br>
**Offline account**

Sign in to enjoy the full range of Microsoft apps and services.<br>
**Limited experience**

Who’s going to use this PC?<br>
\<Your name>  ->  **Next**

Choose and confirm password.<br>
Select security questions<br>
(Choose different security questions from your host machine. Remember that this is a VM which you’ll be using for security purposes, and that if it’s compromised, you don’t want to also give access to your host machine’s official credentials. Write down the responses somewhere so you don’t forget)

For the rest of the options click **‘Skip’** or **‘Next’**.<br>
Wait for the rest of the configurations to complete.

Congrats! You’ve just installed a Windows virtual machine.
