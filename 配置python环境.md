### 使用Anaconda安装python3.6
Ubuntu16.04已经自带了python2.7和python3.52,但配置它们很麻烦，讲一下我之前配置它们俩遇到的难题吧。  
首先，在升级pip的时候，会使pip无法使用，需要配置环境变量的文件。有时候还会安装失败。  
但是使用了Anaconda安装新的python3.6这些统统不是问题。  
而且通过安装Anaconda会自动安装上**jupyter notebook**  
jupyter notebook真的是个神器，后面我会教大家怎么配置主题，使用方面我也会推荐一些视频教程。  
那就先安装了再说吧。  
到[Anaconda](https://www.anaconda.com/)的点击右上角的下载，然后选择适合自己版本的下载按钮进行下载。  
下载好后进入到文件所在的目录，右键->打开终端->执行命令`bash Anacondaxxxxx`这里用xxxx时因为博主不知道你们下载文件是什么版本。    
你们可以先输入`bash Anacoda`然后按一下`Tab`就可以补全后面的内容了。  
运行代码后，根据提示按下回车，直到提示你输入**yes or no**,  
这里毫无意外肯定是输入**yes**
等待它安装，中途会询问你安装到那个文件夹，正常按下`回车`即可，安装到用户的根目录下。  
如果你有其他需求可以设定其他的目录下。  
继续等待安装，然后又出现一个对话框问你是否把Anaconda添加到环境变量中，选择**yes**  
最后，Anaconda安装完成后会询问你是否安装**VScode**，这个根据自身需求吧。博主没有安装，输入**no**即可。  
### 检查是否安装Anaconda成功  
新开一个终端，输入`python`看一下版本号，如果是python3.6说明成功。  
如果是python2.7说明跟博主的情况一样，因为博主之前安装了**oh-my-zsh**。  
Anaconda的环境变量未加入到zsh的环境变量中。  
需要执行两条命令  
请确保终端是在用户的根目录  
新开一个终端就是在根目录下或者输入`cd /..`  
下面的第一条命令中username是要更改成你的用户名，注意一下哟。   
`echo 'export PATH="/home/username/anaconda3/bin:$PATH"' >> ~/.zshrc`    
`source ~/.zshrc`  
再次在终端输入**python**就会发现python的版本时3.65了。  
退出python的交互模式可以输入`exit()`  
### 什么是虚拟环境？  
初学者可以浏览下这里的内容，大神的话可以点击右边的目录跳到下一章节。  
什么是虚拟环境？，这个问题我们可以换一种说法。**为什么需要虚拟环境？**  
这里我举个博主以前犯过的错误，作为栗子。  
博主以前呢，安装python的库都是直接在终端输入`pip3 install xxxx`，这是在**全局环境**中使用python3。    
一直以来，从来未翻过车。直到有一天，博主在用Django2.0做这个博客时，发现在后台的编辑器太丑了，想安装一个可以预览输出效果的markdown编辑器，网上搜了一下，发现有一款编辑器django-mdeditor很好看，于是乎直接`pip3 install django-mdeditor`。  
然后根据网上的教程进行项目配置，突然，整个项目无法运行。  
报错信息是找不到项目的路由配置。（Django2.0和其他1.x版本最大的区别在于路由的路径方法名一个是用path，一个是用url）  
但是那时候，博主不知道发生了什么事情，只能不断的查资料，想修复这个问题。  
后来才发现，原来是**django-mdeditor**不支持Django2.0。而且在安装django-mdeditor的过程中把我原来的Django2.0降级为1.11,导致项目不能运行。  
而且，我原来的python3中很多的库也不能使用了（不知道为什么，找不到原因），这还没完，我的系统还经常报错和崩溃，只好把系统重装了一遍。   
看到这里如果还不明白的话，可以这样理解。  
**全局环境**就是一群人在吃火锅，什么菜都往里面放，如果说有个人叫A，他不吃内脏，然后你把毛肚、金钱肚、草肚往里面一放，那么A就不能和大家一起愉快的吃火锅了。  
**虚拟环境呢**，就像是在一群人去吃自助餐，每个人去拿个盘子和夹子，吃什么，夹什么到自己的盘子就行了。就不会出现说谁谁谁不吃香菜，不吃内脏的问题。  
### 创建虚拟环境  
这里有个分支，一种是用**conda**创建，一种是用**virtualenv**，建议两种都了解一下，因为后期如果把Django部署到服务器的话，需要用到virtualenv方便。conda是在使用爬虫、科学计算的时候比较好用。
#### 使用conda创建虚拟环境
`conda create -n venv3 python=3.6`  
上面这句代码的意思是，使用conda 创建一个名为venv3的虚拟环境，python的版本时3.6。  
激活虚拟环境  
`source activate venv3`  
激活后，你会发现终端命令的左边多了一个`(venv3)`就表明你在虚拟环境中。  
关闭虚拟环境  
`source deactivate`  
虚拟环境怎么使用，可以看博主的**python的web框架系列**的文章，现在讲也没什么用。  
#### 使用virtualenv创建虚拟环境  
这里声明一下，如果你是按照上面教程中使用了Anaconda安装了python3.6的话，你系统自带的python3.52要使用时需要在终端输入`python3.5` pip需要用`pip3.5`  
python2.7需要输入`python2` pip需要用`pip2`  
如果你没有通过上面教程安装anaconda的话，和原来不变。  
##### 安装
`sudo apt-get install python-virtualenv`  
`sudo apt-get install virtualenvwrapper`   
上面不需要指定python版本  
##### 使用
切换到你需要创建虚拟环境的目录  
博主这里写个例子  
在桌面创建了一个名为**python3_mysite**的目录  
进入到python3_mysite目录  
鼠标右键-->在终端打开  
`virtualenv -p /usr/bin/python3 venv`  
创建了一个基于**python3**名为**venv**的虚拟环境  

**启用虚拟环境**  
`source /home/sing/Desktop/python3_mysite/venv/bin/activate`   
然后你就可以发现在终端的左边多了一个**(venv)**  
说明启动成功了。  
**需要注意的地方**  
在虚拟环境中，安装库不要加上'sudo',也不需要'pip3 install xxxx'  
只需要`pip install xxxx`即可。  
不然的话会安装到全局的python中  
**退出虚拟环境**  
`deactivate`
***  
### jupyter notebook配置  
这里声明一下：以下的操作时针对使用了Anaconda安装python3.65的读者。   
首先安装**nb_conda**，这是可以让jupyter notebook使用虚拟环境的一个包。  
`conda install nb_conda`        
其实我们现在可以使用`jupyter notebook`这条命令开启jupyter notebook。    
开启后发现，它的主题是白色的，博主个人感觉很刺眼睛。    
让我们换个主题吧。  
终端按两下`Ctrl` + `C`就可以退出jupyter notebook了。    
首先安装jupyter-themes这个包    
`pip install jupyter-themes` 等待安装完成。    
输入`jt -l`这里的l是英语的小写L，不是1。    
查看有什么主题可以选择。  
更换主题命令`jt -t chesterish -T -N`  
**chesterish**是主题的名字。你也可以选择你喜欢的主题进行更换。  
具体的使用可以浏览博主的requests爬虫示例。  
最后，讲一下怎么让运行jupyter notebook后，让终端可以关闭也不会影响jupyter notebook服务的运行。  
启动jupyter notebook时使用下面的命令。  
`screen jupyter notebook`  
运行后，可以关闭这个终端，也不会影响jupyter notebook服务的运行。  
