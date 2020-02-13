# laTex 安装

>系统为 Win10 ，本文仅供参考

## 一、TeXLive 下载 

- [TeXLive下载（官网）](http://www.tug.org/texlive/)
  
- [TeXLive下载（清华大学镜像）](https://mirrors.tuna.tsinghua.edu.cn/CTAN/systems/texlive/Images/)

- [TeXLive下载（百度网盘）](https://pan.baidu.com/s/1eGHrD4KiWE2u4Ihn2y0v4w) 提取码：zb7b 
  
## 二、TeXLive 安装 

1. 在 TeXLive 文件，找到 `install-tl-advanced.bat`文件，以管理员身份运行。

![](https://raw.githubusercontent.com/qinnian/FigureBed/master/20200213093619.png)

2. 修改 TeXLive 文件的安装位置或其他设置

![](https://raw.githubusercontent.com/qinnian/FigureBed/master/20200213094306.png)

3. 显示安装成功

![](https://raw.githubusercontent.com/qinnian/FigureBed/master/20200213094506.png)

## 三、VSCode 下载安装 

- [VSCode下载（官网）](https://code.visualstudio.com/)

## 四、VSCode 安装插件

- LaTex language support
- LaTex Workshop

## 五、测试LaTeX环境

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
