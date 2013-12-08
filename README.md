LatexReport
===========
latex 幻灯片的基本写法,会逐步完善。
以下描述的是基本,基本的代码格式，后续会描述更复杂的应用，比如添加图片，添加表格，添加代码等等。
1.加载基本类以及设置字体等等。
```latex
\documentclass[]{beamer}% 中括号中设置属性，颜色有blue（default），red，brown，blackandwhite，compress 尽量压缩导航栏。
\usetheme{Madrid}  %加载样式Madrid
\usecolortheme{lily} %colortheme 
\usepackage{url} %用于使用产连接等等。。。
\usepackage{xeCJK}  %如果使用中文的话需要加载这个包
\setCJKmainfont{SimSun} %设置要使用的中文字体。字体必须是在电脑中存在的，可以用fc-list:lang=zh 来查看本机电脑安装的字体列表。
\setbeamertemplate{footline}[frame number] % 定制Madrid的样式，这句话的意思是footline 只显示frame number 其他的都不显示。
\setbeamertemplate{} %还可以设置其他的，待自己发掘
```
标题页的设置
```latex
\title{}
\author{}
%author 的高级形式
\author{
   \texorpdfstring{张刚
                   \newline
                   \href{mailto:zhanggang@ihep.ac.cn}
                 {\footnotesize\ttfamily{zhanggang@ihep.ac.cn}}}
                   {}
   \thanks{你好}}

\institute{}
```
```latex
\begin{document} % begin a new document
\maketitle %将前面的标题信息放到文档中
%设置outline 设置了之后，使用\section outline会将每一个section放入section。
\begin{frame}
       \frametitle{Outline}
       \tableofcontents
\end{frame}
\begin{frame} %add a new page of slide
  \frametitel{}
  \begin{itemize}
    \item ...
    \item ...
    ...
  \end{itemize}
\end{frame}

\begin{frame}
  \frametitel{}
  \begin{itemize}
    \item ...
    \item ...
    ...
  \end{itemize}
\end{frame}

\end{document}
```

