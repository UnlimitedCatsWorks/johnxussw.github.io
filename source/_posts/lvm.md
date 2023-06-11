---
title: lvm
date: 2023-06-11 19:22:56
tags:
---

# LVM

公司电脑用的windows系统，拜visual studio等软件所赐，

时不时就要清理C盘空间，还要担心分配给wsl的虚拟内存会不会不够用。

还不快用无敌的DiskGenius想想办法

然后就进入PE，给C盘加了50G的空间。

虽然解决了问题，可是这真的是一个好的解决方法吗？

在Linux系统中，可以使用LVM来处理动态磁盘分区的问题。

而在Windows中，也有类似的解决方案，那就是动态磁盘(Dynamic Disks)。

在win10和server版本中，叫做Storage Spaces

LVM是Logical Volume Manager的缩写，即逻辑卷管理器。

在了解Windows的解决方案之前，先来看看LVM是怎么工作的。

## 基本概念

使用LVM前，必须了解LVM是怎么抽象磁盘空间的

PE(Physical Extent)  
最小的存储单元，通常是4MB

PV(Physical Volume)
实际挂载的物理卷，和物理磁盘一一对应，可以是硬盘，也可以是SSD

VG(Volume Group)
物理卷的集合，可以理解为一个虚拟的磁盘，可以由多个PV组合而成

LV(Logical Volume)
逻辑卷

当我们创建PV时，存储空间会被自动划分成PE

基本上，PV是物理磁盘，VG是PV的集合，LV是VG的集合。

当然，一个VG也可以只有一个PV，一个LV也可以只有一个VG。

逻辑卷(LV)可以像普通磁盘分区一样使用，但是它的大小和位置都是可以动态调整的。


## 那真的泰裤辣，试试看

```bash

# 查看当前物理硬盘
pvs

# 创建物理硬盘
pvcreate /dev/


# 玛德 有空再写

```

