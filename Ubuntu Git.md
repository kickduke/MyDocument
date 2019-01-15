Ubuntu GitHub配置

```
#安装git
  sudo apt-get install git     
#配置
  git config --global user.name "kickduke" 
  git config --global user.email "3402637550@qq.com"
  git config --list      #查看配置结果
#创建SSH key
  ssh-keygen -t rsa -C "3402637550@qq.com"
  SSH key创建在~/.ssh下，将id_rsa.pub添加到GitHub网站SSH中（用户-settings-SSH）
#测试是否可访问
	ssh -v git@github.com
```





	cd ~/公共的/Git

类似svn的checkout

```
git clone https://github.com/kickduke/GitHubTest.git
```

使用当前本地目录作为库
```
git init
```

--刷新所有变化

```
git add -A
```

--commit

```
git commit -m "注释"
```

--上传
```
git push https://github.com/kickduke/GitHubTest.git
```
--同步到本地
```
git pull https://github.com/kickduke/GitHubTest.git
```