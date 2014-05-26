title: Hello World！使用 Hexo build blog 所踩过的坑
date: 2014-05-17 18:40:19
categories: 学习
tags: [hexo]
description: 第一次搭建自己的博客，记录一下用hexo搭建博客时所遇到的问题（在mac和windows系统中）
---

**Welcome to TiFa's room~**

## 在MAC系统中

### 1.需要的运行环境

1) 安装node.js

在Mac OSX 系统中可以用[nvm](https://github.com/creationix/nvm)来安装node，全称是Node Version Manager，它可以方便的安装你想要装的node版本，并方便卸载，按照上面文档里的命令按照即可，但不要漏了这条命令

    nvm use 0.10

我当时就忘敲了，结果悲剧了。。。

2) 安装git

去[github](https://help.github.com/articles/set-up-git#platform-mac)下载git for Mac的客户端就行，按照文档页下面的命令设置一下全局用户名和邮箱

```
    $ git config --global user.name "Your Name Here"
    $ git config --global user.email "your_email@example.com"
```
下载了git客户端后，它会获取本地的SSH Key自动关联到github的账户配置中，不用手动敲命令去生成Key。有关SSH Key的生成可参照这里[SSH Key](https://help.github.com/articles/generating-ssh-keys)

### 2.域名配置

请参考这里[domain](https://help.github.com/articles/my-custom-domain-isn-t-working),在Dnspod 里一定要设置对IP地址或别名。

### 3.安装Hexo
当环境都配好后就开始用'npm'安装Hexo啦~，命令如下：

    npm install -g hexo

在你指定的目录里初始化Hexo：

    hexo init 

之后依次执行下面的命令就可以启动本地的服务了，地址是[http://localhost:4000](http://localhost:4000)

```
hexo generate
hexo server
```

每次改动后请清除一下本地缓存文件

    hexo clean

再执行

    hexo deploy

去部署到远端的仓库

## 在windows Xp中

### 1.windows的node和git环境配置

如果你用的是Windows Xp以上的系统可以安装[git for Windows](https://help.github.com/articles/set-up-git#platform-windows),可惜我家的挫机要是装了Win 7估计就跑不起来了。。。所以我只能安装[msysgit](http://code.google.com/p/msysgit)了，本来想在windows上用[nvmw](https://github.com/hakobera/nvmw)，但是在天朝确遇到被墙的问题，nvmw获取npm的版本号是通过地址https://raw.github。com/joyent/node/%s/deps/npm/package.json 解析json来获取的，但是这个地址在天朝访问不了，鼓捣了一会没搞定，索性还是老老实实的到[node官网](http://nodejs.org/download/)去下载.msi文件吧，一路安装也挺顺畅的。

### 2.生成SSH Key

windows跟Mac不一样，生成Key要稍稍麻烦一点，需要将生成的id_rsa.pub文件手动copy到github账户设置里的Add SSH Key里，生成密钥的命令：

    ssh-keygen -t rsa -C "your email" 

最后验证一下，

    ssh -T git@github.com

### 3.安装Hexo

在windows上安装的时候遇到了问题，在cmd里使用命令`npm install -g hexo`去安装的时候等了1个小时都没装好，当时我的电脑不会已经挫到这地步了吧，装个hexo都不行了。。。后来用了git bash 再次使用`npm install -g hexo`命令到指定的文件夹去装Hexo，结果好了。。

## 用github来备份管理Hexo源文件

在不同的电脑上写blog这是很多人的需要，所以有必要把Hexo文件管理起来，这样方便在不同的电脑上写博客，方式就是将本地的hexo文件传到你所建的远程仓库中，具体方法参见[使用GitHub来管理博客源文件](http://wuchong.me/blog/2014/01/17/use-github-to-manage-hexo-source/)

## 参考资料和blog

<a href="http://ibruce.info/2013/11/22/hexo-your-blog/" target="_blank">http://ibruce.info/2013/11/22/hexo-your-blog/</a>

<a href="http://beiyuu.com/github-pages/" target="_blank">http://beiyuu.com/github-pages/</a>

<a href="http://zipperary.com/categories/hexo/" target="_blank">http://zipperary.com/categories/hexo/</a>

<a href="http://howiefh.github.io/categories/hexo/" target="_blank">http://howiefh.github.io/categories/hexo/</a>

<a href="http://yangjian.me/workspace/building-blog-with-hexo/" target="_blank">http://yangjian.me/workspace/building-blog-with-hexo/</a>


## git命令手册

<a href="http://git.oschina.net/progit/" target="_blank">Pro Git</a>

<a href="http://www.bootcss.com/p/git-guide/" target="_blank">Git简易手册</a>

## Markdown 手册

<a href="https://www.zybuluo.com/mdeditor?url=https://www.zybuluo.com/static/editor/md-help.markdown#2-分级标题" target="_blank">Markdown 在线语法手册</a>





