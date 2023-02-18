## How I Installed my PHP 7.4 version on my Ubuntu 20.04 ##
![php i,age](https://user-images.githubusercontent.com/108562214/198392175-f6e5a573-5b37-4751-9b99-05549844187d.PNG)


Follow me on another interesting journey as I install PHP version 7.4 on my Ubuntu local environment.<br>
Although, I had earlier installed before creating this,hence the last step says the PHP 7.4 is already the newest version. But I just want to share with you what your outcome should look like.<br>

Also, I cannot deny that I did some research and finally realized how to go about this process, these were the steps I took:<br>
**Step 1**<br>
Started the process on my command prompt, were I ran the command ``` sudo apt-get``` to update itself<br> and it produced the outcome below:<br>

![step1](https://user-images.githubusercontent.com/108562214/196836806-8cd418e2-344d-4f41-b952-c3556e9ba1c4.PNG)


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

![step 2](https://user-images.githubusercontent.com/108562214/196836895-3c1ce97a-bebc-4fb3-97eb-743e760c5d8f.PNG)


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

![step3](https://user-images.githubusercontent.com/108562214/196837029-b1888747-0a8e-435d-8c70-cd093059b62c.PNG)

![step3b](https://user-images.githubusercontent.com/108562214/196837066-aeeaf44d-9ef6-44bd-bf92-c9e3b9c943e7.PNG)


**Step 4**<br>
I needed to check that every package I had installed was up and running. <br>

![step4](https://user-images.githubusercontent.com/108562214/196837153-c3d0dc17-4c9f-4319-8679-450969b8c4e1.PNG)

**Step 5**<br>
Then I began my installation of my PHP version 7.4, using the command ```sudo apt -y install php7.4```.

![step 5](https://user-images.githubusercontent.com/108562214/196837713-8ea3b3d9-ba86-48b8-bf7f-9b21bb2372c0.PNG)



That was how I successfuly installed.

Following extra instructions I was asked to find out all about the version I had just installed, and I accomplished that with the command ```php -v```<br>
I was also instructed to get the /etc/apt.sources.list from it.









```
