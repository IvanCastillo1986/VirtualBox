# VirtualBox


## Shortcuts
Note: Host key is right ctl by default

Host key + f  -  full screen mode<br>
ctrl + alt + F2  -  switch to terminal login (handy if a VM's graphical interface is stuck)<br>



## Download VirtualBox
Download from the following link:<br>
`https://www.virtualbox.org/wiki/Downloads`

## Install VirtualBox
Open the downloaded .exe file.<br>
The installer will open.<br>
Accept the default configurations.
Open VirtualBox.

## Create Virtual Machine in VirtualBox
To create a new Virtual Machine, click on the  **'New'**  button in the top bar.

## Unattended Guest OS Install Setup
VirtualBox allows for an automatic install.

**Username and Password**<br>
These are the default credentials:
**Username**: `vboxuser`<br>
**Password**: `changeme`<br>

These need to be changed!<br>
Otherwise the default credentials will create a user without sudo access!
**Username**: `vboxuser`<br>
**Password**: `changeme`<br>

**Guest Additions**: `check`<br>
This will install the `VBoxGuestAdditions.iso` file included with VirtualBox by default.

Select your resource allocation.

The Unattended Installation should begin doing its thing automatically.

