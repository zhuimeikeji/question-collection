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

## dependencies：

项目的依赖。通过`npm install --save`安装的包会出现在这里。注意，不要把测试工具、代码转换器或者打包工具等放在这里。当你在命令行里面使用`npm install react --save`时，react就会出现在`dependencies`。默认是安装最新的版本。如果想安装某个特定的版本，可以`npm install react@15.6.2`。以下的`dependencies`，格式都是合法的，

``` "dependencies" : { "foo" : "1.0.0 - 2.9999.9999", "bar" : ">=1.0.2 <2.1.2", "baz" : ">1.0.2 <=2.3.4", "boo" : "2.0.1", "qux" : "<1.0.0 || >=2.3.1 <2.4.5 || >=2.5.2 <3.0.0", "asd" : "http://asdf.com/asdf.tar.gz", "til" : "~1.2", "elf" : "~1.2.3", "two" : "2.x", "thr" : "3.3.x", "lat" : "latest", "dyl" : "file:../dyl" } ```

我们常见的是下面这些：

``` "dependencies": { "foo": "1.0.0", // 指定了就是1.0.0版本 "bar": "~1.2.2", // 安装版本号不低于1.2.2的1.2.x的最新版本，例如:1.2.3， 1.2.4等等。1.2.1 ，1.3.x 等就不行了 "baz": "ˆ1.2.2", // 安装版本号不低于1.2.2的1.x.x的最新版本，例如: 1.2.7，1.3.1，1.7.8等。1.2.1 ，2.0.0 等就不行了。注意，如果配置是^0.x.x，则和~0.x.x的效果一样。 "lat": "latest" // 安装最新版本 } ```

dependencies 还可以像下面这样配置：

``` "dependencies": { "foo": "git+ssh://git@github.com:foo/foo.git#v1.0.1", } ```

foo组件的地址为git+ssh://{foo代码库的ssh地址}#v{foo的版本号}

###### 这样的配置在下面这种场景十分有用：

组内的许多项目都有同一个功能，把这个功能抽出来做成组件是很自然的想法。但是每个项目都有自己的代码库，公司也没有内部的npm库，组件应该放在哪里呢？可以专门为组件新建一个代码仓库，将组件放在这里开发、迭代。这样，各个项目都可以引用该组件：只需要在dependencies中将组件配置成上述的形式。至于组件的版本，可以通过git tag来控制。

dependencies还有其他的配置方式，具体在这里查看。

## devDependencies：

项目的依赖。通过`npm run install --save-dev`安装的包会出现在这里。主要是在开发过程中依赖的一些工具。用法与`dependencies`相似。

## bundledDependencies：

数组，打包时的依赖。如果配置了`bundledDependencies`，在项目中执行 `npm pack`将项目打包时，最后生成的.tgz包中，会包含`bundledDependencies`中配置的依赖。
bundledDependencies中的依赖必须在devDependencies或者dependencies中声明过。

## peerDependencies: 

指定当前组件的依赖以其版本。如果组件使用者在项目中安装了其他版本的同一依赖，会提示报错。