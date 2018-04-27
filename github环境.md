##一、安装环境
1.在github网站上先创建好账号

2.使用命令安装git
sudo apt-get install git

3.键入命令 
ssh-keygen -t rsa -C "邮箱地址"
然后会在账户的目录下创建 .ssh文件夹，里面有id_rsa 和 id_rsa.pub 两个文件
可以键入命令之后通过返回的信息 查看.ssh文件目录

4.在github网站的setting界面中，选择
SSH and GPG keys 
然后New SSH key

设置好title,并把id_rsa.pub的内容复制到key中，添加成功

5.测试是否成功
sst -T git@github.com

6.配置Git的个人信息
git config --global user.name "your name" //配置用户名

git config --global user.email "your email" //配置email 

##二、创建本地仓库并上传
1.进入需要上传文件的目录键入
git init
即可生成初始化文件

2.创建一个本地仓库origin，使用命令 “git remote add origin git@github.com:yourName/yourRepo.git”
youname是你的GitHub的用户名，yourRepo是你要上传到GitHub的仓库

3.比如你要添加一个文件xxx到本地仓库，使用命令 “git add xxx”，可以使用“git add .”自动判断添加哪些文件

然后把这个添加提交到本地的仓库，使用命令 ”git commit -m ”说明这次的提交“ “

最后把本地仓库origin提交到远程的GitHub仓库，使用命令 ”git push origin master“

##三、克隆项目到本地
1.直接复制需要clone的项目的  HTTPS clone url，然后在本地键入
git clone url

2.更新本地的仓库
git fetch repositor

3.把更新的内容合并到本地分支，可以使用命令 “git merge origin/master”
如果你不想手动去合并，那么你可以使用： git pull <本地仓库> master // 这个命令可以拉去最新版本并自动合并

##四、分支管理
创建

1 创建一个本地分支： git branch <新分支名字>

2 将本地分支同步到GitHub上面： git push <本地仓库名> <新分支名>

3 切换到新建立的分支： git checkout <新分支名>

4 为你的分支加入一个新的远程端： git remote add <远程端名字> <地址>

5 查看当前仓库有几个分支: git branch

删除

1 从本地删除一个分支： git branch -d <分支名称>

2 同步到GitHub上面删除这个分支： git push <本地仓库名> :<GitHub端分支>

