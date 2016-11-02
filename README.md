# 使用nginx官方镜像搭建自定义静态网站－－简明教程

## step 1
```
$ mkdir nginx && cd nginx
$ mkdir website
```
 把Dockerfile文件放在nginx文件夹下，index.html放在website文件加下
 
## step 2
在nginx目录下，通过Dockerfile创建新镜像
```
$ sudo docker build -t journeycheng/nginx_template .
```

