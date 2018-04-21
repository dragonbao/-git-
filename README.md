1. 创建本地与github代码库连接：首先安装git到本地C盘，找到本地的id_rsa.pub文件 cmd输入 cd ~/.ssh 该文件在此目录下。

2. 打开文件id_rsa.pub 打开你的github账户 在设置中的SSH中复制。

3. 创建本地连接文件夹连接到你的github，先在github上创将一个空仓库，仓库名字与你的本地文件夹（将要与在线github连接的文件夹）同名。

4. github创建好仓库（repository）后，最好写以下readme.md文件，不写也没关系。
---------
  接下来转到本地操作。
  ---------
5.本地打开你要作为 git仓库的文件夹，cmd命令行今日该文件夹目录。比如我的文件夹在D盘下的gitdemo文件夹，那么命令为 cd D:/gitdemo

6.git --version 查看一下git是否安装成功。出现版本号代表安装成功，

7. git remote add origin git@"你自己的github网址"/你之前建好的空仓库名，如何看你的github网址——》打开你的github账号 地址栏就是了。
  &nbsp;&nbsp;比如我的是 git remote add origin git@github.com:dragonbao/空仓库名。
  
8. 将一些文件拷贝至本地的git仓库，此时这些文件在git仓库的工作区，命令行输入 git status 按下回车键，会见到相关提示信息，代表文件夹发生改变。
&nbsp;&nbsp;使用命令git add ./ 将本地仓库下所有文件添加进git 暂存区，使用命令：git commit -m "你自己的注释" 将文件推送至版本库。此时键入命令
git status 会&nbsp;&nbsp;看到提示 告诉你当前文件以你的远程版本库有文件差异，提示你做文件推送一消除差异。

9.写入命令：git push origin master 将本地版本库推动至github仓库，如果之前你在github中写了readme.md文件，
&nbsp;&nbsp;那么这里会报错：failed to push some refer to.........)，
&nbsp;&nbsp;原因就是因为本地仓库缺少了这个readme.md文件，输入命令git pull rebase origin master.回车执行成功会发现本地仓库多了一个readme.md文件.
&nbsp;&nbsp;此时重新执行git push origin master命令 ，此时打开你的github账户，找到同名仓库，不出意外的话在这里会看到你刚推送的本地文件。

10.将一个远程仓库克隆至本地子文件夹下命令：git clone git@要克隆文件的github地址/文件名.

11.一般来说如果版本仓库中存在以中文名称命名的文件或者文件夹，很大几率使用命令 git status 下看到的中文名称是乱码的，  
  &nbsp;&nbsp;在git仓库下写入以下命令解决  
  &nbsp;&nbsp;&nbsp;&nbsp;i:在git项目目录中执行git config core.quotepath false就可以解决了.  
  &nbsp;&nbsp;&nbsp;&nbsp;ii:也可以执行git config --global core.quotepath false进行全局设置.  

