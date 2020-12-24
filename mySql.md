# Add user
```
SHOW GRANTS;
CREATE USER 'user_name'@'%' IDENTIFIED BY 'password';

GRANT ALL PRIVILEGES ON *.* TO 'user_name'@'%' WITH GRANT OPTION;
GRANT PROXY ON ''@'' TO 'user_name'@'%' WITH GRANT OPTION;
or
GRANT SELECT, INSERT, UPDATE, DELETE, CREATE, DROP, RELOAD, PROCESS, REFERENCES, INDEX, ALTER, SHOW DATABASES, CREATE TEMPORARY TABLES, LOCK TABLES, EXECUTE, REPLICATION SLAVE, REPLICATION CLIENT, CREATE VIEW, SHOW VIEW, CREATE ROUTINE, ALTER ROUTINE, CREATE USER, EVENT, TRIGGER ON *.* TO 'user_name'@'%' WITH GRANT OPTION;


```
# MySql 5.7, Amazon Linux2
```
sudo yum localinstall https://dev.mysql.com/get/mysql80-community-release-el7-1.noarch.rpm -y
sudo yum-config-manager --disable mysql80-community
sudo yum-config-manager --enable mysql57-community
sudo yum install mysql-community-server -y
mysqld --version

sudo systemctl start mysqld.service
sudo systemctl enable mysqld.service
systemctl status mysqld.service

$ cat /var/log/mysqld.log | grep password
A temporary password is generated for root@localhost: ************

mysql_secure_installation
Enter password for user root: ************
New password: @@@@@@@@@@@@
Re-enter new password: @@@@@@@@@@@@
Change the password for root ? ((Press y|Y for Yes, any other key for No) : No
Remove anonymous users? (Press y|Y for Yes, any other key for No) : Yes
Disallow root login remotely? (Press y|Y for Yes, any other key for No) : Yes
Remove test database and access to it? (Press y|Y for Yes, any other key for No) : Yes
Reload privilege tables now? (Press y|Y for Yes, any other key for No) : Yes
```
