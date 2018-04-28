##ps命令
参数：
-a 所有进程，但只有本终端
-u 按用户排列
-x 所有终端的进程
可以叠加使用，如
ps -aux


##service
查看所有服务
service --status-all

对服务进行操作
如对mysql服务 关闭|启动|重启
service mysql stop|start|restart  


##cp
普通的复制直接 
cp a b
a,b可以为文件的路径

复制整个目录
cp -a dir1 dir2

##rm
普通的删除直接
rm path

删除目录
rm -r -f dir

##find
find / -name virtualenvwrapper.sh
s

##ls
ls -a 显示所有文件
ls -l 显示所有文件的详细信息

##stat
stat file 查看文件的外部属性


#注意事项
##自带的python别乱删……想玩其他版本的可以配置虚拟环境
如果真手贱删了，请尝试下面的办法：
按ctrl+alt+f1进入控制台 //按ctrl+alt+f7 回到桌面
登录后，输入sudo apt-get install ubuntu-minimal ubuntu-standard ubuntu-desktop

