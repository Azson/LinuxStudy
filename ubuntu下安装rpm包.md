Ubuntu的软件包格式是deb，如果要安装rpm的包，则要先用alien把rpm转换成deb。

sudo apt-get install alien #alien默认没有安装，所以首先要安装它

sudo alien xxxx.rpm #将rpm转换位deb，完成后会生成一个同名的xxxx.deb

sudo dpkg -i xxxx.deb #安装

注意，用alien转换的deb包并不能保证100%顺利安装，所以可以找到deb最好直接用deb 

具体过程：
1. 先安装 alien 和 fakeroot 这两个工具，其中前者可以将 rpm 包转换为 deb 包。安装命令为：

sudo apt-get install alien fakeroot

2. 将需要安装的 rpm 包下载备用，假设为 package.rpm。

3. 使用 alien 将 rpm 包转换为 deb 包：

fakeroot alien package.rpm 
