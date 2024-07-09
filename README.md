# Serv00_Auto_Run
serv00自动启动脚本


run.sh

#!/bin/sh
~/.npm-global/bin/pm2 kill
pkill -kill -u 你的用户名
cd  ~/domains && ~/.npm-global/bin/pm2 start ecosystem.config.js
~/.npm-global/bin/pm2 save

