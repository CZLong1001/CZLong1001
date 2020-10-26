---
layout: post
title: "npm"
subtitle: "基本操作"
date: 2020-10-25 17:00
author: "czl"
header-img: "img/post-bg-2015.jpg"
catalog: true
tags:
  - 工具
---

> https://www.npmjs.com/   基于npm是从npmjs.com平台上下载安装的

```powershell
npm install xxx 把模块安装在当前项目中（node_modules文件夹下）
npm install xxx -g 把模块安装在全局环境中
npm i xxx@1.0.0 安装指定版本号的模块
npm view xxx versions > xxx.versions.json 查看某个模块的版本信息（输出到指定的JSON文件中）

/*
 * 什么情况下会把模块安装在全局？
 *	->可以使用“命令”对任何项目进行操作
 *	->因为在安装目录下生成了 xxx.cmd 的文件，所以我们能够使用 xxx 的命令进行操作
 *
 * 安装在本地项目中的模块
 *	->可以在项目中导入进来使用
 *	->但是默认不能基于命令操作（因为没有.cmd文件）
 *	->但是可以基于package.json中的scripts，配置一些npm可以执行的命令，配置后通过 npm run xxx 执行
 */

npm init -y 初始化当前项目的配置依赖清单（项目文件夹的名字中不能出现中文、大写字母和特殊符号）
	->创建成功后在当前项目中生成 package.json 的清单文件
	dependencies ：生产依赖模块（开发和项目部署的时候都需要）
	devDependencies : 开发依赖模块（只有开发的时候需要）
	scripts : 配置本地可执行命令
		
npm i xxx --save 把模块保存在清单生产依赖中
npm i xxx --save-dev 把模块保存在清单开发依赖中
npm install 跑环境，按照清单安装所需的模块

npm root -g 查看全局安装模块的目录
npm uninstall xxx 
npm uninstall xxx -g 卸载安装过的模块
```

> 提高安装模块速度
>
> 1.基于yarn进行第三方模块管理
>
> ​	需要使用yarn命令操作，但是yarn不能安装全局模块

``` powershell
npm install yarn -g  安装yarn
yarn命令：
    yarn init 初始化
    yarn install 跑环境
    yarn add xxx 安装模块
    yarn remove 移除模块
    ...
```

> 2.基于nrm切源提高npm的速度
>
> ​	切源后继续使用npm命令操作

``` powershell
npm install nrm -g  安装nrm
nrm ls 查看当前有哪些源
nrm use xxx  切源 
```

