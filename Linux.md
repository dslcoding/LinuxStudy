命名规则：
1.长度不能超过255个字符
2.不能使用／当文件名
3.严格区分大小写

相对路径
绝对路径

文件管理
目录管理
ls
cd
pwd

mkdir：创建目录
-p：
／root／x／y
mkdir -p ／root／x/y
查看创建过程
mkdir -pv ／root／x／y

创建x。y

mkdir -pv /mnt/text/x/m /mnt/text/y
mkdir -pv ／mnt／text/{x/m,y}

创建 
/mnt/text3/
a_b,a_c,a_d,a_c
(a+d)(a+c) = ab+ac+ab+dc

tree：查看目录树
 
删除目录：rmdir （remove directory）
删除空目录

文件的创建和删除
# touch
    -a
   -m
  -t
-c
# stat
 创建文件，可以使用文件编辑器
ASCII：美国标准信息交换码
128字符：
    二进制

删除文件 ：rm
-i
-f
-r 删除目录
rm -rf ／删除所有目录

/////////////////////////////////////////////////////////////////////////////
02_04
复制和移动文件
cp: copy
cp SRC DEST
  复制一个文件到一个文件
  多个文件到一个目录
  -r
  -f 强行复制
cp /etc/{passed.inittab.rc.d/rc.sysinit}  /tmp/

mv:move
移动文件

mv SRC DEST
mv -t DEST SRC 先指定目标

install 
-d  DIRECOTRY。。创建目录


／／／／／／／／／／／／／／／／／／／／／／／／／／／／／／／／／／
03_01

发行版：Fedora，RedHat(Centos)，SUSE，Debian(Ubuntu,Mint) , Gentoo,LFS(LInux From Scratch)



正则表达
管道和重定向>< << >>
用户，组，权限
bash 及其权限

目录管理：
ls，cd，pwd，mkdir，rmdir，tree

文件管理：
touch，start，file，rm，cp，mv，，nano

日期时间：
date，clock，hwclock，call

查看文本：
cat。more，tac，less，head，tail，不能打开一个二进制的文件

cat=链接并显示
 cat -n显示行数
 cat -E 显示结束符
终止符号Ctrl+C
翻页==shift+pageUp or pageDown
分屏显示：more，less
 more：向前翻，不支持向后翻
 less：
head：查看前n行
tail：查看后n行 默认是10；
  -f 查看文件尾部，不退出，等待显示后续追加至此文件的新东西

文本处理
 cut，join，sed，awk，grep，
关系型数据库：
表：二维表
文本文件：
Tom：23：male：2013/05/06
cut：
  -d 指定字段分隔符，一个空格
  -f指定要显示的字段，-f 1显示第一个字段，
  -f 1，3
  -f 1 -3

／／／／／／／／／／／／／03_02／／／／／／／／／／／／／／／／／／

文本排序：sort
 man sort 查看sort相关的文档
 -n：数值排序
-r：降序
-t：字段分隔符
- k：以哪个字段为关键字进行排序
-u：排序后相同的行只显示一次
-f：排序时候不区分大小写
unip：
uniq -c sort.test 显示文件中行重复的次数
-d：只显示重复的行
 文本统计：wc（word count）
   -l
 -w
-c
-L

字符处理命令：tr —转换或者删除字符
- d： 删除出现在字符集中的所有字符
tr ab AB

bash及其特性
shell：外壳
GUI：Gnome，KDE，Xfce
CLI：sh，bash，csh，ksh，—>bash(开源)，zsh


进程：在每个进程看来，当前主机上只存在内核和当前进程
进程是程序的副本，进程是程序执行的实例 

用户工作环境：
bash：
管理员#
普通用户$

shell:  子shell

bash
1.命令历史
2.管道，重定向
3.命令别名
4.命令行编辑
5.命令行展开
6.文件名通配
7.变量
8.编程

命令行编辑：
光标跳转：
Crtl+a：跳到命令行首
Crtl+e：跳到命令行尾
Crtl+u：删除光标至命令行首的内容
Crtl+k：删除光标至命令行尾的内容
Crtl+l：清屏

命令历史：


  



