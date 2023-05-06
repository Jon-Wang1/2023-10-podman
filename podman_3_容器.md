### 运行容器
```shell
[root@localhost ~]# podman run --name qytang-nginx -p 8000:80 -d nginx
ec7ad63e1b0ac4a95ed99b5244ac8e0dd53ffd139b023a7c175182a5a7da765c

[root@localhost ~]# podman ps
CONTAINER ID  IMAGE                           COMMAND               CREATED        STATUS            PORTS                 NAMES
ec7ad63e1b0a  docker.io/library/nginx:latest  nginx -g daemon o...  4 seconds ago  Up 4 seconds ago  0.0.0.0:8000->80/tcp  qytang-nginx

[root@localhost ~]# curl http://192.168.1.226:8000
<!DOCTYPE html>
<html>
<head>
<title>Welcome to nginx!</title>
<style>
html { color-scheme: light dark; }
body { width: 35em; margin: 0 auto;
font-family: Tahoma, Verdana, Arial, sans-serif; }
</style>
</head>
<body>
<h1>Welcome to nginx!</h1>
<p>If you see this page, the nginx web server is successfully installed and
working. Further configuration is required.</p>

<p>For online documentation and support please refer to
<a href="http://nginx.org/">nginx.org</a>.<br/>
Commercial support is available at
<a href="http://nginx.com/">nginx.com</a>.</p>

<p><em>Thank you for using nginx.</em></p>
</body>
</html>

```

### 删除容器
```shell
[root@localhost ~]# podman rm -f qytang-nginx
ec7ad63e1b0ac4a95ed99b5244ac8e0dd53ffd139b023a7c175182a5a7da765c

[root@localhost ~]# podman ps
CONTAINER ID  IMAGE       COMMAND     CREATED     STATUS      PORTS       NAMES

```