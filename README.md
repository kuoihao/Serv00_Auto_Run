# Serv00_Auto_Run
serv00自动启动脚本


run.sh
```bash
##创建run.sh脚本
cd ~
touch run.sh
chmod +x run.sh

##写入命令（或者自己复制进去）：
cat << 'EOF' > run.sh
#!/bin/sh
~/.npm-global/bin/pm2 kill
pkill -kill -u 你的用户名
cd ~/domains && ~/.npm-global/bin/pm2 start ecosystem.config.js
~/.npm-global/bin/pm2 save
EOF
```

在 GitHub 仓库中，进入右上角Settings，在侧边栏找到Secrets and variables，点击展开选择Actions，点击New repository secret，然后创建一个名为`SSH_PRIVATE_KEY`的Secret，

获得私钥的命令：
```bash
# 生成新的 SSH 密钥对
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

# 将公钥添加到本地的 authorized_keys 文件中
cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys

# 查看私钥内容
cat ~/.ssh/id_rsa
#复制私钥内容作为SSH_PRIVATE_KEY的值,需要包括
#-----BEGIN OPENSSH PRIVATE KEY-----
#-----END OPENSSH PRIVATE KEY-----这两行
```
如下：
![image](https://github.com/kuoihao/Serv00_Auto_Run/assets/95399503/88f19d91-55ef-4501-a7f1-f71a6625a91a)
在这里添加密钥，不用每次登录
(ssh的原理是把公钥存在serv00的服务器上，github的actions拿着私钥，经过公钥加密私钥解密的验证，双方就可以通信)
