# Serv00_Auto_Run
serv00自动启动脚本


run.sh

#!/bin/sh
~/.npm-global/bin/pm2 kill
pkill -kill -u 你的用户名
cd  ~/domains && ~/.npm-global/bin/pm2 start ecosystem.config.js
~/.npm-global/bin/pm2 save

![image](https://github.com/kuoihao/Serv00_Auto_Run/assets/95399503/88f19d91-55ef-4501-a7f1-f71a6625a91a)
在这里添加密钥，不用每次登录

