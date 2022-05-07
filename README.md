# Create 2 VM 
- Server : 192.168.1.8 (change the ip depand on your network)
- Client : 192.168.1.3 (change the ip depand on your network)

# On Server 

- Install mariadb :
     sudo yum install mariadb-server 
- Startand enable mariadb service
    	sudo systemctl enable --now mariadb
- Secure MariaDB installation
  - sudo mysql_secure_installation
    - 1st Question: No root password
		- Press Y
		- Input your password (mysql root)
		- Y on remove anonymous users
		- Y on Disallow root login remotely
		- Y remove test database
		- Y on reload privilege table
- Login to mysql server
    - mysql -u root -p
    - type your password
    - create database roundcubemail;
    - create user roundcubemail@<type here the client ip>192.168.1.3 identified by 'password';
    - grant all privileges on roundcubemail.* to roundcubemail@192.168.1.3; <type the client ip>
    - flush privileges;

	
# On Client 

- yum install -y podman
- podman pull roundcube/roundcubemail
	
	```
	hfghjgfjhg
