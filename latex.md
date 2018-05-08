# ***LatexLearning***
# 1、	常用符号记录
* 换行：\\，\newline
* 分段：\par
* 退一格：\quad，或者~；退两格：\qquad
* 强行断行：\\* ,强行断行，禁止分页
* 另起新页：\newpage
* 特殊符号：\%，即输入%；\backslash，即输入\；\{，即输入{左大括号;‘-’连字号，‘- -’短破折号，‘- - -’长破折号；\~，波浪号，\sim%～波浪号；^{\circ} ，度（。）；
* 省略号：\ldots %排在基线上，\cdots%设为居中，\vdots%垂直，\ddots%对角线三圆点
* 积分号：\int %\int_a^b,表示积分限从a到b
* 求和运算符：\sum
* 乘积运算符：\prod
* 公式字体加粗：\mathbf{}
* 公式字体中空：\mathbb{}
* 字体命令：\textrm,\mathrm（确保字体大小交换机制起作用，但是只对于较短多项才起作用）
* 自动调整符号：\left( ….\right)，即在\left后加上要调整到符号，再以\right结尾，如果\right后没有符号，就加上点.
* 手工调整符号大小：\Big,\bigg
* 小于空格：\ ,  3/18quad;  \: 4/18quad ;  \; 5/18quad;  \! -3/18quad
* 幻影：\phantom ，可以为不在最终输出种出现的字符预留空间
* 禁止连字：两字母中间加上\{box},或者\/
* 注音符号：\^ ;   \’’   ; \``

# 2、	显示中文：
    \usepackage{CJK}
    \begin{document}
    \begin{CJK}{UTF8}{gbsn}    %gkai CJK自带的楷体
    …
    \begin{CJK}
    \end{document}
# 3、	盒子：
1. 段落盒子Minipage
    ```
    \begin{minipage}[位置][高度][内部高度]{宽度}
    对象..
    \end{minipage}
    or
    \parbox[位置][高度][内部位置]{宽度}{对象} 
    ```
2. 左右盒子box
    ```
    \mbox{对象}    %自生成，不带边框
    \framebox[宽度][位置]{对象}   %带边框
    \fbox{对象}   %带0.4pt边框
    \makebox[宽度][位置]{对象}  位置参数：「l,左;c,居中;r,右对齐;s,占满;」
    \raisebox{位移}[高度][深度]{对象}。  垂直盒子；正负表示高/深度
    ```
# 4、	交叉引用
* 定义：\label{书签名} %\{sec:section1}
* 类别：章节cha,节书签sec,插图fig,表格书签tab,公式equ,文本text
* 方法：\ref{书签名} %序号引用「所有类别」
\pageref{书签名} %页数引用
# 5、	环境(environment)
* 定义：\begin{环境} …\end{环境}   %\begin{document} \end{document}
* 类别：
    * 位置环境：center%居中环境，\centering%居中命令，flushleft%左对齐环境，\riggedright%左对齐命令，对应的有right右对齐命令 
    * 功能环境：绘图环境：picture(高度，宽度)(x偏移，y偏移)
* 建立新的环境：\newenvironment{name}[num]{before}{after}
# 6、	自定义命令
* 定义：\newcommand{\name%命令名}{内容}
* 多参数时：\newcommand{\name}[参数个数]{#1,#2…#n}
* 代入参数\name{}{}{}..
# 7、	杂项
* 数组：
        ```
        \begin{array}{ccc}       %{ccc}即是列数,可加铅垂线|.
        …&…&…&…. \\
        …&…&…&… \\
        … …            
        \end{array}.    特别的：如果要加上括号可以用big或者\left,\right
        ```
    * *用途：表达式，数组，矩阵*
* 脚注：\footnote{footnote text}
* 定理，定义：\newtheorem{name}[counter]{text}[section],name是短关键词，用于标识“定理”。Text定义“定理”的真实名称，会最终显示出来。Counter可以是指定先前声明的“定理”的name，section指定“定理”编号所在的章节层次(可以用section,subsection,paragraph等)
# 8、	排版
* 标题：\title{}
* 作者：\author{} 制作标题：\maketitle
* 首行缩进：\parindent
* 盒子内空白命令：水平\hfill or \hfil，垂直\vfill or \vfil
* 衍生：点\dotfill，直线\hrulefill,上括符\downbracefill,下括符\upbracefill，
* 全局对齐： 
# 9、	公式
* 常用环境：\begin{equation}单个公式不可换行
    - \begin{align},多个公式，可用&分列对齐，\\ 换行 
    - \begin{eqnarray},类似于align,内置
    - \begin{gather},不提供对齐，按照全局方式分别对齐
    - \begin{flalign},用法：只在等号前面使用一个&，适合用来编写多行的公式推导和数值计算过程
    - \begin{multline}，不支持&分列
    - 内嵌环境（不可独立）：\gathered \split \aligned
    - \nonumber
# 10、	编号
* 实心圆点：\begin{itemize} \item…\item \end{itemize};改变实心圆点，就改变\item[symbol]
* 数字排序：\begin{enumerate} \item…\item \end{enumerate};默认数字编号，改变编号方式，\begin{enumerate}[(1)]}%即采用(1),(2),(3)…需要加上宏包usepackage{enumerate}
* 使公式跟随章节编号变，加上代码\numberwithin{eqution}{section}
# 11、	字体相关
* 方法：用大括号分组{},给指定的字加上字体，注意随后\par命令。或者，使用环境.\begin{字体}{内容}\end{字体}
* 常用字体：\textrm,
* 逐字打印：\verb+|text|
# 12、	特殊功能
* 参考文献：\bibitem{maker} ; 再在正文中引用：\cite{maker}
* 索引：\makeindex激活 。（必须引入宏包\usepackage{makeidx}）
* 页眉页脚：
