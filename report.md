---
title: report
date: 2024-03-22 23:18:50
tags:
---
1.安装Git


2.打开GitHub_Settings_keys 页面，新建new SSH Key


3.安装Node

4.安装Hexo
（1）打开终端（windows powershell）
在终端运行命令 npm install hexo-cli -g #完成 hexo 的安装
新建一个文件夹 myblog 用于保存你的本地博客文件
打开文件夹，右键打开 git bash
在 git bash 运行命令
hexo init blog
cd blog #进入 blog 文件
刚开始出现这样的问题是因为没有配好环境变量，配好后得以解决。解决
方法如下：
node.js 安装后在 git bash 中输入 node -v 验证是否安装成功，但是提示：
sh.exe": node :command not found，这是环境变量的问题导致的，选择计算机- 属性-高级系统设置-环境变量。
先查看系统变量部分，发现安装后确实在系统变量的 Path 后追加了安装路
径在打开用户环境变量部分查看了下 Path 的值，发现在最后系统自动加入了
AppData\Roaming\npm，发现环境变量都已经默认设置了，但是为什么上面的
输入不能反馈版本信息呢？需要再追加 C:\Program Files\nodejs，然后关闭掉 git
base，重新打开（如何不重新打开也不能解决问题）后再次输入 node -v，这样
就能成功返回版本信息了。
hexo s #生成静态文件
这里可以在给出的网址 http://localhost:4000/看一下效果，运行完 hexo s 命
令后直接 ctrl+C 退出即可。


打开浏览器输入地址：
localhost:4000


创建 github 库，进 github 官网

创建密钥并添加到 github 账号
git config --global user.name “用户名”
git config --global user.email “邮箱”
ssh-keygen -t rsa
在第三步完成以后按三下回车，直接回车跳过
此时打开用户文件夹，里面有一个.ssh 文件，打开，里面多了两个刚生成
的文件，id_rsa 和 id_rsa.pub。将 id_rsa.pub 文中里的全部内容复制下来。把密钥添加到 github 账号。


部署网页
站点目录下安装发布需要的插件。在 blog 文件内先打开_config.yml 文件，最下面的 deploy 部分做如下修改。
部分博客中出现过拼写错误（如上图 brandh 应该是 branch），网址给错
等，在实际操作中也出现过其它报错。
blog 文件夹内打开 git bash 运行命令
完成以下三步。
hexo clean #清空缓存
hexo g 生成静态文件
hexo d 上传到网页上
如果反复出现连接问题报错，可能是网络问题，我们可以手动将相关文档上
传到 github 上，再次输入网址测试。
检验一下，到 GitHub 给出的我的网址上查看效果。
在手机端也可以正常访问了。



推送网站
点击config.yml文件，修改内容配置，使之与github连接。
安装Git部署插件
npm install hexo-deployer-git --save
绑定域名
登录到阿里云，进入管理控制台的域名列表，找到你的个性化域名，进入解析
内容输入
Markdown文件可以直接被网页识别，所以使用markdown文件可以直接上线到hexo。
发布文章的时候，输入hexo n "博客名字"命令，使得blog根目录下的source文件夹中的_post文件夹中多了一个 博客名字.md 文件。通过带有预览样式的Markdown编辑器实时预览书写的博文样式，也可以通过命令 hexo s --debug 在本地浏览器的localhost:4000 预览博文效果。写好博文并且样式无误后，通过hexo g、hexo d 生成、部署网页。随后可以在浏览器中输入域名浏览。
这里我们把实验报告转换为Markdown格式，就可以上传到hexo了。