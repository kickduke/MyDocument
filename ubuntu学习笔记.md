#### *ubuntu学习笔记*
更新日期|内容
:---:|:---
2018-12-21|新建

##### **常用软件清单**
* fcitx+google/搜狗    输入法
* Gnome tweaks        桌面优化工具
* lantern             翻墙软件
* KolourPaint         简易绘图软件
* notepadqq           类notepad++文本编辑器
* gvim                文本编辑器
* typora              MD编辑器
* GoldenDict          字典  （[词典]-[网站]中添加http://dict.cn/%GDWORD%）
* hardinfo            查看系统配置
* vlc media player    视频播放
* git                 git
* screenfetch         终端界面显示系统信息
##### **更新nvidia显卡驱动**
				ubuntu-drivers devices   #查看设备及推荐驱动版本
				sudo ubuntu-drivers autoinstall   #使用ubuntu资源安装，推荐
				sudo apt-get install nvidia-390

##### **同步双系统时间**
				sudo apt-get install ntpdate
				sudo ntpdate time.windows.com
				sudo hwclock --localtime  --systohc
##### **修改grub引导等待时间**
				sudo gvim /etc/default/grub
				GRUB_TIMEOUT = 60
				sudo update-grub2
##### **修改grub默认进入的系统**
				cd  /boot/grub      
				修改grub.cfg文件权限:   sudo chmod a+w ./grub.cfg
				gvim ./grub.cfg
				修改set default = “0”改为默认启动的index，从0开始
##### **查看存储空间**
				df -hl
##### **解压zip,可以避免中文zip乱码**
				unzip -O CP936 filename.zip
##### **通过桌面打开目录**
				nautilus 目录       或  ./   
##### **安装tweaks桌面优化工具**
				sudo apt  install    gnome-tweaks
##### **安装新字体**
				cd /usr/share/fonts
				sudo mkdir YaheiConsolas
				cd YaheiConsolas
				sudo cp ~/下载/YaHei.Consolas.1.11.ttf
				sudo chmod 644 YaHei.Consolas.1.11.ttf  
				sudo mkfontscale
				sudo mkfontdir
				sudo fc-cache -fv
##### **休眠/挂起**
				pm-hibernate    sudo pm-suspend
##### **音频调整**
				alsamixer
				按M开关，上下调整大小。可解决插入耳机后没有声音的问题
##### **安装htop查看计算机硬件资源使用情况**
				sudo apt-get install htop
				htop
##### **切换到root用户/切换回普通用户**
				sudo -i
				su kqs
				Ctrl+Alt+F2~F6 可以切换到命令行终端，F1是默认图形界面
				命令行无法显示中文，需要安装zhcon，并在终端界面运行zhcon:
				sudo apt-get install zhcon
				sudo zhcon --utf8
##### **安装typora**
				sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys BA300B7755AFCFAE	
				sudo add-apt-repository 'deb http://typora.io linux/'
				sudo apt-get update
				sudo apt-get install typora
##### **安装Lantern翻墙软件**
				双击lantern-installer-64-bit.deb安装
				打开lantern即可
**Python3环境搭建**

```
sudo apt-get install python3   #安装python3
sudo apt-get install python3-pip   #安装pip3
sudo apt install ipython3           #安装ipython3
pip3 install module   #注意一定要用pip3,否则安装的都是python2的
```

游戏（终端）

```
sudo apt-get install bastet    #俄罗斯方块
sudo apt-get install greed     #greed
sudo apt-get install bsdgames  #unix游戏合集，如backgammon  atc等
telnet towel.blinkenlights.nl   #星球大战
ssh sshtron.zachlatta.com       #tron 联网游戏
```





----------
----------

##### **man查看命令/程序帮助**
				man 命令/程序
##### **info更详细的帮助文档**
				info 命令/程序
##### **ls打印文件列表**
				ls -lh
				ls -lha   #可以显示.开头的隐藏文件/目录
##### **通配符**
* *
    匹配0个或者多个字符;
* ?
    匹配一个字符
* [...]
    匹配[]里的某一个字符
* [a-z]
    匹配a到z的某一个字符
* [^...]
    匹配不包含在[]里的某一个字符
##### **whatis一句话显示命令用途**
				whatis 命令
##### **lshw查看硬件**
				lshw  
				sudo lshw -html > lshw.html    #将硬件信息保存到html文件中
##### **find查找文件**
				find . -iname 文件名      #查找当前及子目录下文件，不区分大小写
##### **which定位命令/程序的路径**
				which 命令
##### **pwd显示当前目录**
				pwd
##### **cp复制**
				cp -r 源 目的    #包括文件夹及子文件
##### **touch更新时间戳/创建新文件**
				touch filename    #如果文件存在，更新时间戳;否则创建新文件
##### **rm删除**
* rm -rf 文件名或文件夹
* ~~sudo rm -rf /*~~
##### **df查看文件系统空间**
				df -h
##### **free查看内存占用**
				free -h
##### **apt-get安装**
				sudo apt-get install 软件包
				sudo apt-get update     #刷新source列表，获取最新的软件包索引
				sudo apt-get upgrade    #更新所有软件，不建议使用
				sudo apt-get remove 软件包
##### **chmod文件权限管理**
				chmod ugo 文件名
				其中ugo为数字，分别对应user、group、other  具体含义如下：
					r=4   读
					w=2   写
					x=1   执行
					r+x=5 读执行
					r+w=6 读写
					r+w+x=7 读写执行
##### **kill杀进程**
				kill PID      #PID可以通过htop查询
##### **grep字符串匹配**
				grep 匹配     #可以加参数-e使用正则表达式   可以结合管道|使用
##### **压缩**
				gzip 文件名   #压缩成.gz格式，原文件会消失
				gunzip 压缩文件名  #解压缩，原文件会消失
				gzip -c 文件名 > 压缩文件名      #保留文件的压缩
				gunzip -c 压缩文件名 > 文件名    #保留文件的解压
				
				tar -cvvzf 压缩文件名.tar.gz 文件夹/    #压缩
				tar -xvvzf 压缩文件名.tar.gz           #解压缩
				
				sudo apt-get install p7zip-full
				7z a -t7z 文件名      #压缩成7z
				7z x 压缩文件名        #解压缩
				
				rar e XXX.rar        #解压
				rar a XXX.rar XXX    #压缩
##### **命令组合**
				cmd1 | cmd2   #pipeline,命令1的输出作为命令2的输入
				cmd1 && cmd2  #cmd1执行成功才执行cmd2
				cmd > filename  #命令执行结果重定向到文件（覆盖）
				cmd >> filename   #命令执行结果重定向到文件（追加）
##### **截图**
				PrintScreen键   全屏截图，保存在/图片
				Alt+PrintScreen键   截取当前窗口
				Shift+PrintScreen键  自定义截图
定时关机

```
shutdown -h 14:00     指定时间关机   
shutdown -c     取消
```



##### 包相关操作**

				dpkg -l               #查看已安装包
				dpkg -L 程序名         #查看程序安装了哪些文件
				dpkg -i XXX.deb       #安装本地deb包
				sudo apt-get install XXX     apt安装
				sudo apt-get uninstall XXX   apt卸载
				sudo apt --fix-broken install    安装过程中出现依赖缺失时自动安装依赖
				apt-cache search pkgnames 查找可安装的包
				apt-cache pkgnames    #查看已安装的所有包
				apt-cache depends 程序名    #查看程序依赖
##### **通过终端访问U盘**
				cd /media/用户名/U盘卷标     #正常情况下，Ubuntu会自动挂载U盘到media目录
##### **查看IP地址**
				sudo apt-get install net-tools
				ifconfig -a
				建议通过[设置]-[网络/wifi]查看
​				

##### **Tmux指南**

安装和启动：

```
sudo apt-get install tmux
tmux
```

常用操作：

```
ctrl+b        进入命令模式后再进行以下操作 需快速调整，超时后退出命令模式
	"           上下分屏
	%           左右分屏
	方向键       分屏间移动
	ctrl+方向键  调整分屏大小  
  x           关闭当前窗口
  d           退出tmux
```



##### **Gvim配置**				

安装插件管理工具vundle

```
cd ~/.vim
mkdir bundle
git clone https://github.com/gmarik/vundle.git
配置_vimrc文件
```

安装插件

```
:BundleInstall
```

使用NERDTree

```
:NERDTree 或 F3    #启动NERDTree
:q 或 F3           #关闭NERDTree
ctrl+w             #窗口切换
r                  #刷新当前目录
R                  #刷新根目录
```

查找和替换

```
:/XXX             查找，使用n和N搜索下一个
:%s/AAA/BBB/g     全文替换，AAA替换为BBB
```

