# Bower #

A package manager for the web [http://bower.io](http://bower.io/)

> Bower是一个适合Web应用的包管理器，它擅长前端的包管理，通过其API展示了包依赖模型。使得项目不存在系统级的依赖，不同的应用程序间也不会共享依赖，整个依赖树是扁平的。



## 目录##

1. [bower介绍](#bower介绍)
2. [bower安装](#bower安装)
3. [bower命令](#bower命令)
4. [使用bower](#使用bower)
5. [用bower提交自己类库](#用bower提交自己类库)

- ### bower介绍###

  > Bower 是 twitter 推出的一款包管理工具，基于nodejs的模块化思想，把功能分散到各个模块中，让模 块和模块之间存在联系，通过 Bower 来管理模块间的这种联系。

  - #### 包管理工具一般有以下的功能：####

    1. 注册机制：每个包需要确定一个唯一的 ID 使得搜索和下载的时候能够正确匹配，所以包管理工具需要维护注册信息，可以依赖其他平台。

    2. 文件存储：确定文件存放的位置，下载的时候可以找到，当然这个地址在网络上是可访问的。

    3. 上传下载：这是工具的主要功能，能提高包使用的便利性。比如想用 jquery 只需要 install 一下就可以了，不用到处找下载。上传并不是必备的，根据文件存储的位置而定，但需要有一定的机制保障

    4. 依赖分析：这也是包管理工具主要解决的问题之一，既然包之间是有联系的，那么下载的时候就需要处理他们之间的依赖。下载一个包的时候也需要下载依赖的包。

       > 功能介绍，摘自文章：[http://chuo.me/2013/02/twitter-bower.html](http://chuo.me/2013/02/twitter-bower.html)

- ### bower安装###

  > bower插件是通过npm, Node.js包管理器安装和管理的。

  全局安装bower

  ```npm
  $ npm install -g bower
  ```
  ```npm
  $ bower --version
  ```
  > 检查版本确认是否安装好
  
  ```npm
  $ npm update -g bower
  ```
  > 更新Bower版本,权限问题添加sudo
  
  ```npm
  $ npm uninstall --global bower 
  ```
  > 卸载Bower
  
- ### bower命令###

  `bower help `

  用法:

      bower <command> [<args>] [<options>]

  命令Commands:

  - cache-clean     清除Bower的缓存，或清除指定包的缓存
  - completion       Bower的Tab键自动完成
  - help                   显示Bower命令的辅助信息
  - home                 通过浏览器打开一个包的github发布页
  - info                     查看包的版本信息和描述
  - init                      创建bower.json文件
  - install                 安装一个本地的包到项目
  - link                     在本地bower库建立一个项目链接
  - list                      列出项目已安装的包
  - lookup               根据包名查询包的URL
  - prune                 删除项目无关的包
  - register              注册一个包
  - search                根据包名搜索一包
  - update                更新一个包

  - uninstall              删除一个包

- ### 使用bower###

  1. 安装jQuery到项目

     ```bower
     bower install jquery
     ```

  2. 查看项目中已导入的类库

     ```bower
     bower list
     ```

  3. 安装bootstrap库，并查看依赖情况

     ```bower
     bower install bootstrap
     bower list
     ```

  4. 删除jQuery库

     ```bower
     bower uninstall jquery
     ```

  5. 安装低版本的**jQuery**

     ```bower
     bower install jquery#1.7.2
     ```

  6. 升级jQuery

     ```bower
     bower update jquery
     ```

  7. 查看本地bower已经缓存的类库

     ```bower
     bower cache list
     ```

  8. 查看jQuery库信息

     ```bower
     bower info jQuery
     ```

  9. 查看jQuery的URL

     ```bower
     bower lookup jQuery
     ```

  10. 用浏览器打开dojo的发布主页

  ```bower
     bower home dojo
  ```

     ​

- ### 用bower提交自己类库###

  1. 生成bower.json配置文件

     ```bower
     bower init
     ```

     > 报错：$ bower init
     > bower ENOINT        Register requires an interactive shell
     >
     > Additional error details:
     > Note that you can manually force an interactive shell with --config.interactive
     >
     > ``解决办法：在 windows cmd 里面使用 bower init 而不是在 git bash 里面使用 bower init``

  2. 在github创建一个仓库：xxx-bower

  3. 本地项目绑定并提交到github

     ```git
     git init
     git add .
     git commit -m "注释-备注提交的内容"
     git remote add origin https://github.com/gqzydh/bower.git
     git push -u origin master
     ```

  4. 注册到bower官方类库

     ```bower
     bower register nodejs-bower git@github.com:gqzydh/bower.git
     ```

  5. 查询自己的包

     ```bower
     bower search xxx-bower
     ```

  6. 安装自己的包

     ```bower
     bower install xxx-bower
     ```

模块化，版本依赖，开发类库，发布类库，安装类库，都是一条命令！还能再简单一点么!

