---
title: 25个你不得不知的linux命令
date: 2015/8/12 13:20:46
---

作为一个前端开发人员，其实命令行用的不是很多，况且现在越来越多的工具都有了图形化界面，就连github也打造了一个桌面客户端 [Github Desktop](https://desktop.github.com/)，虽然桌面客户端美观易用，上手难度低，但是作为一个geek，还是要懂一些常见的命令，这样才显得专(zhuang)业(bi)，其实用命令行不仅速度快，而且还能帮助我们理解程序内部运行的原理。再者说了，生命不息，折腾不止，现在是前端，几年之后，说不定在干什么了，后端？全栈？大数据？...谁知道呢，反正我只知道技多不压身，多学点总是好的。

这里说的命令行都是linux系统上面的，mac上也是通用的，但是这些命令在windows上面并不完全适用，windows自带的cmd是很难用的，这里推荐使用 git bash，优点是字体漂亮、文字高亮，缺点是不能兼容所有的linux指令，windows上还有另外一个命令行工具powershell，你可以`Window + R`或者运行，在里面输入`powershell`然后回车，就可以打开了，它支持的指令也比 `cmd` 要多，缺点`git bash`，并不能支持linux上面的所有指令，这是windows用户的痛，所以想体验全部的linux指令的话，屌丝就只能用虚拟机装个linux玩玩，土豪就买台mac吧，你会发现敲代码竟然也会变成一种艺术。

<!-- more -->

### 25个Linux常用命令
---

1. `ls` (windows下为`dir`)
ls命令是列出目录内容(List Directory Contents)的意思。
`ls-l` 以详情模式(long listing fashion)列出文件夹的内容。
`ls-a` 列出所有文件，包括隐藏文件。

2. `cd`
cd命令是切换目录(Change Directory)
cd <path> 切换到指定目录
cd .. 切换到上一级目录
cd / 切换到根目录

3. `pwd`
pwd命令是打印工作目录(Print Working Directory)。
直接在当前目录下输入`pwd`即可。

4. `history`
显示输入的历史记录

5. `mkdir`
Make Directory，在当前目录下新建目录，如果存在，则提示已存在，不能再次创建。

6. `touch`
可以将文件的访问和修改时间更新为当前时间。如果文件不存在，会创建文件，如果文件存在，
则只会更新时间戳，不会改变文件内容。
使用：`touch <filename>`

7. `chmod` 
chmode(change mode)命令，改变文件的模式位，即改变文件的权限，比如读，写，执行等权限。
读，写，执行：`Read(r) = 4` ; `Write(w) = 2` ; `Execute(x) = 1`
给文件只读权限，就设置为'4'，只写权限，就设置为'2'，只执行权限，设置为'1'，读写权限就是4 + 2 = 6，以此类推。
下面设置3种用户和用户组权限，第一个是拥有者，然后是用户所在的组，最后是其它用户。
命令使用方法：`chmod 777 abc.sh`

8. `tar` 
tar命令是磁盘归档。对创建一些文档的归档和它们的解压很有用。

9. `date`
时间，日期

10. `cat`
"cat"代表了联结，连接两个或更多文本文件或者以标准输出形式打印文件的内容。

11. `cp`
cp，即"copy"，把一个文件移动到一个目录里面。
`cp a.txt /Users/vince/Downloads`

12. `mv`
mv，即"move"，移动文件到一个目录里面。
`mv a.txt <path>`

13. `rm` - Remove
 删除给定的文件或文件夹

14. `rmdir` - Remove Directory
rmdir 删除指定的目录

15. `tail` - print TAIL
tail，默认显示指定文件的最后10行，还可用`tail - n`来指定显示的行数（从末尾算起）。

16. `help`
help会在终端列出所有可用的命令。

17. `whatis` - What is this command
whatis 用来查询指定命令的含义。

18. `exit`
用于结束当前的终端通话

19. `ping`
ping 命令通过发送数据包ping远程主机来检测网络连接和服务器状态。

20. `shutdown` 
shutdown 用于关闭计算机，而`shutdown -r` 用于重启计算机。

21. `who` - Who is Logged in
who 命令是列出当前登陆的用户名。

22. `su` - Switch User
su用于切换不同的用户。

23. `uname`
用于显示系统的重要信息，使用`uname -a`可以用来查看所有信息。

24. `free` - Free memory
free用来查看系统的空闲内存、已占用内存、可利用的交换内存等信息，`free -m`可以将单位转换为KB，而`free -g`则转换为GB。

25. `df` - Disk space Free
`df` 命令用来查看硬盘的使用情况。`df -h`可以将结果的单位转换为 `GB`。
