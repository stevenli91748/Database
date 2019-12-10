
# centos 7  默认带Mariadb

    查看是否安装： rpm -qa|grep mysql（或者Mariadb）

    安装：# yum install mariadb-server -yyum -y install  mariadb-server mariadb

    或者#yum -y install  mariadb-server mariadb

    # systemctl start mariadb.service

    # systemctl enable mariadb.service

    # mysql进入命令行

# 在centos 7上安装MySQL

    第一步  centos默认安装了mariadb，因此，在安装mysql之前，需要卸载系统中安装的mariadb。
           查看系统中所有已安装的mariadb包。命令：rpm -qa | grep mariadb
           卸载mariadb。命令：rpm -e "mariadb的包名"。
           若依赖包检测失败，可以使用强制卸载的命令：rpm -e --nodeps "mariadb的包名"
           
    第二步  安装可用的rpm包
           [root]# rpm -Uvh http://dev.mysql.com/get/mysql-community-release-el7-5.noarch.rpm
  
    第三步  查看可用安装资源
           [root]# yum repolist enabled | grep "mysql.*-community.*"
           
    第四步  安装
           [root]# yum -y install mysql-community-server
           
    第五步  配置
    
           开启启动
               [root]# systemctl enable mysqld

           启动MySQL服务
               [root]# systemctl start mysqld
    
           设置密码
               [root]# mysql_secure_installation
               
           设置密码的过程中，有一些需要注意的点如下所示：
               1、Set root password? [Y/n] y        [设置root用户密码]
               2、Remove anonymous users? [Y/n] y            [删除匿名用户]
               3、Disallow root login remotely? [Y/n] n            [禁止root远程登录]
               4、Remove test database and access to it? [Y/n] y       [删除test数据库]
               5、Reload privilege tables now? [Y/n] y        [刷新权限]

     第六步  远程客户端访问
               [root]# mysql -uroot -p       [密码]
               mysql> GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY '123456' WITH GRANT OPTION;

           
