# MY PERSONAL STEP-BY-STEP PREOCEDURE TO INSTALL Ubuntu 20.04 USING VIRTUAL BOX AND VAGRANT #
**This installation/procedure was carried out on my windows 7 Machine**<br>
Before I began installation, I had done some research and realized that not all systems  have their virtualization enabled by default.
Checked my system BIOS and had to enable it from advanced option and saved in order for the system to reboot.

You can now begin the setup process.


**Download and Install your Virtual Box**<br>
**Step 1**<br>
Due to the fact that I am more comfortable with Windows, and did not desire to permanently change my operating system to Linux OS, I decided to host the operating system on a virtual machine.
Go to google and download the virtual box suitable for windows version which is ```x86/amd64``` and start the download.
When it is done, it will appear as a Oracle VM virtual Box Manager, based on the version I chose.
The User Account Control is then prompted asking if you want the file to make changes to your system, of which you click the option ```YES```
Give the virtual machine whatever name you have in mind, something descriptive, create a folder for the machine that you can easily have access to located on the RAM of your local machine, and choose ```Ubuntu (64-bit)``` as the type of Operating System (OS) amongst the several options present.


The Ubuntu 20.04 LTS will download in your local machine to ensure that you receive any updates that are given. Any other applications without the LTS will become outdated with time.

**Step 2**<br>
Select the amount of memory space that is to be allocated to the virtual machine. I realized that the recommended memory is 1024 MB, although, you can decide to add more, depending on the overall space on your local machine. 
Ensure the space allocated is not too much, as this will affect the local machine's performance.

**Step 3**<br>
Choose a hard disk. 
The second option,  to Create a virtual hard disk. As earlier researched, the recommended memory for this is 10.00GB

**Step 4**<br>
For the type of hard disk, choose the first; VDI (VirtualBox Disk Image). 

**Step 5**<br>
For The storage on the hard disk, pick the option for dynamically allocated. A fixed size may take longer to create and cause storage issues later on, especially if the local machine does not have much space.

**Step 6**<br>
The file location and size should be left at the recommended portion of 10.00GB, out of the 2TB size. And then Create.

**Step 7**<br>
This will then show the virtual computer that has been created on the left side of the panel, under the section called Tools. It is powered off on default.


**Download your Vagrant**<br>
We are downloading the vagrant to enable us use the software.
**Step 1**<br>
Go to your browser, search for Vagrant by HashiCorp to download and install.
A folder is to be created in the file explorer of your local machine for its running. You can choose to name it as Vagrant.
It is important to note that Vagrant does not have an interface, so everything will be done in your command prompt which is already in your Windows OS.

**Step 2**<br>
An ISO image which is focal64 is downloaded and installed, like a normal installation, for virtual machines. This is because while working with servers, a CD/ DVD, flash, or external hard drive is needed to do the installation.

**Step 3**<br>
When they are downloaded based on your choice, Vagrant automatically sets them up.The following commands should be typed in the terminal to create a new folder and procure the boxes:<br>
```Cd vagrant```<br>
```Cd boxes ```<br>
```vagrant init ubuntu/focal64```<br>
```vagrant up```<br>
```vagrant ssh```<br>

After following all of these steps, you have successfully installed Linux OS on your local machine using VirtualBox.




















