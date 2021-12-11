

# centos 7  默认带Mariadb

    查看是否安装： rpm -qa|grep mysql（或者Mariadb）

    安装：# yum install mariadb-server -yyum -y install  mariadb-server mariadb

    或者#yum -y install  mariadb-server mariadb

    # systemctl start mariadb.service

    # systemctl enable mariadb.service

    # mysql进入命令行

# 在centos 8上安装MySQL

* [centos8安装mysql8.0.22教程(超详细)](https://blog.csdn.net/qq_39150374/article/details/112471108)

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
        
  1.7 启动mysql
  
       [root] systemctl start mysqld.service   //启动命令
       [root] service mysqld status // 查看MySQL 是否安装好

<a href="https://ibb.co/Fz6sYcs"><img src="https://i.ibb.co/JHnxp8x/mysql123.png" alt="mysql123" border="0"></a>
           
