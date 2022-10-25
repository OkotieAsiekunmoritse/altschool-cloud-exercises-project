
# HOW TO DEPLOY A LARAVEL APPLICATION USING THE FOLLOWING DEPENDENCIES  <br>
```Here I used the following applications to deploy the laravel app:``` <br>
**Apache2** <br>
**MYSQL** <br>
**PHP** <br>
**COMPOSER** <br>
**GIT** <br>
<br>

## Create a domain name and use a cloud instance or droplet <br>
I created this using the Digital Ocean platform and after going through the necessary requirements for the creation, I was given a registered domain name form namecheap platform which i linked to my droplet in digital ocean. <br><br>
![My domain name and droplet from Digitalocean](https://user-images.githubusercontent.com/108562214/197428690-95321bc1-de09-4819-b946-672df9905a98.PNG)
<br>

**Setup Initialization**<br>
Update the packages to the latest version available with the following commands:<br>
```
sudo apt update
sudo apt upgrade

```
<br>

**Install wget package**<br>
```sudo apt install wget```

### Installing the Required Dependencies for Laravel Application <br>
**1. Apache2** <br>
Input in your terminal ```apt install apache2``` <br>
Note that you should use ```sudo``` when running these commands especially when you are not int eh root of your machine, to enable full permission or access to your machine. <br>

**. Setup ufw** <br>
Set up Uncomplicated Firewall (UFW) with Apache to allow public access on default web ports for HTTP and HTTPS<br>
Input ```sudo ufw app list``` for a non root user <br>
Enable te following:<br>
```sudo uff allow SSH``` <br>
```sudo ufw allow 'OpenSSH'``` <br>
```sudo ufw allow 'WWW Full'``` <br>

Then ```sudo systemctl status apache2``` <br>
![apache2 status](https://user-images.githubusercontent.com/108562214/197430072-89ec9f72-0a85-494b-a650-38c93103c6e8.PNG) <br><br>

**3. Install MySql** <br>
Follow these commands: <br>
```wget https://dev.mysql.com/get/mysql-apt-config_0.8.22-1_all.deb``` <br>
```sudo apt update``` <br>
```sudo apt install mysql-server``` <br><br>

Then you will see the status of mysql with ```sudo service mysql status```<br>
![mysql status](https://user-images.githubusercontent.com/108562214/197430382-7bb227ba-d960-49e3-b384-0423d5a7aedb.PNG)

**Secure Mysql** <br>
```sudo mysql_secure_installation``` <br>

![mysqlinstall1](https://user-images.githubusercontent.com/108562214/197870127-72f151ad-6907-4557-a8ba-936877abe370.PNG)<br>
![mysql installation2](https://user-images.githubusercontent.com/108562214/197869571-88f13707-963f-4f12-a979-5ac65a93ce84.PNG)<br> <br>



**4 Install PHP** <br>
Input ```sudo apt -y install lsb-release apt-transport-https ca-certificates``` <br>
```sudo wget -O /etc/apt/trusted.gpg.d/php.gpg https://packages.sury.org/php/apt.gpg``` <br>
 
Include the PPA to the server packages <br>
Input ```echo "deb https://packages.sury.org/php/ $(lsb_release -sc) main" | sudo tee /etc/apt/sources.list.d/php.list```<br>
Update the packages and install PHP  <br>
Run the command:
```sudo apt update``` <br>
```sudo apt install php libapache2-mod-php php8.1-mysql php8.1-common php8.1-mysql php8.1-xml php8.1-xmlrpc php8.1-curl php8.1-gd php8.1-imagick php8.1-cli php8.1-dev php8.1-imap php8.1-mbstring php8.1-opcache php8.1-soap php8.1-zip php8.1-intl -y``` <br>

**Configure PHP** <br>
Configure PHP for Web Applications by changing some values in php.ini file. <br>
Run the command<br>
```sudo nano /etc/php/8.1/apache2/php.ini``` <br>
Edit the following in the nano file<br>

```
upload_max_filesize = 64M 
post_max_size = 128M 
memory_limit = 256M 
max_execution_time = 300 
max_input_vars = 5000 
max_input_time = 150

```
Note:<br>
Execution time deals with long should a php script run before the server stops it from running <br>
Max_input_time deals with how long should a user feed a php script before it cuts it off. <br>

Now, restart your Apache for the changes to take effect.<br>
**Configure Apache** <br>
Disable default Apache configuration.
```sudo a2dissite 000-default``` <br>

**5. Install Composer** <br>
Note you should install your PHP first before installing the composer.<br>
Run the following commands on your terminal:<br>
```php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"``` <br>
```php -r "if (hash_file('sha384', 'composer-setup.php') === '55ce33d7678c5a611085589f1f3ddf8b3c52d662cd01d4ba75c0ee0459970c2200a51f492d557530c71c15d8dba01eae') {      echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"``` <br>
```php composer-setup.php``` <br>
```php -r "unlink('composer-setup.php');"``` <br><br>

Put the composer.phar into a directory on your PATH, so you can simply call composer from any directory (Global install)<br>
```sudo mv composer.phar /usr/local/bin/composer```<br>

Note: Laravel relies on the composer to run as some of the packages uses it to run.<br>

**6.Install Git** <br>
```sudo apt install git ```<br>
In your /var/www/ directory git clone the repository given, which is ```https://github.com/f1amy/laravel-realworld-example-app.git``` <br>

**Clone the repository that was given** <br>
So, run ```sudo git clone https://github.com/f1amy/laravel-realworld-example-app.git``` <br>
To rename ```mv laravel-realworld-example-app.git (newname)``` <br>

**To get the right permissions,run the commands in the terminal** <br>
```sudo chown -R www-data:www-data /var/www/html/asiekunmoritse``` <br>
```sudo chmod -R 775 /var/www/html/asiekunmoritse/storage``` <br>

**Create a new virtual host configuration** <br>
```sudo nano /etc/apache2/sites-available/domainname.conf``` <br>
In the nano file, put in the following: <br>
```
<VirtualHost *:80>
     ServerAdmin admin@domainname.com
     ServerName domainname.com
     ServerAlias www.domainname.com

     DocumentRoot /var/www/html/domainname/public

     <Directory /var/www/html/domainname/public>
         Options Indexes FollowSymLinks
         AllowOverride All
         Require all granted
     </Directory>

     ErrorLog ${APACHE_LOG_DIR}/error.log 
     CustomLog ${APACHE_LOG_DIR}/access.log combined 
 </VirtualHost>

```
Ensure that the document root and directory are the same. In my shell, I put in the path which I had rightfully created my document 
root, and it meant I had to remove the ```html```from both the document root and the directory. I used my domain name as well.<br>
Save and close the file when done.<br>
![sites(coreect1)](https://user-images.githubusercontent.com/108562214/197877886-4141da15-43ae-4498-ab1b-7ad4451be28e.PNG) <br>

Then enable the new configuration, ```sudo a2ensite domainname.conf```. <br>

**Create an env file**<br>
Get into the nano shell of .env with ```sudo nano .env``` <br>
Save and close the file when done<br>
![env(real1)](https://user-images.githubusercontent.com/108562214/197868982-99e7bcda-b670-469a-9202-27cd34de620a.PNG)<br>

Then enable the new configuration by typing the command, ``` sudo a2ensite domainname.conf``` <br>

**Check that the application has been deployed**<br>
Checking with domain name<br>
Open your browser, put in your domain name or your ip address, to be sure that it has actually deployed to the laravel application.<br>
In the url input ```your_domainname``` like i did, and got into the laravel application.<br>
![Laravel pg with https after securing an SSL certificate](https://user-images.githubusercontent.com/108562214/197883757-3efcab96-57da-4679-b4f1-1e96555c80d4.PNG)<br>

Checking with Ipaddress<br>
![laravel with ip address](https://user-images.githubusercontent.com/108562214/197883973-f39dc78c-4ee0-43aa-88db-cf16504db2c6.PNG)<br>

**NOTE** <br>
When comparing both urls, you would notice that connections to my web server for my domainname is ```https`` which means it is secured are secured,while that of the ipaddress id ``http``` which states that is not secure.<br>
The domanname is safe because I secured the SSL certificate before deploying while I didnt do same for the Ipaddress. Research also shows that it is better to use a domain name to deploy safely than an Ipaddress. <br>

**Conclusion** <br>
The journey to accpomplish this prject was not an easy one, it took a lot of research, reading and practice to get to the final output, I hope this can help anyone get theirs as well. <br>












