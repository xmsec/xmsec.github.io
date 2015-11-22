---
layout: post
title: "Use Octopress"
date: 2015-10-02 22:12:23 +0800
comments: true
categories: 
---
### GIT上个人静态博客安装
####    —— evalsafe group

octopress在GIT上的安装，根据视频演示，整理文字内容如下。

需要搭建平台环境，并且修改部分http地址

（2015.11.22更新Ruby镜像地址，因http镜像关闭；增加部分流程）

环境搭建：Git、Ruby、DevKit、MarkdownPad 

 - Git：版本管理工具，将代码托管到 GitHub
 - Ruby + DevKit：生成静态网页
 - MarkdownPad：Windows 下 Markdown 语法编辑器
  
		1.Git config –global user.name “”
		2.Git config –global user.email  “”
		3.C：user目录下.ssh  使用bash  ssh-keygen –t rsa –C “email”  回车
		4.密码可以不用输入。文件生成为pub公钥内容提交到git的settings，ssh keys
		    Add 新的，加入key
		5.bash ssh –T git@github.com  @again
		6.Ruby:Path  Add to Path! & bash  ruby dk.rb init   @generate yml
		7.Yml ruby path
		8.Bash buby dk.rb install
		9.Octopress 克隆

- 克隆 Octopress 至本地

	git clone git://github.com/imathis/octopress.git octopress
- 安装依赖项

	gem sources –a https://ruby.taobao.org
	gem sources –r http://rubygems.org
	gem sources –r https://rubygems.org
	
	vi Gemfile VIM  press i

	gem install bundler
	bundle install
    安装依赖项时需要注意
- 安装并使用默认主题

	rake install
	1.bash rake generate   rake preview
	2.文件夹Sources  include  head.html  google libs.baidu.com/jquery

- 新建博客

	rake new_post["title"]
- 新建单页面

	rake new_page[jikexueyuan]
	# creates /source/jikexueyuan/index.markdown
 
	rake new_page[jikexueyuan/page.html]
	# creates /source/jikexueyuan/page.html
>
>1.工具
	MarkdownPad、记事本、Vim、Emacs……
  >引用
   - 列表、
   * 加粗、
  []()  超链接、
  !{}() 图片、
   ｛% video http 640 320 %}　视频、
···
code
···


- 新建仓库

	username.github.io


- 与本地 Octopress 目录绑定
 
	rake setup_github_pages   输入第一种URL
	rake deploy

- 将 source 目录更新到远程仓库
 
	git add .
	git commit -m 'your message'
	git push origin source

## 博客的自定义配置   

-	主配置文件
	
	在 _config.yml 文件中，设置 url、title、author 等基本信息
	
- 主题安装

	1.到 GitHub 上找主题文件

	2.安装主题
	rake install['themename']

	3.重新生成
	rake generate
 **安装主题会清除原有的配置**
- 增加评论功能

	使用多说插件 [http://duoshuo.com/](http://duoshuo.com/ "http://duoshuo.com/")


注：
1.bash表示bash提示符下
2.部分表述供参考

xmsec