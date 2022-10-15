#  HOW TO USE A BASH SCRIPT AND SCHEDULE A CRONJOB WITH CRONTAB  #
## THE CONCEPT OF BASH SCRIPT ##
### What Is Bash Script and How Does it Function ###
Firstly note that a script is what tells the computer what instructions to follow or say. While bash script instructs the bash shell on what to do. A bash script is a plain text file which contains a series of commands.
Bash scripts is simple, it helps to avoid doing repetitive tasks and it is easy to use.

So, I imbibe you to follow me on this journey on how I used my bash script for this purpose:
Open your text editor from the command line. 
Then type ```vi or nano``` and press enter.

Type ```#!/bin/bash``` 
```#!```  is called shebang or hashbang and it is very necessary to declare the interpreter, while the remaining part is the path to the interpreter. You can get the path to your interpreter by executing the command: which bash

Type all commands you want to execute, save the file with a name and ```.sh``` extension. Then, on your command line, do well to make the file executable with the command: ```chmod +x <file_name>```. 
Then you are free to run your script with the command: ```./<file_name>```<br>
Below is a screenshot of what my bash script for this task looked like:
![First bash script](https://user-images.githubusercontent.com/108562214/195958958-27c13548-2b1f-4e14-abb1-bff5749d6031.PNG)

First of all, install all the necessary packages to setup the email using ```Simple Mail Transfer Protocol (SMTP)``` which is used to send mails from a locqlhost or computer to a configured mailhub.<br>
In your  command line, run the following commands: <br>

```sudo su```<br> 
To operate on your local computer as a roor user,<br>

```apt-get install ssmtp```<br>
To enable you have ssmtp packages to enable smooth communication netween local computer and others<br>

``` apt-get install mailutils```<br>
To enable the mailutils packages<br>

```apt-get install mutt```<br>
To enable its packages as well.<br>
These installations I did to ensure all related processes run effectively when commanded to<br>

On your command line, run ```nano /etc/sstmp/sstmp.conf```<br>
This I did, to enable me edit my Secure Simple Mail Transfer Protocol configuration to suit my mail properties.<br>
So, note that after installing the mail packages like we did earlier, the nano file is also created instantly, so there would be a default nano ssmtp file already inyour system after installation.<br>
After changing the default propertries to my personal mail properties, the screenshot below shows what I finally had:
![etc_ssmtp_ssmtp_conf](https://user-images.githubusercontent.com/108562214/195994202-8b2dc6b7-31f7-4b8f-a8cf-1846dda42fce.PNG)
I changed and included the following into the nano file:<br>
The root<br>
The default root was changed from ```postmaster``` to my ```personal gmail account```.(Note that I used a gmail account for this procedure)<br>

The mailhub<br>
I changed the default mailhub from ```mail``` to ```smtp.gmail.com:456



