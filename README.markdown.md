# .md格式的markdown文件常用语法介绍

README文件后缀名为md。md是markdown的缩写，markdown是一种编辑博客的语言。用惯了可视化的博客编辑器（比如CSDN博客，囧），这种编程式的博客编辑方案着实让人眼前一亮。不过GitHub支持的语法在标准markdown语法的基础上做了修改，称为Github Flavored Markdown，简称GFM。

## 关于标题

规范的README文件开头都写上一个标题，这被称为大标题。

```md
大标题  
====
```

demo --------------------------

大标题  
====

--------------------------

在文本下面加上 等于号 = ，那么上方的文本就变成了大标题。等于号的个数无限制，但一定要大于0个哦。。

比大标题低一级的是中标题，也就是显示出来比大标题小点。

```md
中标题  
-------  
```

demo --------------------------

中标题  
-------

--------------------------

在文本下面加上 下划线 - ，那么上方的文本就变成了中标题，同样的 下划线个数无限制。

除此之外，你也会发现大，中标题下面都有一条横线，没错这就是 = 和 - 的显示结果。

如果你只输入了等于号=，但其上方无文字，那么就只会显示一条直线。如果上方有了文字，但你又只想显示一条横线，而不想把上方的文字转义成大标题的话，那么你就要在等于号=和文字直接补一个空行。

<em>补空行：是很常用的用法，当你不想上下两个不同的布局方式交错到一起的时候，就要在两种布局之间补一个空行。</em>

如果你只输入了短横线（减号）-，其上方无文字，那么要显示直线，必须要写三个减号以上。不过与等于号的显示效果不同，它显示出来时虚线而不是实线。同减号作用相同的还有星号*和下划线_，同样的这两者符号也要写三个以上才能显示一条虚横线。

除此以外，关于标题还有等级表示法，分为六个等级，显示的文本大小依次减小。不同等级之间是以井号  #  的个数来标识的。一级标题有一个 #，二级标题有两个# ，以此类推。


```md
# 一级标题  
## 二级标题  
### 三级标题  
#### 四级标题  
##### 五级标题  
###### 六级标题
```


demo --------------------------

# 一级标题  
## 二级标题  
### 三级标题  
#### 四级标题  
##### 五级标题  
###### 六级标题

--------------------------

注意井号#和标题名称要并排写作一行, 实际上，前文所述的大标题和中标题是分别和一级标题和二级标题对应的。即大标题大小和一级标题相同，中标题大小和二级标题相同。

## 显示文本

### 普通文本

直接输入的文字就是普通文本。需要注意的是要换行的时候不能直接通过回车来换行，需要使用\<br>(或者\<br/>)。也就是html里面的标签。<em>事实上，markdown支持一些html标签，你可以试试。</em>当然如果你完全使用html来写的话，就丧失意义了，毕竟markdown并非专门做前端的，然而仅实现一般效果的话，它会比html写起来要简洁得多得多啦。

```md
这是一段普通的文本，  
直接回车不能换行，<br>  
要使用\<br>
```

demo --------------------------

这是一段普通的文本，  
直接回车不能换行，<br>  
要使用\<br>

--------------------------

注意第三行的\<br>前加了反斜杠 \ 。目的就是像其他语言那样实现转义，也就是 <  的转义。

此外，要显示一个超链接的话，就直接输入这个链接的URL就好了。显示出来会自动变成可链接的形式的。

```html
显示空格的小Tip
默认的文本行首空格都会被忽略的，但是如果你想用空格来排一下版的话怎么办呢，有个小技巧，那就是把你的输入法由半角改成全角就OK啦。
```

### 单行文本

使用两个Tab符实现单行文本。

```md
Hello,大家好，我是果冻虾仁。
```

demo --------------------------

        Hello,大家好，我是果冻虾仁。

--------------------------

### 多行文本

多行文本和单行文本异曲同工，只要在每行行首加两个Tab

```md
欢迎到访  
很高兴见到您  
祝您，早上好，中午好，下午好，晚安 
```

demo --------------------------

        欢迎到访  
        很高兴见到您  
        祝您，早上好，中午好，下午好，晚安 

--------------------------

### 字体设置斜体、粗体、删除线

```md
这里是文字 - 正常

*这里是文字 - 倾斜*

**这里是文字 - 加粗**

***这里是文字 - 倾斜加粗***

_这里是文字 - 倾斜_

__这里是文字 - 加粗__

___这里是文字 - 倾斜加粗___

~这里是文字 - 下划线~

~~这里是文字 - 下划线~~
```

demo --------------------------

这里是文字 - 正常

*这里是文字 - 倾斜*

**这里是文字 - 加粗**

***这里是文字 - 倾斜加粗***

_这里是文字 - 倾斜_

__这里是文字 - 加粗__

___这里是文字 - 倾斜加粗___

~这里是文字 - 下划线~

~~这里是文字 - 下划线~~

--------------------------




## 部分文字的高亮

如果你想使一段话中部分文字高亮显示，来起到突出强调的作用，那么可以把它用 \`  \` 包围起来。注意这不是单引号，而是Tab上方，数字1左边的按键（注意使用英文输入法）。

```md
Thank `You` . Please `Call` Me `Coder`
```

demo --------------------------

Thank `You` . Please `Call` Me `Coder`

--------------------------

## 文字超链接

给一段文字加入超链接的格式是这样的 \[要显示的文字\]\(链接的地址\)。比如：

```md
[我的博客](https://www.zhi-jie.net) 
```

demo --------------------------

[我的博客](https://www.zhi-jie.net) 

--------------------------

你还可以给他加上一个鼠标悬停显示的文本。

```md
[我的博客](https://www.zhi-jie.net "悬停显示") 
```

demo --------------------------

[我的博客](https://www.zhi-jie.net "悬停显示") 

--------------------------

即在URL之后 用双引号括起来一个字符串。同样要注意这里是英文双引号。

### 锚点

锚点其实就是页内超链接。比如我这里写下一个锚点，点击回到目录，就能跳转到目录。 在目录中点击这一节，就能跳过来。

注意：在简书中使用锚点时，点击会打开一个新的当前页面，虽然锚点用的不是很舒服，但是可以用注脚实现这个功能。

###### 语法说明：

在你准备跳转到的指定标题后插入锚点{#标记}，然后在文档的其它地方写上连接到锚点的链接。

```md
#### 测试目录 {#index}

跳转到[目录](#index)
```

demo --------------------------

#### 测试目录 {#index}

跳转到[目录](#index)

--------------------------

### 注脚

在需要添加注脚的文字后加上脚注名字\[^注脚名字],称为加注。 然后在文本的任意位置(一般在最后)添加脚注，脚注前必须有对应的脚注名字。

```md
测试注脚[^1]，测试注脚[^2]

[^1]:对方空间噶开始减肥爱上
[^2]:山东警方哈萨克送快递放假啊说
```

demo --------------------------
测试注脚[^1]，测试注脚[^2]

[^1]:对方空间噶开始减肥爱上
[^2]:山东警方哈萨克送快递放假啊说

--------------------------


## 插入图片

### 来源于网络的图片

网上有很多README插入图片的教程了，经我自己多次测试呢，发现可以使用的最简单，最基本的语法是：

```md
![](http://www.baidu.com/img/bdlogo.gif)
```

demo --------------------------

![](http://www.baidu.com/img/bdlogo.gif)

--------------------------

即 叹号! + 方括号[ ] + 括号( ) 其中叹号里是图片的URL。

如果不加叹号! ,就会变成普通文本baidu了。

在方括号里可以加入一些 标识性的信息，比如

```md
![baidu1](http://www.baidu.com/img/bdlogo.gif)  
```

demo --------------------------

![baidu1](http://www.baidu.com/img/bdlogo.gif)  

--------------------------

这个方括号里的baidu并不会对图像显示造成任何改动，如果你想达到<em>鼠标悬停</em>显示提示信息，那么可以仿照前面介绍的文本中的方法，就是这样：

```md
![baidu2](http://www.baidu.com/img/bdlogo.gif "百度logo")   
```

demo --------------------------

![baidu2](http://www.baidu.com/img/bdlogo.gif "百度logo")    

--------------------------

### GitHub仓库里的图片

有时候我们想显示一个GitHub仓库(或者说项目)里的图片而不是一张其他来源网络图片，因为其他来源的URL很可能会失效。那么如何显示一个GitHub项目里的图片呢？

其实与上面的格式基本一致的，所不同的就是括号里的URL该怎么写。

```md
https://gitee.com/ 你的用户名 / 你的项目名 / raw / 分支名 / 存放图片的文件夹 / 该文件夹下的图片  (gitee.com 非特定)
```

这样一目了然了吧。比如：

```md
![](https://gitee.com/zhuimei/question-collection/raw/master/img/testimg.jpeg) 
```

demo --------------------------

![](https://gitee.com/zhuimei/question-collection/raw/master/img/testimg.jpeg)  

--------------------------

或则用相对路径支持项目中的图片

```md
![](./img/testimg.jpeg) 
```

demo --------------------------

![](./img/testimg.jpeg)  

--------------------------

### base64 图片

```md
![avatar](data:image/jpeg;base64,/9j/4AAQSkZJRg......)
```

demo --------------------------

![avatar](data:image/jpeg;base64,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)

--------------------------

这个时候会发现插入的这一长串字符串会把整个文章分割开，非常影响编写文章时的体验。如果能够把大段的base64字符串放在文章末尾，然后在文章中通过一个id来调用，文章就不会被分割的这么乱了。
可以用下方的高级用法

```md
![avatar][base64str]

[base64str]:data:image/jpeg;base64,/9j/4AAQSkZJRg......
```

demo --------------------------

![avatar][base64str]

--------------------------

用高级用法时，格式代码和标示的代码至少中间要空一行，否则可能显示不正确


### 给图片加上超链接

如果你想使图片带有超链接的功能，即点击一个图片进入一个指定的网页。那么可以这样写：

```md
[![baidu3](http://www.baidu.com/img/bdlogo.gif)](https://www.zhi-jie.net "悬停显示")
```

demo --------------------------

[![baidu3](http://www.baidu.com/img/bdlogo.gif)](https://www.zhi-jie.net "悬停显示")

--------------------------

```md
[![baidu4][baidu5]](https://www.zhi-jie.net)

[baidu5]:http://www.baidu.com/img/bdlogo.gif  "悬停显示"
```

demo --------------------------

[![baidu4][baidu5]](https://www.zhi-jie.net)

[baidu5]:http://www.baidu.com/img/bdlogo.gif  "悬停显示"

--------------------------

这两句和前面的写法差异较大，但是也极易模仿着写出，就不过多介绍了。只需注意上下文中的 baidu 是你自己起的标识的名称，可以随意，但是一定要保证上下两行的 标识 是一致的。
这样就能实现 点击图片进入网页的功能了。


## 表格

表格的基本写法很简单，就跟表格的形状很相似：

```md
学号|姓名|性别|分数
-|-|-|-
1|张三|男|56
2|李四|女|87
3|王五妹|女|98
```

demo --------------------------

学号|姓名|性别|分数
-|-|-|-
1|张三|男|56
2|李四|女|87
3|王五妹|女|98

--------------------------

表格对齐方式：我们可以指定表格单元格的对齐方式，冒号在左边表示左对齐，右边表示有对齐，两边都有表示居中。

```md
学号|姓名|性别|分数
:-|:-|:-:|-:
1|张三|男|56
2|李四|女|87
3|王五妹|女|98
```

demo --------------------------

学号|姓名|性别|分数
:-|:-|:-:|-:
1|张三|男|56
2|李四|女|87
3|王五妹|女|98

--------------------------

## 分割线

你可以在一行中用三个以上的星号(*)、减号(-)、底线(_)来建立一个分隔线，行内不能有其他东西。你也可以在星号或是减号中间插入空格

```md
***
---
____
```

demo --------------------------

***
---
____

--------------------------

## 引用

### 普通引用

```md
> 文字
> 文字
>
> 文字
> 文字
```

demo --------------------------

> 文字
> 文字
>
> 文字
> 文字

--------------------------

### 引用的嵌套使用

嵌套从小到大可以不空行，如果从大到小不空行就会所有层级内容输出到最后。

```md
> 第一层
>> 第二层
>>> 第三层
>>>> 第四层
>>>>> 第五层
>>>>>> 第六层
>>>>>>> 第七层
>>>>>>>> 第八层
>>>>>>>>> 第九层
>>>>>>>> 第八层

>>>>>>> 第七层

>>>>>> 第六层

>>>>> 第五层

>>>> 第四层

>>> 第三层

>> 第二层

> 第一层
```

demo --------------------------

> 第一层
>> 第二层
>>> 第三层
>>>> 第四层
>>>>> 第五层
>>>>>> 第六层
>>>>>>> 第七层
>>>>>>>> 第八层
>>>>>>>>> 第九层
>>>>>>>> 第八层

>>>>>>> 第七层

>>>>>> 第六层

>>>>> 第五层

>>>> 第四层

>>> 第三层

>> 第二层

> 第一层

--------------------------

### 引用其它要素

引用的区块内也可以使用其他的 Markdown 语法，包括标题、列表、代码区块等。

```md
> ## 标题
>> * 列表
>> * 列表
>>>         区块
>>>> ```
>>>> 测试代码
>>>> ```
```

demo --------------------------

> ## 标题
>> * 列表
>> * 列表
>>>         区块
>>>> ```
>>>> 测试代码
>>>> ```

--------------------------



## 列表

### 无序列表

使用 *，+，- 表示无序列表。
注意：符号后面一定要有一个空格，起到缩进的作用。

```md
* 无序列表
* 无序列表
* 无序列表

+ 无序列表
+ 无序列表
+ 无序列表

- 无序列表
- 无序列表
- 无序列表
```

demo --------------------------

* 无序列表
* 无序列表
* 无序列表

+ 无序列表
+ 无序列表
+ 无序列表

- 无序列表
- 无序列表
- 无序列表

--------------------------

### 有序列表

使用数字和一个英文句点表示有序列表。
注意：英文句点后面一定要有一个空格，起到缩进的作用。

```md
1.有序列表
2.有序列表
3.有序列表

1. 有序列表
2. 有序列表
3. 有序列表
```

demo --------------------------

1.有序列表
2.有序列表
3.有序列表

1. 有序列表
2. 有序列表
3. 有序列表

--------------------------

### 无序列表和有序列表同时使用

```md
* 无序列表
* 无序列表
* 无序列表

1. 有序列表
2. 有序列表
3. 有序列表

* 1. 无有序列表
* 2. 无有序列表
* 3. 无有序列表

1. * 有无序列表
2. * 有无序列表
3. * 有无序列表
```

demo --------------------------

* 无序列表
* 无序列表
* 无序列表

1. 有序列表
2. 有序列表
3. 有序列表

* 1. 无有序列表
* 2. 无有序列表
* 3. 无有序列表

1. * 有无序列表
2. * 有无序列表
3. * 有无序列表

--------------------------

### 列表和其它要素混合使用

列表不光可以单独使用，也可以使用其他的 Markdown 语法，包括标题、引用、代码区块等。

```md
* # 无序标题

> 引用

> 引用

* ## 无序中标题

        区块

* ### 无序小标题

\```
代码块
\```
```

demo --------------------------

* # 无序标题

> 引用

> 引用

* ## 无序中标题

        区块

* ### 无序小标题

```md
代码块
```

--------------------------

（1）加粗效果不能直接用于列表标题里面，但是可以嵌套在列表里面混合使用。

（2）列表中包含代码块（前面加2个tab或者8个空格，并且需要空一行，否则不显示）。


在使用列表时，只要是数字后面加上英文的点，就会无意间产生列表，比如2017.12.30 这时候想表达的是日期，有些软件把它被误认为是列表。解决方式：在每个点前面加上\就可以了。

```md
2019\.10\.29 日期格式为例。
```

demo --------------------------

2019\.10\.29 日期格式为例。

--------------------------


[base64str]:data:image/jpeg;base64,/9j/4AAQSkZJRgABAQEASABIAAD/2wBDAAgGBgcGBQgHBwcJCQgKDBQNDAsLDBkSEw8UHRofHh0aHBwgJC4nICIsIxwcKDcpLDAxNDQ0Hyc5PTgyPC4zNDL/2wBDAQkJCQwLDBgNDRgyIRwhMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjL/wAARCABLAHkDASIAAhEBAxEB/8QAHAAAAgMBAQEBAAAAAAAAAAAABQYDBAcCAQgA/8QAPxAAAgEDAgMEBggEBAcAAAAAAQIDAAQRBSEGEjETQVFhFHGBkaGxFiIjMkJSU9EHYsHwJDNylBUXQ1RVk/H/xAAZAQADAQEBAAAAAAAAAAAAAAABAwQCAAX/xAAkEQACAgMAAgMAAgMAAAAAAAABAgARAxIhBEETMWEFQoGx8P/aAAwDAQACEQMRAD8ARdLBgmmTOeVh8Kf9OkGsaDeaauO1liPZg/nG6/EfGkHTiZJ537yQaP6Ffm2vkZW5frVJl+7lWEg2hiszvcIWZOVlOCPCo4ldmHKDjONhTVxVpq2urS3SBUt737YHGyk/fHv39tVLVrVG5Y7pY0C4CsPn4kmnfINbEk+IlyD6hfgANFrchYEE27dR/MtP99pOm6xGFvbZJCPuuNnX1MNxWf2WqtpMMnozwyKW25V6eOP77qatD4jh1VTH2bQ3EYyyk5Dea/tXLkub+IqJxrN1a6bc21k5k5VhGHYlidz1PUnzquscFyvNE6uPFTQnjK/hj1qGORsN2AO426nvq1wrw9ca3ctcM729jAftZwcEn8q+fyrLNR7OHeCG9Js0spxqVy3JFHzCIYyZHxjYeAzuaHahfSyl4+bMZYNsOh3/AHovxBfwx3VtZW8SvK+EjjztGg7/AO/M1LDHb+mW1rp1ta3NyUMs813kxhNwAoHn30gEE7GU9A0X/MUjKAMk7Vd0xLW7u0iurwWkLf8AV5C4B8wDt66Zte4d59Oe8RbdJoxlhDnDD299JkZgUjtLgKPIZ+VMUg9ESwK8M0aLhXhu1QPd62JARkYmRQfdk1KJeB7ADkRLhh/K8nz2pGt7zh+3GZ3uZj3iOPHxJq19LeH7baDSJHPjLMq/IGmcmLMcxxrplqOXT9Jkx3cqLGPhmuPp9df+IP8A7D+1JcnHvLtb6XYxDuLczn5iovp9f/p2P+3H70dv2GpneiLzGX1Cp9Pk+3dT+CU+7Nc8OrzNN6l/rVOGcQajKG+6zke3O1YYWzCaxnVrjvxevpfB8UybmCVWJ8FOx+PLWc5YMAcg+dN+r62n0b9BiILzEB/JRv8A0FLztDcssrPhwBlT1z+1HDap0RmYBn4YT0zQJJo3kupBAvL9UMfjTJonD6Wl4uoJqSGLJMMa5y5xuvsFftLuLa7jCX8KyREYJ8qYNNvbCBpYTbJBHG2LeVyFVeYgYz4nalbszVHtiVUsQLecLT8TcYWplV4tMihDXVz0CqCTyg/mPQevPdTdrnEdlpOnJ6JF2djbr9lFGPvf34+2pr26iMa2cTfZKcuw/G3eaWNQiDCRSmV6V1/K1ehFajEtn7MULTVL+/vNQ1S5ZWdRzKOgGT0HljajmlSanbWlvdW1q9688O5D4Cb539Q9lK8g7C0ngRGMrTMFUDOwFFbI6hbcPryT5leNwsecFBkAoR3HAz7aGVf9w4CNqj/LPrkdhMj6eq2/oyztOZPunIyuO/bIpMvNLuYGYsSq52OKl0u+1KDTu0u5AnpGLeKNnJL/AFgWJPqziiGu6XJp932sdzqLpcWU0pW5YFUYYxykev112FT0CazFQ6lhf59RC1dZoZIwXY8xIGD16U16j/CvU4rWO40y7iv2KBpIT9nIDjflycN7waTtDhk1TX9Ot5XeTnuEB5jnbOT8q+gCSDttVDMUoSU0xJAoTBruO70qIJdQyxTKcNHKpVh76of8Tf8AIPfX0DqNnZ6va+janaRXcPcJBuvmrDcew0uf8u+Ff+zu/wDdt+1EZF9wFT6me8OW0sbT9pE6Z5ccwxnrQC8Gbifykb51oMSbikKaZ47m7VGIWQuj47xnOPgKT4775GMEqGVj1OTXUZPMMHBz1NR1asFja8jWX/LOebbuwaurkxfYf0S8jd2tJJAjMCm7YwceNUdejFjMlgkzSiNe0du05vrN0GfIY99XrWzs9RmiilKSXSYRlJKmRAuBykbc3TbHXvoXcaTcIkcaRSmUyvCEKYO2P3PWlrjCtsI5sxZNSI+6PqrX+k2z5y5ULIc/iGxonOgYy5pd4c02fTLYxXDIzO/Phd+X2+ynKURiBiQMkeFK1CGhMs5Y2ZLwpouhz6dI0sKSXE0jmRpAGIOcYHgNqr6zwfbGbmS7Md4cdnLzEF1HQb7OQO7PNt3jFJ8+sXPDWohAxMNyvbKT3EkggeWwpl0njK0ubFrbUollRjzcrjIPgRUeTYEn1GjEri0NNOrPSYIblL64uY7swKYxcXE3YpG3fhQM+we+iOn3M1/HPZO91Pp8gaIiC2ARsjB+s2+M+3vJriDWtChbntNJhL4wCy82PfXup8VmJVjsYY4HEfPLmIDbwUHv76wrehAfGyM2zmZ1/DazWbiYuwB9GRmz4H7ta+TQHh9jcg37R2JaWMZlgiCOxychsDfoMe2jWSzBVGWJwB4mqWfY3O015Oi1Q+kw/qL7651CQWC3LSEf4dWZjn8oyawr6U6n+c+6toha5ljUf4k3FZtcnE8x/nb51pikKCxOANyT3Vl07iSdypyCxIPjvSfA6zGLJ5OBUsKc5YBgCFJGTjJ8KjGOnfX7oa9OYhxEeSRpEjbl7ELEQOpBG+3fkmjsd691qVq84Hb9mI3bGGclObmbxPUeyklG5DlSR4YNGNHurifVLRWdmVOZsMxPRTQI5NXHlWKup8BV26vVtLGW6uWKqFJxjoKErKcgn11Brfb6rClpGpVJHUSPnAVM5JydulJP7DONUgm4sFlcaZbyi2jRlLToEDYPd453HrzVCGK7ty1v6HqkEan/ACjaiYA+R22q3NDetqSJw8krWyKI0jQHIUdM+Z7/ADzTBpUfFts2ZLB0B3+0mAH71H9DVeiUJiWrJIMg0/h/Xr/sTHbTJa9X7e3WAsB3bnJolxJcWWnacbW8eFL5o2MKuMvsO720Rk1DiJkCi2iVvEzZ+QqO5S9keMyoGuOzPMAVDfPOKQL22I+pSAAmob7grgKKeLhsTXIcTTys55xg46Dbu6U0QXHYXMUxXm5GDcueuKp2qmK0jQgggbg9xrotTC5JuK1lbXpPSNLvi+xnVlOP5v8A7WcfRq1/Un99aHqa9rahM7FsmhHoq/kHupRzMp5GpiUjoiPqfEctzZyW0aKgk+qWGc476AJAz9Nh41ZRQ8CcwznB+NMmladaXEf2sIbB7ya9UjH46XXJ5+PGcjUIpsqr9QbnuxuTVi30jUbvHY2cpB72XlHxrRbeztrc4hgjT/SoFXolBPSoX/kT/VZavgj+xiHbcGahJgzSQxDwyWPw2ph0jhKCyuVmkmlkblKnoowRTMFA6AV4xJfB6eFTt5mZvdRy+NjHqW9Mi4YQhZrsJKuxXs849uTTTarw6VASa0lHhK39DtSBfaLptwvaS2UTSEbtjB99J2qwrYB/RXliHgsrY92aZhzKxqu/9+xT4WAsHk+irdbZYuWBI1j8IcAfCgms6nLYr/htDuZ2K8wdkJX1ELuPbWA6Vq2odvtdyrv1U4Pwprt+KtdtZEWLVLnl8Gbm+eatLa8IkgS/qFNT4o1uaRknWW1h/ShTsdvXjmPvoLA63tyipbF5id5F3bHeSe+tM0HVr3UYV9MmE2RvzIv7UW1K2gttKuXggiiZl+sUQKTv34o72tiDWjRiqSFUKOg2oVea1FBMbeBWubr9KP8AD/qPQUN4rvLi3ito4ZmjWWUI/KcEj19RRLTbWC2twsMSoOpwOteY7agGXqlz1ZbkojXQTmP4U6Dy8677cfkFWJwORdqq8q+FJu+mNHJ//9k=

