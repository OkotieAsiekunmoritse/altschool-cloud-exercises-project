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
Then you are free to run your script with the command: ```./<file_name>```
Below is a screenshot of what my bash script for this task looked like:
<img src="C:\Users\Media\altschool-cloud\Git version exercise\First bash script.PNG" alt="First bash script" style="height: 100px; width:100px;"/>

![alt text](
