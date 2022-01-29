

# centos 7  默认带Mariadb

    查看是否安装： rpm -qa|grep mysql（或者Mariadb）

    安装：# yum install mariadb-server -yyum -y install  mariadb-server mariadb

    或者#yum -y install  mariadb-server mariadb

    # systemctl start mariadb.service

    # systemctl enable mariadb.service

    # mysql进入命令行

# 在centos 8上安装MySQL

* [centos8安装mysql8.0.22教程(超详细)](https://blog.csdn.net/qq_39150374/article/details/112471108)
* [Centos7安装MySQL](https://www.cnblogs.com/niceyoo/p/11508919.html)
 
安装步骤如下:

  1.1 如果服务器之前安装过mysql请先卸载,我这里是用yum安装的，现在通过yum去卸载
        [root] yum remove -y mysql
        [root] find / -name mysql
        列出查询到的文件，使用如下命令删除每一个文件
        [root] rm -rf 

  1.2 卸载完成后，使用以下命令:
      下载mysql安装包:
        [root] yum install -y wget

        [root] wget https://dev.mysql.com/get/mysql80-community-release-el8-1.noarch.rpm

        [root] yum install mysql80-community-release-el8-1.noarch.rpm
 
  1.3 禁用CentOS8自带mysql模块
  
        [root] yum module disable mysql 
        
  1.4 安装mysql命令       
  
        [root] yum install mysql-community-server
        
  1.5 启动mysql
   
       [root] systemctl start mysqld.service   //启动命令
       [root] service mysqld status // 查看MySQL 是否安装好

<a href="https://ibb.co/Fz6sYcs"><img src="https://i.ibb.co/JHnxp8x/mysql123.png" alt="mysql123" border="0"></a>

  1.6 显示mysql的随机密码
  
      [root] grep 'temporary password' /var/log/mysqld.log
      
      密码是host:后面的一串字符
      
  1.7  登录并修改mysql密码
  
      [root] mysql -u root -p 
      password:
      
      mysql> ALTER USER 'root'@'localhost' IDENTIFITED BY 'Gz@19731108'    
      mysql> FLUSH PRIVILEGES
      mysql> exit

 1.8 Mysql8开放远程访问
 
      mysql> create user 'root'@'%' identified by 'Gz@19731108'; //1、先创建权限记录
      mysql> grant all privileges on *.* to 'root'@'%' with grant option; //2、授权
 
 1.9 开放防火墙端口      
 
     如果有防火墙，可按如下命令操作
     
     # 查看防火墙的规则
     [root] systemctl status iptables.service
     
     使用vi 对 /etc/sysconfig/iptables文件编辑, 在该文件添加一行代码
     
     [root] vi /etc/sysconfig/iptables
     
     -A INPUT -m state --state NEW -m tcp -p tcp --dport 3306 -j ACCEPT
     
     保存和重启防火墙
     
     [root] service iptables restart
     
1.10 使用 navicat 连解数据库

    host:   remote ip address   (example: visual machine ip addreee: 192.168.33.180)
    port:   3306
    user:   root
    paswword:  Gz@19731108
     
