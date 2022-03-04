# Mac 下使用 tree 生成文件树形结构

2022.03.02

## 下载安装

https://www.jianshu.com/p/3fac8eb15c7b

## 命令

### 1. 显示当前路径下所有目录结构

```shell
~$ tree
.
├── HELP.md
├── mvnw
├── mvnw.cmd
├── pom.xml
├── src
│   ├── main
│   │   ├── java
│   │   │   └── com
│   │   │       └── xiakaibo
│   │   │           └── xlblogxkb
│   │   │               ├── ...
│   │   └── resources
│   │       ├── application.yml
│   │       ├── mapper
│   │       │   ├── ...
...
```

### 2. 将目录结构保存到文件中

o: output

```shell
~$ tree -o fileName
```


例：
```shell
~$ tree -o tree.txt
```

### 3. 只显示文件夹

d: directory

```shell
~$ tree -d
.
├── src
│   ├── main
│   │   ├── java
│   │   │   └── com
│   │   │       └── xiakaibo
│   │   │           └── xlblogxkb
│   │   │               ├── config
│   │   │               ├── ...
│   │   └── resources
│   │       ├── mapper
│   │       ├── static
│   │       └── templates
│   └── test
│       └── java
│           └── com
│               └── xiakaibo
│                   └── xlblogxkb
└── ...
45 directories
```

### 4. 显示最后修改时间

D: Date

```shell
~$ tree -D
[Mar  2 01:38]  .
├── [Feb  4 11:14]  HELP.md
├── [Feb  4 11:14]  mvnw
├── [Feb  4 11:14]  mvnw.cmd
├── [Feb  4 14:49]  pom.xml
├── [Feb  4 11:14]  src
│   ├── [Feb  4 11:14]  main
│   │   ├── [Feb  4 11:14]  java
│   │   │   └── [Feb  4 11:14]  com
│   │   │       └── [Feb  4 11:14]  xiakaibo
│   │   │           └── [Feb 16 12:39]  xlblogxkb
│   │   │               ├── [Feb  4 11:58]  CodeGenerator.java
│   │   │               ├── [Feb 16 12:39]  XlblogXkbApplication.java
...
```

### 5. 显示 n 层目录

L: Level

```shell
~$ tree -L n
```

例：

```shell
~$ tree -L 1
.
├── HELP.md
├── mvnw
├── mvnw.cmd
├── pom.xml
├── src
├── target
└── xlblog-xkb.iml
```

### 6. 忽略特定文件夹或文件

I: Ignore

```shell
~$ tree -I pattern
```

例：

```shell
~$ tree -I "target" -I "src"
.
├── HELP.md
├── mvnw
├── mvnw.cmd
├── pom.xml
└── xlblog-xkb.iml
```









