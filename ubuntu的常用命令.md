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

##后台运行程序
一般来说可以之间在命令尾部加上符号“&”，表示放到一个作业队列

然后可以通过命令"jobs -l"查看到作业队列的情况

第二种方法是直接通过命令运行后，按下“ctrl+z”让进程暂停，然后通过"bg"命令+作业号（可以通过"jobs"命令查看作业号）将停止的程序放到后台运行

如果要将后台程序放到前台，可以通过"fg"命令+作业号

##环境变量
可以键入命令“env”查看环境变量

键入命令“echo $PATH”即可查看PATH变量的值

如将路径“/usr/lib/python3.6”添加到PATH变量最前面，可以
键入命令“export PATH=/usr/lib/python3.6:$PATH”，
放到最后面，可以键入命令“export PATH=$PATH:/usr/lib/python3.6”

##编译运行C/c++程序
对于C++确保安装了g++,C确保安装了gcc

如对hello.c/hello.cpp

键入命令"g++/gcc hello.c/hello.cpp -o a.out"即可在当前目录下生成脚本文件"a.out"

键入命令"./a.out"即可运行

#注意事项
##自带的python别乱删……想玩其他版本的可以配置虚拟环境
如果真手贱删了，请尝试下面的办法：
按ctrl+alt+f1进入控制台 //按ctrl+alt+f7 回到桌面
登录后，输入sudo apt-get install ubuntu-minimal ubuntu-standard ubuntu-desktop

