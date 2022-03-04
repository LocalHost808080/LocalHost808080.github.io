# Git Debug Records

2022.02.14



## Bug 1：Push 失败

### 问题描述

```shell
~$ git push origin master
error: src refspec master does not match any.
error: failed to push some refs to 'git@github.com:LocalHost808080/LocalHost808080.github.io.git'
```

### 错误原因

远程仓库的分支名不是 `master`，而是 `main`。

### 解决方法

```shell
~$ git push origin main
Enumerating objects: 9, done.
Counting objects: 100% (9/9), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (5/5), 435 bytes | 87.00 KiB/s, done.
Total 5 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To github.com:LocalHost808080/LocalHost808080.github.io.git
   9716047..5f083ac  main -> main
```

