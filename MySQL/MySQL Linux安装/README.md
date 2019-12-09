centos 7 不带MySql 要用Mariadb

查看是否安装： rpm -qa|grep mysql（或者Mariadb）

安装：# yum install mariadb-server -yyum -y install  mariadb-server mariadb

或者#yum -y install  mariadb-server mariadb

# systemctl start mariadb.service

# systemctl enable mariadb.service

# mysql进入命令行
