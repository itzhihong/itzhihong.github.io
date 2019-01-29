---
layout:     post
title:      "新的开始，2019年1月"
subtitle:   ""
date:       2019-01-29 22:00:00
author:     "Itzhihong"
header-img: ""
---

> 创建一个es用户，然后修改用户的shell
> sudo usermod -s /bin/bash esserver


> 检查docker用户是否存在，给用户增加docker权限，这样执行docker时不需要加sudo
> sudo groupadd -g 999 docker 
> sudo  gpasswd -a esserver docker

> 拉取docker镜像
> docker pull elasticsearch:6.5.0

> 创建容器启动
> docker run -d -v /Users/wangzhihong/elasticsearch/data:/usr/share/elasticsearch/data -v > > > >     /Users/wangzhihong/elasticsearch/logs:/user/share/elasticsearch/logs -p 9200:9200 --name='es' elasticsearch:6.5.0
> 其中-v制定volumn影视，前面为本地路径，后面为容器路径。
> -p制定容器映射端口
>  --name 制定容器名称，后续可以使用容器ID或者名称操作该容器



> 容器管理

> 删除容器：
> docker rm es

> 导出本地镜像
> docker save -o delasticsearch.tar elasticsearch

> 导入
> docker load --input delasticsearch.tar 



> 查看docker日志：
> docker logs -f -t --tail 200 es

> docker ps查看容器id
> 通过进入容器：
> sudo docker exec -it ec4b65b873ae  /bin/bash
