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


> 上面的方法不适合index.html文件经常需要修改的情况。因为在创建镜像的时候，index.html文件是被复制到镜像中。如果想要容器中的index.html文件随着修改而变，那么需要重新创造新的镜像。

> 另外一种方法不需要创建新的镜像，采用数据卷的方式
```
$ sudo docker run --name nginx-flexiable -d -p 8080:80 -v /home/ubuntu/nginx/website:/usr/share/nginx/html:ro nginx
```
这样你在index.html中作了修改之后，刷新网页就可以看到修改后的网页。这是因为容器中的网页文件挂载在主机上的数据卷，主机上作了修改，容器中也会跟着改变。
