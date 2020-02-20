# LaTeX 的文本语法

## 一、基本结构

```latex
\documentclass{article} 

\begin{document}

\end{document}
```

上述三⾏代码代表了⼀个 LaTeX ⽂件必不可少的三个部分。

- `\documentclass{article}` 表⽰该⽂档的类型是期刊（aiticle） ，LaTeX 还⽀持 report（报 告） 、book（书籍）、beamer（幻灯⽚）等多种类型。

- `\begin{document}` 和 `\end{document}` 表⽰⽂档内容的开始和结束，所有正⽂内容都写在其中。
  
- `\begin{document}` 前的部分我们称为导⾔区，宏包都是写在导⾔区。

```latex
\documentclass{article} 

%这是导言区 

\begin{document} 


\end{document}
```

## 二、支持中文

2020年 LaTeX 对中⽂的⽀持已经很完善，因此我们可以直接 使⽤ `\documentclass[UTF8]{ctexart}`，代表该⽂档是中⽂论⽂（ctex+article）。 

```latex
\documentclass[UTF8]{ctexart} 

\begin{document} 

关注微信公众号“钦念博客”

\end{document}
```
![](https://raw.githubusercontent.com/qinnian/FigureBed/master/20200216171756.png)

## 三、特殊字符

 % 表示注释，$、^、_ 等用于排版数学公式，& 用于排版表格

 如果想要输入以上符号，需要使用以下带反斜线的形式输入：

```latex
\documentclass[UTF8]{ctexart} 

\begin{document} 

\#

\$ 

\% 

\& 

\{ \} 

\_

\^{} 

\~{} 

\textbackslash

\end{document}
```

![](https://raw.githubusercontent.com/qinnian/FigureBed/master/20200220095946.png)

>注：
>
>(1)`\^` 和 `\~` 两个命令是需要带参数的，如果不加一对花括号（空参数），就将后面的字符作为参数，形成重音效果。
>
>(2)`\\` 被直接定义成了手动换行的命令，输入反斜杠就只好用 `\textbackslash`

## 四、标点符号

LATEX 的单引号 ‘ ’ 用 `和 ' 输入；双引号 “ ” 用 `` 和 '' 输入

```latex
\documentclass[UTF8]{ctexart} 

\begin{document} 

``请关注微信公众号 `钦念博客' 。''

\end{document}
```
![](https://raw.githubusercontent.com/qinnian/FigureBed/master/20200220100730.png)

LATEX 中有三种长度的“横线”可用：

- 连字号（hyphen）:用来组成复合词；

- 短破折号（en-dash）：用来连接数字表示范围；

- 长破折号（em-dash）：用来连接单词，与中文语境中的破折号类似。

```latex
\documentclass[UTF8]{ctexart} 

\begin{document} 
\noindent
daughter-in-law, X-rated\\
pages 13--67\\
yes---or no?

\end{document}
```
![](https://raw.githubusercontent.com/qinnian/FigureBed/master/20200220101829.png)

LATEX 提供了命令 `\ldots` 来生成省略号，相对于直接输入三个点的方式更为合理。`\ldots` 和 `\dots` 是两个等效的命令。


```latex
\documentclass[UTF8]{ctexart} 

\begin{document} 

one, two, three, \ldots one hundred.

\end{document}
```
![](https://raw.githubusercontent.com/qinnian/FigureBed/master/20200220103501.png)

## 五、文字强调

强调文字的方法，要么是添加下划线等装饰物，要么是改变文字的字体。

LATEX 定义了 `\underline` 命令用来为文字添加下划线：

```latex
\documentclass[UTF8]{ctexart} 

\begin{document} 

An \underline{underlined} text.

\end{document}
```
![](https://raw.githubusercontent.com/qinnian/FigureBed/master/20200220104613.png)

`\underline` 命令生成下划线的样式比较机械，不同的单词可能生成高低各异的下划线，并且无法换行。`ulem` 宏包解决了这一问题，它提供的 `\uline` 命令能够轻松生成自动换行的下划线。

另外，`\emph` 命令用来将文字变为斜体以示强调。如果在本身已经用 `\emph` 命令强调的文字内部嵌套使用 `\emph` 命令，内部则使用直立体文字。

```latex
\documentclass[UTF8]{ctexart} 

\begin{document} 

An example of \uline{some long and underlined words.}


Some \emph{emphasized words,including \emph{double-emphasized}words}, are shown here.

\end{document}
```
![](https://raw.githubusercontent.com/qinnian/FigureBed/master/20200220110145.png)


## 六、断行断页

- 句尾添加 `\\` 强制换行
- 句尾添加 `\par` 强制换段（或者按两次`Enter`）
- 句尾添加 `\newpage` 强制换页

```latex
\documentclass[UTF8]{ctexart} 

\begin{document} 
	
	关注微信公众号“钦念博客”\\我的GitHub是https://github.com/qinnian
	
	我的知乎账号是“钦念”\par
	我的博客网站：www.qinnian.xyz
	
\end{document}
```
![](https://raw.githubusercontent.com/qinnian/FigureBed/master/20200216201301.png)

- 段前添加 `\noindent` 取消缩进（默认段⾸是缩进两格的）

```latex
\documentclass[UTF8]{ctexart} 

\begin{document} 
	
	关注微信公众号“钦念博客”\\我的GitHub是https://github.com/qinnian
	
	\noindent
	我的知乎账号是“钦念”\par
	我的博客网站：www.qinnian.xyz
	
\end{document}
```
![](https://raw.githubusercontent.com/qinnian/FigureBed/master/20200216202204.png)

