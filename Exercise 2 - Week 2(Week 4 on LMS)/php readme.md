## How I Installed my PHP 7.4 version on my Ubuntu 20.04 ##

![php-image (1)](https://user-images.githubusercontent.com/108562214/187519023-88db7ed0-2af0-4445-91c0-cfeb4b6e63f6.jpg)



Follow me on another interesting journey as I install PHP version 7.4 on my Ubuntu local environment.<br>
Although, I had earlier installed before creating this,hence the last step says the PHP 7.4 is already the newest version. But I just want to share with you what your outcome should look like.<br>

Also, I cannot deny that I did some research and finally realized how to go about this process, these were the steps I took:<br>
**Step 1**<br>
Started the process on my command prompt, were I ran the command ``` sudo apt-get``` to update itself<br> and it produced the outcome below:<br>

```
vagrant@ubuntu-focal:~$ sudo apt-get update
Hit:1 http://ppa.launchpad.net/ondrej/php/ubuntu focal InRelease
Hit:2 http://archive.ubuntu.com/ubuntu focal InRelease
Get:3 http://security.ubuntu.com/ubuntu focal-security InRelease [114 kB]
Get:4 http://archive.ubuntu.com/ubuntu focal-updates InRelease [114 kB]
Get:5 http://archive.ubuntu.com/ubuntu focal-backports InRelease [108 kB]
Reading package lists... Done
E: Release file for http://security.ubuntu.com/ubuntu/dists/focal-security/InRelease is not valid yet (invalid for another 11h 2min 42s). Updates for this repository will not be applied.
E: Release file for http://archive.ubuntu.com/ubuntu/dists/focal-updates/InRelease is not valid yet (invalid for another 11h 3min 47s). Updates for this repository will not be applied.
E: Release file for http://archive.ubuntu.com/ubuntu/dists/focal-backports/InRelease is not valid yet (invalid for another 9h 13min 58s). Updates for this repository will not be applied.

```

**Step 2**<br>
I then followed this without another command ``` sudo apt -y install software-properties-common```, which installs software to manage distributions and independent software vendors.
The ```-y``` flag is incuded because it plays the role of automatically agreeing to do the installation. If the ```-y``` flag is absent, there would be a constant prompt in your terminal window for each installation.
```
vagrant@ubuntu-focal:~$ sudo apt -y install software-properties-common
Reading package lists... Done
Building dependency tree
Reading state information... Done
software-properties-common is already the newest version (0.99.9.8).
0 upgraded, 0 newly installed, 0 to remove and 16 not upgraded.

```

**Step 3**<br>
Then  I put in the next command ``` sudo add-apt-repository ppa:ondrej/php```, for all versions of your PHP to be displayed
```
vagrant@ubuntu-focal:~$ sudo add-apt-repository ppa:ondrej/php
 Co-installable PHP versions: PHP 5.6, PHP 7.x and most requested extensions are included. Only Supported Versions of PHP (http://php.net/supported-versions.php) for Supported Ubuntu Releases (https://wiki.ubuntu.com/Releases) are provided. Don't ask for end-of-life PHP versions or Ubuntu release, they won't be provided.

Debian oldstable and stable packages are provided as well: https://deb.sury.org/#debian-dpa

You can get more information about the packages at https://deb.sury.org

IMPORTANT: The <foo>-backports is now required on older Ubuntu releases.

BUGS&FEATURES: This PPA now has a issue tracker:
https://deb.sury.org/#bug-reporting

CAVEATS:
1. If you are using php-gearman, you need to add ppa:ondrej/pkg-gearman
2. If you are using apache2, you are advised to add ppa:ondrej/apache2
3. If you are using nginx, you are advised to add ppa:ondrej/nginx-mainline
   or ppa:ondrej/nginx

PLEASE READ: If you like my work and want to give me a little motivation, please consider donating regularly: https://donate.sury.org/

WARNING: add-apt-repository is broken with non-UTF-8 locales, see
https://github.com/oerdnj/deb.sury.org/issues/56 for workaround:

# LC_ALL=C.UTF-8 add-apt-repository ppa:ondrej/php
 More info: https://launchpad.net/~ondrej/+archive/ubuntu/php
Press [ENTER] to continue or Ctrl-c to cancel adding it.

Hit:1 http://ppa.launchpad.net/ondrej/php/ubuntu focal InRelease
Hit:2 http://archive.ubuntu.com/ubuntu focal InRelease
Get:3 http://security.ubuntu.com/ubuntu focal-security InRelease [114 kB]
Get:4 http://archive.ubuntu.com/ubuntu focal-updates InRelease [114 kB]
Get:5 http://archive.ubuntu.com/ubuntu focal-backports InRelease [108 kB]
Reading package lists... Done
E: Release file for http://security.ubuntu.com/ubuntu/dists/focal-security/InRelease is not valid yet (invalid for another 11h 1min 7s). Updates for this repository will not be applied.
E: Release file for http://archive.ubuntu.com/ubuntu/dists/focal-updates/InRelease is not valid yet (invalid for another 11h 2min 12s). Updates for this repository will not be applied.
E: Release file for http://archive.ubuntu.com/ubuntu/dists/focal-backports/InRelease is not valid yet (invalid for another 9h 12min 24s). Updates for this repository will not be applied.

```
**Step 4**<br>
Then I ran the command ```sudo apt-get update``` so your package manager can see the newly listed packages.<br>
I did a rerun on the ```apt-get``` command for the reason of updating it just as the name signifies.
```
vagrant@ubuntu-focal:~$ sudo apt-get update
Hit:1 http://archive.ubuntu.com/ubuntu focal InRelease
Hit:2 http://ppa.launchpad.net/ondrej/php/ubuntu focal InRelease
Get:3 http://security.ubuntu.com/ubuntu focal-security InRelease [114 kB]
Get:4 http://archive.ubuntu.com/ubuntu focal-updates InRelease [114 kB]
Get:5 http://archive.ubuntu.com/ubuntu focal-backports InRelease [108 kB]
Reading package lists... Done
E: Release file for http://security.ubuntu.com/ubuntu/dists/focal-security/InRelease is not valid yet (invalid for another 11h 0min 41s). Updates for this repository will not be applied.
E: Release file for http://archive.ubuntu.com/ubuntu/dists/focal-updates/InRelease is not valid yet (invalid for another 11h 1min 47s). Updates for this repository will not be applied.
E: Release file for http://archive.ubuntu.com/ubuntu/dists/focal-backports/InRelease is not valid yet (invalid for another 9h 11min 59s). Updates for this repository will not be applied.

```
**Step 5**<br>
Then I began my installation of my PHP version 7.4, using the command ```sudo apt -y install php7.4```.
```
vagrant@ubuntu-focal:~$ sudo apt -y install php7.4
Reading package lists... Done
Building dependency tree
Reading state information... Done
php7.4 is already the newest version (1:7.4.30-5+ubuntu20.04.1+deb.sury.org+1).
0 upgraded, 0 newly installed, 0 to remove and 16 not upgraded.
```

That was how I successfuly installed.

Following extra instructions I was asked to find out all about the version I had just installed, and I accomplished that with the command ```php -v```<br>
I was also instructed to get the /etc/apt.sources.list from it.









```
