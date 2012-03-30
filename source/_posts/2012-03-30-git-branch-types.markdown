---
layout: post
title: "Git Branch types"
date: 2012-03-30 23:58
comments: true
categories: 
---

    git中branch有三种类型：
    
1. local branch

本地分支，就是我们平常操作的分支，git中默认是master分支  
可以通过 git branch  b1 来建立本地分支，通过 git checkout b1 来切换分支

1. tracking branch

        A 'tracking branch' in Git is a local branch that is connected to a remote branch. 
        When you pull on that branch, it automatically pulls to the remote branch that it is connected with.

跟踪分支是一种和远程分支有直接联系的本地分支(远程分支的本地书签、别名)，跟踪分支是一种本地分支！

当我们在跟踪分支上使用git pull命令，会自动从相应的remote branch上fetch，然后在merge到该分支上.  
如果我们想在跟踪分支上直接使用git push命令，让它自动push到对应的remote branch上.  
还需要设置push的默认行为：

    git config push.default tracking

当我们使用git clone命令后，会自动在本地建立一个master的分支来跟踪origin/master.  
我们也可以使用:

    git checkout -b b1 origin/master
    
或者

    git checkout --track -b develop   origin/develop

命令来手工新建一个跟踪分支develop，并切换到该分支上(该本地develop 对应origin/develop)  
如果我们想把已经存在的一个分支b2转换成一个tracking branch，需要

    git config branch.b2.remote origin
    git config branch.b2.merge refs/heads/master

或者，我们手工修改~/.git/config文件.  
下面是一个tracking branch的配置信息 :

    [branch "master"]
        remote = origin
        merge = refs/heads/master
        
1. remote branch

它实际上是指向远端服务器的某个分支，用来跟踪远程分支的变化，  也即以前提到过的origin/master分支
