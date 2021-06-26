---
title: 在腾讯云用宝塔配置&升级 Hexo
cover: 'https://cdn.kulipoi.com/img/hexo_tencent.png'
categories: Hexo
tags: Hexo
abbrlink: 6fda3183
date: 2021-05-31 23:53:41
updated: 2021-05-31 23:53:46
---

距离之前的更新已经过去很久了，最近将自己的站从GitPage移动到了腾讯云
感觉腾讯的轻量云还是很不错的。
这次把自己万年不更新的Hexo从2.x版本一口气更新到了最新的Hexo5

这次我们来讲讲 如何在腾讯云上部署&升级Hexo

### 准备 - 配置Git

网上的教程都是用Centos直接装，我比较喜欢可视化的界面，所以我们用宝塔
如果你还没有宝塔面板，你可以从[这里安装](https://bt.cn)

- 首先我们在进入文件管理在Home目录新建 “Git” 和 “Hexo” 文件夹
  （Git目录来配置Git文件和自动配置钩子 Hexo目录来存放你的博客）

- 在git目录下创建一个叫 HexoBlog 的裸仓库 即 Bare repo

  ```Code
  cd ..
  cd home
  cd git
  git init --bare hexoBlog.git 
  ```

- 创建一个钩子

  在生成好的 ``home/git/hexoBlog.git/hooks/``目录下我们新建一个无后缀的文件，并命名为``post-receive``，在该文件中添加代码

  ```
  #!/bin/bash
  git --work-tree=/home/hexo --git-dir=/home/git/hexoBlog.git checkout -f
  ```

  修改该文件的权限 ``chmod +x /home/git/hexoBlog.git/hooks/post-receive``

### 部署

如果你还不会部署Hexo，可以看我以前的文章，这里就不再赘述了。

- 修改本地的Hexo的配置文件

  ```code
  deploy:
    type: git
    repository: 
        tencent: root@你的云服务器ip:/home/git/hexoBlog
  ```

- 在宝塔的网站管理新建网站，并将网站的根目录指向我们之前新建的 Hexo 目录即可。

### 检测

一切都已经接近尾声，还不赶快 ``hexo g -d``一下看看成果吗？

### 饭后甜点

关于如何更新Hexo，网上的文章我也看了很多，也是很多种方法，有的过时了，有的乱七八糟，我给大家总结一哈。

1. 首先确认自己本地的Hexo版本 即 ``hexo version``

2. 尝试使用 `npm install -g hexo-cli`·更新，当然一般都是失败的，不然我也不会写这么多了。

3. 更新npm-check

   ```
   npm install -g npm-check
   npm-check
   ```

4. 选择你需要的升级

   ```
   npm install -g npm-upgrade
   npm-upgrade
   ```

   基本上一路Yes就可以了，最后别忘了输入个Y

5. 升级并保存

   ```
   npm update -g
   npm update --save
   ```

6. 最后确认自己本地的Hexo版本 即 ``hexo version``

### 甜点后的小零食

当然这中间碰到了一些问题，我把我遇到的分享给大家

- <font color=Red>hooks/post-update: No such file or directory</font>

  你安装的时候眼睁睁的看着一个那么大的 post-receive 文件摆在那里，他就是找不到，按照网上找到的解决办法是编码问题，具体解释查看[这里]([remote: error: cannot run hooks/post-receive: No such file or directory_猿派的博客-CSDN博客](https://blog.csdn.net/qq_42006301/article/details/115215549?utm_medium=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~default-7.control&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~default-7.control)) 。

  解决方案 使用 文件编码转换工具 Dos2Unix. 转换 post-receive文件

  ```
  yum install dos2unix
  dos2unix post-receive
  ```

- <font color=Red>The "mode" argument must be integer</font>
  大概率原因是你安装的hexo版本过低导致和现版本的Nodejs不兼容，我的解决办法即为升级Hexo到最新版，或者你也可以选择降低Nodejs版本至较稳定的12.x版本。



