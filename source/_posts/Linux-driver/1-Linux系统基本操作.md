---
title: 1-Linux系统基本操作
date: 2025.2.17
updated:
tags:
  - Linux
  - 驱动开发
  - 
categories:
  - Linux
  - 驱动开发
  - 
keywords:
  - Linux
  - 驱动开发
  - 
top_img:
cover:
---

# 一.linux内核

## 1.啥是内核

![image-20240725204524887](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240725204524887.png)

内核约等于操作寄存器，但是内核不能被用户直接操作，而是要通过调用

## 2.内核下载

## ![image-20240725204737104](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240725204737104.png)

![image-20240725205015723](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240725205015723.png)

谁都能用内核源码封装一个操作系统

## 3.远程连接

finalshell ->ssh ->ip地址

wsl

# 二.基础命令

![image-20240725213218690](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240725213218690.png)

## 1.基本命令

### ls

默认打开home

ls -ahl /

### cd

默认进去home目录

注意相对绝对路径

可以使用特殊路径符

![image-20240725214818087](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240725214818087.png)

### pwd（print work directory）

查看当前目录

### mkdir（make directory）

新建目录

mkdir -p 路径 	一次性创建多层目录

注：在home下做命令是可以不考虑权限

![image-20240725215154797](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240725215154797.png)

## 2.文件操作命令

### touch

创建文件



### cat

查看文件内容



### more

查看文件内容，支持翻页比cat更牛逼，可查看内容多的文档

空格翻页



### cp

复制文件

cp -r 路径		复制文件夹

  

### mv

移动文件

文件改名

### rm

删除

![image-20240725221708073](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240725221708073.png)

![image-20240725222233801](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240725222233801.png)

强制删除需要更高的权限，root用户下删除文件会提示询问是否删除，加上-f后直接不弹出

![image-20240725222344378](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240725222344378.png)

## 3.查找命令

### which

查找命令存放的地方

![image-20240725222939991](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240725222939991.png)

### find

两种搜索方式，同时可以使用通配符



![image-20240725224045327](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240725224045327.png)

查找文件![image-20240725224026231](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240725224026231.png)



## 4.

### echo

在命令行输出指定内容

可以用双引号“”包围，如果内容比较复杂，有空格或特殊符号的时候

可以用反引号``包围，被包围的内容会被作为命令执行



任何可以产生结果的东西可以通过重定向符写入到文件中，这里由于echo可以直接将文字打印出来方便理解放在这里

![image-20240725225713313](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240725225713313.png)



### tail

从后往前看文件的东西

当持续追踪后，可以再开一个命令窗，对文件进行修改，在追踪中的窗口中会一直执行追踪，可以看到现象，ctrl+c结束

![image-20240725225924816](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240725225924816.png)

## 5.

### grep

在文件把想要找到的字输出出来

标红的意思是不填内容，搭配管道符使用

![image-20240725230531665](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240725230531665.png)

## wc

文件内容的统计

默认输出 行数 单词数 字节数

![image-20240725230910766](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240725230910766.png)



管道符 |	

![image-20240725231123443](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240725231123443.png)

# 三.vi\vim文本编辑器

直接打开是命令模式，并以其作为中转

![image-20240725231731343](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240725231731343.png)

![image-20240725232925022](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240725232925022.png)

![image-20240725233106406](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240725233106406.png)

![image-20240725233213522](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240725233213522.png)

# 三.用户权限

## 1.root用户（超级管理员）

![image-20240731110720419](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240731110720419.png)

普通用户只在自己的home是是有权限，例如在根目录下无法创建文件夹

![image-20240731111020482](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240731111020482.png)

![image-20240731113525280](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240731113525280.png)

![image-20240731113911326](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240731113911326.png)

## 2.用户、用户组

![image-20240731114614723](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240731114614723.png)

![image-20240731114715542](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240731114715542.png)

![image-20240731115012411](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240731115012411.png)

![image-20240731121213497](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240731121213497.png)

![image-20240731121258867](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240731121258867.png)

## 3.权限信息

![image-20240731121409372](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240731121409372.png)

![image-20240731121445715](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240731121445715.png)

## 4.修改权限控制

### 修改权限信息

![image-20240731121633486](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240731121633486.png)

![image-20240731121830853](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240731121830853.png)

### 修改所属的用户、用户组

![image-20240731122028921](C:\Users\23092\AppData\Roaming\Typora\typora-user-images\image-20240731122028921.png)

# 四.快捷键



# 五.linux文件管理

Linux 系统中的 7 种文件类型，包括：普通文件、目录、字符设备文件、块设备文件、符号链接文件、管道文件以及套接字文件。

## 5.1静态文件与inode

文件没打开前儿是存放在磁盘里如u盘，他以一种固定的形式进行存放，我们叫他静态文件。

硬盘的最小储存单位是扇区（512字节，0.5kb）。

多个扇区组成块，他是文件存取的最小单位，通常是4kb八个扇区。

由于一个个读取扇区效率太低，而是一次读取一个块

硬盘在分区或格式化是会有俩区域，数据区和inode区

后者存放 inode table （inode表），他存放一个个inode节点，每个文件对应一个inode，相当于一个结构体，记录文件不同信息

在windows下快速格式化是只清理inode区



**打开一个文件，系统内部会将这个过程分为三步：**

1) 系统找到这个文件名所对应的 inode 编号；

2) 通过 inode 编号从 inode table 中找到对应的 inode 结构体；

3) 根据 inode 结构体中记录的信息，确定文件数据所在的 block，并读出数据。



文件被打开后，内核会申请一段内存（缓存区），他从静态文件变成了动态文件，我们在对其进行操作是对动态文件操作，在结束操作时内核会自动同步到磁盘中。





## 5.2空洞文件

使用lseek（）可以修改文件读写位置的偏移量，当偏移字节大于文件字节，会形成空洞文件。

这样做是有好处的，比如在下载文件时，还没下完就已经有内存占用，我们可以开启多个线程从不同位置写入，这样可以提高下载速度。



## 5.3



## 5.5

