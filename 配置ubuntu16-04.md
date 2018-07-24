### 配置环境   
#### 目录语言
在安装ubuntu时，我们选择了中文，如果直接使用，在终端上会需要切换中文输入法，输入**桌面**，这样很麻烦。  
需要把文件配置设为英文，方法如下：  
打开终端，跟着步骤来，记得把这篇文章收藏到书签哦。  
输入```export LANG=en_US``` 将语言环境设为英文。  
输入``` xdg-user-dirs-gtk-update```更新配置  
然后会出现一个对话框，问你是否把目录转为英文，点击同意。  
输入``` export LANG=zh_CN```将语言环境设为简体中文   
收藏本篇博文后，重启电脑。  
重启进入电脑后会出现一个对话框，系统会问你是否把目录设为中文，  
**勾选不再提示**，点击保留原来的目录。ok，搞掂。  
#### 更换软件源  
按下Win键，输入```setting```点击齿轮的图标   
看到系统栏有个**软体和更新**，点击它。  
里面有个**下载自：中国的服务器**， 点击它，选择其他站点。  
然后找到阿里云的链接**mirrors.aliyun.com**,选择它，输入密码后，关闭。  
最后点击**重新载入**，等待运行完毕即可。  
#### 设置root密码
打开终端
按下：```Ctrl``` + ```Alt``` + ```T```  
输入```sudo passwd root```  
输入两次你要设置root账户的密码  
再输入```su root```测试是否能进入root模式  
出现‘#’号说明成功了  
切换到普通用户 ```su username```这里的username是你自己装机时设定的用户名。  
忘记的话看一下上面的终端命令@前面的字符就是你的普通用户名。（当然可以强制关闭终端再开启终端恢复普通用户）
### 优化ubuntu  
#### 删除多余的软件
##### 删除LibreOffice（自主选择）  
这个软件相当于office三件套，博主win7中有正版的Office，需要时切回win7系统即可，卸载该软件也可以在后面装wps  
```sudo apt remove libreoffice-common```  
##### 删除不常用的自带软件  
```sudo apt-get remove thunderbird totem rhythmbox simple-scan gnome-mahjongg aisleriot gnome-mines cheese transmission-common gnome-orca webbrowser-app gnome-sudoku onboard deja-dup```   
上面那一大堆代码要一次复制完哦。  

#### 安装常用的软件  
这里先说一下终端安装软件的命令  
```sudo apt-get install xxxx```  
xxxx是软件名   
##### 安装 tree  
```sudo apt-get install tree```  
这个软件时可以查看目录的树结构  
##### 安装vim
```sudo apt-get install vim```  
这个软件是博主很少用，不过还是安装一个。这是文本编辑器。  
##### 安装deb包管理工具GDebi  
```sudo apt-get install gdebi```
这个软件在安装deb安装包时会自动下载包所需要的依赖  
右击的deb包，选择**打开方式**，然后点击**GDebi软件包安装**即可。  
博主觉得好用的deb包都放到了百度网盘（需要地址）  
注意，搜狗输入法不建议安装，打字打多了的话时不时会报错需要重启后方可使用，找不到原因。  
##### 安装git
```sudo apt-get install git```  
具体配置方式可以看我在github上wiki的文章，这里请**右键打开新的标签页打开链接**  
##### 火箭家族产品安装
博主是使用Python为主，这里以PyCharm为例  
*方法一*：  
到[Toolbox App](http://www.jetbrains.com/toolbox/app/)点击**Download**
双击运行里面的**jetbrains-toolbox**  
选择自己需要的**IDE**和版本下载  
*方法二*：
到IDE的官网下载压缩包安装[PyCharm](http://www.jetbrains.com/pycharm/download/#section=linux)
下载完成后把压缩包解压到你想放的目录（最好创建一个专门的目录放置）  
进入到解压后的文件夹（这里以PyCharm为例）  
```cd home/sing/jet/pycharm-2017.2.3/bin```  
*这里也可以打开bin的目录，右键-->在终端打开-->输入以下代码*     
运行 pycharm.sh 找以**sh**结尾的文件，其他编辑器也一样  
终端输入```.pycharm.sh```   
即可运行。
### 美化
#### 安装unity-tweak-tool
```sudo apt-get install unity-tweak-tool ```
可以到这位博主写的文章[不美翻怎么开发!Ubuntu 16.04 LTS深度美化!(2017年度定稿版)](https://www.jianshu.com/p/4bd2d9b1af41)
里面有很多漂亮的主题和字体可以预览再选择下载，然后通过**unity-tweak-tool**进行设置。
#### 安装oh-my-zsh  
系统自带的终端太样衰了，把它弄漂亮点。  
**安装zsh**  
```sudo apt-get install zsh```  
**设置zsh为默认shell，如果提示权限不够，在开头加上sudo**  
```chsh -s $(which zsh)```    
重启前请确认没有在下载文件，有文件修改未保存的，不然后果就是这篇博文就写了两次。  
**打开终端看一下效果**  
是否如下图所示   
**$**需要图片  
**安装curl**  
 这里需要curl下载oh-my-zsh  
 ```sudo apt-get install curl```  
 **下载oh-my-zsh**  
 ```sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"```  
**更换oh-my-zsh主题**  
 安装完成后，选择喜欢的主题吧，可到[oh-my-zsh主题](https://github.com/robbyrussell/oh-my-zsh/wiki/Themes)进行预览，选择好喜欢的主题，把名字记下。  
 ```sudo gedit  ~/.zshrc```  
 然后按下```Ctrl``` + ```F``` 搜索**ZSH_THEME="robbyrussell"**，把robbyrussell替换成喜欢的主题名字，博主选择的时**ys**这个主题。
 ### 最终效果
 如图所示
 **需要图￥**  
最后输入
```sudo apt update && sudo apt upgrade```
