## git clone报错Failed to connect to github或443
如果cmd能ping通github.com，那么可以去改一下git的代理
1. 先找到本地的代理端口
   
   ![image](https://github.com/Cookie-ch/problems-solutions/assets/79464052/25a2b2ef-d476-474a-a1f5-4b17f3742773)

3. 将git的代理端口改为此端口
   ```
   git config --global https.proxy https://172.0.0.1:33210
   git config --global http.proxy http://172.0.0.1:33210
   ```
