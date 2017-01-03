---
title: 开机显示unknown filesystem错误完美解决
date: 2016/12/27 8:20:45
categories:
- 系统
tags:
- Ubuntu
---

和往常一样，早上起来第一件事情就是打开电脑，但是打开之后没有看到熟悉的开机界面，映入眼帘的是一个黑窗口，上面显示一个错误：
```
error: unknown filesystem.
Entering rescue mode...
grub rescue>
```
当时就有一种不好的预感，但是第一反应是关机重启，重启之后发现还是不行，还有滴滴滴的响声，不甘心，继续重启，如此反复了几次，终于发现今天的问题不是重启能够解决的。
<!-- more -->
于是拿出手机，打开 `Google` 搜索关键字 `unknown filesystem`，一看好多类似的问题，不过大多是英文的，大概看了一下，出问题的主要是安装双系统的，比如 `Windows+Ubuntu` 或者 `Mac + Ubuntu`的，我的就是Windows+Ubuntu双系统，突然想起来昨天动了Ubuntu所在的磁盘。本来我的电脑上有C、D、E、F、G五个磁盘，之前折腾 `Linux` 把G盘分出去50G安装了一个 `Ubuntu 16.04 LTS`，昨天看着磁盘太多很不爽，于是就把G盘剩余的80G和F盘合并了，又因为安装Linux之后，Linux会成为默认开机项，这才引发了重启之后找不到盘符无法开机的问题。

解决方法很简单，只需要三步：
1. 找到 `ubuntu` 所在的分区
```
ls // 查看所有分区
ls (hd0,msdos1) // 如果回车后是 unknown filesystem，继续试下一个分区，直到不是 unknown filesystem，那个分区就是 ubuntu 所在的分区，我的Ubuntu是在(hd0,msdos8)
```
2. 修改启动分区
```
set root=(hd0,6)
set prefix=(hd0,6)/boot/grub
insmod normal
normal
```
3. 修复grub（上一步过后会进入linux系统中）
```
sudo update-grub
sudo grub-install /dev/sda
```

从发现问题到顺利进入系统，十分钟，而且还是不慌不忙的，我好像又成熟了一点呢，哈哈
