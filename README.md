# bash_pash_history
给bash添加路径快速切换方法, 跨shell同步路径

## install
```
$ cd ~
$ git clone https://github.com/ymzuiku/bash_pash_history.git
```
> 在 .bash_profile 中添加以下内容

```sh
if [ -f ~/bash_pash_history/.bash_pash_history ];then
  source ~/bash_pash_history/.bash_pash_history
fi
```

## Use

把当前路径添加到快捷路径:

```sh
$ pa pathName
```

cd到之前保存的快捷路径:

```sh
$ pc pathName
```

查看保存的快捷路径:

```sh
$ pl
```

删除某一个快捷路径:

```sh
$ pd 1  (用编号删除)
$ pd pathName (用名字删除)
```

清空快捷路径:

```sh
$ p-clear
```

