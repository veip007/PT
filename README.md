# transmission
```
docker run -d \
  --name=transmission \
  -e PUID=1000 \
  -e PGID=1000 \
  -e TZ=Shanghai/China \
  -e TRANSMISSION_WEB_HOME=/transmission-web-control/ \
  -e USER=veip007 \
  -e PASS=github.com \
  -p 9091:9091 \
  -p 51413:51413 \
  -p 51413:51413/udp \
  -v /root/transmission/config:/config \
  -v /root/transmission/downloads:/downloads \
  -v /root/transmission/watch:/watch \
  --restart unless-stopped \
  linuxserver/transmission
  ```

  ```
  其中```  -e USER=veip007 \ ```
 ``` -e PASS=github.com \``` 为您的用户名和密码
 WEB访问地址为 IP:9091  防火墙记得端口放行9091和51413
 
 
___
 
 # Qbittorrent
```
 docker run --restart=always --name qbittorrent -d \
-p 6881:6881 \
-p 6881:6881/udp \
-p 8080:8080 \
-v ~/qbittorrent/config:/config \
-v ~/qbittorrent/downloads:/downloads \
linuxserver/qbittorrent
```

 qbittorrent地址：http://ip:8080
用户名：admin
密码：adminadmin
配置和/下载目录：~/qbittorrent

### 注意Qbittorrent 默认端口6881被很多PT站封掉，自己更换端口。同时防火墙放行
 
 
 

其它docker命令：
拉镜像
```docker pull xxxx/yyyyy:1.0.31```

改标签
```docker image tag xxxx/yyyyy:1.0.31 veip007/yyyyyy:1.0.31```

登陆docker
```docker login```

将镜像推送到账号
```docker push veip007/yyyyyy:1.0.31```

上文1.0.31可自定义。若最新版则为：latest
