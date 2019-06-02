---
title: Ubuntu java7 升级到 java8
date: 2019-05-29 13:40:05 +0800
comments: true
categories:
  - linux
  - java
tags:
  - linux
  - ubuntu
  - java
---


# 查看原版本

`java -version`

显示如下

```bash
java version "1.7.0_101"
OpenJDK Runtime Environment (IcedTea 2.6.6) (7u101-2.6.6-0ubuntu0.14.04.1)
OpenJDK 64-Bit Server VM (build 24.95-b01, mixed mode)
```

# 安装 opensdk 8

```bash
add-apt-repository ppa:openjdk-r/ppa
apt-get update
apt-get install openjdk-8-jdk
```

# 列出已经安装的Java版本

```bash
update-java-alternatives -l
```

显示如下：

```bash
java-1.7.0-openjdk-amd64 1071 /usr/lib/jvm/java-1.7.0-openjdk-amd64
java-1.8.0-openjdk-amd64 1069 /usr/lib/jvm/java-1.8.0-openjdk-amd64
```

# 手动切换版本

```bash
update-alternatives --config java
```
选择java-8-openjdk-amd64即可

```bash
	There are 2 choices for the alternative java (providing /usr/bin/java).

	  Selection    Path                                            Priority   Status
	------------------------------------------------------------
	  0            /usr/lib/jvm/java-7-openjdk-amd64/jre/bin/java   1071      auto mode
	  1            /usr/lib/jvm/java-7-openjdk-amd64/jre/bin/java   1071      manual mode
	* 2            /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java   1069      manual mode

	Press enter to keep the current choice[*], or type selection number: 2
```





