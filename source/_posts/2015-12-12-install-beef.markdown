---
title: "Debian安装『BeEF xss』"
date: 2015-12-12 14:19:21 +0800
comments: true
categories: [linux,安全,XSS]
tags:
  - linux
  - BeEF
  - XSS
  - 安全
---

　　在BeEF的[wiki](https://github.com/beefproject/beef/wiki)上,安装的方法写的很详细，按照上面的方法来操作就可以~但是，前提是你得系统不受到我们亲爱的长城防火墙的影响，现在分享下我的安装过程~

1、安装『git』和『curl』
	
	apt-get update
	apt-get install curl git

2、安装rvm，通过rvm来安装ruby

###### 提醒：安装rvm和ruby的时候不要用root账户

<!--more-->
```
curl -sSL https://raw.githubusercontent.com/wayneeseguin/rvm/master/binscripts/rvm-installer | bash -s stable		//安装rvm
source ~/.rvm/scripts/rvm		//激活rvm
rvm install 2.1.5		//安装ruby 2.1.5版本
rvm use 2.1.5 -- default		//设置2.1.5为默认版本
```	
接着，我们就要安装bundler，但是蛋疼的问题就在这里,因为我们有伟大的长城~~

###### 在此感谢马云，谢谢淘宝提供的[ruby国内镜像](https://ruby.taobao.org/)

我们现在来替换官方镜像

```
gem sources --add https://ruby.taobao.org/ --remove https://rubygems.org/
```
来看下是否替换成功~

```
gem sources -l
```
如果如下显示成功~~

```
*** CURRENT SOURCES ***
https://ruby.taobao.org/
```

现在来通过gem安装 bundler

```
gem install bundler
```

3、下载BeEF XSS

```
git clone git://github.com/beefproject/beef.git /你要安装的目录/beef
cd beef
```
在beef目录下，有个Gemfile的文件

vi编辑器打开他~~

```
vi Gemfile
```	
替换文件里ruby的官方网址为

```
https://ruby.taobao.org/
```
保存退出，接着

```
bundle install
ruby beef
```
至此，全部安装完成!
