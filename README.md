# linux mint lamp
* Step 1: Update Linux
sudo apt-get update && sudo apt-get dist-upgrade -y
sudo reboot

* Step 2: Install the LAMP Server
sudo apt-get install lamp-server^ -y

* Step. 3: Setup MySQL
All you have to do here is enter a password for the root account.

* Step 4: Test Apache
http://localhost

* Step 5: Test PHP
Create file:
sudo nano /var/www/html/info.php

* Copy and Paste:
<?php phpinfo(); ?>

* Restart Apache
sudo service apache2 restart

* PHP is configured
http://localhost/info.php

* Step 6: Install PHPMyAdmin
...
