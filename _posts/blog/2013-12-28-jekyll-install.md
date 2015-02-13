---

layout: post

title: 安装jekyll

description: 安装jekyll的命令

category: blog

---

#### 1. Gem安装jekyll
	
	sudo gem install jekyll
	
	sudo gem install jekyll rdiscount
	
	jekyll --server
	

#### 2. jekyll支持table的方案

_config.yml中加入下面代码

	redcarpet:
	extensions: ["no_intra_emphasis", "fenced_code_blocks", "autolink", "tables", "with_toc_data"]


