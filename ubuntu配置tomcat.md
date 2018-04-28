##1.下载tomcat
官网：http://tomcat.apache.org/download-80.cgi#8.5.9
我们下载的是tar.gz格式的压缩文件

##2.解压
sudo tar -zxvf apache-tomcat-8.5.9.tar.gz
把最后一个参数改成自己下载好的版本即可

可以将解压文件复制到自定义的文件夹中
新建的文件夹最好改变下权限，避免访问失败
chmod 777 -R tomcat
数字参数为3bit，从高位到低位分别表示 可读，可写和可执行
有3个这样的数字限制了各个用户，从左至右表示 所有者，组用户和其他用户
-R表示对该文件及其所有子目录都修改权限，所以要注意别只修改了当前文件夹的权限了

##3.配置
进入 /apache-tomcat-8.5.9/bin 的目录，修改startup.sh的内容
在最后面添加

export JAVA_HOME=/usr/java/jdk1.8.0_111
export JRE_HOME=${JAVA_HOME}/jre
export CLASSPATH=.:%{JAVA_HOME}/lib:%{JRE_HOME}/lib
export PATH=${JAVA_HOME}/bin:$PATH

export TOMCAT_HOME=/usr/tomcat/apache-tomcat-8.5.9

###注意把java和tomcat对应的目录改成自己机器上的

##4.测试
sudo ./startup.sh
.sh文件运行要在其前面加上 ./

运行成功后即可在浏览器上输入 localhost:8080 访问
可以在server.xml文件修改tomcat的启动端口和IP
