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

### Branch 分支

分支用于为项目增加新功能或修复 Bug 时使用。

* 创建分支 `git branch dev`
* 查看分支 `git branch`
* 切换分支 `git checkout dev`
* 创建并切换分支 `git checkout -b feature/bbs`
* 合并 dev 分支到 master

```
git checkout master
git merge dev
```

* 删除分支 `git branch -d dev`
* 删除没有合并的分支 `git branch -D dev`
* 删除远程分支 `git push origin :dev`
* 查看未合并的分支 (切换到 master) `git branch --no-merged`
* 查看已经合并的分支 (切换到 master) `git branch --merged`

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

---------------

## 冲突

不同分支修改同一个文件或不同开发者修改同一个分支文件都可能造成冲突，造成无法提交代码。

当合并git,或拉取的时候会存在 `git merge` 合并动作中存在冲突。

可以先通过 `git diff` 查看是否有冲突。 备注：`git diff` 详讲单独做篇幅

使用编辑器修改冲突的文件

添加暂存 `git add .` 表示已经解决冲突

`git commit` 提交完成

-----------------

## 储藏（Stashing）

当你正在进行项目中某一部分的工作，里面的东西处于一个比较杂乱的状态，而你想转到其他分支上进行一些工作。问题是，你不想提交进行了一半的工作，否则以后你无法回到这个工作点。

"暂存" 可以获取你工作目录的中间状态 —— 也就是你修改过的被追踪的文件和暂存的变更 —— 并将它保存到一个未完结变更的堆栈中，随时可以重新应用。

* 储藏工作 `git stash`, 执行存储时，添加备注，方便查找 `git stash save "save message"`
* 查看储藏列表 `git stash list`
* 显示做了哪些改动 `git stash show`，默认show第一个存储,如果要显示其他存贮，后面加stash@{$num}，比如第二个 `git stash show stash@{1}`
* 显示第一个存储的改动 `git stash show -p`，如果想显示其他存存储，命令：git stash show  stash@{$num}  -p ，比如第二个：`git stash show  stash@{1}  -p`
* 应用某个存储 `git stash apply`,但不会把存储从存储列表中删除，默认使用第一个存储,即stash@{0}，如果要使用其他个，`git stash apply stash@{$num}` ， 比如第二个：`git stash apply stash@{1}` 
* 命令恢复之前缓存的工作目录 `git stash pop`，将缓存堆栈中的对应stash删除，并将对应修改应用到当前的工作目录下,默认为第一个stash,即stash@{0}，如果要应用并删除其他stash，命令：`git stash pop stash@{$num}` ，比如应用并删除第二个：`git stash pop stash@{1}`
* 丢弃stash@{$num}存储，从列表中删除这个存储 `git stash drop stash@{$num}`
* 删除所有缓存的stash  `git stash clear`

说明:新增的文件，直接执行stash是不会被存储的

---------------------

## 关联多个平台的SSH KEY

1. 生成指定SSH KEY

```
ssh-keygen -t rsa -C "备注"
```

2. 进入SSH目录，创建CONFIG

```
cd ~/.ssh
touch config
```

3. 打开CONFIG，填写对应站点数据

```
Host github.com
HostName github.com
User git
IdentityFile c:\Users\super\.ssh\id_rsa

Host gitee.com
HostName gitee.com
User git
IdentityFile c:\Users\super\.ssh\gitee_id_rsa
```

User 用户名可以都用 git

说明：修改后使用 `source config`, 使修改生效

--------------------------

## 同一个项目提交到多个平台

```
git remote add github git@github.com/youname/youprojectname.git
git remote add coding git@coding.net/youname/youprojectname.git
git push github master
git push coding master
```

通常用origin作为远程仓库的名字，它只是个名字而已，你可以换成你喜欢的名字。例如我这里换成了github和coding

---------------------------

## git 优先级划分

#### 一.配置文件级别：

（1）.当前项目级别。

（2）.当前电脑用户级别。

（3）.系统级别。

#### 二.分别介绍：

（1）.项目级别：

配置文件位于当前项目 `.git\config` 目录下。

特别说明：.git目录默认状态是隐藏的；读取配置文件代码如下：

```
$ git config --local -l
```

local参数指定读取当前项目下的配置文件，l是list的缩写，当然也可以写成：

```
$ git config --local --list
```

（2）.当前用户级别：

也可以称之为全局配置文件，对当前电脑用户下所有的git项目都有效。

这是我本机电脑的位置，此配置文件对于Administrator管理员账号下的所有项目都是有效的。

读取配置文件内容代码如下：

```
$ git config --global -l
```

global 参数指定读取全局配置文件，l是list的缩写，当然也可以写成：

```
$ git config --global --list
```

#### 三.配置文件优先级:

配置文件的配置项有可能是重复的，优先级关系由大到小如下：

（1）.当前项目级别。

（2）.当前电脑用户级别。

（3）.系统级别。

#### 四.一些简易的配置

1. 设置全局变量

```
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
```

2. 查看 config 配置列表

```
$ git config --list
```

3. 查看单个配置 

```
$ git config user.name 
John Doe
```

4. 项目级别配置

```
$ git config --local
```

5. 综合修改 用户下的 `.gitconfig`， 通过修改该文件达到修改全局配置 
