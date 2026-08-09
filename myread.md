# 教程连接
https://academicpages.github.io/
https://jayrobwilliams.com/posts/2020/06/academic-website/

# 本地渲染

## 安装依赖
```bash
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
---
layout: archive-----------------归档页布局，也就是页面会按列表方式显示文章。
permalink: /year-archive/-------导航里写的链接。
title: "博客页"------------------页面标题，打开这个页面时顶部显示的名字。
author_profile: true------------左侧显示作者信息卡片。
redirect_from:------------------旧链接跳转到这个页面，方便兼容以前的网址。
  - /wordpress/blog-posts/
---

{% include base_path %}----------------------------------------------------把站点的基础路径引入进来，方便后面生成链接时路径正确
{% capture written_year %}'None'{% endcapture %}---------------------------先创建一个变量 written_year，初始值设成 None。它的用途是记录“上一篇文章显示的年份”。
{% for post in site.posts %}-----------------------------------------------把你站点里所有博客文章都遍历出来。
  {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}--------------这行从当前文章的日期里提取年份，例如 2026、2025，并保存到 year 变量里。
  {% if year != written_year %}-------------------------------------------这一段：如果年份变了，就先显示一个年份标题，比如 2026、2025。
    <h2 id="{{ year | slugify }}" class="archive__subtitle">{{ year }}</h2>---这行会输出一个二级标题，内容就是年份本身，比如 2026。
    {% capture written_year %}{{ year }}{% endcapture %}
  {% endif %}
  {% include archive-single.html %}---------------------------------------每一篇文章用统一的卡片样式展示出来。
{% endfor %}

# _posts
博客内容页

# _includes/archive-single.html 
单篇文章卡片显示模板。它的作用是定义"博客列表、论文列表、演讲列表里的每一条内容怎么排版和显示"。
文章标题：显示文章的标题并做成可点击的链接
阅读时间（已被注释掉）：显示大概需要多少时间读完
发布日期和其他元数据（已被注释掉）：原来显示"Published: August 06, 2026"
文章摘要：显示文章的预览文字
下载链接（论文相关）：显示论文、幻灯片、引用信息等链接

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



