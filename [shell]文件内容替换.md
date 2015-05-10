```
sed -i 's#^PROXY_ENABLED="no"#PROXY_ENABLED="yes"#' proxy
sed -i 's#^PROXY_ENABLED=".*"#PROXY_ENABLED="yes"#' proxy
```
1 `set -e`表示一旦脚本中有命令的返回值为非0，则脚本立即退出，后续命令不再执行

2 `cat <<EOF`        
EOF只是一个分界符，其实你完全可以用abcde替换，也一样的功能，只是大家都习惯用EOF来表示。                      
当shell看到<<的时候，它就会知道下一个词是一个分界符。             
结合这两个标识，即可避免使用多行echo命令的方式，并`实现多行输出`的结果。             
`cat <<- EOF 和 cat << EOF`         
>intentionally mixed spaces and tabs here -- tabs are stripped by "<<-EOF", spaces are kept in the output                    

`cat <<-EOF`                              
**需要输出的内容...**                            
EOF               

3 `文件描述符`注意这么一个概念，默认的数字中，               
**0** 表示标准输入(键盘)，**1** 表示标准输出(终端屏幕)，**2** 为标准错误输出(终端屏幕)                

shell 编程中使用到得if语句内判断参数

　　–b 当file存在并且是块文件时返回真

　　-c 当file存在并且是字符文件时返回真

　　-d 当pathname存在并且是一个目录时返回真

　　-e 当pathname指定的文件或目录存在时返回真

　　-f 当file存在并且是正规文件时返回真

　　-g 当由pathname指定的文件或目录存在并且设置了SGID位时返回为真

　　-h 当file存在并且是符号链接文件时返回真，该选项在一些老系统上无效

　　-k 当由pathname指定的文件或目录存在并且设置了“粘滞”位时返回真

　　-p 当file存在并且是命令管道时返回为真

　　-r 当由pathname指定的文件或目录存在并且可读时返回为真

　　-s 当file存在文件大小大于0时返回真

　　-u 当由pathname指定的文件或目录存在并且设置了SUID位时返回真

　　-w 当由pathname指定的文件或目录存在并且可执行时返回真。一个目录为了它的内容被访问必然是可执行的。

　　-o 当由pathname指定的文件或目录存在并且被子当前进程的有效用户ID所指定的用户拥有时返回真。
