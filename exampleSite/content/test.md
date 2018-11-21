## Docker

### Docker 安装
参考[CentOS Docker 安装 菜鸟教程](1)  
Docker官方镜像仓库地址[dockerhub](2)

### 运行一个web应用
```bash
runoob@runoob:~# docker pull training/webapp  # 载入镜像
runoob@runoob:~# docker run -d -P training/webapp python app.py
```

### 常用命令
- 来列出本地主机上的镜像 `docker images` 
- 查看运行列表 `docker ps` 
- 查找
	- docker search httpd
	- docker pull httpd

- 安装运行
	```bash
	[root@ecs-399d ~]# docker run --name httpd_1 -d -P httpd
1f1088d98d5b6dc0099b85d7014efb948468d5012840fbbcf5f5766dc1b1a85a
[root@ecs-399d ~]# docker ps
CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES
1f1088d98d5b httpd "httpd-foreground" 6 seconds ago Up 5 seconds 0.0.0.0:32768->80/tcp httpd_1
[root@ecs-399d ~]# curl localhost:32768
<html><body><h1>It works!</h1></body></html>
```
这时候访问外网ip:32768 已经可以访问了。
关于docker端口映射的更多信息 [博客园](3)

### 其他
docker太牛了，所有复杂的应用只用几行命令就可以部署完成。
目前我部署了
- httpd
- teakki
- owncloud

[1]:http://www.runoob.com/docker/centos-docker-install.html
[2]:https://hub.docker.com/
[3]:https://www.cnblogs.com/jie-fang/p/7920863.html