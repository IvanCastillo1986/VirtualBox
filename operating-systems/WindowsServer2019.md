# Windows Server 2019


## Download Windows Server 2019
Download from the following link:<br>
`https://info.microsoft.com/ww-landing-windows-server-2019.html`

The required Registration information does not have to be legitimate, so feel free to add whatever you'd like.<br>
For example:<br>
First name: John<br>
Last name: Doe<br>
Email: fake-email@email.com<br>
Company: Fake Company LLC<br>
Job role: IT<br>
Phone: 555-5555
Click **'Download Now'**

Download the **'64-bit edition'** ISO download for the desired language.
It should take some time, since the download is over 5GB.


## Install Windows Server 2019
Open  **VirtualBox**.
Click  **'New'**.

### Virtual machine Name and Operating System
**Name**: `WindowsServer2019`<br>
**Folder**: **leave as default**<br>
**ISO Image**: `<not selected>`<br>
**Type**: `Microsoft Windows`<br>
**Version**: `Windows 10 (64-bit)`

NOTE: leave ISO image as default \<not selected>. Otherwise it will crash and produce an error during installation.

You should be safe with the following resource allocations:<br>
4GB RAM<br>
2 cores<br>
25GB hard disk<br>

You should now see your powered off **WindowsServer2019** virtual machine in the VirtualBox left panel.<br>
Click on this tab, and then click **Settings** on the VirtualBox top panel.<br>

**Storage**  ->  **Controller: SATA**  ->  **WindowsServer2019.vdi**<br>
In the  **Attributes**  section, you can select  **Solid-state Drive**  since it provides higher performance.<br>

**Storage**  ->  **Controller: SATA**  ->  **Empty**  ->  **Attributes**<br>
Click on the CD icon to the right of the  **Optical Drive**.<br>
**Choose a disk file...**, then select the Windows Server 2019 ISO you just downloaded.<br>
Click  **OK**.

Click  **Start**  in the VirtualBox top panel.

If you see something worth changing, select your preference.<br>
Click  **Next**.<br>
Click  **Install Now**.

Select the operating system you want to install<br>
**Windows Server 2019 Standard Evaluation (Desktop Experience)**<br>
Click  **Next**<br>
NOTE:  this will give you graphical interface for much easier interaction.

Applicable notices and license terms<br>
Check  **I accept the license terms**.<br>
Click  **Next**.

Which type of installation do you want?<br>
Select  **Custom: Install Windows only (advanced)**

Where do you want to install Windows?<br>
**Drive 0 Unallocated Space**<br>
Click  **Next**.<br>
NOTE:  this is the dynamic drive that we allocated the space to earlier.

The installation process should take a while, depending on your host machine's specs.

Customize settings<br>
**User name**:  `Administrator`<br>
**Password**:  \<enter your new password>

Congrats! You've just installed Windows Server 2019.


## Logging into Windows Server 2019
Upon booting the machine, you'll come across a locked screen. A message will be displayed that reads:<br>
`Press Ctrl+Alt+Delete to unlock.`<br>
Pressing these keys directly will instead bring up your Host machine's Security options menu.

Instead, click on  **Input**  ->  **Keyboard**  ->  **Insert Ctrl+Alt+Del**<br>
This will insert this command directly into the VM.<br>
You can also use the following shortcut:<br>
`Host key + delete`