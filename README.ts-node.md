# typescript 起步之安装及配置 ts-node 环境变量

要想编写第一个 hello typescript 程序，当然要经过安装这个必要的过程，我们分为接下来几个步骤：

#### 步骤一：全局安装 typescript

```
npm install -g typescript
```

#### 步骤二：全局安装 ts-node

安装它的原因是typescript自带的tsc命令并不能直接运行typescript代码。但值得注意的是 ts-node 并不等于 typescript 的 Node.js ，仅仅封装了 typescript 的编译过程，提供直接运行typescript代码的能力。

```
npm install -g ts-node
```

#### 步骤三：编写第一个typescript程序

typescript 的文件后缀名为 .ts ，文件中输入以下内容：

```
console.log('Hello Typescript ! ')
```

#### 步骤四：打开控制台，并输入

```
ts-node 文件名.ts    // Hello Typescript !
```