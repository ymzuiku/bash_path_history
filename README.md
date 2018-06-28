# bash_pash_history
给bash添加路径快速切换方法

## install
```
$ cd ~
$ curl https://github.com/ymzuiku/bash_pash_history/README.md -o .bash_pash_history --progress
```
> 在 .bash_profile 中添加以下内容

```sh
p_values=()
p_keys=()
function p(){
  if [ $1 == "-a" -o $1 == "--add" ];then
  _pa $2
  elif [ $# == 0 ];then
  _pl
  elif [ $1 == "-l" -o $1 == "--log" ];then
  _pl
  elif [ $1 == "-c" -o $1 == "--clear" ];then
  _pc
  else
    len=${#p_keys[@]}
    for((i=0;i<$len;i++));do
      key=${p_keys[$i]}
      value=${p_values[$i]}
      if [ $1 == $key ]; then
        cd $value
      fi
      # echo [$i] $key $value
    done
  fi
}
function _pa(){
  len=${#p_keys[@]}
  p_keys[$len]=$1
  p_values[$len]=`pwd`
  echo "[$len][p] add ${p_keys[$len]} ${p_values[$len]}"
}
function _pc(){
  p_values=()
  p_keys=()
  echo "[p] did empty"
}
function _pl(){
  len=${#p_keys[@]}
  if [ $len == 0 ];then
    echo "[p] is empty"
  fi
  for((i=0;i<$len;i++));do
    key=${p_keys[$i]}
    value=${p_values[$i]}
    echo [$i] $key $value
  done
}
```

## Use

把当前路径添加到快捷路径:

```sh
$ p -a pathName
```

cd到之前保存的快捷路径:

```sh
$ p pathName
```

查看保存的快捷路径:

```sh
$ p -l
```

清空快捷路径:

```sh
$ p -c
```

