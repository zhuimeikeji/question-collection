# npm包serve的简单使用

前端打好包后有时需要将打包好的项目跑一下看看效果，但又不能直接打开，这时可以简单使用serve工具：

首先下载：

```
mkdir serve-demo
cd serve-demo
npm i serve --save
```

然后将其他项目打好的包放进这个文件夹，比如放入一个build文件夹，然后在package.json中添加一行npm脚本：

```
"serve": "serve ./build"
```

然后在本项目目录下跑个服务即可：

```
npm run serve
```

会在命令行下出现这句：INFO: Accepting connections at http://localhost:5000

在浏览器输入http://localhost:5000即可查看到你打包好的项目