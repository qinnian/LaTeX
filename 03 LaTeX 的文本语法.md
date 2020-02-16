# LaTeX 的文本语法

## 一、基本结构

```latex
\documentclass{article} 

\begin{document}

\end{document}
```

上述三⾏代码代表了⼀个 LaTeX ⽂件必不可少的三个部分。

- `\documentclass{article}` 表⽰该⽂档的类型是期刊（aiticle） ，LaTeX 还⽀持 report（报 告） 、book（书籍）、beamer（幻灯⽚）等多种类型。

- `\begin{document}` 和 `\end{document}` 表⽰⽂档内容的开始和结束，也就是说，所有正⽂内容都写在其中。
  
- `\begin{document}` 前的部分我们称为导⾔区，宏包我们都是写在导⾔区。

LaTeX 中，我们⽤ % 表⽰注释

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

## 三、章与节

如果⽂档类型为 article ，我们采⽤ `\section{章节名}` 、 `\subsection{章节名}` 开启⼀个章节或者次级章节。

```latex
\documentclass[UTF8]{ctexart} 

\begin{document} 
	\section{第一章节}
	 
	Hello World 
	
	\subsection{小标题} 
	Hello World 
	
	\section{第二章节} 
	Hello World 

\end{document}
```
![](https://raw.githubusercontent.com/qinnian/FigureBed/master/20200216204556.png)

默认情况下，第⼀级章节标题是居中显⽰的(注意，上图预览视图的第⼀⾏是⻚眉)，显然这不符合⼤多数需要，为此需要在导⾔区添加⼀些设置章节格式的代码

```latex
\documentclass[UTF8]{ctexart} 
\CTEXsetup[name={第,章}]{section}
\CTEXsetup[format={\zihao{-3}\raggedright\bfseries}]{section}

\begin{document} 
	\section{第一章节}
	 
	Hello World 
	
	\subsection{小标题} 
	Hello World 
	
	\section{第二章节} 
	Hello World 

\end{document}
```
![](https://raw.githubusercontent.com/qinnian/FigureBed/master/20200216205325.png)

## 四、行与段

换⾏
- ⼀⾏的末尾添加 `\\` 表⽰另起⼀⾏。

换段
- 第一种：两次按 Enter 表⽰另起⼀段落，
- 第二种：一段的末尾添加 `\par` 表⽰另起⼀段落。

```latex
\documentclass[UTF8]{ctexart} 

\begin{document} 
	
	关注微信公众号“钦念博客”\\我的GitHub是https://github.com/qinnian
	
	我的知乎账号是“钦念”\par
	我的博客网站：www.qinnian.xyz
	
\end{document}
```
![](https://raw.githubusercontent.com/qinnian/FigureBed/master/20200216201301.png)

>默认段⾸是缩进两格的，若想取消缩进，段前添加 `\noindent` 

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

## 五、字体设置

### 字体选择

下⾯代码⽤于设置正⽂部分中英⽂的默认字体分别为 `Roman Times New` 和 `楷体-简` （Windows 上写楷体即可）

`xeCJK` 宏包⽤于设置中⽂字体，`fontspec` 宏包⽤于设置 英⽂字体，将其添加到导⾔区即可。
```latex
\usepackage{xeCJK} 
\setCJKmainfont[BoldFont={黑体-简}]{楷体-简} 
```
```latex
\usepackage{fontspec} 
\setmainfont{Times New Roman}
```

### 六、字体大小

通常使⽤ `\zihao{数字}` 的⽅式来改变字体⼤⼩，数字的⼤⼩表⽰该部分⽂字为⼏号字体。
```latex
\documentclass[UTF8]{ctexart} 
\CTEXsetup[name={第,章}]{section}
\CTEXsetup[format={\zihao{-3}\raggedright\bfseries}]{section}


\begin{document} 

    \section{这是第一章节} 
    \zihao{2} 
    Hello World 
        \subsection{这是次级章节} 
        Hello World
    \section{这是第二章节} 
    Hello World 

\end{document}
```
![](https://raw.githubusercontent.com/qinnian/FigureBed/master/20200216210749.png)

如果只想改变某部分⽂字的⼤⼩，可以⽤⼀对⼤括号 {} 括住 `\zihao{数字}和⽂字` ， LaTeX 中⼀对⼤括号 {} 表⽰⼀个环境，环境内的格式控制语句只对环境中的⽂字起作⽤。
```latex
{\zihao{3} Hello World}
```

## 七、页面设置

### 纸张设置

LaTeX 中可以通过可选项来设置⻚⾯纸张的⼤⼩（默认为 A4 ）

```latex
\documentclass[UTF8,a4pape r]{ctexart}
```

### 页边距

LaTeX 可以⽤ geometry 宏包来设置⻚边距

```latex
\usepackage{geometry} 
\geometry{left=2.5cm,right= 2.5cm,top=2.0cm,bottom=2cm}
```
### 页眉页脚

LaTeX 中⽤ `\pagestyle` 来设置⻚眉⻚脚，默认为⻚眉显⽰ 章节标题和⻚码 ，⻚脚为空。默认⻛格⽤下⾯的代码表⽰：

```latex
\pagestyle{headings}
```

如果要取消⻚眉⻚脚，⽤代码：
```latex
\pagestyle{empty}
```