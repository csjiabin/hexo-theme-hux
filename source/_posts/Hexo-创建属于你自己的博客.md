---
title: 'Hexo,创建属于你自己的博客'
catalog: false
author: CSjiabin
header-img: /img/home-bg.jpg
date: 2018-08-16 22:58:09
tags:
    - hexo
    - github
    - node
---
# 前言
欢迎来到Hexo！该文章非常适合不懂前端的人搭建自己的博客，接下来我会讲解我为什么会选择`hexo`和`hexo`博客搭建步奏。最近想要搞个个人博客，因为不想自己搞站点，所以找到了`github pages`，它提供给我们域名和空间，多省事啊。那静态页面用什么工具呢？一开始我用的是`jekyll`,然后我有了那句经典的感受，那句话是从入门到放弃，啊，多么痛的领悟！

###### 下面我来扒一扒：
1. `jekyll`需要安装`ruby`,`python`等，`hexo`需要`nodejs`，当然为了push到github都需要装个`git`,速度上`jekyll`生成静态站点的速度比`hexo`慢多了，如果你时间多。
2. 便捷性，`hexo`完爆`jekyll`，同样是quick start，虽然都是几个命令，就可以预览效果了，但是效果差了十万八千里。
3. 插件和样式，你写完post，想做个categories？对于`hexo`就是so easy，在你的文章前面的使用category: 分类名，`hexo`就给你在右边生成，包括分类主页，默认样式，你啥都不用干。而`jekyll`需要自己写标签语言遍历然后在创建各个分类的主页，在设置页面css，或者用ruby写插件去搞，这下老子要骂娘了，我他妈根本不会ruby啊，官方为什么不主动提供好现成的插件？我只是个后端工程师，不是全栈，页面+css真的玩不来，不知道提供些theme供人选择？

> 废话不多说，接下来会以我的博客为例子搭建一个hexo的giahub pages！
### Hexo相关命令总结
```shell 
$ hexo init #初始化一个项目

$ hexo new page "xxx" #生成页面

$ hexo new "" #生成文章

$ hexo clean #清除缓存

$ hexo s  #启动本地服务

$ hexo g  #保存修改，生成文件

$ hexo d  #发布到远程

$ npm install --save xxx  #安装插件

$ npm unstall xxx #卸载插件
```
上述命令将贯穿于整个博客过程，不难，能动手尽量别复制粘贴

### 准备工作
安装 Hexo 相当简单。然而在安装前，您必须检查电脑中是否已安装下列应用程序：

- [Node.js](http://nodejs.org/)
- [Git](http://git-scm.com/)

如果您的电脑中已经安装上述必备程序，那么恭喜您！接下来只需要使用 npm 即可完成 Hexo 的安装。
```shell
$ npm install -g hexo-cli
```
如果您的电脑中尚未安装所需要的程序，请根据以下安装指示完成安装。
#### 安装 Git
- Windows：下载并安装 [git](https://git-scm.com/download/win).
- Mac：使用 [Homebrew](http://mxcl.github.com/homebrew/), [MacPorts](http://www.macports.org/) ：`brew install git`;或下载 [安装程序](http://sourceforge.net/projects/git-osx-installer/) 安装。
- Linux (Ubuntu, Debian)：`sudo apt-get install git-core`
- Linux (Fedora, Red Hat, CentOS)：`sudo yum install git-core`
#### 安装 Node.js
安装 Node.js 的最佳方式是使用 [nvm](https://github.com/creationix/nvm)。

cURL:
```shell 
$ curl https://raw.github.com/creationix/nvm/master/install.sh | sh
```
Wget:
```shell 
$ wget -qO- https://raw.github.com/creationix/nvm/master/install.sh | sh
```
安装完成后，重启终端并执行下列命令即可安装 Node.js。
```shell 
$ nvm install stable
```
或者您也可以下载 [安装程序](http://nodejs.org/) 来安装。
><strong>Windows 用户</strong>
>对于windows用户来说，建议使用安装程序进行安装。安装时，请勾选<strong>Add to PATH</strong>选项。
>另外，您也可以使用<strong>Git Bash</strong>，这是git for windows自带的一组程序，提供了Linux风格的shell，在该环境下，您可以直接用上面提到的命令来安装Node.js。打开它的方法很简单，在任意位置单击右键，选择“Git Bash Here”即可。由于Hexo的很多操作都涉及到命令行，您可以考虑始终使用<strong>Git Bash</strong>来进行操作。
#### 安装 Hexo
所有必备的应用程序安装完成后，即可使用 npm 安装 Hexo。
```shell
$ npm install -g hexo-cli
```

### 用法
在这里以我的博客主题为例子(也可以按hexo官方文档进行搭建)，移植的主题 [Hux Blog](https://github.com/Huxpro/huxpro.github.io)，我为了您的方便而发布整个项目，因此您只需按照下面的说明操作，即可轻松自定义您自己的博客！ 让我们开始！！！
![](WX20180826-004151@2x.png)
#### 初始化
```shell
$ git clone https://github.com/csjiabin/hexo-theme-hux.git
$ cd hexo-theme-hux
$ npm install
```
#### 站点配置
你可以通用修改 `_config.yml` 文件来轻松的开始搭建自己的博客:
```yml
title: xxx  # 博客名，站点名称 
author: xxx # 博客作者名字 #
description: xxx # 对站点的描述，搜索引擎会抓取，可以自定义
keyword: xxx # 向搜索引擎说明你的网页的关键词
theme: huxblog # themes目录下的主题目录

# 您可以决定是否显示侧边栏
# Sidebar settings
sidebar: true  # whether or not using Sidebar.
sidebar-about-description: "Goals determine what you going to be!!"
sidebar-avatar: https://avatars1.githubusercontent.com/u/20592953?s=460&v=4   # use absolute URL, seeing it's used in both `/` and `/about/

# 您可以决定是否显示帖子标签。
# Featured Tags
featured-tags: true   # whether or not using Feature-Tags

```

#### 撰写博文

```shell
$ hexo new post <post name>  # 或者`hexo new <post name>`生成文章
```
要发表的文章一般以 `Markdown` 的格式放在这里`_posts/`，你只要看看这篇模板里的文章你就立刻明白该如何设置。
> 不同`Markdown`格式语法的可以看这篇 [文章 &rarr;](/2018/08/26/Markdown%E4%BD%BF%E7%94%A8%E6%8C%87%E5%8D%97/)
```yml
---
title: '<post name>'
catalog: true
author: CSjiabin
header-img: /img/home-bg.jpg
date: 2018-08-16 22:58:09
tags:
    - hexo
---
```
启动本地服务调试
```shell
$ hexo s --debug 
```
> --debug 调试模式，会监听文件的变动进行重启，但不会监听最外层的`_config.yml`文件

#### 开启评论功能
- 首先，你需要去注册一个Disqus帐号。不要直接使用我的啊！
- 其次，你只需要在下面的 ` _config.yml` 文件中设置一下就可以了。
```yml
# 评论系统
# Disqus（https://disqus.com/）
disqus_username: csjiabin
```
> 另外你可以其他评论系统使用，例： `Gitalk`、`多说` 等

### 部署到github
上面所有的操作完成之后，你就可以将你的Blog项目部署到github上了。
部署之前先修改`_config.yml`文件。
```yml
deploy:
  type: git
  repo: https://github.com/<yourAccount>/<repo>
  branch: <your-branch>
```
> 备注：在hexo3.x版本下，这里的type应该填git，不是github；另外冒号后面都有一个英文的空格，不然会报错的。

配置完`_config.yml`文件后，在命令后执行以下命令：
```shell
$ hexo generate(g)   # 把文章生成页面
$ hexo deploy(d)    # 部署到github可与hexo g合并为 hexo d -g
```

### Have fun ^_^
如果你喜欢这个项目请给我点个[Star](https://github.com/csjiabin/csjiabin.github.io/stargazers)吧！[Following](https://github.com/csjiabin) 也将不胜感激!
如有其他疑问可以给我留言，我会第一时间为您解答！