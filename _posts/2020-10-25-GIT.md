---
layout: post
title: "GIT"
subtitle: "基本操作"
date: 2020-10-25 17:00
author: "czl"
header-img: "img/post-bg-2015.jpg"
catalog: true
tags:
  - 工具
---

#### 1.GIT的全局配置

```shell
$ git config -l  查看配置信息
$ git config --global -l	查看全局配置信息

配置全局信息：用户名和邮箱
$ git config --global user.name chenzelong
$ git config --global user.email 1257433726@qq.com
```

#### 2.创建仓库完成版本控制

> 创建本地git仓库

``` shell
$ git init    会生成一个隐藏文件夹“.git”（不能删）
```

> 在本地编写完成代码后（工作区），把一些文件提交到暂存区

```shell
$ git add xxx 	把某一个文件或者文件夹提交到暂存区
$ git add . 	把当前仓库中所有最新修改的文件都提交到暂存区
$ git add -A	把所有最新修改的文件都提交到暂存区

$ git status 查看当前文件的状态（红色代表在工作区，绿色代表在暂存区，看不见表示已经提交到历史区）
```

> 把暂存区内容提交到历史区

```shell
$ git commit -m'描述信息'

查看历史版本信息（历史记录）
$ git log
$ git reflog  包含回滚的信息
```

#### 3.把本地仓库信息提交到远程仓库

```shell
建立本地仓库和远程仓库的链接
$ git remote -v 	查看本地仓库和哪些远程仓库保持链接
$ git remote add origin Git远程仓库地址	 让本地仓库和远程仓库新建一个链接（origin是随便起的一个链接名，可以改，但是一般都用这个）
$ git remote rm origin 		删除origin这个关联信息

$ git pull origin 分支名  拉取远程仓库文件到本地
$ git push origin 分支名  把本地代码提交到远程仓库

$ git clone 远程仓库git地址 别名   从远程仓库克隆（别名可以不设置，默认是仓库名）
```

> 项目开发流程
>
> ​	1.项目负责人先创建中央仓库并增加协作者
>
> ​	2.小组成员基于$ git clone 把远程仓库及其内容克隆到本地一份（解决了三件事情：初始化本地仓库；与对应的远程仓库保持了关联；把远程仓库默认内容拉取到本地）
>
> ​	3.每个成员写完自己的程序后，基于“git add / git commit”把自己修改的内容存放到历史区，然后通过“git pull / git push”把本地信息和远程仓库信息保持同步（可能涉及冲突的处理）