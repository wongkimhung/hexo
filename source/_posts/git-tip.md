---
title: git-tip
date: 2016-04-11 17:30:28
tags: git
---

> 如果我们往一个非空的目录下 clone git 项目，就会提示错误信息

> fatal: destination path '.' already exists and is not an empty directory.

解决方案：


```
#进入到要操作的非空目录
cd /workdir/proj1

# checkout git 信息
git clone --no-checkout git@github.com:wongkimhung/blog.git tmp  

#将 tmp 目录下的 .git 目录移到当前目录
mv tmp/.git .


#删除临时文件夹
rmdir tmp

#设置版本为HEAD
git reset --hard HEAD
```

#### 然后就可以进行各种正常操作了。

> filename too long

```
git config core.longpaths true
```
