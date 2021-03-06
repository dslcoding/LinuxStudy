###//////////////////////////////////////// 02_03////////////////////////////////////////

## 文件系统：
## rootfs：根文件系统

## FHS: Linux
### /boot ：系统启动相关的文件，如内核，initrd，还有grub(bootlader)
### /dev： 设备文件
       设备文件：
             块设备：随机访问 块设备
             字符设备：线性访问，按字符为单位，鼠标和显示器都是字符设备
       设备号：主设备号（major）和次设备好（minor）
### /etc  配置文件，纯文本的文件
### /home 用户的家目录，每一个用户的家目录默认为/home/USERNAME
### /root 没有家目录，不建议以root直接登陆
### /lib  库文件
      /lib/modules： 内核模块文件（静态库(win .la , linux .a)和动态库(win .dll, linux .so共享对象)两种）
### /media 挂载点目录 ，移动设备

### /mnt  额外的临时文件
### /opt  可选目录 第三方的文件目录
### /proc 伪文件系统，内核映射文件
### /sys  伪文件系统，跟硬件设备相关的属性映射文件
### /tmp  临时文件

###//////////////////////////////////////// 02_03////////////////////////////////////////


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


###／／／／／／／／／／／／／03_01／／／／／／／／／／／／／／／／／／


## 发行版：Fedora，RedHat(Centos)，SUSE，Debian(Ubuntu,Mint) , Gentoo,LFS(LInux From Scratch)



## 正则表达
## 管道和重定向>< << >>
## 用户，组，权限
## bash 及其权限

## 目录管理：
ls，cd，pwd，mkdir，rmdir，tree

## 文件管理：
touch，start，file，rm，cp，mv，，nano

## 日期时间：
date，clock，hwclock，call

## 查看文本：
cat。more，tac，less，head，tail，不能打开一个二进制的文件
1.cat=链接并显示
2.cat -n显示行数
3.cat -E 显示结束符
4.终止符号Ctrl+C
5.翻页==shift+pageUp or pageDown
6.分屏显示：more，less
7.more：向前翻，不支持向后翻
8.less：
9.head：查看前n行
11.tail：查看后n行 默认是10；
12.-f 查看文件尾部，不退出，等待显示后续追加至此文件的新东西

## 文本处理
 cut，join，sed，awk，grep

## 关系型数据库：
表：二维表

## 文本文件：
Tom：23：male：2013/05/06

## cut：
1.-d 指定字段分隔符，一个空格
2.-f指定要显示的字段，-f 1显示第一个字段，
3.-f 1，3
4.-f 1 -3


## ///////////03_02///////////////////////////

## 文本排序：sort
1. man sort 查看sort相关的文档
2.-n：数值排序
3.-r：降序
4.-t：字段分隔符
5.-k：以哪个字段为关键字进行排序
6.-u：排序后相同的行只显示一次
7.-f：排序时候不区分大小写

## unip：
1. -c sort.test 显示文件中行重复的次数
2.-d：只显示重复的行

## 文本统计：wc（word count）
1.-l
2.-w
3.-c
4.-L

## 字符处理命令：
1.tr —转换或者删除字符
2.-d： 删除出现在字符集中的所有字符
3.tr ab AB

## bash及其特性
1.shell：外壳
2.GUI：Gnome，KDE，Xfce
2.CLI：sh，bash，csh，ksh，—>bash(开源)，zsh


# 进程：在每个进程看来，当前主机上只存在内核和当前进程
# 进程是程序的副本，进程是程序执行的实例

# 用户工作环境：
1.bash：
2.管理员#
3.普通用户$

shell:  子shell

# bash
1.命令历史
2.管道，重定向
3.命令别名
4.命令行编辑
5.命令行展开
6.文件名通配
7.变量
8.编程
9.命令补全

## 命令行编辑：
光标跳转：
Crtl+a：跳到命令行首
Crtl+e：跳到命令行尾
Crtl+u：删除光标至命令行首的内容
Crtl+k：删除光标至命令行尾的内容
Crtl+l：清屏

## 命令历史：
1.查看命令历史：history
2. -c：清空命令历史
3. -d：OFFSEF 【n】删除指定位置的命令 == history -d 100
4. -w:保存命令历史到历史文件

## 环境变量
PATH： 命令索搜路径
HISTSIZE: 命令存储最大的历史大小（1000条）

## 命令历史的使用技巧
1. !n： 执行命令历史中的第n条命令
2.!-n: 执行命令历史中的倒数第n条命令
3. !!:执行上一条命令
4.!+String：执行命令历史中最近一个执行的命令
5.!$:引用上一个命令的最后一个参数 == Ess . == Alt .

## 命令补全
  ### 搜索PATH环境变量所指定的每个路径下以我们给出的字符串开头的可执行文件，如果多于一个，两次tab，可以给出列表，否则将直接补全。

## 路径不全
   搜索我们给出的起始路径下的每个文件名，并试图补全。
## //////////////////03-03///////////////////////
## 命令别名

 - 1.alias commend = commend [options] - - - [arguments] ==  alias cls=clear
 - 2.注意在shell中定义的别名尽在当前shell的生命周期中有效，别名的有效范围为当前的sehll进程：
 - 3.ualias cls 取消命令别名


## 命令替换
 把命令中某个子命令替换为执行结果的过程

## bash支持的引导
- ``：命令替换
- “”：弱引用，可以实现变量替换
- '':强引用，不完成变量替换


##  文件名通配（globbied）
- *：任意长度的任意字符 a* *a
- ？：任意单个字符
- []： 制定范围内的任意字符
- [abc] [a-m] [a-z][A-Z][0-9][a-zA-z][0-9a-zA-Z]
[][:space(空白字符):]]
[:pause:]:标点符号的集合
[:lower:]:小写字符
[:upper:]:大写字符
[:algha:]:大小写字符
[:digit:]：数字
[:alnum:]:数字和大小写字母
-  man 7 glob (通配符帮助)
- [^]:匹配这个范围职位的任意单个字符


# //////////////////03-04///////////////////////
## 计算机资源
- 权限
- 用户
- 用户，容器，关联权限：用户组，方便地指派权限
- 用户和组都是标识符
- 安全上下文

## 权限 r,w,x
- 文件：
- r:可读，可以使用类似cat等命令查看文件内容
- w:可写，可以编辑或删除此文件
- x：可执行，exacutable，可以以命令提示符下当作命令提交内核运行
- 目录：
- r：可以对此目录执行ls以列出内部的所有文件
- x：可以使用cd切换进此目录，也可以使用ls -l查看内部文件的详细信息(默认权限)
- w：可以在此目录创建文件
- rwx：
- r--：只读
- r-w：读和执行
- ---：010无权限
- --x: 001 执行
- -w-：010写
- -wx：011写和执行
- r--：100只读
- r-x：101读和执行
- rw-：110读写
- rwx：111读写执行
- rwxr-xr-x 755  
- 用户：UID，/etc/passwd
- 组：GID，/etc/group
- 影子口令：
-1.用户 /etc/shadow
-2.组：/etc/shadow
- 用户类别：
- 1.管理员：0
- 2.普通用户：[1-65535] 系统用户[1-499] 一般用户[500 - 60000]
- 用户组：
- 1.管理员组：
- 2.普通组：系统组：一般组：
- 用户组类别：
- 1.私有组：创建用户时，如果没有为其他指定所属的组，系统会自动为其创建要给与用户名同名的组
- 2.基本组：用户的默认组
- 3.附加组：默认组意外的其他组
- account：登录名
- pawward：密码
- uid
- GID：基本组ID
- comment：注释
- HOME DIR：家目录
- SHELL：用户的默认shell
- /etc/shadow account:登录名
- encryted password: 加密的密码

### 加密方法
1. 对称加密：加密和解密使用同一个密码
2. 公钥加密：每个密码都成对出现，一个为私钥（secret key），一个为公钥（public key）
【公钥密钥比私钥长度长，且安全高，速度慢】
3. 单向加密：散列加密，提取数据特征码，用作数据完整性校验 1）雪崩效应 2）定长输出。MD5128位的定长输出，SHA1160位定长输出

### 用户管理
1. useradd,userdel,usermod,passwd,chsh,chfn,fingre,id,chage

### 组管理
1. groupadd,groupdel,groupmod,gpasswd

# ////////////////////04_01///////////////////////////////

## useradd [options] USERNAME
1. -u UID
2. -g GID (基本组)
3. —G GID,...(附加组)
4. -c "COMMENT" 指定注视信息
5. -d /path/to/somedirectory 指定某一个目录
6. /etc/shells: 指定了当前系统可用的安全shell
7. -d shell
8. -m -k  强制给用户添加家目录

## 环境变量
1. PATH
2. HISTSIZE
3. SHELL

## userdel：
1. userdel [options] USERNAME -r:同时删除用户的家目录  userdel -r user2
2. id:查看用户的属性信息
3. -u
4. -g
5. -G
6. -n

## finger:查看用户账号信息
1. finger USERNAME

## 修改用户账号属性 usermod
1. 修改uid -u UID
2. 修改基本组 -g GID
3. -a -G:不使用-a选项，会覆盖此前的目录
4. -d -m：
5. -s
6. 更改用户名 -l
7.-L：锁定账号，不能登陆
8.-U；解锁账号
9. chsh：修改用户的shell
10.chfn：修改用户的注视信息

## 密码管理
1.passwd [USERNAME]
2. --stdin
3.-l
4.-n
5.-d 删除用户密码
6. pwck 检查密码的完整性

## 组管理
1. groupadd 创建组
2. groupadd 1）-g GID 2）-r：添加为系统组
3. groupmod 1）-g GID 制定id 2）-n：GRPNAME 修改用户名
4. groupdel 删除组
5. gpasswd： 给组加密码
6. newgrp GRPNAME <-->exit

# ////////////////////04_02///////////////////////////////
## 权限管理：
1. r:
2. w:
3. x：

### 三类用户
1. 1)属主 2）属组 3)其他用户

### 改变用户属主，只有管理员权限才能改变文件的属主
1. chown username file,....== chown hadoop /tmp/abc
2. -R:修改目录以及内部文件的属性
3. --reference=/path/to/somefile file,...
4. chgrp username file,....== chown hadoop /tmp/abc 1) -R:修改目录以及内部文件的属性 2)--reference=/path/to/somefile file,...
7. chgrp GRPNAME file... 1)-R 2)--reference=/path/to/somefile file....
8. chown USERNAME:GRPNAME file,....

### 修改文件的权限 chmod
1. 修改三类用户的权限 1)chmod MODE file,... 2)-R 3)--reference=/path/to/somefile file,...
2. 修改某类用户或某些类用户权限 1)u,g,o,a chmod 用户类别=mode file,...
3. 修改某类的用户的某位或某些权限 1)u,g,o,a chmod 用户类别+|— mode file,...
