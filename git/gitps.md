## git clone报错Failed to connect to github或443
如果cmd能ping通github.com，那么可以去改一下git的代理
1. 先找到本地的代理端口
   
   ![image](https://github.com/Cookie-ch/problems-solutions/assets/79464052/25a2b2ef-d476-474a-a1f5-4b17f3742773)

3. 将git的代理端口改为此端口
   ```
   git config --global https.proxy https://172.0.0.1:33210
   git config --global http.proxy http://172.0.0.1:33210
   ```
查看代理
```
git config --global http.proxy
```
取消代理
```
git config --global --unset http.proxy 
git config --global --unset https.proxy
```
   

## 在子模块中创建并push文件
note是主目录的一个子模块，需要添加文件到node目录下，需要先进入note目录，创建、提交文件到本地仓库，任何返回到主项目更新、提交、push

```
hasee@DESKTOP-M447911 MINGW64 ~/Desktop/chch/My_github (master)
$ cd note/

hasee@DESKTOP-M447911 MINGW64 ~/Desktop/chch/My_github/note (main)
$ mkdir CN

hasee@DESKTOP-M447911 MINGW64 ~/Desktop/chch/My_github/note (main)
$ touch CN/vxlan.md

hasee@DESKTOP-M447911 MINGW64 ~/Desktop/chch/My_github/note (main)
$ git add CN/vxlan.md

hasee@DESKTOP-M447911 MINGW64 ~/Desktop/chch/My_github/note (main)
$ git commit -m "Add vxlan.md in note submodule"
[main 60fa8ed] Add vxlan.md in note submodule
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 CN/vxlan.md

hasee@DESKTOP-M447911 MINGW64 ~/Desktop/chch/My_github/note (main)
$ cd ..

hasee@DESKTOP-M447911 MINGW64 ~/Desktop/chch/My_github (master)
$ git add note

hasee@DESKTOP-M447911 MINGW64 ~/Desktop/chch/My_github (master)
$ git commit -m "Update note submodule"
[master 7b6d19b] Update note submodule
 1 file changed, 1 insertion(+), 1 deletion(-)

hasee@DESKTOP-M447911 MINGW64 ~/Desktop/chch/My_github (master)
$ git push origin master
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 12 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 267 bytes | 267.00 KiB/s, done.
Total 2 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote: This repository moved. Please use the new location:
remote:   git@github.com:Cookie-ch/my_project.git
To github.com:chen03210/my_project.git
   44786e2..7b6d19b  master -> master

hasee@DESKTOP-M447911 MINGW64 ~/Desktop/chch/My_github (master)
$

```
