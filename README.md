# Redis Docker with alpine

添加了默认的redis.conf配置文件到 /usr/local/etc/redis/redis.conf  
如果需要使用自定义的配置文件,只需要 -v your/redis.conf:/usr/local/etc/redis/redis.conf 即可 

默认时区 中国

目前官方最新版本的 redis容器默认不带配置文件,  本容器解决了这个麻烦!

注意, 各个版本的配置文件可能不通用, 官方配置文件参考
https://redis.io/docs/manual/config/

本容器默认绑定为  127.0.0.1:6379   无密码

如果你非本地访问,需要自己修改配置文件中的绑定
~~~conf
# 绑定IP设定, 这里将要绑定的IP放到后面用空格隔开即可, 或者直接  bind * -::*  绑定到所有IP
bind 127.0.0.1 192.168.2.8

# 默认监听端口 6379,
port 6379

# 链接密码设定
requirepass 123456789
~~~


https://hub.docker.com/r/tekintian/redis/tags


拉取
$ docker push tekintian/redis

运行
$ docker run -it -d -p 6379:6379 tekintian/redis

查看运行日志 
docker logs <容器ID>

进入容器
docker exec -it <容器ID> bash



使用交流
tekin
tekintian@gmail.com
http://dev.yunnan.ws


https://github.com/docker-library/redis
