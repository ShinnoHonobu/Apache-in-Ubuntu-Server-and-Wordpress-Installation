![PP19](https://github.com/ShinnoHonobu/Apache-in-Ubuntu-Server-and-Wordpress-Installation/assets/113822318/b9d24a52-4d38-4eb8-8f18-e0eccb88e445)![PP14](https://github.com/ShinnoHonobu/Apache-in-Ubuntu-Server-and-Wordpress-Installation/assets/113822318/389f0311-a899-4b9c-8ee3-11e8808940e8)# Apache-in-Ubuntu-Server-and-Wordpress-Installation
This repository contains how to Install and configure Ubuntu Server and Install Wordpress in Ubuntu Server

## Steps to Install Apache Hadoop on Ubuntu Server
1. Make sure Ubuntu Server has been installed, which in this experiment was installed on Virtualbox, and SSH has been installed on Ubuntu Server and make sure the connected network is in a stable condition
2. Before downloading Apache, it is best to update the package repository first to ensure that the available version is up to date/updated with the command below.
	```
	sudo apt update
	```

3. Then, install Apache with the command below.
   	```
	sudo apt install apache2
	```

	However, make sure that the connected connection has sufficient data packets because later it will use up the resources of the connected data packets.
4. After Apache is installed, Apache needs to be activated first to ensure whether the existing Apache is running properly with the command below.
	```
	sudo systemctl start apache2
	```

	To save time in the future by automatically activating Apache every time you boot, you can use the command below.
	```
	sudo systemctl enable apache2
	```
5. Next, check the status of Apache to see if it is running properly with the command below.
	```
	sudo systemctl status apache2
	```
6. Make sure that Apache is running and can be checked via a Web Browser. Before that, it is important to find out the IP of the Ubuntu Server that is running, with the command below.
	```
	hostname -I
	```
7. Then, check in the browser (which this time is done in Google Chrome) by entering the IP of the running Ubuntu Server, so that a display like the one below appears.
	![PP7](https://github.com/ShinnoHonobu/Apache-in-Ubuntu-Server-and-Wordpress-Installation/assets/113822318/577fe4ec-6805-499d-bd67-82bd4c92a83a)

8. Apache Hadoop has been installed on Ubuntu Server

## Steps to run a Remote Server on Ubuntu Server
1. Make sure Ubuntu Server has been installed, which in this experiment was installed on Virtualbox, and SSH has been installed on Ubuntu Server and make sure the connected network is in a stable condition. And of course Ubuntu Server must be active.

2. Before starting remotely on the server, you need to find out the IP of the Ubuntu Server you are running, with the command below.
	```
	hostname -I
	```

3. First of all, you can remote the Ubuntu Server via Command Prompt from Windows, with the command below.
	```
	ssh master@192.168.56.111
	ifconfig
	```

4. Then, remote server can also be done in PuTTY, with the command below.
	![PP9](https://github.com/ShinnoHonobu/Apache-in-Ubuntu-Server-and-Wordpress-Installation/assets/113822318/30eb471b-eb12-49ec-bdeb-d9c17bf02af5)
	```
	ssh master@192.168.56.111
	ll
	```
	![PP10](https://github.com/ShinnoHonobu/Apache-in-Ubuntu-Server-and-Wordpress-Installation/assets/113822318/f018fbaa-7fe3-4f0e-a864-783120b07ca6)

5. Apart from that, remote server can also be done on Ubuntu Desktop, with the same command as remote in CMD as below.
	![PP11](https://github.com/ShinnoHonobu/Apache-in-Ubuntu-Server-and-Wordpress-Installation/assets/113822318/d51fc68f-4ad0-428b-b030-938923f81b58)
	```
	ssh master@192.168.56.111
	ls
	```

## Steps to Install Wordpress on Ubuntu Server
1. Make sure Ubuntu Server has been installed, which in this experiment was installed on Virtualbox, and SSH has been installed on Ubuntu Server and make sure the connected network is in a stable condition

2. Before downloading WordPress, it is best to update the package repository first to ensure that the available version is up to date/updated with the command below.
	```
 	sudo apt update
	```

3. Then, install MySQL with the command below.
	```
  	sudo apt install mariadb-server mariadb-client
	```
	However, make sure that the connected connection has sufficient data packets because later it will use up the resources of the connected data packets.

4. After WordPress is installed, WordPress needs to be configured for initial handling first with the command below.
	```
  	sudo mysql_secure_installation
	```
	After the command is input, there are several guidelines that need to be followed. Just adjust it to user needs.

5. Next, install PHP with the command below.
	```
  	sudo apt install php php-mysql libapache2-mod-php
	```

6. Make sure PHP is installed and can be tested using WordPress with the command below.
	```
  	cd /var/www/html/
	sudo nano info.php
	<?php phpinfo(); ?>
	```
	Then check the Web Browser (in this experiment using Google Chrome) to test the PHP with the command below.
	![PP8](https://github.com/ShinnoHonobu/Apache-in-Ubuntu-Server-and-Wordpress-Installation/assets/113822318/73433204-5b17-4d26-ace6-c9c75009b534)

7. Then, log in to the installed MySQL with the command below and enter the command for the database.
	```
	mysql -u root -p
 	CREATE DATABASE wordpress_db;
 	CREATE USER 'wp_user'@'localhost' IDENTIFIED BY 'password';
	GRANT ALL ON wordpress_db.* TO 'wp_user'@'localhost' IDENTIFIED BY 'password';
	FLUSH PRIVILEGES;
 	Exit;
	```

8. Then, download and extract the latest version of WordPress with the command below.
	```
	sudo wget https://wordpress.org/latest.tar.gz
	sudo tar -xvf latest.tar.gz
	```
	Later the Wordpress folder will appear in the html directory.
	![PP13](https://github.com/ShinnoHonobu/Apache-in-Ubuntu-Server-and-Wordpress-Installation/assets/113822318/06601556-94bf-4cd2-b5bd-a7306af44d4b)

9. Next, change the WordPress folder permissions and add the uploads folder with the command below.
	```
 	sudo chown -R www-data:www-data wordpress/
 	sudo chmod -R 755 wordpress/
	sudo mkdir wordpress/wp-content/uploads
 	sudo chown -R www-data:www-data wordpress/wp-content/uploads/
	```
10. Then, install WordPress via a Web Browser, with a display like the one below.
	![PP14](https://github.com/ShinnoHonobu/Apache-in-Ubuntu-Server-and-Wordpress-Installation/assets/113822318/0a0e04b5-0425-4362-bc8f-59dfc9589ab9)

11. For the image below, you can fill in the columns with the database and user account that was previously created in MySQL.
	![PP15](https://github.com/ShinnoHonobu/Apache-in-Ubuntu-Server-and-Wordpress-Installation/assets/113822318/aaf89208-0fc1-4e75-90d8-fe7e30dc129b)

12. Enter the Web name, Username and Password as desired as shown below.
	![PP17](https://github.com/ShinnoHonobu/Apache-in-Ubuntu-Server-and-Wordpress-Installation/assets/113822318/a128357f-ffb3-4c3e-b8c2-92dfbd8e6295)

13. Then, re-enter the Username and Password with the display below.
	![PP19](https://github.com/ShinnoHonobu/Apache-in-Ubuntu-Server-and-Wordpress-Installation/assets/113822318/3e70d77a-b520-4757-856b-72a895e29f64)

14. WordPress has been installed perfectly if it looks like the one below.
	![PP20](https://github.com/ShinnoHonobu/Apache-in-Ubuntu-Server-and-Wordpress-Installation/assets/113822318/62b0f317-9f92-49e2-861a-fcc99904967c)

## Example Post in Wordpress
Here are the example of the feeds in Wordpress : 
	![PP22](https://github.com/ShinnoHonobu/Apache-in-Ubuntu-Server-and-Wordpress-Installation/assets/113822318/75b46a05-2122-453c-b587-ac2fca13772a)
	![PP21](https://github.com/ShinnoHonobu/Apache-in-Ubuntu-Server-and-Wordpress-Installation/assets/113822318/d0d174e2-f19c-47fd-840d-157b665b01b2)

