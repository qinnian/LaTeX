# LaTex 的安装与配置


## 一、TeXLive 下载 

- [TeXLive下载（官网）](http://www.tug.org/texlive/)
  
- [TeXLive下载（清华大学镜像）](https://mirrors.tuna.tsinghua.edu.cn/CTAN/systems/texlive/Images/)

- [TeXLive下载（百度网盘）](https://pan.baidu.com/s/1eGHrD4KiWE2u4Ihn2y0v4w) 提取码：zb7b 
  
## 二、TeXLive 安装 

1. 在 TeXLive 文件，找到 `install-tl-advanced.bat`文件，以管理员身份运行。

![](https://raw.githubusercontent.com/qinnian/FigureBed/master/20200213093619.png)

2. 修改 TeXLive 文件的安装位置，为了控制一下TeX Live占用的内存大小，我们可以选择修改N. of collections选项，并根据个人需要，去掉Texworks(比较老的编辑器，不推荐)以及部分我们日常不会使用的语言包，例如阿拉伯语、斯洛伐克语等等

![](https://raw.githubusercontent.com/qinnian/FigureBed/master/20200213094306.png)

3. 经过一段漫长的安装，欢迎进入 TeXLive 的世界

![](https://raw.githubusercontent.com/qinnian/FigureBed/master/20200213094506.png)

4. 检查安装是否成功
```
tex -v //查看 tex 的版本信息
```
![](https://raw.githubusercontent.com/qinnian/FigureBed/master/20200215092012.png)

```
latex -v //查看 laTeX 的版本信息
```
![](https://raw.githubusercontent.com/qinnian/FigureBed/master/20200215133653.png)

```
xelatex -v //查看 XeTeX 的版本信息
```

![](https://raw.githubusercontent.com/qinnian/FigureBed/master/20200215133831.png)

```
pdflatex -v //查看 pdfTeX 的版本信息
```
![](https://raw.githubusercontent.com/qinnian/FigureBed/master/20200216093131.png)

## 三、TeXstudio 下载安装 

- [TexStudio下载（官网）](https://texstudio.updatestar.com/zh-cn)
  
- [TexStudio下载（百度网盘）](https://pan.baidu.com/s/1YlqTPoR1YDviW8BxNCR5oA) 提取码：pcs5j

## 四、测试LaTeX环境

``` LaTex
\documentclass[UTF8]{ctexart}
    \title{钦念博客}
    \author{Qinnian}
    \date{\today}
    \begin{document}
    \maketitle
    www.qinnian.xyz
\end{document}
```
按 `Ctrl+S` 完成编译加保存功能

![](https://raw.githubusercontent.com/qinnian/FigureBed/master/20200213100024.png)
