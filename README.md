# Apache-in-Ubuntu-Server-and-Wordpress-Installation
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
