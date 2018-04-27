#问题来源
1.下载软件很慢，因为使用了国外的源
2.使用apt出现无法定位包的错误

##添加163源（当然还有其他的如阿里的源）
1.编辑文件   /etc/apt/sources.list

2.修改文件内容如下：
deb http://mirrors.163.com/ubuntu/ precise main universe restricted multiverse 
deb-src http://mirrors.163.com/ubuntu/ precise main universe restricted multiverse 
deb http://mirrors.163.com/ubuntu/ precise-security universe main multiverse restricted 
deb-src http://mirrors.163.com/ubuntu/ precise-security universe main multiverse restricted 
deb http://mirrors.163.com/ubuntu/ precise-updates universe main multiverse restricted 
deb http://mirrors.163.com/ubuntu/ precise-proposed universe main multiverse restricted 
deb-src http://mirrors.163.com/ubuntu/ precise-proposed universe main multiverse restricted 
deb http://mirrors.163.com/ubuntu/ precise-backports universe main multiverse restricted 
deb-src http://mirrors.163.com/ubuntu/ precise-backports universe main multiverse restricted 
deb-src http://mirrors.163.com/ubuntu/ precise-updates universe main multiverse restricted

3.依次键入下列命令
sudo apt-get clean
sudo apt-get update
sudo apt-get upgrade

4.然后可以在  系统设置->软件更新 部分看到更新的情况
