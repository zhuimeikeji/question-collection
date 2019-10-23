# git 常用语法介绍


## 安装

自诞生于 2005 年以来，Git 日臻成熟完善，在高度易用的同时，仍然保留着初期设定的目标。它的速度飞快，极其适合管理大项目 。

Git 可以在 `windows`、`Mac`、`Linux` 全平台系统使用。登录 [https://git-scm.com/downloads](https://git-scm.com/downloads) 下载你系统的 Git 软件并进行安装。

windows 用户我更建议安装 `git for windows` ，下载地址： [https://gitforwindows.org](https://gitforwindows.org)

包信 `Git Base` 、`Git Gui`

安装后通过以下命令查看，如果显示版本号那就是安装成功了

```  
git --version
```
-------

## Gui

Gui 指 Git 的图形界面管理软件，[https://git-scm.com/downloads/guis](https://git-scm.com/downloads/guis) 这个网址列出了多个可供基本上所有平台使用的 `Gui` 软件。如果要使用 `Gui` 而非命令行操作，我推荐 `sourcetree `这也是我多年使用的软件，功能强大、跨平台、免费。

--------

## 配置

配置文件为 `~/.gitconfig` ，执行任何 Git 配置命令后文件将自动创建。

第一个要配置的是你个人的用户名称和电子邮件地址。这两条配置很重要，每次 Git 提交时都会引用这两条信息，说明是谁提交了更新，所以会随更新内容一起被永久纳入历史记录：

```
git config --global user.email "1020536633@qq.com"
git config --global user.name "zhuimei"
```

#### 常用

* 初始化新仓库 `git init`
* 克隆旧仓库 `git clone xxxx`
* 查看状态 `git status`
* 提交单个文件 `git add index.php`
* 提交所有文件 `git add -A`
* 使用通配符提交 `git add *.js`
* 提交到仓库中 `git commit -m '提示信息'`
* 提交已经跟踪过的文件，不需要执行 `add git commit -a -m '提交信息'`
* 删除版本库与项目目录中的文件 `git rm index.php`
* 只删除版本库中文件但保存项目目录中文件 `git rm --cached index.php`
* 修改最后一次提交 `git commit --amend`


