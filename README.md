# Install **LAMP** on **Linux Mint x64**

* Step 1: Update Linux:
	```apt-get update && sudo apt-get dist-upgrade -y```
	```reboot```

* Step 2: Install the LAMP Server
	```sudo apt-get install lamp-server^ -y```

* Step. 3: Setup MySQL
	__enter a password for the root account.__

* Step 4: Test Apache in browser
	```http://localhost```

* Step 5: Test PHP
  1. Create file:
	```sudo nano /var/www/html/info.php```

  2. Copy and Paste:
	```php phpinfo();```

  3. Restart Apache:
	```sudo service apache2 restart```

  4. PHP is raedy:
	```http://localhost/info.php```

* Step 6: Install PHPMyAdmin
	___install fromm Linux Mint app manager___
