# Markdown----语法简记
> the grammar of Markdown 

## 宗旨
 Markdown的目标是实现**易读易写**。
 
 一份使用Markdown 格式撰写的文件应该可以直接以纯文本发布，并且看起来不会像是由许多标签或者是格式指令所构成。
 
 Markdown 语法受到一些既有 text-to-HTML 格式的影响，包括 Setext、atx、Textile、reStructuredText、Grutatext 和 EtText，而最大灵感来源其实是纯文  本电子邮件的格式。
 
## 兼容HTML
Markdown 语法的目标是：成为一种适用于网络的书写语言。

不在 Markdown涵盖范围之内的标签，都可以直接在文档里面用HTML撰写。不需要额外标注这是HTML或者Markdown，直接加标签就可以了。

要制约的只有一些 HTML 区块元素――比如 <div></div>、<table></table>、<pre></pre>、<p></p> 等标签，必须在前后加上空行与其它内容区隔开，还要求它们的开始标签与结尾标签不能用制表符或空格来缩进。Markdown 的生成器有足够智能，不会在 HTML 区块标签外加上不必要的 <p></p> 标签。

## 特殊字符自动转换

## 区块元素
###  段落和换行
一个 Markdown 段落是由一个或多个连续的文本行组成，它的前后要有一个以上的空行（空行的定义是显示上看起来像是空的，便会被视为空行。比方说，若某一行只包含空格和制表符，则该行也会被视为空行）。普通段落不该用空格或制表符来缩进。

### 标题
Markdown 支持两种标题的语法，类 Setext 和类 atx 形式。

类 Setext 形式是用底线的形式，利用 = （最高阶标题）和 - （第二阶标题）

类 Atx 形式则是在行首插入 1 到 6 个 # ，对应到标题 1 到 6 阶

### 区块引用Blockquotes
> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

### 列表
Markdown 支持有序列表和无序列表。

无序列表使用星号、加号或是减号作为列表标记：
*   Red
*   Green
*   Blue

等同于：
+   Red
+   Green
+   Blue

也等同于：
-   Red
-   Green
-   Blue

有序列表则使用数字接着一个英文句点：
1.  Bird
2.  McHale
3.  Parish

### 代码区块
要在 Markdown 中建立代码区块很简单，只要简单地缩进 4 个空格或是 1 个制表符就可以，例如，下面的输入：

这是一个普通段落：

    这是一个代码区块。

这个每行一阶的缩进（4 个空格或是 1 个制表符），都会被移除，例如：

Here is an example of AppleScript:

    tell application "Foo"
        beep
    end tell

代码区块中，一般的 Markdown 语法不会被转换，像是星号便只是星号，这表示你可以很容易地以 Markdown 语法撰写 Markdown 语法相关的文件。

### 分隔线
你可以在一行中用三个以上的星号、减号、底线来建立一个分隔线，行内不能有其他东西。你也可以在星号或是减号中间插入空格。下面每种写法都可以建立分隔线：

* * *

***

*****

- - -

---------------------------------------

##  区段元素
### 链接
Markdown 支持两种形式的链接语法： 行内式和参考式两种形式。

要建立一个行内式的链接，只要在方块括号后面紧接着圆括号并插入网址链接即可，如果你还想要加上链接的 title 文字，只要在网址后面，用双引号把 title 文字包起来即可，例如：

This is [an example](http://example.com/ "Title") inline link.

[This link](http://example.net/) has no title attribute.

参考式的链接是在链接文字的括号后面再接上另一个方括号，而在第二个方括号里面要填入用以辨识链接的标记：

This is [an example][id] reference-style link.
你也可以选择性地在两个方括号中间加上一个空格：

This is [an example] [id] reference-style link.
接着，在文件的任意处，你可以把这个标记的链接内容定义出来：

[id]: http://example.com/  "Optional Title Here"

链接内容定义的形式为：

方括号（前面可以选择性地加上至多三个空格来缩进），里面输入链接文字
接着一个冒号
接着一个以上的空格或制表符
接着链接的网址
选择性地接着 title 内容，可以用单引号、双引号或是括弧包着
下面这三种链接的定义都是相同：

[foo]: http://example.com/  "Optional Title Here"
[foo]: http://example.com/  'Optional Title Here'
[foo]: http://example.com/  (Optional Title Here)

### 强调

Markdown 使用星号（*）和底线（_）作为标记强调字词的符号，用两个 * 或 _ 包起来的话，例如：

*single asterisks*

_single underscores_

**double asterisks**

__double underscores__

但是如果你的 * 和 _ 两边都有空白的话，它们就只会被当成普通的符号。

### 代码
如果要标记一小段行内代码，你可以用反引号把它包起来，例如：

Use the `printf()` function.

如果要在代码区段内插入反引号，你可以用多个反引号来开启和结束代码区段：

``There is a literal backtick (`) here.``

### 图片
允许两种样式： 行内式和参考式。

行内式的图片语法看起来像是：

![Alt text](/path/to/img.jpg)

![Alt text](/path/to/img.jpg "Optional title")
详细叙述如下：

一个惊叹号 !
接着一个方括号，里面放上图片的替代文字
接着一个普通括号，里面放上图片的网址，最后还可以用引号包住并加上 选择性的 'title' 文字。
参考式的图片语法则长得像这样：

![Alt text][id]
「id」是图片参考的名称，图片参考的定义方式则和连结参考一样：

[id]: url/to/image  "Optional title attribute"
到目前为止， Markdown 还没有办法指定图片的宽高

## 其他
### 自动链接
Markdown 支持以比较简短的自动链接形式来处理网址和电子邮件信箱，只要是用尖括号包起来， Markdown 就会自动把它转成链接。一般网址的链接文字就和链接地址一样，例如：

<http://example.com/>

### 反斜杠

Markdown 可以利用反斜杠来插入一些在语法中有其它意义的符号，例如：如果你想要用星号加在文字旁边的方式来做出强调效果，你可以在星号的前面加上反斜杠：

\*literal asterisks\*
Markdown 支持以下这些符号前面加上反斜杠来帮助插入普通的符号：

\\   反斜线

\`   反引号

\*   星号

\_   底线

\{}  花括号

\[]  方括号

\()  括弧

\#   井字号

\+   加号

\-   减号

\.   英文句点

\!   惊叹号
