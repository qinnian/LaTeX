# LaTeX 的文档元素

## 一、章节

- article 文档类带编号的层级为 `\section` / `\subsection` / `\subsubsection` 三级；

- report/book 文档类带编号的层级为 `\chapter` / `\section` / `\subsection` 三级。
  
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

## 二、目录

在 LATEX 中生成目录非常容易，只需在合适的地方使用命令：

```latex
\tableofcontents
```
这个命令会生成单独的一章（book / report）或一节（article），标题默认为 “Contents”。

有时我们使用了 \chapter* 或 \section* 这样不生成目录项的章节标题命令，而又想手动生成该章节的目录项，可以在标题命令后面使用：

```latex
\addcontentsline{toc}{⟨level⟩}{⟨title⟩}
```

其中 ⟨level⟩ 为章节层次 chapter 或 section 等，⟨title⟩ 为出现于目录项的章节标题。

## 三、标题页

LATEX 支持生成简单的标题页。首先需要给定标题和作者等信息：

```latex
\title{⟨title⟩} 
\author{⟨author⟩}
\date{⟨date⟩}`
```
其中前两个命令是必须的（不用 `\title` 会报错；不用 `\author` 会警告），`\date` 命令可选。`LATEX` 还提供了一个 `\today` 命令自动生成当前日期，`\date` 默认使用 `\today`。在 `\title`、`\author`等命令内可以使用 `\thanks` 命令生成标题页的脚注，用 `\and` 隔开多个人名。

在信息给定后，就可以使用 `\maketitle` 命令生成一个简单的标题页了。

## 四、特殊环境

### 1、列表环境

LATEX 提供了基本的有序和无序列表环境 enumerate 和 itemize，两者的用法很类似，都用 \item 标明每个列表项。enumerate 环境会自动对列表项编号。

其中 \item 可带一个可选参数，将有序列表的计数或者无序列表的符号替换成自定义的符号。列表可以嵌套使用，最多嵌套四层。

```latex
\documentclass[UTF8]{ctexart} 

\begin{document} 

\begin{enumerate}
	\item An item.
	\begin{enumerate}
		\item A nested item.\label{itref}
		\item[*] A starred item.
	\end{enumerate}
	\item Reference(\ref{itref}).
\end{enumerate}

\end{document}
```
![](https://raw.githubusercontent.com/qinnian/FigureBed/master/20200220145657.png)

## 2、对齐环境

用`\centering`、`\raggedright`、`\raggedleft`命令直接改变文字的对齐方式

```latex
\documentclass[UTF8]{ctexart} 

\begin{document} 

\centering
Centered text paragraph.

\raggedright
Left-aligned text paragraph.

\raggedleft
Right-aligned text paragraph.

\end{document}
```
![](https://raw.githubusercontent.com/qinnian/FigureBed/master/20200220150657.png)


## 五、图片

LATEX 本身不支持插图功能，需要由 graphicx 宏包辅助支持。在调用了 graphicx 宏包以后，就可以使用 `\includegraphics` 命令加载图片了：

```latex
\includegraphics[⟨options⟩]{⟨filename⟩}
```

其中 `⟨filename⟩` 为图片文件名，与使用 `\include` 命令类似，文件名有时需要使用相对路径或绝对路径。图片文件的扩展名可写可不写。

另外 `graphicx` 宏包还提供了 `\graphicspath` 命令，用于声明一个或多个图片文件存放的目录，使用这些目录里的图片时可不用写路径。
