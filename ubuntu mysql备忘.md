安装：

```
sudo apt-get install mysql-server mysql-client
sudo netstat -tap | grep mysql    #检查是否安装成功
```

启动/关闭mysql

```
service mysql start     #启动
service mysql status    #查看状态 
service mysql stop      #关闭
```

默认的密码是随机的，修改步骤如下：

```
sudo cat /etc/mysql/debian.cnf     #查看debian-sys-maint用户密码
mysql -u debian-sys-maint -p       #登录，密码输入上一步骤查到的password
mysql>
	use mysql;
	update mysql.user 
	set authentication_string=password('123456')
	where user = 'root'
	  and Host = 'localhost';
	update user set plugin='mysql_native_password';
	flush privileges;
	quit;
mysql -u root -p                  #root登录，密码为123456
```



用户管理：

```
#创建新用户，%可远程访问，localhost只能本地访问
	create user 'brs_admin'@'%' identified by '123456';
#赋权
	grant select,update,delete,insert on boardroom.* to brs_admin@'%';
	flush privileges;
```

