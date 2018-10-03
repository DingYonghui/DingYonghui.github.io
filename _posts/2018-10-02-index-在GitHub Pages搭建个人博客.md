---
layout: post
title: '在GitHub Pages搭建个人博客'
date: 2018-10-02
author: 丁永辉
color: rgb(255,210,32)
cover: '../picture/2018-10-02-index-在GitHubPages搭建个人博客.jpg'
tags: index
---

## 1 准备工作

### **1.1 本地安装git**

Git官网：https://git-scm.com/downloads
Git教程：[廖雪峰的官方网站](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)   [菜鸟教程](http://www.runoob.com/git/git-tutorial.html)

本地安装好git，并学习熟悉`git命令`。

### **2.2 注册github账号**

GitHub官网：https://github.com/

在Github上注册账号。

## 2 开始使用

### **2.1 线上部署**

1. 首先在 `github` 上新建一个仓库，命名为 `你的github用户名.github.io` ；
2. 接着将该项目 `clone` 到本地仓库；
3. 然后下载 `DingYonghui.github.io` 的 [源码](https://github.com/DingYonghui/DingYonghui.github.io) 到本地；
4. 将所有文件拷贝到自己的本地仓库根目录下，除了Gemfile、Gemfile.lock这两个文件；
5. 将 `_config.yml` 文件更改为自己的配置（下面会介绍）；
6. 完成修改`_config.yml`后先`commit`到本地仓库，然后`push`到自己的 `github` 线上仓库；
7. 在`github`中`setting`找到`GitHub Pages`进行配置，即可通过分配的URL访问自己的博客。
8. 配置好域名，即可通过域名 `https://你的github用户名.github.io` 访问看到自己的博客（选做）。

### **2.2 本地部署**

1. 暂无


## 3 配置文档

### **3.1 配置分类**（大部分配置在`_config.yml`）

- 开始
  - 配置站点
  - 写文章（在`_posts`目录下每一篇markdown文章的头信息）
- 组件
  - 博主个人信息
  - 社交媒体
  - 首页显示信息（在根目录下`index.html`的头信息）
  - 导航栏
  - 分页
  - 代码高亮主题
  - 友情链接
  - 页脚
- 第三方服务
  - 评论系统的切换
  - 文章分享
  - 网站流量追综的配置

### **3.2 `_config.yml`定义自己的配置**

**修改 `_config.yml` 文件，便可快速搭建属于你自己的个人博客。一部分配置，默认已经是配置好的，你只需要修改下面列出的内容即可完成搭建。**

#### 配置站点

```yaml
# Site settings 配置站点
title: '丁永辉的个人博客'
description: '技术与人生，信息安全、算法、Java'
keywords: '技术与人生、Java、信息安全、算法'
url: 'http://www.dingyonghui.cn' # your host
```

该部分配置html页面的头部信息。

`title` ：用于页面的 title 标签的显示内容

`description` ：网站的简介

`keywords` ：网站的关键词

`url` ：网站域名

#### 博主个人信息

```yaml
# 博主
author: true
name: '丁永辉'
NickName: '黑客与漫画'
webtitle: '清风明月'
bio: '晨钟暮鼓，洗尽铅华。' # 个人简介
about: true
aboutyou: '热爱生活，热爱技术。'
portraits: '/assets/profile.jpg' # your portraits image file path
```

该部分显示在 `关于博主` 页面，与 `社交媒体` 一同显示，如[关于我](http://www.dingyonghui.cn/about.html)所示。

`author`：使用 `true` 或者 `false` 来打开或关闭博主信息卡片，默认 true ，最佳体验也是 true 。

`about`：使用 `true` 或者 `false` 来打开或关闭博主关于信息，即是否显示 `aboutyou` 部分的信息。默认 true ，该部分需要在 aboutyou 中输入相关信息，支持在此填写html代码。

#### 社交媒体

```yaml
# SNS
SNS: true
SNS-icon: #['Facebook', 'weibo', 'qq', 'github', 'Dribbble', 'Twitter', 'instagram', 'weixin', 'Codepen']
  mail: '1214914477@qq.com'
  weixin: '/assets/ding-wechat.jpg' # 你的微信二维码存放的地址
  qq: '/assets/ding-QQ.jpg' # 你的qq二维码存放的地址 or http://wpa.qq.com/msgrd?v=3&uin='你的QQ号'&site=qq&menu=yes
  github: 'https://github.com/DingYonghui'
  #Codepen: ''
  #weibo: ''
  #instagram: ''
  Twitter: ''
  #Dribbble: ''
  #Facebook: ''
  Google: ''
  zhihu: ''
  #juejin: ''
  #twitch: ''
```

​        只要在需要开启的社交账号的名字后填写你的个人主页链接即可。不需要开启的就在那一行的头部用 # 注释这一行即可。如果需要更换每个图标的排列位置，只需要改变他们的每一行排列的顺序即可。

`SNS`：填写  `true` 或者 `false` 来打开或者关闭这一部分。

#### 导航栏

```yaml
# nav 中文字符空格：&emsp;
nav: # 最佳体验 六个标签 且最好每个标签不超过4中文字
  首页: '/'
  标签: '/tags.html'
  时间线: '/timeline.html'
  关于我: '/about.html'
  友情链接: '/friendLink.html'
```

​        默认全部开启他们，当然如果想要自己添加，按照格式填在下方即可，当然页面显示顺序与每一行的位置有关。

#### 分页

```yaml
# 分页
paginate: 5
paginatepath: ['page:num']
```

`paginate`：在首页一页最多显示多少篇博客的数字。

​        本地部署的需要使用 `gem install jekyll-paginate` 或 `sudo gem install jekyll-paginate` 安装Jekyll的分页插件。

#### 代码高亮主题

```yaml
# 代码高亮 使用rouge
highlighter: rouge
# 代码高亮主题使用pygments主题: autumn\ default\ emacs\ friendly\ manni\ murphy\ pastie\ perldoc\ tango 任选一个你喜欢的主题名称填在下面的单引号中
pygmentsTheme: 'default'
```

​	代码高亮使用 jekyll3.0 之后的默认高亮引擎 `rouge` 。关于主题，只需要在 `pygmentsTheme` 后填写喜欢的主题名称即可。共有9款主题可选，主题名见上文。

​	代码高亮的写法：

~~~markdown
``` css
*{
 margin:0;
 padding:0;
}
```
~~~

#### 友情链接

```yaml
# 友情链接
friends:
  # jekyll: 'https://www.jekyll.com.cn/'
  爪哇部落: 'http://www.javatribe.org/'
```

​	按格式填写即可，排序与配置文件里的排序有关。

#### 页脚

```yaml
# since
footer:
  since: 2018
```

​	用于页脚显示时间。

#### 评论系统的切换

```yaml
# 评论 最佳体验 在disqus、livere和Gitment之间三选一
# disqus 评论
disqus: false
disqus_url: '' # https://abc.disqus.com/embed.js
# 来必力评论
livere: true
livere_uid: 'MTAyMC80MDEwMi8xNjYyOQ==' # MTAyMC80MDEwMi8xNjYyOQ==
# Gitment评论 OAuth Application
Gitment: false
Gitment_owner: 'DingYonghui'  # github用户名
Gitment_repo: 'DingYonghui.github.io.gitment'  # github博客存放的仓库名
client_id: ''  # 注册 OAuth Application 后获得的 client_id
client_secret: ''  # 注册 OAuth Application 后获得的 client_secret
```

​        使用 `true` 或者 `false` 开启或关闭某个评论系统。可开启多个。

​        推荐开启 **`来必力`** 评论。

#### 文章分享

```yaml
# Share : weibo, qq, wechat, tencent, douban, qzone, linkedin, diandian, facebook, twitter, google
social-share: true
social-share-items: ['qq', 'wechat']
#social-share-items: ['qq', 'wechat', 'weibo', 'twitter', 'facebook']
```

​	使用了第三方分享插件[Share.js](http://overtrue.github.io/share.js/)，支持一键分享到微博、QQ空间、QQ好友、微信、腾讯微博、豆瓣、Facebook、Twitter、Linkedin、Google+、点点等社交网站。

​	只需要填写相关的名称在 `social-share-items` 后即可，显示顺序与书写顺序有关。

#### 网站流量追综的配置

```yaml
# 百度统计 在baidu-url里填写自己相关的url代码
baidu: true
baidu-url: 'cc8f7c008f4862ae7919a469ab99db32'
# 谷歌分析 在google-ID里填写自己在谷歌分析获得的追踪ID
google: false
google-ID: ''
```

​	在 `baidu-url` 和 `google-ID` 分别填上注册获取的相关信息。使用 `true` 或者 `false` 开启或关闭他们。  

​       出于中国大陆网络环境，默认开启 百度统计 ，当然可以多开。

### **3.3 `index.html`定义自己的配置**

#### 首页显示信息

```yaml
---
layout: default
title: 丁永辉的个人博客 
page-title: My name is DingYonghui
home-title: Just do it.
description: This is my personal blog.
---
```

​	该部分位于 `index.html` 页面，修改 `title` 、`page-title` 、`home-title`  、`description`为个人想要的信息，默认配置的显示效果如[首页](http://www.dingyonghui.cn/)所示。

### 3.4 在`_posts`目录下每一篇markdown文章的头信息定义自己的配置

#### 写文章

​	博客通过解析 `markdown` 文件来部署文章页面的，所以用户写文章只需要写一篇markdown，并放置在站点根目录下的 `_post` 文件夹即可。具体的markdown语法自行上网搜索学习，或使用markdown编辑器进行写作。推荐一款 markdown编辑器：[typora](https://www.typora.io) 。支持 windows 、mac OSX 、Linux 。

关于文章 YAML头信息：

```yaml
layout: post
title: '在GitHub Pages搭建个人博客'
date: 2018-10-02 08:44:13
author: 丁永辉
color: rgb(255,210,32)
cover: '../picture/2018-10-02-index-在GitHubPages搭建个人博客.jpg'
tags: index
```

`color`：

​	此处的color用于post页面的顶部位置的背景色。如上面展示图所示为 `rgb(154,133,255)` 色。

​	对于color的书写，如果颜色代码为 `rgb` 或 `rgba` 又或是 `英文单词` 的话，可以不用引号包裹，但如果颜色代码为 `#123456` 这种16进制码的话，就必须使用引号包裹。所以，在使用中，推荐一致都使用引号，以免错误使用。

​	当然，如果你在书写文章时，忘记写color的值的话，主题默认会为你填写 `rgb(154,133,255)` 色。就是上图显示的颜色。虽然不影响页面的显示，但如果想要更多彩的页面效果的话，建议在每一篇的头信息里写上 color 值。

`cover`：

​	此处需填写某一张图片的 `url` ，`url` 值可以是线上的某张图片，也可以是博客目录下的图片。关键是要书写正确。这张图片用于在首页下博客列表里显示，如[首页](http://www.dingyonghui.cn/)中博客列表显示的图片。



## 4 参考模板

http://jekyllthemes.org/
https://github.com/xukimseven/HardCandy-Jekyll
https://github.com/KeJunMao/jekyll-theme-mdui
https://github.com/erayaydin/jekyll-bulma
https://github.com/joytou/joytou.github.io
https://github.com/suyan/suyan.github.io
https://github.com/zxixia/jekyll-xixia
https://github.com/chrisbobbe/jekyll-theme-prologue
https://github.com/zhisheng17/zhisheng17.github.io
https://github.com/leopardpan/leopardpan.github.io/
https://github.com/anTtutu/anTtutu.github.io/

## 5 参考博文

1、利用Github Page 搭建个人博客网站
https://blog.csdn.net/tzs_1041218129/article/details/53214497
2、创建GitHub技术博客全攻略
https://blog.csdn.net/renfufei/article/details/37725057/
3、使用 GitHub, Jekyll 打造自己的免费独立博客
https://blog.csdn.net/on_1y/article/details/19259435
4、用 Github + Jekyll 写博客
https://blog.csdn.net/u014015972/article/details/50497254
5、搭建Hexo博客中碰到的坑
https://www.jianshu.com/p/a2fe56d11c4f

6、实现网站统计之百度统计
https://blog.csdn.net/qq_39579242/article/details/81016477

## 7 其他

1、来必力评论
https://livere.com/
2、百度统计
https://blog.csdn.net/qq_39579242/article/details/81016477
3、markdown工具
https://www.typora.io/

















