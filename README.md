# 解决的问题

我们平时使用终端时，经常需要在不同的路径来回跳转，如何更便捷的添加、使用、移除快捷路径，并且在多个shell直接共享快捷路径，就是这个小项目需要解决的问题。

## Install
```sh
$ cd ~
$ git clone https://github.com/ymzuiku/bash_pash_history.git
```
在 .bash_profile 中添加以下内容, 引入文件

```sh
if [ -f ~/bash_pash_history/.bash_pash_history ];then
  source ~/bash_pash_history/.bash_pash_history
fi
```

重新加载.bash_profile

```sh
$ source ~/.bash_profile
```

## Use

把当前路径添加到快捷路径:

```sh
$ pa pathName
```

cd到之前保存的快捷路径:

```sh
$ pc 0  (用编号跳转)
$ pc pathName (用名字跳转)
```

查看保存的快捷路径:

```sh
$ pl
```

删除某一个快捷路径:

```sh
$ pd 0  (用编号删除)
$ pd pathName (用名字删除)
```

清空快捷路径:

```sh
$ p-clear
```

#### 整个项目很简单，只有130行shell代码，有兴趣的可以查看源码：
[.bash_pash_history文件](https://github.com/ymzuiku/bash_pash_history/blob/master/.bash_pash_history)

如果你喜欢, 请给一个Star :)