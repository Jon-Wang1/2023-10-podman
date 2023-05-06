### 查看Linux版本
```shell
[root@localhost ~]# cat /etc/rocky-release
Rocky Linux release 9.1 (Blue Onyx)

```

### 安装PodMan
```shell
dnf install -y podman

```

### 安装PodMan Compose
```shell
dnf install python3-pip
pip3 install podman-compose

```