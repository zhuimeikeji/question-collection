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

### 常用

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

### 清理

* 放弃没有提交的修改 `git checkout .`
* 删除没有 add 的文件和目录 `git clean -fd`
* 显示将要删除的文件或目录 `git clean -n`

### Log管理

* 查看日志 `git log`
* 查看最近 2 次提交日志并显示文件差异 `git log -p -2`
* 显示已修改的文件清单 `git log --name-only`
* 显示新增、修改、删除的文件清单 `git log --name-status`
* 一行显示并只显示 SHA-1 的前几个字符 `git log --oneline`

### Alias 别名

通过创建命令别名可以减少命令输入量。

```
git config --global alias.c commit
```

可以在配置文件 `～/.gitconfig` 中查看或直接编辑

下面是一个 Git 命令 Alias 配置

```
[alias]
a = add .
c = commit
s = status
l = log
b = branch
```

现在可以使用 `git a` 实现 `git add .` 一样的效果了。

### 系统 Alias

在 `~/.bash_profile` 文件中定义

```
alias gs="git status"
alias gc="git commit -m "
alias gl="git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit  "
alias gb="git branch"
alias ga="git add ."
alias go="git checkout"
```

命令行直接使用 `gs` 即可以实现 `git status` 一样的效果了。

window 系统需要使用 `git for window` 中的 `Git Base` 软件

##### .gitignore 忽略设置

一般我们总会有些文件无需纳入 Git 的管理，也不希望它们总出现在未跟踪文件列表。 通常都是些自动生成的文件，比如日志文件，或者编译过程中创建的临时文件等。 在这种情况下，我们可以创建一个名为 `.gitignore` 的文件，列出要忽略的文件模式。 来看一个实际的例子：

```
$ cat .gitignore
*.[oa]
*~
```

第一行告诉 Git 忽略所有以 `.o` 或 `.a` 结尾的文件。一般这类对象文件和存档文件都是编译过程中出现的。 第二行告诉 Git 忽略所有以波浪符（`~`）结尾的文件，许多文本编辑软件（比如 Emacs）都用这样的文件名保存副本。 此外，你可能还需要忽略 `log`，`tmp` 或者 `pid` 目录，以及自动生成的文档等等。 要养成一开始就设置好 `.gitignore` 文件的习惯，以免将来误提交这类无用的文件。

文件 `.gitignore` 的格式规范如下：

* 所有空行或者以 ＃ 开头的行都会被 Git 忽略。
* 可以使用标准的 `glob` 模式匹配。
* 匹配模式可以以（/）开头防止递归。
* 匹配模式可以以（/）结尾指定目录。
* 要忽略指定模式以外的文件或目录，可以在模式前加上惊叹号（!）取反。

所谓的 `glob` 模式是指 `shell` 所使用的简化了的正则表达式。 星号（`*`）匹配零个或多个任意字符；`[abc]` 匹配任何一个列在方括号中的字符（这个例子要么匹配一个 a，要么匹配一个 b，要么匹配一个 c）；问号（`?`）只匹配一个任意字符；如果在方括号中使用短划线分隔两个字符，表示所有在这两个字符范围内的都可以匹配（比如 `[0-9]` 表示匹配所有 0 到 9 的数字）。 使用两个星号（`*`) 表示匹配任意中间目录，比如 a/**/z 可以匹配 a/z , a/b/z 或 a/b/c/z 等。

我们再看一个 .gitignore 文件的例子：

```
# no .a files
*.a

# but do track lib.a, even though you're ignoring .a files above
!lib.a

# only ignore the TODO file in the current directory, not subdir/TODO
/TODO

# ignore all files in the build/ directory
build/

# ignore doc/notes.txt, but not doc/server/arch.txt
doc/*.txt

# ignore all .pdf files in the doc/ directory
doc/**/*.pdf
```



