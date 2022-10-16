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
Here is a screenshot of what my .yml file looks like:<br>
![playbook content 1](https://user-images.githubusercontent.com/108562214/196012378-dd895bfb-a959-4e10-a72b-a1a6a6740029.PNG)<br>
<br>

* Test run the playbook<br>
<br>
To avoid errors and hitches along the final execution process, check to see that all syntax rules in the playbook were obeyed and to check that the instructions given will run eventually. <br>
Use the command: ``` ansible-playbook filename.yml -i name of file containing ip address --check```<br>


