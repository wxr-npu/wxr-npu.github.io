# 教程连接
https://academicpages.github.io/
https://jayrobwilliams.com/posts/2020/06/academic-website/

# 本地渲染

## 安装依赖
```bash
sudo apt install ruby-bundler
bundle config set --local force_ruby_platform true
sudo apt install ruby-dev ruby-bundler nodejs build-essential gcc make
bundle install
```

## 启动关闭
在项目目录执行：
```bash
bundle exec jekyll serve -l -H localhost
```
然后在浏览器打开 http://localhost:4000

在线访问：https://wxr-npu.github.io

在终端中按 `Ctrl+C` 停止服务。


> 修改 Markdown 文件（_pages, _posts, _data 等）后会自动重新生成
> 修改 `_config.yml` 后CSS/JS 等核心模板文件后需要手动停止并重启 Jekyll 服务



-----------------------------------------------------------------------------------------------
# _data/navigation.yml
修改上方的导航信息的名称和连接
下方的url对应着_page当中的md的permalink: /archive-layout-with-content/

# _config.yml
信息栏






# _pages/about.md
首页信息

# _pages/blog.html

layout: archive-----------------归档页布局，也就是页面会按列表方式显示文章。
permalink: /year-archive/-------导航里写的链接。
title: "博客页"------------------页面标题，打开这个页面时顶部显示的名字。
author_profile: true------------左侧显示作者信息卡片。
redirect_from:------------------旧链接跳转到这个页面，方便兼容以前的网址。
  - /wordpress/blog-posts/

# _pages/tag-archive.html
按照tags排序的博客页


# _posts
博客内容页

# _includes/archive-single.html 
单篇文章卡片显示模板。它的作用是定义"博客列表、论文列表、演讲列表里的每一条内容怎么排版和显示"。
文章标题：显示文章的标题并做成可点击的链接
阅读时间（已被注释掉）：显示大概需要多少时间读完
发布日期和其他元数据（已被注释掉）：原来显示"Published: August 06, 2026"
文章摘要：显示文章的预览文字
下载链接（论文相关）：显示论文、幻灯片、引用信息等链接
# _includes/author-profile.html
作者卡片模板，模板支持社交字段，可在里面添加CSDN



# _sass/layout/_page.scss
决定md文件的页面渲染效果



-----------------------------------------------------------------------------------------------------------
# md格式学习
## 分割线
------
## 一级标题另一个写法
一级标题
======
## 添加链接
添加连接[this one](https://github.com/academicpages/academicpages.github.io/blob/master/_talks/2012-03-01-talk-1.md) 
## 添加图片
添加图片效果
![Editing a Markdown file for a talk](/images/editing-talk.png)

## 行内公式正确渲染
CSDN上使用$公式$，但在这里需要使用\\(公式\\)的格式来渲染行内公式。
