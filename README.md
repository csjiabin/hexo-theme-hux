# Hexo-Theme-Huxblog

> 移植的主题 [Hux Blog](https://github.com/Huxpro/huxpro.github.io), 感谢 [Huxpro](https://github.com/Huxpro) 设计这样一个完美的主题。

### [Example &rarr;](https://csjiabin.github.io/hux) （已迁移主题至`next` [hexo-theme-next](https://github.com/csjiabin/hexo-theme-next)）


![](/screenshot/WX20180823-100155.png)

## Usage

我没有把它作为一个单独的主题文件夹发布，因为有一些页面是手动添加和修改的，所以您应该手动在`source`中为新页面创建一些额外的文件夹，并修改`_config`。如果你只有一个主题文件夹。

所以我只是推了整个hexo项目，为了你的方便，所有的预设置和样板文件都包括在内了，看看，继续定制你自己的博客吧!

##### Directory Structure
```markdown
|-- project
    |-- .gitignore
    |-- README.md
    |-- _config.yml
    |-- package.json
    |-- scaffolds <!-- hexo new [scaffolds] 模板 -->
    |   |-- draft.md
    |   |-- page.md
    |   |-- post.md
    |-- source
    |   |-- 404.md
    |   |-- CNAME <!-- 进行域名解析 -->
    |   |-- README.md
    |   |-- robots.txt
    |   |-- sw.js <!-- ServiceWorkerRegistration -->
    |   |-- _posts <!-- 文章存放目录 -->
    |   |-- about
    |   |   |-- index.md
    |   |-- archives
    |   |   |-- index.md
    |   |-- img 
    |   |   |-- 404-bg.jpg
    |   |   |-- about-bg.jpg
    |   |   |-- apple-touch-icon.png
    |   |   |-- contact-bg.jpg
    |   |   |-- favicon.ico
    |   |   |-- home-bg-o.jpg
    |   |   |-- home-bg.jpg
    |   |   |-- icon_wechat.png
    |   |   |-- tag-bg.jpg
    |   |   |-- signature
    |   |       |-- black.png
    |   |       |-- white.png
    |   |-- offline
    |   |   |-- index.md
    |   |-- pwa
    |   |   |-- manifest.json
    |   |   |-- icons
    |   |       |-- pwa_icon_128.png
    |   |       |-- pwa_icon_512.png
    |   |-- tags
    |       |-- index.md
    |-- themes <!-- 博客主题存放目录 -->
        |-- huxblog <!-- 自定义主题 -->
            |-- LICENSE
            |-- README.md
            |-- _config.yml
            |-- languages_to_be_added
            |   |-- default.yml
            |   |-- en.yml
            |   |-- zh-CN.yml
            |   |-- zh-TW.yml
            |-- layout
            |   |-- 404.ejs
            |   |-- about.ejs
            |   |-- archive.ejs
            |   |-- archives.ejs
            |   |-- index.ejs
            |   |-- keynote.ejs
            |   |-- layout.ejs
            |   |-- offline.ejs
            |   |-- page.ejs
            |   |-- post.ejs
            |   |-- tags.ejs
            |   |-- _partial
            |       |-- footer.ejs
            |       |-- head.ejs
            |       |-- header.ejs
            |       |-- nav.ejs
            |       |-- pagination.ejs
            |-- source
                |-- css
                |   |-- bootstrap.css
                |   |-- bootstrap.min.css
                |   |-- highlight.styl
                |   |-- hux-blog.css
                |   |-- hux-blog.min.css
                |   |-- rocket.styl
                |   |-- signature.styl
                |   |-- syntax.css
                |   |-- toc.styl
                |   |-- images
                |       |-- ironman.png
                |       |-- rocket.png
                |-- fonts
                |   |-- glyphicons-halflings-regular.eot
                |   |-- glyphicons-halflings-regular.svg
                |   |-- glyphicons-halflings-regular.ttf
                |   |-- glyphicons-halflings-regular.woff
                |   |-- glyphicons-halflings-regular.woff2
                |-- js
                    |-- animatescroll.min.js
                    |-- bootstrap.js
                    |-- bootstrap.min.js
                    |-- hux-blog.js
                    |-- hux-blog.min.js
                    |-- jquery.js
                    |-- jquery.min.js
                    |-- jquery.nav.js
                    |-- jquery.tagcloud.js
                    |-- toc.js
                    |-- totop.js

```
##### 1.Init

```shell
git clone https://github.com/csjiabin/hexo-theme-hux.git
cd hexo-theme-hux
npm install

```

##### 2.Modify
修改 `_config.yml`文件，把你自己的信息归档。
尤其是这部分:

```
deploy:
  type: git
  repo: https://github.com/csjiabin/hexo-theme-hux.git
  branch: gh-pages
```
替换你的仓库地址

##### 3.Writting/Serve/Deploy

```shell
hexo new post IMAPOST
hexo serve // hexo本地运行
hexo clean && hexo deploy // hexo会将静态文件自动推送到你的repo的特定分支(gh-pages)中!
```

##### 4.Enjoy! 
Please [Star](https://github.com/csjiabin/csjiabin.github.io/stargazers) this Project if you like it! [Following](https://github.com/csjiabin) would also be appreciated!
