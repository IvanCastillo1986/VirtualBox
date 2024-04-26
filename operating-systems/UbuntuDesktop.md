# Ubuntu Desktop

This install is for **Ubuntu Desktop**, which gives you a GUI interface and performs as a client.<br>
It is unlike **Ubuntu Server** which only gives you a terminal and thus performs as a server.<br>
It runs the GNOME Shell and GNOME libraries.


## Download Ubuntu Desktop
Download at the following link:<br>
`https://ubuntu.com/download/desktop`

Click on the `Download 22...LTS` button to begin downloading the iso file.


## Install Ubuntu Desktop
**Name**: `Ubuntu-desktop`<br>
**Folder**: **leave as default**<br>
**ISO Image**: `<select downloaded Ubuntu Desktop iso file>`<br>
**Type**: `Linux`<br>
**Version**: `Ubuntu (64-bit)`<br>
Check the `Skip unattended installation` option.<br>
Click  **Next**.

4GB Memory<br>
2 CPU<br>
32GB Virtual Hard Disk

View the **Summary**, then click `Finish`.

Select the created Ubuntu-desktop Virtual machine in the left panel.

### Updates and other software
**What apps would you like to start with?**: `Minimal installation`<br> 
NOTE: this is for a security lab, so you won't need the bells and whistles.
**Other options**: `Download updates while installing Ubuntu`<br>
Click `Continue`.

### Installation type
**This computer currently has no detected operating systems. What would you like to do?**: `Erase disk and install Ubuntu`<br>
Click `Install Now`.

**Write changes to disks?**<br>
`Yes`<br>
Click `Continue`

**Where are you?**<br>
Click `Continue`

_Example input_
Your name: `Ivan`<br>
Your computer's name: `ubuntu-desktop`<br>
Pick a username: `ubuntu-user`<br>
Choose a password: `<choose a strong password>`<br>
Click `Continue`.

Finally, Ubuntu should begin the automatic portion of the installation.<br>
When the installation completes, click `Restart now`

## Update Ubuntu
Run the following commands:<br>
`sudo apt update`<br>
`sudo apt upgrade`


## Configure Ubuntu
SSH connection currently will not function. So let's set it up.

Shut down the machine:<br>
`$  sudo shutdown now`

You'll need to open the port for SSH access.<br>
In the VirtualBox window:<br>
`Ubuntu-desktop`  ->  `Settings`  ->  `Network`  ->  `Advanced`  ->  `Port Forwarding`<br>
Click the green `Add new rule` button on the top right.

**Name**: `SSH`<br>
**Protocol**: `TCP`<br>
**Host Port**: `22`<br>
**Guest Port**: `22`

Spin your Ubuntu Desktop VM back up.<br>
Open your Windows terminal window.

Connect via SSH:<br>
`ssh ubuntu-user@localhost`

Alternately, you can choose to name the localhost's IP. It's 127.0.0.1:
`ssh ubuntu-user@127.0.0.1`

Accept the connection. You know this is the machine you've just created:<br>
**Are you sure you want to continue connecting (yes/no/\[fingerprinting])?** `yes`

You should now be connected via a secure SSH connection.<br>
Congrats!
