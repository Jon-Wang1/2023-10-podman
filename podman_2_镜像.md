###修改registries的优先级
```shell
# 修改文件 "/etc/containers/registries.conf"

# 改Image Pull的优先级
unqualified-search-registries = ["docker.io", "registry.access.redhat.com", "registry.redhat.io"]

```

### 拉镜像
```shell
[root@localhost ~]# podman pull nginx
✔ docker.io/library/nginx:latest
Trying to pull docker.io/library/nginx:latest...
Getting image source signatures
Copying blob 8db4caa19df8 done
Copying blob bf36b6466679 done
Copying blob 9c2d6be5a61d done
Copying blob 15a97cf85bb8 done
Copying blob 6b7e4a5c7c7a done
Copying blob 9e3ea8720c6d done
Copying config 448a08f1d2 done
Writing manifest to image destination
Storing signatures
448a08f1d2f94e8db6db9286fd77a3a4f3712786583720a12f1648abb8cace25

```

### 查看镜像
```shell
[root@localhost ~]# podman images
REPOSITORY               TAG         IMAGE ID      CREATED     SIZE
docker.io/library/nginx  latest      448a08f1d2f9  2 days ago  147 MB
```


### retag 镜像
```shell
[root@localhost ~]# podman tag 448a08f1d2f9 docker.io/collinsctk/podman-nginx
[root@localhost ~]# podman images
REPOSITORY                         TAG         IMAGE ID      CREATED     SIZE
docker.io/library/nginx            latest      448a08f1d2f9  2 days ago  147 MB
docker.io/collinsctk/podman-nginx  latest      448a08f1d2f9  2 days ago  147 MB

```

### 推送镜像
```shell
[root@localhost ~]# podman login
Username: collinsctk
Password:
Login Succeeded!

[root@localhost ~]# podman push docker.io/collinsctk/podman-nginx
Getting image source signatures
Copying blob bf36b6466679 skipped: already exists
Copying blob 15a97cf85bb8 skipped: already exists
Copying blob 8db4caa19df8 skipped: already exists
Copying blob 9e3ea8720c6d skipped: already exists
Copying blob 6b7e4a5c7c7a skipped: already exists
Copying blob 9c2d6be5a61d skipped: already exists
Copying config 448a08f1d2 done
Writing manifest to image destination
Storing signatures
```

### 删除镜像
```shell
[root@localhost ~]# podman rmi 448a08f1d2f9
```