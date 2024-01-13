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

## su: Authentication failure
方法一：重置root密码
原因有可能是输错root密码，或没有设置root密码
```
sudo passwd root
```

方法二：如果方法一还是报错，可以输入`sudo screen`
Screen是一款由GNU计划开发的用于命令行终端切换的自由软件。用户可以通过该软件同时连接多个本地或远程的命令行会话，并在其间自由切换
进入之后会是root用户，`exit`退出


## Vim: Warning: Output is not to a terminal
这是因为某些错误操作导致terminal卡死，比如下面的操作：

![image](https://github.com/Cookie-ch/problems-solutions/assets/79464052/58731524-299a-4f83-b396-42b6650e37bb)

其实是进入了vim编辑状态，输入`ESC`后`shift + zz`即可退出
