#ubuntu16.04配置java环境

##1.先进入官网下载需要的jdk版本
网站：http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html

##2.解压下载得到的tar.gz文件到指定目录
tar -zxvf jdk-8u171-linux-x64.tar.gz
将解压后的文件夹copy到指定目录
cp -a jdk1.8.0_171 /usr/lib/jvm

###3.配置环境变量
sudo gedit /etc/profile
在文件的末位添加
export JAVA_HOME=/usr/lib/jvm/jdk1.8.0_171
export JRE_HOME=/usr/lib/jvm/jdk1.8.0_171/jre
export CLASSPATH=.:$CLASSPATH:$JAVA_HOME/lib:$JRE_HOME/lib
export PATH=$PATH:$JAVA_HOME/bin:$JRE_HOME/bin

####上述路径改成自己的即可


###4.输入java -version进行测试

###5.没安装成功
sudo update-alternatives --install /usr/bin/java java /usr/lib/jvm/jdk1.8.0_171/bin/java 300
sudo update-alternatives --install /usr/bin/javac javac /usr/lib/jvm/jdk1.8.0_171/bin/javac 300
sudo update-alternatives --config java

该方案是解决当前用户无法使用java的情况，将配置更新到当前用户

###6.编码
vim hello.java //建立java文件
javac hello.java  //编译class文件，并且生成和class文件中类名相同的文件
java hello //运行

