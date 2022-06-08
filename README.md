# TCS Website

## 内容更新方法

#### 新闻

在`_posts/`目录下新建一个文件, 文件名格式为`YYYY-MM-DD-name`。博客内容例如
```
---
layout: post
title: Release of ABC v1.2 
categories:
- Release
- Software
feature_text: |
  ## Release of ABC v1.2 
  _The first alpha version_
---

We have released the new version of our super useful tool [ABC v1.2](https://a_url)
```

文件开头的两个`---`之间为元信息, `layout`都固定为post不需要修改。其他几项: 
* `title`为网站标题
* `feature_text`为显示在网页图片上的文字, 可以写HTML或者Markdown
* `categories`给一个列表, 会显示在网页上

其它部分为具体news内容, 可以写Markdown或者HTML。

#### 人员
在`_members/`下, 每个人员对应一个文件, 例如`_members/pinyanlu.md`:

```
---
layout: member
name: Pinyan Lu
image: assets/images/people/pinyanlu.jpeg
description: The lab head
role: pi
aliases:
links:
  home-page: lupinyan.com
  email: lupinyan@blabla.com
  google-scholar: KFQERBwAAAAJ
---

Prof. Pinyan Lu is the chair of the School of Information Management and Engineering, Shanghai University of Finance and Economics, and an member of Zhiyuan Chair Professor group. He got his Ph.D. in Computer Science from Tsinghua University. His research interests lie in complexity theory, algorithms design and algorithmic game theory.
```

元信息部分`layout`不需要修改, 其它信息:
* `name`: 名字
* `role`: 职位, 可选项目前有 pi, res, eng, postdoc, intern, 可选项目可在`_data/roles.yaml`里修改
* `links`: 个人相关链接, 会显示在个人详细信息页面 (比如home-page, email, google-scholar等)。 可选项、icon、text可在`_data/links.yaml`里修改
* `description`: 个人具体职位描述, 会显示在个人详细信息页面
* `image`: 照片, 我们把大家照片放在`assets/images/people/`下

## 本地修改方法

```
git clone git@github.com:shawnpoo/shawnpoo.github.io.git
# 或者使用git pull从最新的main分支拉
# --- 修改、更新文件 ---
git add 修改的文件
git commit -am "用一句话描述修改了什么"
git push
```

### 安装Jekyll
跟随[这个指导](https://jekyllrb.com/docs/installation/)在本地装jekyll。可以在修改完后本地预览。

```
bundle install # install dependencies
bundle exec jekyll serve -P${PORT} # build the site any time a source file changes and serves it locally
```

本地浏览器打开`http://localhost:$PORT`就可以看到网站。

 
## Other Notes

用了两个模板: Team部分用的[lab-website-template](https://github.com/greenelab/lab-website-template), 主体和其它部分用的[Alembic](https://github.com/daviddarnes/alembic)
