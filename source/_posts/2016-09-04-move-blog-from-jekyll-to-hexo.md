---
title: 把博客从 Jekyll 迁移到 Hexo
tags: [blog, hexo, github pages]
---

在上次的文章中（[使用 Github 搭建个人博客](/2014/01/01/blog-github/)）介绍了怎么用 `Github` 默认支持的 Web 框架 `Jekyll` 来搭建博客。相对于曾经接触过的 `Wordpress` 是不知道要轻量级多少倍了。但是在使用过程中也发现几点问题：
1. 配置过于繁琐
2. 对 `markdown` 支持不是特别好

近几年随着 `Hexo` 的发展，社区中不断对这个博客框架的贡献，使得 `Hexo` 日趋完善，并且涌现出几大优点：
1. 源于 `nodejs` 的超快渲染速度，可以把几百个 `md` 文档瞬间生成
2. 对 `markdown` 支持更好，并且还扩展 `Github` 的 `markdown` 语法
3. 一键部署
4. 丰富的插件和主题

<!-- more -->

## 安装 Hexo
安装 Hexo 非常简单：
- 安装 Git
- 安装 node（hexo 是基于 nodejs 的，建议用 nvm 来安装）
- 安装 Hexo
  ``` bash
  $ npm install hexo-cli -g
  ```

## 开始建站
``` bash
$ hexo init your-project-folder
$ cd your-project-folder
$ npm install
$ hexo server
```
之后编辑文件夹下的 `_config.yml` 进行全站设置

## 把文章从 Jekyll 迁移到 Hexo
从 Jekyll 迁移非常简单，把所有文章从 `_posts` 文件夹内的所有文件复制到 `source/_posts` 文件夹，并在 `_config.yml` 中修改 `new_post_name` 参数

``` bash
new_post_name: :year-:month-:day-:title.md
```

如果发现网站没发生变化，需要手动清除下

``` bash
$ hexo clean
$ hexo serve
```

## 增加其他页面
``` bash
$ hexo new page about # 关于
$ hexo new page tags # 标签
$ hexo new page categories # 分类
```

## 部署设置
支持 Github 和 HeroKu，我只用了 Github，所以就记录下 Github 设置

1. 安装插件
``` bash
$ npm install hexo-deployer-git --save
```

2. 配置 `_config.yml`(默认传到`gh-pages`分支)
``` yml
deploy:
  type: git
  repo: <repo url>
```

## 设置自定义域名
利用 github 的 pages 功能可以在项目页面查看网站信息。新建文件 `source/CNAME`，写上网站域名：
```
www.yoursite.com
```
同时在 dns 解析到 github 的 ip

## 常用命令
``` bash
$ hexo new [layout] <title> # 新建文章, layout 可在 _config.yml 中设置默认值

$ hexo new draft <title> # 新建草稿

$ hexo --draft # 查看草稿

$ hexo publish [layout] <title> # 发表草稿

$ hexo serve --draft # 启动服务器，参数 draft 可以预览草稿

$ hexo generate --deploy # 生成后自动部署网站

$ hexo list # 查看所有静态文件

$ hexo clean
```

## 总结
配置好后，一般的流程：

**新建草稿 -> 发布草稿 -> 预览 -> 生成并发布**

参考：
[Hexo 官方文档](https://hexo.io/zh-cn/docs/)

---------- EOF ----------
