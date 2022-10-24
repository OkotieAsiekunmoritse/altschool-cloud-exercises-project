
# HOW TO DEPLOY A LARAVEL APPLICATION USING THE FOLLOWING DEPENDENCIES# <br>
```Here I used the following applications to deploy the laravel app:``` <br>
**1 Apache2** <br>
**2 MYSQL** <br>
**3 PHP** <br>
**4 COMPOSER** <br>
**5 GIT** <br>
<br>

## Create a domain name, and use a cloud instance or droplet ##<br>
I created this using the Digital Ocean platform and after going through the necessary requirements for the creation, I was given a registered domain name form namecheap platform which i linked to my droplet in digital ocean. <br><br>
![My domain name and droplet from Digitalocean](https://user-images.githubusercontent.com/108562214/197428690-95321bc1-de09-4819-b946-672df9905a98.PNG)
<br>

### Installing the required dependencies for Laravel application ### <br>
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
```sudo mysql_secure_installation``` <br><br>

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
```php -r "if (hash_file('sha384', 'composer-setup.php') === '55ce33d7678c5a611085589f1f3ddf8b3c52d662cd01d4ba75c0ee0459970c2200a51f492d557530c71c15d8dba01eae') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"``` <br>
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
<br>
I reset my domain name, for the file to become like the screenshot below:<br>
 ![sites](https://user-images.githubusercontent.com/108562214/197436708-a0c4f7ea-0ba5-43e4-b4d4-735df99e5d4d.PNG)
<br> <br>

Then enable the new configuration, ```sudo a2ensite domainname.conf```.

**Create an env file**<br>
Get into the nano shell of .env with ```sudo nano .env``` <br>
![env 2](https://user-images.githubusercontent.com/108562214/197439231-dcd5c209-25b6-4132-aa8f-b857460e5923.PNG) <br>













