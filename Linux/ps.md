## ssh免密登录仍然需要密码
可能是因为目标主机的相关文件权限太大，ssh不允许用户的主目录和`.ssh`以及`authorized_keys`文件的权限开放的太大

解决方法：
```
修改用户xxx主目录的权限，不能为777
chmod 755 /home/xxx
修改.ssh目录的权限，必须是700
chmod 700 /home/xxx/.ssh
修改密钥文件authorized_keys的权限，必须是600
chmod 600 /home/xxx/.ssh/authorized_keys
```
