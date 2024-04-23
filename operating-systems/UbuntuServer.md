# Ubuntu


## Download Ubuntu Server
Download at the following link:<br>
`https://ubuntu.com/download/server`

Click on the `Download 22...LTS` button to begin downloading the iso file.


## Install Ubuntu Server
**Name**: `Ubuntu-server`<br>
**Folder**: **leave as default**<br>
**ISO Image**: `<select downloaded Ubuntu iso file>`<br>
**Type**: `Linux`<br>
**Version**: `Ubuntu (64-bit)`<br>
Check the `Skip unattended installation` option.<br>
Click  **Next**.

1.5GB RAM<br>
1 core<br>
10GB Storage

View the **Summary**, then click `Finish`.

**Language Configuration**: use arrow keys to select language. Highlight `Done`. Press `Enter`.<br>
**Keyboard Configuration**: use arrow keys to select keyboard configuration. Highlight `Done`. Press `Enter`.<br>
**Choose type of install**: use arrow keys to select `Ubuntu Server (minimized)`. Highlight `Done`. Press `Enter`.<br>
**Network Connections**: leave Network Connection as default. This will be your private IP address. Highlight `Done`. Press `Enter`.<br>
**Configure Proxy**: press `Enter` to configure Ubuntu archive mirror. When it's finished, press `Enter`.<br>
NOTE:  the Ubuntu Archive is a collection of software packages that are maintained and distributed by Canonical (which also created Ubuntu) for Ubuntu Linux distribution. If you don't select a mirror and just press `Enter`, the installer will automatically set a default mirror which should be the closest to your geographical location.<br>
**Guided Storage Configuration**: use arrow keys to make sure that `Use an entire hard disk` and `Set up this disk as an LVM group` is selected. Highlight `Done`. Press `Enter`.<br>
**Storage Configuration**: you can choose to review the installation configurations here. Highlight `Done`. Press `Enter`.<br>
**Confirm destructive action**: use arrow keys to highlight `Continue`. Press `Enter`.<br>
NOTE:  this is a fresh virtual hard disk that you've just created, so you don't have to worry about 


### Profile setup
**Your name**: `<your name. Ex: ivan>`<br>
**Your servers name**: `<server name. Ex: ubuntu-server>`<br>
**Pick a username**: `<username. Ex: ubuntu-user>`<br>
**Password**: `<choose a strong password! Ex: deliCaCies-27!>`

**Upgrade to Ubuntu Pro**: skip for now. Press `Enter`.

**SSH Setup**: use arrow keys to highlight `Done`. Press `Enter`. You can do this later.<br>
**Featured Server Snaps**: press `Tab` to highlight `Done`. Press `Enter`.

Finally, Ubuntu should begin the automatic portion of the installation.<br>
After it's finished, you can choose to view the logs. But do not reboot.

When prompted with `remove the installation media and press Enter`, you can just press enter.<br>
VirtualBox will do this automatically when you reboot.

After a wall of text for a few seconds, text will stop printing.<br>
If you just hit the down key, you should see the login prompt.<br>
Enter the username and password that you set during installation.


## Update Ubuntu
Run the following commands:<br>
`sudo apt update`<br>
`sudo apt upgrade`


## Configure Ubuntu
SSH connection currently will not function. So let's set it up.

Shut down the machine:<br>
`$  sudo shutdown now`

In the VirtualBox window:<br>
`Ubuntu-server`  ->  `Settings`  ->  `Network`  ->  `Advanced`  ->  `Port Forwarding`<br>
Click the green `Add new rule` button on the top right.

**Protocol**: `TCP`<br>
**Host Port**: `22`<br>
**Guest Port**: `22`

Spin your Ubuntu Server VM back up.<br>
Open your Windows terminal window.

Connect via SSH:<br>
`ssh ubuntu-user-3@localhost`

Accept the connection. You know this is the machine you've just created:<br>
**Are you sure you want to continue connecting (yes/no/\[fingerprinting])?** `yes`

You should now be connected via a secure SSH connection.<br>
Congrats!