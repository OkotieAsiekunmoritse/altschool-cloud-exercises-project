# MY PERSONAL STEP-BY-STEP PREOCEDURE TO INSTALL Linux OS USING VIRTUAL BOX #
**This installation/procedure was carried out on my windows 7 Machine**<br>
Before I began installation, I had done some research and realized that not all systems  have their virtualization enabled by default.
Checked my system BIOS and had to enable it from advanced option and saved in order for the system to reboot.

You can now begin the setup process.

**1. Download and Install your Virtual Box**<br>
Due to the fact that I am more comfortable with Windows, and did not desire to permanently change my operating system to Linux OS, I decided to host the operating system on a virtual machine.
Go to google and download the virtual box suitable for windows version which is ```x86/amd64``` and start the download.
When it is done, it will appear as a Oracle VM virtual Box Manager, based on the version I chose.
The User Account Control is then prompted asking if you want the file to make changes to your system, of which you click the option ```YES```
Give the virtual machine whatever name you have in mind, something descriptive, create a folder for the machine that you can easily have access to located on the RAM of your local machine, and choose Ubuntu (64-bit) as the type of Operating System (OS) amongst the several options present.

```



```






















To start the matter you go need go the vagrant official vagrant website to download vagrant enter your host machine or local machine. Just click make you reach were you go download. Once you done download am the installation na straight matter, just dey follow the prompt were the installation dey show you. To know if e install well go your terminal/cmd depending on the machine you day use type

vagrant

You suppose see something like this were show say e install well.

achebe@okechukwus-MacBook-Pro ~ % vagrant
Usage: vagrant [options] <command> [<args>]

    -h, --help                       Print this help.

Common commands:
     autocomplete    manages autocomplete installation on host
     box             manages boxes: installation, removal, etc.
     cloud           manages everything related to Vagrant Cloud
Once you done finish that one, na to setup the VirtualBox for your machine. E go make sense if de whole installation dey one folder. So we go create folder con enter that folder.

achebe@okechukwus-MacBook-Pro ~ % cd Desktop 
achebe@okechukwus-MacBook-Pro Desktop % mkdir -p TestVagrant/Box/Ubuntu_20_04
achebe@okechukwus-MacBook-Pro Desktop % cd TestVagrant/Box/Ubuntu_20_04 
After we done create the Ubuntu_20_04 folder inside Desktop/TestVagrant/Box folder the next thing na to install the vagrant ubuntu using the "vagrant init" command.

vagrant init ubuntu/focal64
You suppose get this output

A `Vagrantfile` has been placed in this directory. You are now
ready to `vagrant up` your first virtual environment! Please read
the comments in the Vagrantfile as well as documentation on
`vagrantup.com` for more information on using Vagrant.
The next thing na to startup your virtual machine with this command

vagrant up
Once e done finish, you done set to use your virtual machine with ubuntu inside am. To enter your machine, you go use this command

vagrant ssh
You suppose see this output.

Welcome to Ubuntu 20.04.4 LTS (GNU/Linux 5.4.0-122-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Wed Aug 10 23:19:29 UTC 2022

  System load:  0.01              Processes:               118
  Usage of /:   4.1% of 38.70GB   Users logged in:         0
  Memory usage: 23%               IPv4 address for enp0s3: 10.0.2.15
  Swap usage:   0%


0 updates can be applied immediately.
To make show say na ubuntu your virtual machine dey run, type this command.

hostnamectl
For my own, see the result wey I get.

vagrant@ubuntu-focal:~$ hostnamectl
   Static hostname: ubuntu-focal
         Icon name: computer-vm
           Chassis: vm
        Machine ID: 87a9bd2baeb54bcda24765b89147565a
           Boot ID: 3b9ba20e3d494ac89568bb487c447a7f
    Virtualization: oracle
  Operating System: Ubuntu 20.04.4 LTS
            Kernel: Linux 5.4.0-122-generic
      Architecture: x86-64
Like this we done finish the installation of ubuntu for our virtual machine, e sweet abi. The next thing we go do na to run some configuration like setting our private_network set to dhcp.

To get your IP address of your virtual machine, you go use

ifconfig
if you get this error

vagrant@ubuntu-focal:~$ ifconfig

Command 'ifconfig' not found, but can be installed with:

apt install net-tools
Please ask your administrator.
You go use the "sudo" command run am, i.e

sudo apt install net-tools
Then run the "ifconfig" command again and you go get something like this.

vagrant@ubuntu-focal:~$ ifconfig
enp0s3: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 10.0.2.15  netmask 255.255.255.0  broadcast 10.0.2.255
        inet6 fe80::52:20ff:fe6d:cccd  prefixlen 64  scopeid 0x20<link>
        ether 02:52:20:6d:cc:cd  txqueuelen 1000  (Ethernet)
        RX packets 80714  bytes 112088617 (112.0 MB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 11575  bytes 942445 (942.4 KB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 49  bytes 4998 (4.9 KB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 49  bytes 4998 (4.9 KB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
To configure our vagrant virtual machine(VM) to use dchp as private_network so we fit give am our own ip, we go need exit the VM with the "exit" command con halt our VM with "vagrant halt".

exit

vagrant halt
Once we done comot our VM, for the folder wey we run the installation , the installation add one Vagrantfile where various vagrant configuration dey. Na from this file you go add our configuration.

Inside the configuration, add this line of code con save am join.

config.vm.network "private_network", type: "dhcp"
No be here e go end oo, we go need do some small configuration for VirtualBox, ooo I dey assume say you done install VirtualBox and e dey work normal normal from your end.
