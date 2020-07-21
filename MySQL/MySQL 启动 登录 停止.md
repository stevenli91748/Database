

# 启动 

style 1:

bin\> net star mysql81 (that is service name mysql81 , not database name)


style 2:

go to windows service, looking for the mysql service name , for example: mysql81 . change the state by hand


# 登录

style 1:

bin\> mysql -u root -p

enter password:

or 

style 2:

bin\> mysql --user=root --password=gz19731108

mysql>

# 停止

style 1:

bin\> net stop mysql81 (that is service name mysql81 , not database name)


style 2:

go to windows service, looking for the mysql service name , for example: mysql81 . change the state by hand

