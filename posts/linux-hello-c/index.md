# linux 编程初体验

> 在 Linux 上编译 c 语言文件。

### 打开 vim 编辑器
（没有就用 vi, 或者先安装 vim`sudo apt-get install vim`)
```
$ vim
```

### 编辑文件

打开文件编辑器之后编辑文件
![](images/ubuntu.png)

首先按`Esc`再`:`进入末行命令  
再保存为 hello.c 文件后退出
```
: w hello.c
: q
```

打开目录看看生成的文件
```
$ ls
```

### 编译生成可执行文件并执行
```
$ gcc hello.c -o hello
$ ./hello
```
![](images/hello.png)

若权限不够则加可执行权限`chmod +x hello`
