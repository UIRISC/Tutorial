# Tutorial

> **Author: [StevenChaoo](https://github.com/StevenChaoo)**

![vscode](https://img.shields.io/badge/visual_studio_code-007acc?style=flat-square&logo=visual-studio-code&logoColor=ffffff)![neovim](https://img.shields.io/badge/Neovim-57a143?style=flat-square&logo=Neovim&logoColor=ffffff)![git](https://img.shields.io/badge/Git-f05032?style=flat-square&logo=git&logoColor=ffffff)

This blog is written by **Neovim** and **Visual Studio Code**. You may need to clone this repository to your local and use **Visual Studio Code** to read. ***Markdown Preview Enhanced*** plugin is necessary as well.

This blog will be the very first repository in this organization for facilitating us doing research well. How to be a successful Ph.D student is as same as how to do your research successfully. I was enlightened by [[Tutorial by Mark Dredze]](https://www.cs.jhu.edu/~mdredze/publications/HowtoBeaSuccessfulPhDStudent.1_1.pdf), hoping it could enlighten you either.

This tutorial will divided into **three parts**. As Mark said, mastering some technical tools will help you effectively conduct successful research such as Make, Bash configuration, vi/vim etc.. I will share three useful technical tools can help you control your code or files, deploy your code on server, and compile your own paper or report with git, Unix basic, and LaTeX basic respectively.

**All the notes are summarized through my own actual use. There must be many mistakes. Welcome to point out and welcome to submit a PR.**

- [Tutorial](#tutorial)
  - [1. Git](#1-git)
  - [2. Unix basic](#2-unix-basic)
  - [3. LaTeX basic](#3-latex-basic)

## 1. Git

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

## 3. LaTeX basic
