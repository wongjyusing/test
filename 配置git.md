### 什么是git?  
关于这个问题，我们可以换一个说法，为什么需要git？  
结合这个这篇博文，博主写了好几个版本，最后决定把这个版本发了上来。  
不使用git的话，我需要新建配置git0.md、git1.md、git2.md、git3.md……  
最后再从中挑选一个版本发布出来给大家浏览。  
但博主使用了git的话，我只需要生成一个文件，然后通过git生成几个分支，就可以进行版本控制了。而且还可以查看博主之前做了什么操作，修改了什么内容。  
### 安装git和配置github  
`sudo apt-get install git`  
博主不喜欢讲理论，习惯先实践再谈理论。  
单纯使用本地的git操作很难看到做了什么，先请大家到[GitHub](https://github.com/)注册一个github帐号。(注意使用右键->在新的标签页打开链接)  
把终端的目录切换到根目录下。  
输入`ls -a`  
查看是否有.ssh这个目录，有的话再进去看看有没有id_rsa和id_rsa.pub这两个文件。  
如果有的话，那就点击右边的目录跳到下一章节。  
像博主一样没有的话跟着步骤来。  
确认你的终端在根目录下。  
输入`ssh-keygen -t rsa -C "youremail@example.com"`  
请把youremail@example.com改成你自己的邮箱。  
再次输入`ls -a`  
看到多了一个.ssh这个目录。  
输入命令`cd .ssh`进入该目录  
输入`ls`看到有id_rsa和id_rsa.pub这两个文件。  
id_rsa是私钥，不能让其他人知道哟，id_rsa.pub是公钥，这个可以放心告诉别人。  
使用命令`gedit id_rsa.pub`打开这个文件，复制里面的所有内容后，关闭这个文件。
***
登录到你的github后。  
点击你的头像后，会出现一个下拉式窗口，点击里面的**Settings**  
跳转到你的个人设置页面。  
左边有个**SSH and GPG keys**，点击它，进入到里面去。  
右上角有个绿色的New SSH key按钮,按下它，会让你填入title和SSH这两个信息。  
title可以随便填。  
SSH要填入刚才你从id_rsa.pub的内容。  
好了搞定。  
注意，记得去注册github的邮箱中验证你的邮件。  
### 创建你的第一个远程代码仓库   
首先，在你的桌面上创建一个目录，名为**test**。  
然后在你的github上创建一个的仓库，点击**New repository**  
填入仓库名，填写test，其他的都不用填，点击**Create repository**  
进入到test目录，右键->开启终端  
依次输入以下代码：
```
echo "# test" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/wongjyusing/test.git
git push -u origin master
```
注意`git remote add origin https://github.com/wongjyusing/test.git`里面的地址换成github给你的地址。  
