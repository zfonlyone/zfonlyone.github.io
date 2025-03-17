---
title: Hexo 建站
date: 2020-11-23 10:47:10
tags: "code"
categories: "code" 
---
# 安装
npm install -g hexo-cli

# hexo在5.0之后把swig给删除了需要自己手动安装
npm i hexo-renderer-swig
之后
hexo clean
hexo generate 
hexo server
<!-- more --> 

# 修改Hexo 博客目录中的 _config.yml
theme: fluid  # 指定主题
language: zh-CN  # 指定语言，会影响主题显示的语言，按需修改

# 首次使用主题的「关于页」需要手动创建：
hexo new page about
创建成功后，编辑博客目录下 /source/about/index.md，添加 layout 属性。

# 生成文章的时候生成一个同名的资源目录用于存放图片文件
post_asset_folder: true



# 图片使用方法：
{% asset_img test.png 图片引用方法一 %}

![图片引用方法二](test.png)

方法三：md中无法查看，但页面可以看到
![图片引用方法三](/images/test.png)


# 修改
1. 浏览器tab页名称
修改根目录下 _config.yml 中的 title 字段。
2. 博客标题
主题目录 themes\fluid 下 _config.yml 中的 blog_title 字段。
3. 主页正中间的文字
主题目录 themes\fluid 下 _config.yml 中的 text 字段。

# 阅读量统计
Leancloud 的免费服务来进行统计



# 使用淘宝源的 cnpm 替换 npm
npm install -g cnpm --registry=https://registry.npm.taobao.org
cnpm install -g cnpm                 # 升级 npm
cnpm cache clean -f                 # 清除 npm 缓存
===更新 hexo: 进入 blog 目录，执行如下命令=== 
# 更新 package.json 中的 hexo 及个插件版本
cnpm install -g npm-check           # 检查之前安装的插件，都有哪些是可以升级的 
cnpm install -g npm-upgrade         # 升级系统中的插件
npm-check
npm-upgrade

# 更新 hexo 及所有插件
cnpm update
使用npm的话，用下面命令更新
npm install -g npm

# 确认 hexo 已经更新
hexo -v

#本地启动
hexo g
hexo s

#推送
hexo g -d

#新电脑重新部署error
##进入站点根目录
cd /usr/local/src/hexo/***/

##删除git提交内容文件夹
rm -rf .deploy_git/

##执行
git config --global core.autocrlf false

git config --global user.email "you@example.com"
git config --global user.name "Your Name"
生成密钥
ssh-keygen -t rsa -C ‘上面的邮箱’
最后在.ssh目录下(C盘用户文件夹下)得到了两个文件：id_rsa（私有秘钥）和id_rsa.pub（公有密钥）
复制id_rsa.pub到github

##最后
hexo clean && hexo g && hexo d



