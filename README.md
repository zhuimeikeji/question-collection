# 问题集锦整理

#### 介绍

这是一个杂乱无章的一些问题集锦，可能是遇到什么写什么。所以没有规律。

{**以下是码云平台说明，您可以替换此简介**
码云是 OSCHINA 推出的基于 Git 的代码托管平台（同时支持 SVN）。专为开发者提供稳定、高效、安全的云端软件开发协作平台
无论是个人、团队、或是企业，都能够用码云实现代码托管、项目管理、协作开发。企业项目请看 [https://gitee.com/enterprises](https://gitee.com/enterprises)}

#### 浏览器跨域DEBUG =========================

###### 同源策略 (Same origin policy)

Netscape(网景公司)提出的一种安全策略

所谓同源即(域名,协议,端口相同)

目的为了保护本地数据不被非同源数据污染

可以请求,返回,但返回的数据无法获取.会报错

###### 跨域产生原因

ajax跨域,iframe跨域

###### chrome跨域设置

选择一个chrome快捷方式,右键属性,

快捷方式/目标

在目标路径后添加

        --disable-web-security --user-data-dir="c:\ChromeDebug"

注意空格与引号

        "C:\Program Files (x86)\Google\Chrome\Application\chrome.exe" --disable-web-security --user-data-dir="c:\ChromeDebug"

IE或360等可以参考下面链接文档设置：

[https://blog.csdn.net/weixin_40695725/article/details/100575598](https://blog.csdn.net/weixin_40695725/article/details/100575598)

#### vscode 设置 =========================

1，mac系统VScode设置中文

macOS 快捷键：·command + shift + p· 

输入搜索 ·configure language· 或则 选择 ·configure display language·

如果没有需要的语言需要安装对应语言包 

2.git 修改记录

VsCode中的GitLens插件刚好能满足这个需求



#### 安装教程 =========================

1. xxxx
2. xxxx
3. xxxx

#### 使用说明

1. xxxx
2. xxxx
3. xxxx

#### 参与贡献

1. Fork 本仓库
2. 新建 Feat_xxx 分支
3. 提交代码
4. 新建 Pull Request


#### 码云特技

1. 使用 Readme\_XXX.md 来支持不同的语言，例如 Readme\_en.md, Readme\_zh.md
2. 码云官方博客 [blog.gitee.com](https://blog.gitee.com)
3. 你可以 [https://gitee.com/explore](https://gitee.com/explore) 这个地址来了解码云上的优秀开源项目
4. [GVP](https://gitee.com/gvp) 全称是码云最有价值开源项目，是码云综合评定出的优秀开源项目
5. 码云官方提供的使用手册 [https://gitee.com/help](https://gitee.com/help)
6. 码云封面人物是一档用来展示码云会员风采的栏目 [https://gitee.com/gitee-stars/](https://gitee.com/gitee-stars/)