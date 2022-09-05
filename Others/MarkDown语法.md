# 代码高亮(\` 或\~)
```python
def 
    return 0
```

待办
====
- [x] have done
    - [x] first
    - [x] second
- [ ] should do

### 强调语法
##### 粗体
换行末尾加两个空格再回车
I just love **bold text**.  
I just love __bold text__.  
Love **is** bold
##### 斜体
Italicized text is the *cat's meow*.  
Italicized text is the _cat's meow_.  
A *cat* meow
##### 粗体和斜体
This text is ***really important***.  
This text is ___really important___.  
This text is __*really important*__.  
This text is **_really important_**.  
This is really ***very*** important text.  

### 引用语法
> 单引用模块

> 多段落引用
>
> 多段落引用

> 嵌套块论文
>
>> 嵌套块论文

> #### 带其他元素的引用
>
> - 111111111111
> - 111111111111
>
>  *1111* 111111 **111111**.


### 有序列表
1. First item
5. Second item
8. Third item  
    3. Indented item  
    2. Indented item  
4. Fourth item

### 无序列表
> 破折号 (-)、星号 (*) 或加号 (+) 
- First item
- Second item
- Third item
    - Indented item
    - Indented item
- Fourth item

### 代码语法
At the command prompt, type `nano`.  
``Use `code` in your Markdown file.``

### 分隔线语法
单独一行三个及以上星号，破折号，下划线，分隔线前后添加空行保证兼容性。

---

单独一行三个及以上星号，破折号，下划线，分隔线前后添加空行保证兼容性。

### 链接语法
这是一个链接 [bilibilo](https://www.bilibili.com/)。
###### 给链接增加Title(鼠标悬停)
这是一个链接 [bilibili](https://www.bilibili.com/ "霹雳霹雳")。
###### 网址和Email(尖括号变为可点击链接)
<https://www.bilibili.com/>
<326338@zuhao360>

### 图片
![嘉然](https://user-images.githubusercontent.com/100335931/184601183-645ca5b9-f42f-4ff6-8c1b-0e3cc4ffcb1e.png "嘉门")
或给图片添加链接  
[![Diana](https://user-images.githubusercontent.com/100335931/184601183-645ca5b9-f42f-4ff6-8c1b-0e3cc4ffcb1e.png "嘉门")](csdiy.wiki)
### 表格(冒号是对齐方式)
| 姓名   | 生日 |    神必数字 |
| :----- | :--: | -------: |
| 嘉然然 | 0307   | 14536456 |
| 向晚AvavaAvA |  0612  | 241 |
| 乃琳 |  0808  | 3231 |
> 使用表格的HTML字符代码（&#124;）在表中显示竖线（|）字符。
### 转义字符
\引导 包括
> \ \` * _ {} [] () # + - . ! |

> 在 HTML 文件中，有两个字符需要特殊处理： < 和 & 。 < 符号用于起始标签，& 符号则用于标记 HTML 实体，如果你只是想要使用这些符号，你必须要使用实体的形式，像是&lt;和&amp;。
> & 符号其实很容易让写作网页文件的人感到困扰，如果你要打「AT&T」 ，你必须要写成「AT&amp;T」 ，还得转换网址内的 &
> Markdown 允许你直接使用这些符号，它帮你自动转义字符。如果你使用 & 符号的作为 HTML 实体的一部分，那么它不会被转换，而在其它情况下，它则会被转换成 &amp;。

### 内嵌HTML标签
- 行级内联标签
    > HTML 的行级內联标签如 `<span>`、`<cite>`、`<del>` 不受限制，可以在 Markdown 的段落、列表或是标题里任意使用。
- 区块标签
    > 区块元素──比如 `<div>`、`<table>`、`<pre>`、`<p>` 等标签，必须在前后加上空行，以便于内容区分。而且这些元素的开始与结尾标签，不可以用 tab 或是空白来缩进。  
    Markdown 会自动识别这区块元素，避免在区块标签前后加上没有必要的 `<p>` 标签。  
### 脚注
Here's a simple footnote,[^与内容无关] and here's a longer one.[^bignote]

[^与内容无关]: 脚注序号按顺序排列

[^bignote]: 脚注2
### 标题编号 {#标题编号1}
### 链接到标题id
[Heading IDs](#heading-ids)  
> 这部分没看懂  

流程图(不知道为什么用不了)
------
	```mermaid
	graph TB
	A[Apple]-->B{Boy}
	A---C(Cat)
	B.->D((Dog))
	C==喵==>D
	style A fill:#2ff,fill-opacity:0.1,stroke:#faa,stroke-width:4px
	style D stroke:#000,stroke-width:8px;
	```

> 删除符号： ~~你知道的太多了。~~ 

> 插入表情：笑嘻了 :sweat_smile: [emjoy大全](https://gist.github.com/rxaviers/7360908)

> \` 也用于禁止URL外链

> 横屏滑动幻灯片 `<![](url),![](url)>`

> `%20`代替空格保持兼容性

>  - 单空格 `&nbsp;`或`&#160;`或`&#xA0;`  
>  - 双空格 `&ensp;`或&#8194;`或`&#x2002;`  
>  - 四空格 `&emsp;`或&#8195;`或`&#x2003;`  
>  - 细空格`&thinsp;`或&#8201;`或`&#x2009;`  
