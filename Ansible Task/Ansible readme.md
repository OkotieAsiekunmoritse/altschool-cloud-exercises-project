# HOW TO GET YOUR ANSIBLE PLAYBOOK RUNNING, WITH APACHE2, PYTHON3 AND ANSIBLE #

## STEP BY STEP PROCEDURE ##
* Run the following commands as a ```sudo``` user to get the right permissions to be able to achieve this task. <br>
<br>

```apt install apache2```<br>
This is to ensure all apache2 packages are installed or updated in the computer<br>

 ```apt install python3```<br>
This is to ensure all python packages are installed or updated in the computer<br>

```apt install ansible```<br>

* Allow your machine create a Secure Shell Key(SSH) by running the command ```ssh keygen```<br>
This is a sample of what the randomart image of the key will look like:<br>
```
+---[RSA 3072]----+
|=B.BEo=o . =o.   |
|*oX .o oo =.o.   |
|o+o+o . .+ oo    |
| +.. .    o  .   |
|o .     S     .  |
|.o .     o o o   |
|  +       * + .  |
| .         + .   |
|                 |
+----[SHA256]-----+
```
<br>
Run the command ```ssh-copy-id -i ip address of second machine```, this is executed to copy the key created from one machine to another, in other to be able to communicate or log into the other machine from the first machine. <br>
The try to login from that machine to the other machine with the command ``` ssh @machine ipaddress ```<br>
It immediately logs you into your other machine.<br>
Exit from the second machine back to your first machine to execute more commands.<br>

* Go to your ansible directory ```cd ansible```<br>
<br>
Create a file shell for your second machine's ip address by typing the ip address in the file using nano.<br>
```nano "name of shell created" ```

* Start creating your playbook by creating a yml file shell<br>
<br>
A yaml or yml file is simply a language through which instructions are written in the order in which they would be executed. <br>
So,ensure that ```.yml``` is included at the end of whatever name you decide to give the file created.<br>
There is also a specified syntax for beginning a yml file and the writeup must be in a uniformed line all through.<br>
A yml file must beggin with ```---``` for the first line and ```-``` on the second line, before you begin writing your instructions.<br>
Here is a look at what my .yml file looks like:<br>


![playbook content 1](https://user-images.githubusercontent.com/108562214/196054266-552d268f-a6c6-49c6-9d7a-9aa6a79552c7.PNG)

![playbook content 1(cont'd)](https://user-images.githubusercontent.com/108562214/196054563-24a6a9e0-1221-49ce-9cf8-971ed4e4702a.PNG)

<br>

* Test run the playbook<br>
<br>
To avoid errors and hitches along the final execution process, check to see that all syntax rules in the playbook were obeyed and to check that the instructions given will run eventually. <br>
Use the command: ``` ansible-playbook filename.yml -i name of file containing ip address --check```<br>
The run the actual process with the same command but withou the ```--check```<br>
This screenshot below is what I got after I ran the check and nothing was wrong, I then did the actual execution.<br>
<br>

![ansible-playbook](https://user-images.githubusercontent.com/108562214/196054129-307a7f75-f518-4718-b3b7-41d64c7ae594.PNG)<br>



* Check the ipaddress to see if it works<br>
Inout the Ip address of your second machine into your google browser to see whether the default page of Papache 2 Ubuntu, comes up just like the way mine did from the screenshot below.<br>
![Apache2 ubuntu default page](https://user-images.githubusercontent.com/108562214/196053984-7e491bc9-3998-4015-b65b-cc36b7a4a4ca.PNG)<br>


* Check the ip address with the index.php to see if the set time zone of Afica/Lagos is displayed just like the screenshot below<br>
![Rendered page](https://user-images.githubusercontent.com/108562214/196054466-17e23986-69e1-4b94-925a-007e8410f214.PNG)




