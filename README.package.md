# package.json的所有配置项及其用法

在前端开发中，npm已经是必不可少的工具了。使用npm，不可避免的就要和`package.json`打交道。平时`package.json`用得挺多，但是没有认真看过官方文档。本文结合npm官方文档以及自己平时使用过程中的感悟，谈一谈`package.json`。官方文档在[这里](https://docs.npmjs.com/files/package.json.html)。

## name: 

这个很好理解，就是package的名称。不过需要注意的是，name有长度限制(虽然一般都不会超)，而且name不能以 【点】 或者 【下划线】开头，name中不能有大写字母。这个是每一个package必须的。在业务代码中，通过require(${name})就可以引入对应的程序包了。

## version: 

package的版本。对于业务项目来说，这个往往不太重要，但是如果你要发布自己的项目，这个就显得十分重要了。name和version共同决定了唯一一份代码。npm是用[npm-semver](https://docs.npmjs.com/misc/semver.html)来解析版本号的。我们一般见到的都是大版本.次要版本.小版本这种版本号，比如16.1.0。版本号的规则、含义其实蛮多的，可以参考[这篇文章](https://segmentfault.com/a/1190000011368506)。

## desription：

包的描述。开发组件库时必需，简明的向库的使用者介绍这个库是干嘛的。对于公司的业务项目，这个配置项一般无所谓。

## keywords：

关键词。一个字符串数组，对这个npm包的介绍。组件库必需，便于使用者在npm中搜索。对于公司业务项目，这个配置一般无所谓。

## homepage： 

项目主页。对于开发组件库来说挺有用的。

## bugs：

开发者的联系方式，代码库的issues地址等。如果代码使用者发现了bug，可以通过这个配置项找到提bug的地方

## license：

开源协议。对于开源组件库，这个十分重要。之前react还因为这事儿没少被社区嫌弃。开源协议略微复杂.

## author：

项目的作者。可以为字符串，对象。

## contributors：

项目的贡献者。author的数组。

## main：

代码入口。这个十分重要，特别是对于组件库。当你想在node_modules中修改你使用的某个组件库的代码时，首先在node_modules中找到这个组件库，第一眼就是要看这个main，找到组件库的入口文件。在这个入口文件中再去修改代码吧。

## scripts：

指定了运行脚本命令的npm命令行缩写。十分重要。

## directories：

对整个代码结构的描述。告诉代码包使用者可以在哪里找到对应的文件。

## files：

数组。表示代码包下载安装完成时包括的所有文件。

## repository：

对于组件库很有用。让组件库使用者找到你的代码库地址。这个配置项会直接在组件库的npm首页生效。例子:

``` "repository": { "type": "git", "url": "git+https://github.com/CoyPan/react-scroll-to-show-cb.git" }, ```

## config：

用于添加命令行的环境变量。具体用法见[这里](https://docs.npmjs.com/misc/config)。

## engines：

指定项目所依赖的node环境、npm版本等。

## private：

如果设为true，无法通过npm publish发布代码。

## bin：

用来指定各个内部命令对应的可执行文件的路径。具体用法这里不多讲了。详情可以点击[这里](https://docs.npmjs.com/files/package.json.html#bin)。

