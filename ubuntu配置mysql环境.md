##1.下载必要的包
sudo apt-get isntall mysql-server 
###据说按照上述命令之后是不需要安装mysql-client的，我是继续安装了mysql-client
期间会提示设置root用户的密码

##2.测试是否安装完成
service myusql start 启动mysql服务

sudo netstat -tap|grep mysql 查看mysql是否在运行

进入mysql界面
mysql -uroot -p
然后输入密码即可


##3.遇到一些问题

###1.无法打开mysql,报错
ERROR 2002 (HY000): Can't connect to local MySQL server through socket  '/var/lib/mysql/mysql.sock' (2)

原因是.sock文件没有配置对，先找到mysql.sock 或者 mysqld.sock 的位置
find / -type s 2> /dev/null
网上大部分说是找mysql.sock，我也是没找到，才用了mysqld.sock

然后修改配置文件
gedit /etc/my.cnf

修改sockt的值为你找到的.sock文件路径

重启服务即可

####2.设置数据库的编码方式
进入数据库后，输入
show variables like "char%"
可以显示charset的设置表，有的不是utf8
在数据库中设置重启后又回复原样
可以永久设置，输入
sudo gedit /etc/mysql/mysql.conf.d/mysql.cnt
在文件内容的[mysqld]添加一行
character_set_server=utf8
保存重启服务，即可生效

####3.完全卸载Mysql
依次键入命令
sudo apt-get autoremove mysql* --purge
sudo apt-get remove apparmor 
sudo rm /var/lib/mysql/ -R  //非常重要
sudo rm /etc/mysql/ -R   //非常重要




