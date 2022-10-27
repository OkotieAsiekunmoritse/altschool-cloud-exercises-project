# Creating Groups, Creating Users, and Generating SSH keys #

## Creating 3 groups: Admin, Support and Engineering <br>

```
vagrant@ubuntu-focal:/$ sudo groupadd admin
vagrant@ubuntu-focal:/$
vagrant@ubuntu-focal:/$ sudo groupadd support
vagrant@ubuntu-focal:/$
vagrant@ubuntu-focal:/$ sudo groupadd engineering
vagrant@ubuntu-focal:/$
```
## Adding admin group to sudoers<br>

![sudoers 1](https://user-images.githubusercontent.com/108562214/196829531-bd02cf6a-0eaa-4559-a151-32fbecdf4650.PNG)


## Creating a user in each of the groups<br>

```
vagrant@ubuntu-focal:~$ sudo useradd -g admin -m -s /bin/bash child_admin
vagrant@ubuntu-focal:~$
vagrant@ubuntu-focal:~$ sudo useradd -g support -m -s /bin/bash child_support
vagrant@ubuntu-focal:~$
vagrant@ubuntu-focal:~$ sudo useradd -g engineering -m -s /bin/bash child_engineering
vagrant@ubuntu-focal:~$

```
![child1](https://user-images.githubusercontent.com/108562214/196831513-ea715b3b-9ec2-4099-b694-085d3967d553.PNG)


## Generating  SSH keys for child_admin(user) in the admin group<br>

```
To generate SSH keys for child_admin(user) in the admin group, do this:<br>

vagrant@ubuntu-focal:~$ sudo passwd child_admin
New password:
Retype new password:
passwd: password updated successfully

```
![child key-gen](https://user-images.githubusercontent.com/108562214/196832241-42349799-8739-49e0-9a76-dbab4b2f0b30.PNG)



