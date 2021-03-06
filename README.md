WSL Ubuntu 18.04/18.10适用 
## 自动安装软件列表

* Git
* PHP 7.2
* Nginx
* MySQL
* Composer
* Nodejs （自动更新到稳定版）
* Yarn
* Redis
* Beanstalkd
* Memcached

## 可选手动安装软件列表*

以下软件需手动执行安装脚本：

* Elasticsearch：`./install_elasticsearch.sh`

## 安装步骤

##### 请用root用户执行安装脚本命令

```
wget -qO- https://raw.githubusercontent.com/zoang/wsl-ubuntu/master/download.sh - | bash
```

此命令会将安装脚本下载到当前用户目录下的 `wsl-ubuntu` 目录，并自动执行安装，在安装结束后会在屏幕上输出 Mysql root 账号的密码，请妥善保存。

如果当前不是 root 用户则不会自动安装，请切换到 root 账户后执行 `./install.sh`。


## 其他说明


##### 1. WSL 快捷启动环境```
安装脚本使用 Alias 集成部分环境服务快速启动。请进入 root 用户后执行 wsl 即可。
wsl快捷启动PHP、MYSQL、SSH、REDIS等。

```
#wsl
```

##### 2. 在 /etc/nginx/nginx.conf http {} 内加入下面代码（重要，解决未知 BUG）

```
http{
#加入如下，解决未知Unix Socket BUG
fastcgi_buffering off; 
}
```

##### 3. 默认主机说明

```
默认主机：127.0.0.1
适用 Xshell \ Mysql 连接
```

##### 3. HOST 说明
直接修改 Windows host 即可

```
# C:\Windows\System32\drivers\etc\hosts
127.0.0.1 larabbs.test
```