---
title: CentOs安装oh my zsh
date: 2019-04-23 07:49:05 +0800
comments: true
categories: [Linux,Centos]
---

# 安装zsh包

``` bash
yum -y install zsh
```

# 切换默认shell为zsh

``` bash
chsh -s /bin/zsh
```

# 重启服务器使得配置生效

``` bash
reboot
```

# 安装on my zsh

### curl
``` bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

### wget
``` bash
sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"
```

# 修改oh my zsh 主题

在`~/.oh-my-zsh/themes`目录下已经列出了yum安装的主题，所以我们直接使用就可以了

``` bash
vim ~/.zshrc
```

``` bash
ZSH_THEME="主题名"
```

之后source即可

``` bash
source ~/.zshrc
```


