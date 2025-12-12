# Start VM when Windows starts
This will start an Ubuntu virtual machine when Windows 11 starts up (even if you haven't logged in yet).

## List VMs
Open your shell (command prompt).<br>
The following command will tell the VirtualBox executable file to list all the virtual machines currently running on your computer:<br>
`"C:\Program Files\Oracle\VirtualBox\VBoxManage.exe" list vms`

The output will show you the name of the operating system, followed by what seems like random characters. This long string of chracters is the UUID, which Windows will use to start the VM everytime the computers boots. 

Open up "Task Scheduler".<br>
"Actions" right panel -> Task Scheduler Library -> Create Task

**General** tab<br>
Name: start vm<br>
Location: \<br>
Run whether user is logged in or not<br>

**Triggers** tab<br>
Begin the task: At startup

**Actions** tab<br>
Click **New** button

**New Action** panel<br>
Program/script: `"C:\Program Files\Oracle\VirtualBox\VBoxManage.exe" startvm <VM_UUID> --type headless`

A window will appear asking if you're sure about running the program. Click **Yes**.<br>
You'll be asked for the admin password. Type it in. Click **Ok**.

