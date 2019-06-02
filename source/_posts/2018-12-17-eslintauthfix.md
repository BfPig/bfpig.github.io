---
title: sublime配置ESlintAuthFix
date: 2018-12-17 02:10:05 +0800
comments: true
categories: [sublime,tools]
tags:
  - tools
---

- 全局安装eslint
- 安装ESlintAuthFix

cmd + shift + p  => install pack => ESlintAuthFix

- 查看eslint的位置
    `which eslint`

- 配置环境变量

    `xport PATH=path::$PATH`


- 设置ESlintAuthFix

package setting => ESlintAuthFix => settingDefault

```json

{
  "eslint_path": "path",
  "show_panel": true
}

```

- 设置快捷键

```json

{ "keys": ["ctrl+shift+h"], "command": "eslint_auto_fix" }

```