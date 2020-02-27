# LaTeX 的样式设定

## 一、字体选择

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

### 二、字体大小

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
### 字体颜色

调用 color 或 xcolor 宏包后，我们就可以用如下命令切换颜色

```latex
\large\sffamily
{\color{red} 红色} \\
{\color{blue} 蓝色}
```
## 三、页面设置

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

### 四、间距

#### 水平间距

LATEX 默认为将单词之间的“空格”转化为水平间距。如果需要在文中手动插入额外的水平间距，可使用 \hspace 命令

```latex
This\hspace{1.5cm}is a space of 1.5 cm.
```

#### 垂直间距

```latex
A paragraph.
\vspace{2ex}
Another paragraph.
```

### 五、超链接

```latex
\href{⟨url⟩}{⟨text⟩}
```

