Video Refering Refering : https://www.youtube.com/watch?v=Bof94c-TtqM

Google Cloud Setup Ubuntu, Nginx, MySQL , PHP5 & PHPMYADMIN 

Google Instance Setup:
1. Sign Trial & Login [All the credit card must be settle]
2. Create a project
3. Go to compute engine 
4. Create VM instance
	- Name [what instance name you want to give]
	- Region & Zone [what you want depend on what service you wanted]
	- Machine type [just choose low spec. You can scale after that.]
	- Boot disk [I prefer ubuntu. So I go with ubuntu-14.0]
	- Firewall [enable HTTP & HTTPS traffic]

SSH Command: 
- sudo apt-get update
- sudo apt-get install nginx
- sudo service nginx restart
- sudo apt-get install mysql-server php5-mysql
- sudo mysql_install_db
- sudo /usr/bin/mysql_secure_installation

- sudo service mysql restart
- sudo apt-get install php5-fpm
- sudo nano /etc/php5/fpm/php.ini
	- {search on nano command F6 or Ctrl+W}
	- search [cgi.fix_pathinfo=1]
	- uncomment
	- change [cgi.fix_pathinfo=0]
- sudo nano /etc/php5/fpm/pool.d/www.conf
	- check on [listen = /var/run/php5-fpm.sock]
- sudo service php5-fpm restart
- sudo nano /etc/nginx/sites-available/default
	- add to [server{index "index.php" index.html index.fm;}] 
	- uncomment 
		[location ~ \.php$ {
			fastcgi_pass unix:/var/run/php5-fpm.sock;
			fastcgi_index index.php;
			include fastcgi_params;
		}]
- cd /usr/share/nginx/html
- ls
- sudo nano index.php
	<?php
	phpinfo();
	?>
- sudo apt-get install phpmyadmin
	- setting password of the database administrative user
	- setting mysql application password for phpadmin
	
- sudo ln -s /usr/share/phpmyadmin /usr/share/nginx/html
- cd /usr/share/nginx/html
- sudo php5enmod mcrypt
- sudo service php5-fpm restart
