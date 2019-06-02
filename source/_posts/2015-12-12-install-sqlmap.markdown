---
title: "Debian安装『SQLmap』"
date: 2015-12-12 14:15:05 +0800
comments: true
categories:
  - linux
  - [安全,sql]
tags:
  - linux
  - SQLmap
  - 安全
---


###### 1、安装git

	apt-get install git 
	
###### 2、从github上克隆sqlmap到本地
github提供了两种地址，SSL和SSH，都可以使用，建议使用git~

```
地址1：
https://github.com/sqlmapproject/sqlmap.git
地址2：
git@github.com:sqlmapproject/sqlmap.git
```
克隆命令：

```
git clone git@github.com:sqlmapproject/sqlmap.git /你要放sqlmap的目录路径
```

<!--more-->

OK，搞定，安装完了，试试先~

```
cd /sqlmap的目录
./sqlmap.py -h
```
不过这样的话，每次运行都要cd到sqlmap的目录下，稍稍有些麻烦~
###### 3、建立快捷方式~
```
ln -s /sqlmap路径/sqlmap.py /usr/bin/sqlmap
```
现在试下任意目录运行sqlmap吧~

```
sqlmap -h
```