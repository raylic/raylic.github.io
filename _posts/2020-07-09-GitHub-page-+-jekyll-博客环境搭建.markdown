---
layout: post
title:  "GitHub page + jekyll 博客环境搭建"
date:   2020-07-09 23:38:40 +0800
categories: blog
---
> 前言：学前端也有好几个月了，期末考试定在八月，实训的录取结果也迟迟没有通知，在这空挡里打算认真写一个个人网站，并趁此机会养成写博客的习惯。起初有打算用LAMP搭建wordpress，考虑到要现买服务器还有域名啥的，加上想自己写一些组件，于是选择了GitHub page  + jekyll。然而，搭建环境就遇到的相当多的问题，于是有了下面的内容

### Jekyll环境配置

`jekyll`的运行需要设备上有以下环境

- `Ruby` 2.5及以上
- `RubyGems`
- `GCC`和`make`

**安装Ruby**

首先下载 [Ruby installer](https://rubyinstaller.org/) 安装，将安装路径添加到 `path`，打开`cmd`输入

```shell
ruby -v
```

**安装RubyGems**

下载 [RubyGems](https://rubygems.org/pages/download) 并解压，打开`cmd`输入

```shell
cd path
#path改为解压路径
ruby setup.rb
gem -v
#成功输出则表示安装成功
```

**安装gcc**

下载[mingw](http://www.mingw.org) 并运行

找到`mingw32-gcc-g++-bin` 右键点击 `Make for Installation`

完成后，添加`mingw`的安装路径到`path`，默认是`C:\MinGW\bin`

`cmd`中输入

```shell
gcc -v
```

**安装bundler 和 jekyll**

`gem`安装完成以后，在`cmd`中输入

```shell
gem install jekyll bundler
```

检验

```shell
jekyll -v
```

这一步往往系统提示出错，多数情况下是`gem`包版本有问题，根据提示信息，安装对应的版本的包

```shell 
gem install packgename -v '0.0.0'
#其中packgename改成出错的bao名，'0.0.0'改成对应版本
```

必要的话还需要删除包

```shell
gem uninstall packgename -v '0.0.0'
```

不断排查错误直到`jekyll -v`能正常运行，该阶段结束
