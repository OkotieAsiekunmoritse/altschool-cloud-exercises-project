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

```sudo```<br> 
<br>
To operate on your local computer without having permission issues while running your commands<br>

```apt-get install ssmtp```<br>
<br>
To enable you have ssmtp packages to enable smooth communication netween local computer and others<br>

``` apt-get install mailutils```<br>
<br>
To enable the mailutils packages<br>

```apt-get install mutt```<br>
<br>
To enable its packages as well.<br>
These installations I did to ensure all related processes run effectively when commanded to<br>

On your command line, run ```nano /etc/sstmp/sstmp.conf```<br>
This I did, to enable me edit my Secure Simple Mail Transfer Protocol configuration to suit my mail properties.<br>
So, note that after installing the mail packages like we did earlier, the nano file is also created instantly, so there would be a default nano ssmtp file already inyour system after installation.<br>
After changing the default propertries to my personal mail properties, the screenshot below shows what I finally had:<br>
![etc_ssmtp_ssmtp_conf](https://user-images.githubusercontent.com/108562214/195994202-8b2dc6b7-31f7-4b8f-a8cf-1846dda42fce.PNG)<br>
<br>
I changed the following in the nano file:<br>
<br>
* The root<br>
The default root was changed from ```postmaster``` to my ```personal gmail account```.(Note that I used a gmail account for this procedure)<br>
<br>

* The mailhub<br>
I changed the default mailhub from ```mail``` to ```smtp.gmail.com:465<br>
<br>

*  The hostname<br>
I changed the hostname from ```main``` to my system hostname<br>
<br>

The following were added to the nano file:<br>
<br>

* AuthUser<br>
This is were you add yor mail address again<br>
<br>

* Authpass<br>
This is were I added the password from my gmail application. (Note that your gmail account password and the gmail application password are very different, also ensure you have done your 2 step verification for your account. I encountered some issues because I thought both passwords were the same. I had to go online to browse on how to create a gmail application password, and followed the necessary steps as guided by google.)<br>
``` 

Create & use App Passwords

If you use 2-Step-Verification and get a "password incorrect" error when you sign in, you can try to use an App Password.
Go to your Google Account.
Select Security.
Under "Signing in to Google," select App Passwords. You may need to sign in. If you don’t have this option, it might be because:
2-Step Verification is not set up for your account.
2-Step Verification is only set up for security keys.
Your account is through work, school, or other organization.
You turned on Advanced Protection.
At the bottom, choose Select app and choose the app you using and then Select device and choose the device you’re using and then generate.
Follow the instructions to enter the App Password. The App Password is the 16-character code in the yellow bar on your device.
Tap Done.

```
<br>

* Use TLS<br>
TLS which means ```Transport Layer Security``` is very much needed as it encrypts data sent over the internet to ensure that hackers are unable to see what you transmit.It is useful for confidential and sensitive information like passwords, credit card numbers, amongst others.<br>
Set and enable the TLS feature to ```YES```.<br>
<br>

* Use STARTTLS<br>
Ensure you include the STARTTLS. I used port 465 (SSL) for my mailhub because the other port did not senfd my mail, hence I disenable my STARTTLS even though it was included. In place of port 465, if port 587 (TLS) is used and functions properly when sending your mail, then comment out ```UseSTARTTLS= YES```.<br>
<br>

* FromLine Override<br>
Ensure that you enable this to ```YES``` as well.<br>
<br>
Save all the editing done by overwriting it with ctrl o, then save and exit the file.<br>
<br>
<br>
Test what you have done by sending yourself a test email. I di this by running the command ```echo "Hey Mo!" | mail -s "Hey girl" your mail address```<br>
Where ```echo``` is the command that sends ```Hey Mo``` as the content of the mail, ```-s``` refers to the sublect of the mail which in this case is ```Hey girl```, then my email address.<br>
<br>

The bash script earlier displayed at the beginning shows specific commands to execute the task.<br>
<br>
The script created a log file, which includes the date and time, echo of the expected output, as well as the details of your system's memory. I also created another script specifically for my mail showing the contents of the echo, and also including the details pf the system's memory as well.<br>

I did this by:
* Creating a folder for my script and log file, which I called memory_logs.<br>
Run the command<br>
```mkdir memory_logs```<br>
```cd memory_logs```<br>
<br>

* Creating a shell file using nano.
```nano memory_logs.sh```<br>
<br>

* Then I included in what I needed to in my bash script which is diplayed in the screenshot, under the heading of what is a bashscript at the beginning of this file.<br>

* #!<br>
To ensure that I was creating a bash script,I statrted with my shebang, as all bash scripts should begin.<br>
<br>

* Path=/home/vagrant/memory_logs/log_file.log<br>
I went back to my command line to very my path, by running the command ```pwd``` to check the present directory path leading to my shell, which I then put in as my path. Make sure to check your path to ensure you are directing the instruction form the right place.<br>
<br>
 
* Touch ${path}<br>
I did this to touch the path which is specified above.<br>
<br>

* Then I created my email.sh shell file using nano as well. Study the screenshot below.<br>
![Email_sh](https://user-images.githubusercontent.com/108562214/196010429-ff4e2ce5-2a2c-4663-8706-9929cbb5c867.PNG)<br>
<br>
In the email bash script:<br>
* The ```mutt -a``` command used is to attach the log file gotten from the path variable.<br>
<br>

* The ```&& Sudo rm -f ${path}``` deletes the log file after it has been sent.
<br>

* To schedule my cronjob for timely execution of the bash script, I executed the command crontab -e , and included the folowing as displayed in white text in the screenshot below<br>
![cronjob](https://user-images.githubusercontent.com/108562214/196011030-d120cced-4cd6-43b3-ab15-884238048c95.PNG)<br>
The first instruction simply points to our bash script and instructs that it should be executed “At minute 0” of every hour of every day of the month, every month and evry day of the week.<br>
The second instruction instructs the script that it should be executed "At minute 0, and hour 0" of everyday of the month, every month and every day of the week.<br>
![Email Report1](https://user-images.githubusercontent.com/108562214/196011347-f991bc23-98c2-43eb-9c4a-93567d68f0a2.PNG)<br>
I recieved my mail at the set time specified with the content in the body as specified as well.


 


