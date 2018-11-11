---
title: Github Page+Hexo搭建博客
categories: 
- web前端
tags:  
- Hexo
- 实战经验
---

## 搭建个人博客好处?

1.个人博客更自由、更独立，能畅所欲言，不受监管审查。

2.个人博客交互性较强方便分享经验，交流提升，也更方便互相学习、交友以及宣传。

3.方便优化、推广，建立个人品牌。  

4.方便对自己的经验知识的总结。

## 准备

1.Github账号

2.配置过的Git 

3.Node.js

4.Markdown编辑器

## 安装配置

1.在任意位置点击鼠标右键，选择Git Bash

2.输入命令：npm install -g hexo 

3.在安装位置下，右键运行Git Bash，输入命令：hexo init 

4.在_config.yml,进行基础配置 

| `title`       | 网站标题                                                     |
| ------------- | ------------------------------------------------------------ |
| `subtitle`    | 网站副标题                                                   |
| `description` | 网站描述                                                     |
| `author`      | 您的名字                                                     |
| `language`    | 网站使用的语言                                               |
| `timezone`    | 网站时区。Hexo 默认使用您电脑的时区。[时区列表](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)。比如说：`America/New_York`, `Japan`, 和 `UTC` 。 |

5.在hexo官网上下载自己喜欢的theme并配置主题

6.生成静态文件

```
$ hexo clean
$ hexo g
```

7.启动服务器就可以看到你初始的博客 

```
$ hexo server
```

## Github配置 

创建与你的Github用户名相对应的Github Page仓库，必须是username.github.io，复制仓库的地址

## **上传项目** 

1.打开hexo文件夹下的_config.yml文件，修改deploy为以下代码，repository后面的是你的仓库地址 

注意：type、repository、branch冒号的后面都有一个空格 　　　

```
deploy: 
  type: git 
  repository:  
  branch: master
```

2.安装[hexo-deployer-git](https://github.com/hexojs/hexo-deployer-git)自动部署发布工具 

3.输入以下命令部署 

```
$ hexo d
```

4.然后在浏览器输入username.github.io就可以看到你的博客

## Hexo写作 

在\Hexo\source\_posts文件下，新建.md文件就可以写文章 

在Git Bash 输入如下命令：hexo clean && hexo g && hexo d 发布到Github 

## 绑定域名 

1.购买域名 

2.域名解析

3.在hexo的source目录下，创建CNAME文件，没有后缀，打开文件后输入你的域名 

4.保存之后部署到服务器 ，配置就完成了 

## 结尾

[使用*hexo*，如果换了电脑怎么*更新*博客？](https://www.zhihu.com/question/21193762/answer/134278844)



