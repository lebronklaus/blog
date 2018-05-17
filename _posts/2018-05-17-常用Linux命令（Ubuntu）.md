---
layout: post
title:  常用linux命令
subtitle:   一个demo
date:   2018-05-18
author: xiuhao
header-img: img/post-bg-android.jpg
catalog:    true
tags:
    - Linux
    - Ubuntu
---

### 1. apt-get 安装卸载
安装xxx`apt-get install xxx `
卸载但不删除配置`apt-get remove xxx `
卸载并删除相关配置`apt-get purge xxx `
修复依赖损坏`apt-get -f install`
重新获取软件包列表`apt-get update`
进行更新`apt-get upgrade`

### 2.SSH远程登录
安装ssh-server服务`sudo apt-get install openssh-server`
查看安装的ssh服务`dpkg -l|grep ssh`
确认ssh是否启动`ps -e|grep ssh`
停止ssh服务`sudo /etc/init.d/ssh stop`
启动ssh服务`sudo /etc/init.d/ssh start`
重启ssh服务`sudo /etc/init.d/ssh restart`
ssh-server配置文件路径`/etc/ssh/sshd_config`
登录ssh`ssh username@ip_address`
生成私钥文件`ssh-keygen -t rsa//每次执行产生的私钥都不相同`
把公钥写到目标机实现免密登录`scp ~/.ssh/id_rsa.pub xxx@remote_ip:/root/.ssh/authorized_keys`
或分两步：
1. `scp ~/.ssh/id_rsa.pub xxx@remote ip:pub_key//将文件拷贝到远程服务器`
2. `cat ~/pub_key >> ~/.ssh/authorized_keys//需登录远程服务器来执行该操作`

