# 使用nginx官方镜像搭建自定义静态网站－－简明教程

## step 1
```
$ mkdir nginx && cd nginx
$ mkdir website
```
 把Dockerfile文件放在nginx文件夹下，index.html放在website文件加下
 
## step 2
切换到nginx目录下，通过Dockerfile创建新镜像
```
$ sudo docker build -t journeycheng/nginx_template .
```
执行成功的话，可以查看到journeycheng/nginx_template的新镜像
```
$ sudo docker images
```
## step 3
启动容器
```
$ sudo docker run --name nginx-example -d -p 8080:80 journeycheng/nginx_temple
```
启动成功后，在浏览器上http://host-ip:8080 就可以看到index.html的界面了
![1]
(https://github.com/journeycheng/nginx_template/raw/1.png)
