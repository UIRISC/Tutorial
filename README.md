# Tutorial

> **Author: [StevenChaoo](https://github.com/StevenChaoo)**

![vscode](https://img.shields.io/badge/visual_studio_code-007acc?style=flat&logo=visual-studio-code&logoColor=ffffff) ![neovim](https://img.shields.io/badge/Neovim-57a143?style=flat&logo=Neovim&logoColor=ffffff) ![git](https://img.shields.io/badge/Git-f05032?style=flat&logo=git&logoColor=ffffff) ![visitors](https://visitor-badge.glitch.me/badge?style=flat-square&page_id=UIR-ISCIE.Tutorial&left_color=grey&right_color=blue)

This blog is written by **Neovim** and **Visual Studio Code**. You may need to clone this repository to your local and use **Visual Studio Code** to read. ***Markdown Preview Enhanced*** plugin is necessary as well.

This blog will be the very first repository in this organization for facilitating us doing research well. How to be a successful Ph.D student is as same as how to do your research successfully. I was enlightened by [[Tutorial by Mark Dredze]](https://www.cs.jhu.edu/~mdredze/publications/HowtoBeaSuccessfulPhDStudent.1_1.pdf), hoping it could enlighten you either.

This tutorial will divided into ~~**three**~~ **four parts**. As Mark said, mastering some technical tools will help you effectively conduct successful research such as Make, Bash configuration, vi/vim etc.. I will share four useful technical tools can help you control your code or files, deploy your code on server, compile your own paper or report and set proxy using Clash with *git basic*, *Unix basic*, *LaTeX basic* and *Clash for Linux* respectively.

**All the notes are summarized through my own actual use. There must be many mistakes. Welcome to point out and welcome to submit a PR.**

- [Tutorial](#tutorial)
  - [1. Git basic](#1-git-basic)
  - [2. Unix basic](#2-unix-basic)
  - [3. LaTeX basic](#3-latex-basic)
  - [4. Clash for Linux](#4-clash-for-linux)

## 1. Git basic

You don't need to know how git works and what difference between git and other version control tools (Definitly, if you want to know the background and the very foundemantal scheme of git, this book is recommanded *Git Pro*). Just memory the usage of git and use it frequently.

**Installment on Linux:**
```shell
$ sudo apt/dnf/pacman install git-all
```

**Installment on MacOS:**
```shell
$ git --version
```

**Installment on Windows:**
Official version can be download automatically at [https://git-scm.com/download/win](https://git-scm.com/download/win).

**Clone exist repository:**
```shell
$ git clone https://github.com/xxx/CurrentName [NewName]
```

**Initial your local repository:**
```shell
$ cd ./Project_name
$ git init
```

**Check status:**
```shell
$ git status
```

**Track Files:**
```shell
$ git add xxx # add single file
$ git add xxx yyy zzz # add multiple files
$ git add . # add all files in current directory
```

**Submit:**
```shell
$ git commit -m "xxx"
```

**Check commit log:**
```shell
$ git log
```

**Re-submit:**
```shell
$ git commit -m "xxx"
$ git add forgotten_file
$ git commit --amend
```

**Branch:**
```shell
$ git branch new_branch # create new branch
$ git checkout new_branch # swtich branch
$ git branch # check all branches
```

**Romote:**
```shell
$ git remote add origin https://github.com/xxx/Name.git
$ git push -u origin master # push at first time
$ git push # push to remote repository
```

## 2. Unix basic

**Shut down & Reboot:**
```shell
$ shutdown -h now / time # shutdown immediately / after time
$ reboot # reboot
```

**Check document:**
```shell
$ shutdown --help
$ man shutdown
```

**Change directory:**
```shell
$ cd directory/ # change to directory in current path
$ cd ~# change current path to home directory
$ cd ../ # change to parent directory
```

**Check files:**
```shell
$ ls # list all files in current directory, -a for hidden files
```

**Directory manipulate:**
```shell
$ mkdir directory # create directory in certain path
$ rm directory # delete directory, -r for iterative, -f for force
$ mv directory /new_directory # change name or move to another directory
$ cp directory /new_directory # copy directory
```

**File manipulate:**
```shell
$ touch file # create file in certain path
$ rm file # delete file, -f for force
$ mv file /new_directory/new_file # change name or move to another directory
$ cp file /new_directory/new_file # copy file
$ vi/vim/nvim/nano/emacs file # edit file with vi-based / nano / emacs
$ cat/ccat/bat file # view file in command line
```

**Change permission:**
```shell
chmod 111 file # r, w, and x means readable, writable, and executable respectively. -/d{---}{---}{---} means file / directory {user's permission} {group with user's permission} {other group's permission}
```

**Zip:**
```shell
tar [option] file.tar file1 file2 ... # -z for using gzip tools to zip files, -c for zip files, -x for unzip file, -v for display process of zip, -f for use certain file name
```

**Search:**
```shell
$ alias | grep gclone # use grep to find 'gclone' in content beyond 'alias' command
$ find . -size +100M # find files of which size is larger than 100M in current path
$ locate pwd # search all files about pwd
$ which anaconda # fine path of anaconda
```

**su, sudo:**
```shell
$ su another_user # switch to another_user
$ sudo brew install neofetch # install neofetch with root identification
```

**Other commands:**
```shell
$ pwd # check current path
$ ps -ef # check all procession activated
$ kill pid # kill certain procession with pid (procession id number)
$ ifconfig # check nic information
$ ping ip # check connection status with ip
```

## 3. LaTeX basic

LaTeX template of thesis of University of International Relations.
```tex
\documentclass[12pt]{article}
% ----------------------------------------库函数⬇️
\usepackage[a4paper,left=25mm,right=25mm,top=25mm,bottom=25mm]{geometry}  
\usepackage{ctex}        % 中文库
\usepackage{titletoc}    % 目录库
\usepackage{fancyhdr}    % 页眉库
\usepackage{url}         % 链接库
\usepackage{graphicx}    % 图片库
\usepackage{float}       % 数学库
\usepackage{amsmath}     % 复杂数学库
\usepackage{amssymb}     % 花体字符库
\usepackage{algorithm}   % 算法流程图库
\usepackage{algorithmic} % 算法流程图库
\usepackage{listings}    % 代码块库
\usepackage{xcolor}      % 代码块颜色库
\usepackage{multirow}    % 多行合并表格库
\usepackage{array}       % 表格库
\usepackage{booktabs}    % 三线表库
% ----------------------------------------库函数⬆️
% ----------------------------------------正文内英文字体设置⬇️
\setmainfont{Times New Roman}
% ----------------------------------------正文内英文字体设置⬇⬆️
% ----------------------------------------代码风格设置⬇️
\lstset{
    basicstyle          =   \sffamily,          % 基本代码风格
    keywordstyle        =   \bfseries,          % 关键字风格
    commentstyle        =   \rmfamily\itshape,  % 注释的风格，斜体
    stringstyle         =   \ttfamily,          % 字符串风格
    flexiblecolumns,                            % 列间自由宽度
    numbers             =   left,               % 行号的位置在左边
    showspaces          =   false,              % 是否显示空格
    numberstyle         =   \zihao{-5}\ttfamily,% 行号的样式，小五号，tt等宽字体
    showstringspaces    =   false,              % 显示空格
    captionpos          =   t,                  % 这段代码的名字所呈现的位置，t指的是top上面
    frame               =   lrtb,               % 显示边框
}
\lstdefinestyle{Python}{
    language        =   Python,                 % 语言选Python
    basicstyle      =   \zihao{-5}\ttfamily,
    numberstyle     =   \zihao{-5}\ttfamily,
    keywordstyle    =   \color{blue},
    keywordstyle    =   [2] \color{teal},
    stringstyle     =   \color{magenta},
    commentstyle    =   \color{red}\ttfamily,
    breaklines      =   true,                   % 自动换行
    columns         =   fixed,                  % 固定字间距
    basewidth       =   0.5em,
}
\lstdefinestyle{C++}{
    language        =   C++,                    % 语言选C++
    basicstyle      =   \zihao{-5}\ttfamily,
    numberstyle     =   \zihao{-5}\ttfamily,
    keywordstyle    =   \color{blue},
    keywordstyle    =   [2] \color{teal},
    stringstyle     =   \color{magenta},
    commentstyle    =   \color{red}\ttfamily,
    breaklines      =   true,                   
    columns         =   fixed,                  
    basewidth       =   0.5em,
}
% ----------------------------------------代码风格设置⬆️
% ----------------------------------------正文⬇️
\begin{document}
% 封面
\begin{titlepage}
	\center
    \includegraphics[width=10cm]{UIR.png}\\[3cm]
    \begin{flushleft}
        \text{\zihao{3}\heiti\qquad\qquad 中文标题：在这里输入中文标题}\\[0.5cm] 
        \text{\zihao{3}\heiti\qquad\qquad 英文标题：Enter your title name here}\\[3cm] 
    \end{flushleft}
	\begin{minipage}{0.5\textwidth}
		\begin{flushleft}\zihao{3}
			\heiti 届\quad\quad\ \ \, 别：xxxx级\\[0.5cm]
			\heiti 院\quad\quad\ \ \, 系：网络空间安全学院\\[0.5cm]
            \heiti 专业与方向：网络空间安全\\[0.5cm]
            \heiti 姓\quad\quad\ \ \, 名：xxx\\[0.5cm]
            \heiti 学\quad\quad\ \ \, 号：xxxxxxxx\\[0.5cm]
            \heiti 指\;导\;\,教\;师：xxx
		\end{flushleft}
	\end{minipage}\\[3cm]
    \text{\zihao{3}\heiti 完成时间：20xx年x月}
	\vfill 
\end{titlepage}
% 行间距
\linespread{1.5}
% 页眉
\pagestyle{fancy}
\fancyhead[C]{文章题目}
\fancyhead[L, R]{}
% 标题
\pagenumbering{Roman}
\title{\songti \zihao{2} \textbf{题目}}
\author{\fangsong \zihao{-3}作者1 \quad 作者2}
\date{}
\maketitle
% 摘要
\ctexset{abstractname = {\zihao{-4}摘要}}
\begin{abstract}
    \zihao{-4}\fangsong 中文摘要\\
    \zihao{-4} \textbf{\heiti 关键字：}中文关键词1；中文关键词2
\end{abstract}
\ctexset{abstractname = {\zihao{-4}Abstract}}
\begin{abstract}
    \zihao{-4} 英文摘要 \\
    \zihao{-4} \textbf{\heiti Keywords：}英文关键词1;英文关键词2
\end{abstract}
% 目录
\newpage
\tableofcontents
\contentsmargin{0pt}
\renewcommand\contentspage{\thecontentspage}
\dottedcontents{section}[20pt]{\vspace{1mm}\bfseries\songti\zihao{-4}}{25pt}{5pt}
\dottedcontents{subsection}[50pt]{\vspace{1mm}\songti\zihao{-4}}{30pt}{5pt}
\dottedcontents{subsubsection}[80pt]{\vspace{1mm}\songti\zihao{-4}}{40pt}{5pt}
% 文章内容
\newpage
\pagenumbering{arabic}
\section{\songti\zihao{-4}第一部分}
\section{\songti\zihao{-4}第二部分}
\subsection{\songti\zihao{-4}第二部分第一小节}
\subsubsection{\songti\zihao{-4}第二部分第一小节第一分节}
\section{\songti\zihao{-4}第三部分}
% 简单公式
\clearpage
\songti\zihao{-4}在语句内添加公式用$a^2=b^2+c^2$来表示
\songti\zihao{-4}在语段间添加公式用$$a^2=b^2+c^2$$来表示
% 分点
\clearpage
\songti\zihao{-4}分点可以用以下代码表示：
\begin{enumerate}
    \songti\zihao{-4}\item xxx
    \songti\zihao{-4}\item xxx
    \songti\zihao{-4}\item xxx
\end{enumerate}
或
\begin{itemize}
    \songti\zihao{-4}\item xxx
    \songti\zihao{-4}\item xxx
    \songti\zihao{-4}\item xxx
\end{itemize}
% 图片
\clearpage
\songti\zihao{-4}展示图片可以用如图1来表示：
\begin{figure}[H]
    \label{fig:图片}
    \centering
    \includegraphics[scale=0.5,trim=150 220 150 220,clip]{图片.jpeg}
    \caption{\fangsong 这是一张图片}
\end{figure}
% 表格
\clearpage
\songti\zihao{-4}展示表格可以用如表1来表示：
\begin{table}[H]
    \centering
    \begin{tabular}{ccc}
        \hline
        Parameters & T & $k_1$ \\ 
        \hline
        Values & 0.02s & 10 \\ 
        \hline
    \end{tabular}
    \caption{\fangsong 这是一个表格}
\end{table}
% 伪代码
\clearpage
\songti\zihao{-4}展示算法/伪代码可以用下面的方法来表示：
\begin{algorithm}[htb]
    \caption{ Framework of ensemble learning for our system.}
    \label{alg:Framwork}
    \begin{algorithmic}[1] % 这个1表示每一行都显示数字
    \REQUIRE ~~\\ % 算法的输入参数：Input
        The set of positive samples for current batch, $P_n$;\\
        The set of unlabelled samples for current batch, $U_n$;\\
        Ensemble of classifiers on former batches, $E_{n-1}$;
    \ENSURE ~~\\ % 算法的输出：Output
        Ensemble of classifiers on the current batch, $E_n$;
        \STATE Extracting the set of reliable negative and/or positive samples $T_n$ from $U_n$ with help of $P_n$;
        \STATE Training ensemble of classifiers $E$ on $T_n \cup P_n$, with help of data in former batches;
        \STATE $E_n=E_{n-1}\cup E$;
        \STATE Classifying samples in $U_n-T_n$ by $E_n$;
        \STATE Deleting some weak classifiers in $E_n$ so as to keep the capacity of $E_n$;
    \RETURN $E_n$; % 算法的返回值
    \end{algorithmic}
\end{algorithm}
\begin{algorithm}
    \caption{An example}
    \label{alg:2}
    \begin{algorithmic}
        \STATE {set $r(t)=x(t)$}
        \REPEAT
        \STATE set $h(t)=r(t)$
        \REPEAT
        \STATE set $h(t)=r(t)$
        \UNTIL{B}
        \UNTIL{B}
    \end{algorithmic}
\end{algorithm}
\begin{algorithm}
    \caption{Calculate $y = x^n$}
    \label{alg:3}
    \begin{algorithmic}
        \REQUIRE $n \geq 0 \vee x \neq 0$
        \ENSURE $y = x^n$
        \STATE $y \Leftarrow 1$
    \IF{$n < 0$}
        \STATE $X \Leftarrow 1 / x$
        \STATE $N \Leftarrow -n$
    \ELSE
        \STATE $X \Leftarrow x$
        \STATE $N \Leftarrow n$
    \ENDIF
    \WHILE{$N \neq 0$}
        \IF{$N$ is even}
            \STATE $X \Leftarrow X \times X$
            \STATE $N \Leftarrow N / 2$
        \ELSE[$N$ is odd]
            \STATE $y \Leftarrow y \times X$
            \STATE $N \Leftarrow N - 1$
        \ENDIF
    \ENDWHILE
    \end{algorithmic}
\end{algorithm}
\begin{algorithm}[h]
    \caption{An example for format For \& While Loop in Algorithm}
    \label{alg:4}
    \begin{algorithmic}[1]
        \FOR{each $i \in [1,9]$}
            \STATE initialize a tree $T_{i}$ with only a leaf (the root);\
            \STATE $T=T \cup T_{i};$\
        \ENDFOR
        \FORALL {$c$ such that $c \in RecentMBatch(E_{n-1})$}
            \STATE $T=T \cup PosSample(c)$;
        \ENDFOR
        \FOR{$i=1$; $i<n$; $i++$ }
            \STATE $//$ Your source here;
        \ENDFOR
        \FOR{$i=1$ to $n$}
            \STATE $//$ Your source here;
        \ENDFOR
            \STATE $//$ Reusing recent base classifiers.
        \WHILE {$(|E_n| \leq L_1 )and( D \neq \phi)$}
            \STATE Selecting the most recent classifier $c_i$ from $D$;
            \STATE $D=D-c_i$;
            \STATE $E_n=E_n+c_i$;
        \ENDWHILE
    \end{algorithmic}
\end{algorithm}
% 复杂公式
\clearpage
\songti\zihao{-4}展示复杂公式可以用下面的方法来表示：
\begin{gather}    % 会产生编号
	a+b=b+a\\
	ab=ba
\end{gather}
\begin{gather*}    % 不会产生编号
a \times b=b \times a\\
ab=ba   
\end{gather*}
\begin{gather}    % 会编号
a+b=b+a \notag \\    % \notag阻止编号
ab=ba   \notag     % \notag阻止编号
\end{gather}
\begin{align}
	x &= t + \cos t + 1\\
	y &= 2\sin t
\end{align}
\begin{equation}
	\begin{split}
	\cos 2x &= \cos^2 x - \sin^2 x\\
	&= 2\cos^2 x - 1
	\end{split}
\end{equation}
\begin{equation}
	D(x) = \begin{cases}
	1, &\text{如果} x \in \mathbb{Q}\\    % mathbb花体字符
	0, &\text{如果} x \in \mathbb{R}\setminus\mathbb{Q}	
		   \end{cases}    % \text是为了在数学公式中处理中文
\end{equation}
% 代码块
\clearpage
\songti\zihao{-4}展示代码块可以用下面的方法来表示：
\lstinputlisting[
    style       =   Python,
    caption     =   {\bf test.py},
    label       =   {test.py}
]{test.py}
\lstinputlisting[
    style       =   C++,
    caption     =   {\bf test.cpp},
    label       =   {test.cpp}
]{test.cpp}
% 参考引用
\clearpage
\songti\zihao{-4}参考文献这样使用\cite{ref2}
\begin{thebibliography}{99}  
    \bibitem{ref1}Zheng L, Wang S, Tian L, et al., Query-adaptive late fusion for image search and person re-identification, Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition, 2015: 1741-1750.  
    \bibitem{ref2}Arandjelović R, Zisserman A, Three things everyone should know to improve object retrieval, Computer Vision and Pattern Recognition (CVPR), 2012 IEEE Conference on, IEEE, 2012: 2911-2918.  
    \bibitem{ref3}Lowe D G. Distinctive image features from scale-invariant keypoints, International journal of computer vision, 2004, 60(2): 91-110.  
    \bibitem{ref4}Philbin J, Chum O, Isard M, et al. Lost in quantization: Improving particular object retrieval in large scale image databases, Computer Vision and Pattern Recognition, 2008. CVPR 2008, IEEE Conference on, IEEE, 2008: 1-8.  
\end{thebibliography}
\end{document}
% ----------------------------------------正文⬆️
```

## 4. Clash for Linux

Step 1: Install.

```bash
# 0. Download clash-linux-amd64-vxx.xx.xx.gz from https://github.com/Dreamacro/clash/releases.
cd {Download folder}
# 1. Unzip the file.
gunzip clash-linux-amd64-vxx.xx.xx.gz
# 2. Move it to personal bin folder.
sudo mv clash-linux-amd64-vxx.xx.xx /usr/local/bin/clash
# 3. Add execute permission to clash.
sudo chmod +x /usr/local/bin/clash
# 4. Initial config.yaml and Country.mmdb
clash
```

Step 2: Modify configurations.

```bash
# 0. Download your personal config.yaml file.
cd {Download folder}
# 1. Chaneg config.yaml
mv config.yaml ~/.config/clash/config.yaml
```

Step 3: Start proxy at boot.

```bash
# 1. Move ~/.config/clash folder to /etc/
sudo mv ~/.config/clash /etc
# 2. Edit clash.service
echo "[Unit]
Description=Clash Daemon

[Service]
ExecStart=/usr/local/bin/clash -d /etc/clash/
Restart=on-failure

[Install]
WantedBy=multi-user.target" >> clash.service
# 3. Move clash.service to /etc/systemd/system
sudo mv clash.service /etc/systemd/system
# 4. Enable clash.service
sudo systemctl enable clash.service
# 5. Start clash.service
sudo systemctl start clash.service
```

Step 4: Set proxy mannually.

```bash
# 1. Start proxy.
export all_proxy=sock5://127.0.0.1:xxxx
# 2. Stop proxy.
unset all_proxy
```

Or you can write following command in .zshrc or .bashrc.

```zsh
alias proxy="export all_proxy=sock5://127.0.0.1:xxxx"
alias unproxy="unset all_proxy"
```
