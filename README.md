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



latex 学习
===========

latex处理源文件，首先要知道文档类型。有\documentclass来提供。
```latex
\documentclass[option]{class}
```
class 包含论文（article），信件，幻灯片等等。
article 排版科技期刊、短报告、程序文档、邀请函等。
report 排版多章节的长报告、短篇的书籍、博士论文等。
book 排版书籍。

Option:
  缺省10pt。
  缺省letterpaper。可以是a4paper，a5paper，legalpaper等等。
  其他参数等用的时候再查。

下面给出一个例子
```latex
\documentclass[11pt,twoside,a4paper]{article}
```
关于宏包：
```latex
\usepackage[option]{package}
```
页面样式
```latex
\pagestyle{style}
```
style 包括：
plain 页眉为空，页脚由居中的的页码组成。这是默认的页面式样。
headings 页眉由当前的章节标题和页码组成，页脚为空。
empty 设置页眉、页脚均为空。

可用
```latex
\thispagestyle{style}
```
来改变当前页的格式。


大型文档：拆分源文件
使用如下命令：
```latex
\include{filename} 不想换页插入的用\input{filename}

\includeonly{filename,filename,...}
```
只有在includeonly命令包含下的filename才会生效

使用syntonly 宏包可以让LATEX 快速的检查你的文档：LATEX 浏览你的
文档，仅仅检查语法和所使用的命令是否正确，不会产生DVI 输出。
```latex
\usepackage{syntonly}
\syntaxonly
```

