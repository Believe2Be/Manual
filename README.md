# Install **LAMP** whith **WordPress** app on **Linux Mint x64**

* Step 1: Update Linux:
	```$ apt-get update && sudo apt-get dist-upgrade -y```
	```$ reboot```

* Step 2: Install the LAMP Server
	```$ sudo apt-get install lamp-server^ -y```

* Step. 3: Setup MySQL
	__enter a password for the root account.__

* Step 4: Test Apache in browser
	```http://localhost```

* Step 5: Test PHP
  1. Create file:
	```$ sudo nano /var/www/html/info.php```

  2. Copy and Paste:
	```php phpinfo();```

  3. Restart Apache:
	```sudo service apache2 restart```

  4. PHP is raedy:
	```http://localhost/info.php```

* Step 6: Install PHPMyAdmin
	___install fromm Linux Mint app manager___
	
* Step 7: Install WordPress CMS
	```
	$ wget -c http://wordpress.org/latest.tar.gz
	$ tar -xzvf latest.tar.gz
	```
	 ___Next, move the WordPress files from the extracted folder to the Apache default root directory, /var/www/html/:___
	```
	$ sudo chown -R www-data:www-data /var/www/html/
	$ sudo chmod -R 755 /var/www/html/
	$ sudo mv wordpress/ /var/www//html/
	```
* Step 8: Create WordPress Database
	```
 	mysql -u root -p
	mysql> CREATE DATABASE wp_myblog;
	mysql> GRANT ALL PRIVILEGES ON wp_myblog.* TO 'your_username_here'@'localhost' IDENTIFIED BY 'your_chosen_password_here';
	mysql> FLUSH PRIVILEGES;
	mysql> EXIT;
 	```
	
	___Move to the /var/www/html/ directory and rename existing:___
	```
	$ sudo mv wp-config-sample.php wp-config.php
	```
	
	___and then update your database information in the MySQL settings section:___
	```
	// ** MySQL settings - You can get this info from your web host ** //

	/** The name of the database for WordPress */
	define('DB_NAME', 'database_name_here');


	/** MySQL database username */

	define('DB_USER', 'username_here');


	/** MySQL database password */
	define('DB_PASSWORD', 'password_here');

	/** MySQL hostname */
	define('DB_HOST', 'localhost');


	/** Database Charset to use in creating database tables. */

	define('DB_CHARSET', 'utf8');

	/** The Database Collate type. Don't change this if in doubt. */ 

	define('DB_COLLATE', '');
	
	```
	___Next, you need to restart the web server and MySQL service with the following command:___
	```
	$ sudo systemctl restart apache2.service 
	$ sudo systemctl restart mysql.service
	```
	
	
