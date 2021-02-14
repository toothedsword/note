# Note
  [test](test1);
# install perl
    note: 5.28 can not be installed successfully. So 5.26 are installed.

  cmd to install perl
     wget https://www.cpan.org/src/5.0/perl-5.28.1.tar.gz
     tar -xzf perl-5.28.1.tar.gz
     cd perl-5.28.1
     # ./Configure -des -Dprefix=$HOME/localperl
     should use:
     ./Configure -de # that means for all the users
     make
     make test
     make install

    #=> PDL
    cpgplot.h
    http://www.astro.caltech.edu/~tjp/pgplot/
    https://pkgs.org/download/pgplot
    https://fedora.pkgs.org/30/rpmfusion-nonfree-x86_64/pgplot-5.2.2-45.fc30.x86_64.rpm.html
    pgplot-5.2.2-45.fc30.x86_64.rpm
    perl-PGPLOT-2.21-12.fc30.x86_64.rpm
    pgplot-devel-5.2.2-45.fc30.x86_64.rpm
    #=> check installed perl pm
    find `perl -e 'print "@INC"'` -name 'WMO.pm' -print
    
# PDL algorithm
    (;-) remove 1 dims
    (;_) flatten
    
# gdb
gfortran -g test.f90


# Network

内外网同时连:
sudo route add -net 10.24.237.0 netmask 255.255.255.0 gw 10.24.45.1 dev enp0s31f
另外需要，有一台电脑安装inode，必须在线，其他电脑才能直接连接内网[](viewnior /home/leon/doc/note/fig/2021-02-0710-51-41.png)

反向隧道:
在笔记本建立本机到ADS的隧道：
ssh -f -N -R 11111:localhost:22 -p 122 leon@1.119.5.181
用autossh更加稳定
autossh -M 5678 -N -R 11111:localhost:22 -p 122 leon@1.119.5.181 
在ADS服务器上：
ssh localhost -p 11111
in /etc/ssh/sshd_config set: GatewayPorts yes

ads@leon-hp:~$ ps -ef | grep autossh
ads       200293  195477  0 17:22 pts/3    00:00:00 /usr/lib/autossh/autossh -M 5678 -N -R 11117:localhost:22 -p 22 10.1.100.92
ads       227219    4767  0 17:30 pts/2    00:00:00 /usr/lib/autossh/autossh -M 5680 -N -R 11118:localhost:22 -p 122 1.119.5.181
ads       245091  244443  0 17:35 pts/1    00:00:00 grep --color=auto autossh
ads@leon-hp:~$ ps -ef | grep autossh | grep -v grep
ads       200293  195477  0 17:22 pts/3    00:00:00 /usr/lib/autossh/autossh -M 5678 -N -R 11117:localhost:22 -p 22 10.1.100.92
ads       227219    4767  0 17:30 pts/2    00:00:00 /usr/lib/autossh/autossh -M 5680 -N -R 11118:localhost:22 -p 122 1.119.5.181

# linux command
head -9 test.txt | tail -n +4
BT download: 
rtorrent [url]

# format u pan
mkfs.fat /dev/sdc

# generate the centos system u pan
fdisk -l
umount /dev/sdb
mkfs.fat /dev/sdb -I
dd if=ubuntu-16.0.3-desktop-amd64.iso of=/dev/sdb

# ubuntu
从现有系统下载所有依赖的包
apt-get的deb包在 
/var/cache/apt/archives
apt-get -o dir::cache::archives="/root/" -d install git
安装本地deb包[](https://blog.csdn.net/zhaoyang22/article/details/4235596#:~:text=1.%E5%A6%82%E4%BD%95%E5%AE%89%E8%A3%85deb%E6%96%87%E4%BB%B6,f%20install%E6%8C%89%E5%9B%9E%E8%BD%A6%E3%80%82) dpkg[](viewnior /home/leon/doc/note/fig/2021-02-0711-56-39.png)

# hp wifi adapter
https://github.com/M000M/Driver-Realtek-RTL8821CE

# connect wifi by command line
https://yq.aliyun.com/articles/704878

# toolbox 
export $(dbus-launch)
export NSS_USE_SHARED_DB=ENABLED

# cd record
    mkisofs -r -o file.iso your_folder_name/
    cdrecord -scanbus
    cdrecord -v -dev=1000,0,0 /home/YourImage.iso
    
# install vim
./configure --with-features=huge --enable-multibyte  --enable-python3interp=yes --with-python3-config-dir=/usr/local/python3/lib/python3.5/config-3.5m --prefix=/usr/local/vim81
https://blog.csdn.net/Kardiyal/article/details/85383231

./configure --enable-pythoninterp=yes --with-python-config-dir=/lib64/python2.7/config/ --with-features=huge --enable-multibyte

# booking
订票人：Lu,Tingting（卢婷婷）
护照号：EB3433541
护照签发日：2017年10月31日
护照到期日：2027年10月30日
签证时间：2019年11月18日~2029年11月12日
身份证：610425199202222220

订票人：Peng, Liang (彭亮)
护照号：G46398905
护照签发日：2010年11月25日
护照到期日：2020年11月24日
签证时间：2019年11月8日~2029年11月5日
身份证：420525198111211417


乘机人：田福厚
身份证：150123197102048510
订票日期：2019年11月5日
建议航班：国航CA1340
 16:45广州白云机场--20:00首都机场
 项目编号：SQ2019DQS-06


乘机人：彭亮
身份证：420525198111211417
订票日期：2019年12月4日
建议航班：海南航空HU7807
14:05首都国际机场T1 -- 17:15白云国际机场T1
项目编号：部门日常  --  广东气象学术会议

乘机人：彭亮
身份证：420525198111211417
订票日期：2019年12月6日
建议航班：南方航空CZ3115
08:30 白云国际机场T2 -- 11:35 大兴国际机场
项目编号：部门日常  --  广东气象学术会议

# python
#=> pip
-i
[清华大学](https://pypi.tuna.tsinghua.edu.cn/simple/), [阿里云](https://mirrors.aliyun.com/pypi/simple/), 
[豆瓣(douban)](http://pypi.douban.com/simple/), [中国科学技术大学](http://pypi.mirrors.ustc.edu.cn/simple/)

#=> plot
[自定义colorbar的颜色](https://www.jianshu.com/p/758b2c3f79cc)


# python

Python读写、创建文件[原文链接](http://www.cnblogs.com/juandx/p/4962089.html)
python中对文件、文件夹（文件操作函数）的操作需要涉及到os模块和shutil模块。

得到当前工作目录，即当前Python脚本工作的目录路径: os.getcwd()

返回指定目录下的所有文件和目录名:os.listdir()

函数用来删除一个文件:os.remove()

删除多个目录：os.removedirs（r“c：\python”）

检验给出的路径是否是一个文件：os.path.isfile()

检验给出的路径是否是一个目录：os.path.isdir()

判断是否是绝对路径：os.path.isabs()

检验给出的路径是否真地存:os.path.exists()

返回一个路径的目录名和文件名:os.path.split()
eg os.path.split(‘/home/swaroop/byte/code/poem.txt’)
结果：(‘/home/swaroop/byte/code’, ‘poem.txt’)

分离扩展名：os.path.splitext()

获取路径名：os.path.dirname()

获取文件名：os.path.basename()

运行shell命令: os.system()

读取和设置环境变量:os.getenv() 与os.putenv()

给出当前平台使用的行终止符:os.linesep Windows使用’\r\n’，Linux使用’\n’而Mac使用’\r’

指示你正在使用的平台：os.name 对于Windows，它是’nt’，而对于Linux/Unix用户，它是’posix’

重命名：os.rename（old， new）

创建多级目录：os.makedirs（r“c：\python\test”）

创建单个目录：os.mkdir（“test”）

获取文件属性：os.stat（file）

修改文件权限与时间戳：os.chmod（file）

终止当前进程：os.exit（）

获取文件大小：os.path.getsize（filename）

文件操作：
os.mknod(“test.txt”) 创建空文件
fp = open(“test.txt”,w) 直接打开一个文件，如果文件不存在则创建文件

关于open 模式：

w 以写方式打开，
a 以追加模式打开 (从 EOF 开始, 必要时创建新文件)
r+ 以读写模式打开
w+ 以读写模式打开 (参见 w )
a+ 以读写模式打开 (参见 a )
rb 以二进制读模式打开
wb 以二进制写模式打开 (参见 w )
ab 以二进制追加模式打开 (参见 a )
rb+ 以二进制读写模式打开 (参见 r+ )
wb+ 以二进制读写模式打开 (参见 w+ )
ab+ 以二进制读写模式打开 (参见 a+ )

fp.read([size]) #size为读取的长度，以byte为单位

fp.readline([size]) #读一行，如果定义了size，有可能返回的只是一行的一部分

fp.readlines([size]) #把文件每一行作为一个list的一个成员，并返回这个list。其实它的内部是通过循环调用readline()来实现的。如果提供size参数，size是表示读取内容的总长，也就是说可能只读到文件的一部分。

fp.write(str) #把str写到文件中，write()并不会在str后加上一个换行符

fp.writelines(seq) #把seq的内容全部写到文件中(多行一次性写入)。这个函数也只是忠实地写入，不会在每行后面加上任何东西。

fp.close() #关闭文件。python会在一个文件不用后自动关闭文件，不过这一功能没有保证，最好还是养成自己关闭的习惯。 如果一个文件在关闭后还对其进行操作会产生ValueError

fp.flush() #把缓冲区的内容写入硬盘

fp.fileno() #返回一个长整型的”文件标签“

fp.isatty() #文件是否是一个终端设备文件（unix系统中的）

fp.tell() #返回文件操作标记的当前位置，以文件的开头为原点

fp.next() #返回下一行，并将文件操作标记位移到下一行。把一个file用于for … in file这样的语句时，就是调用next()函数来实现遍历的。

fp.seek(offset[,whence]) #将文件打操作标记移到offset的位置。这个offset一般是相对于文件的开头来计算的，一般为正数。但如果提供了whence参数就不一定了，whence可以为0表示从头开始计算，1表示以当前位置为原点计算。2表示以文件末尾为原点进行计算。需要注意，如果文件以a或a+的模式打开，每次进行写操作时，文件操作标记会自动返回到文件末尾。

fp.truncate([size]) #把文件裁成规定的大小，默认的是裁到当前文件操作标记的位置。如果size比文件的大小还要大，依据系统的不同可能是不改变文件，也可能是用0把文件补到相应的大小，也可能是以一些随机的内容加上去。

目录操作：
os.mkdir(“file”) 创建目录
复制文件：
shutil.copyfile(“oldfile”,”newfile”) oldfile和newfile都只能是文件
shutil.copy(“oldfile”,”newfile”) oldfile只能是文件夹，newfile可以是文件，也可以是目标目录
复制文件夹：
shutil.copytree(“olddir”,”newdir”) olddir和newdir都只能是目录，且newdir必须不存在
重命名文件（目录）
os.rename(“oldname”,”newname”) 文件或目录都是使用这条命令
移动文件（目录）
shutil.move(“oldpos”,”newpos”)
删除文件
os.remove(“file”)
删除目录
os.rmdir(“dir”)只能删除空目录
shutil.rmtree(“dir”) 空目录、有内容的目录都可以删
转换目录
os.chdir(“path”) 换路径

Python读写文件
1.open
使用open打开文件后一定要记得调用文件对象的close()方法。比如可以用try/finally语句来确保最后能关闭文件。

file_object = open(‘thefile.txt’)
try:
all_the_text = file_object.read( )
finally:
file_object.close( )

注：不能把open语句放在try块里，因为当打开文件出现异常时，文件对象file_object无法执行close()方法。

2.读文件
读文本文件

input = open('data', 'r')
#第二个参数默认为r
input = open('data')

    1
    2
    3

读二进制文件

input = open('data', 'rb')

    1

读取所有内容

file_object = open('thefile.txt')
try:
     all_the_text = file_object.read( )
finally:
     file_object.close( )

    1
    2
    3
    4
    5

读固定字节

file_object = open('abinfile', 'rb')
try:
    while True:
         chunk = file_object.read(100)
        if not chunk:
            break
         do_something_with(chunk)
finally:
     file_object.close( )

    1
    2
    3
    4
    5
    6
    7
    8
    9

读每行

list_of_all_the_lines = file_object.readlines( )

    1

如果文件是文本文件，还可以直接遍历文件对象获取每行：

for line in file_object:
     process line

    1
    2

3.写文件
写文本文件

output = open('data', 'w')

    1

写二进制文件

output = open('data', 'wb')

    1

追加写文件

output = open('data', 'w+')

    1

写数据

file_object = open('thefile.txt', 'w')
file_object.write(all_the_text)
file_object.close( )

    1
    2
    3

写入多行

file_object.writelines(list_of_text_strings)

    1

注意，调用writelines写入多行在性能上会比使用write一次性写入要高。

在处理日志文件的时候，常常会遇到这样的情况：日志文件巨大，不可能一次性把整个文件读入到内存中进行处理，例如需要在一台物理内存为 2GB 的机器上处理一个 2GB 的日志文件，我们可能希望每次只处理其中 200MB 的内容。
在 Python 中，内置的 File 对象直接提供了一个 readlines(sizehint) 函数来完成这样的事情。以下面的代码为例：

file = open('test.log', 'r')sizehint = 209715200   # 200Mposition = 0lines = file.readlines(sizehint)while not file.tell() - position < 0:       position = file.tell()       lines = file.readlines(sizehint)

    1

每次调用 readlines(sizehint) 函数，会返回大约 200MB 的数据，而且所返回的必然都是完整的行数据，大多数情况下，返回的数据的字节数会稍微比 sizehint 指定的值大一点（除最后一次调用 readlines(sizehint) 函数的时候）。通常情况下，Python 会自动将用户指定的 sizehint 的值调整成内部缓存大小的整数倍。

file在python是一个特殊的类型，它用于在python程序中对外部的文件进行操作。在python中一切都是对象，file也不例外，file有file的方法和属性。下面先来看如何创建一个file对象：

file(name[, mode[, buffering]])

    1

file()函数用于创建一个file对象，它有一个别名叫open()，可能更形象一些，它们是内置函数。来看看它的参数。它参数都是以字符串的形式传递的。name是文件的名字。
mode是打开的模式，可选的值为r w a U，分别代表读（默认） 写 添加支持各种换行符的模式。用w或a模式打开文件的话，如果文件不存在，那么就自动创建。此外，用w模式打开一个已经存在的文件时，原有文件的内容会被清空，因为一开始文件的操作的标记是在文件的开头的，这时候进行写操作，无疑会把原有的内容给抹掉。由于历史的原因，换行符在不同的系统中有不同模式，比如在 unix中是一个\n，而在windows中是‘\r\n’，用U模式打开文件，就是支持所有的换行模式，也就说‘\r’ ‘\n’ ‘\r\n’都可表示换行，会有一个tuple用来存贮这个文件中用到过的换行符。不过，虽说换行有多种模式，读到python中统一用\n代替。在模式字符的后面，还可以加上+ b t这两种标识，分别表示可以对文件同时进行读写操作和用二进制模式、文本模式（默认）打开文件。
buffering如果为0表示不进行缓冲;如果为1表示进行“行缓冲“;如果是一个大于1的数表示缓冲区的大小，应该是以字节为单位的。

file对象有自己的属性和方法。先来看看file的属性。

closed #标记文件是否已经关闭，由close()改写
encoding #文件编码
mode #打开模式
name #文件名
newlines #文件中用到的换行模式，是一个tuple
softspace #boolean型，一般为0，据说用于print

    1
    2
    3
    4
    5
    6

file的读写方法：

F.read([size]) #size为读取的长度，以byte为单位
F.readline([size])
#读一行，如果定义了size，有可能返回的只是一行的一部分
F.readlines([size])
#把文件每一行作为一个list的一个成员，并返回这个list。其实它的内部是通过循环调用readline()来实现的。如果提供size参数，size是表示读取内容的总长，也就是说可能只读到文件的一部分。
F.write(str)
#把str写到文件中，write()并不会在str后加上一个换行符
F.writelines(seq)
#把seq的内容全部写到文件中。这个函数也只是忠实地写入，不会在每行后面加上任何东西。
file的其他方法：


F.close()
#关闭文件。python会在一个文件不用后自动关闭文件，不过这一功能没有保证，最好还是养成自己关闭的习惯。如果一个文件在关闭后还对其进行操作会产生ValueError
F.flush()
#把缓冲区的内容写入硬盘
F.fileno()
#返回一个长整型的”文件标签“
F.isatty()
#文件是否是一个终端设备文件（unix系统中的）
F.tell()
#返回文件操作标记的当前位置，以文件的开头为原点
F.next()
#返回下一行，并将文件操作标记位移到下一行。把一个file用于for ... in file这样的语句时，就是调用next()函数来实现遍历的。
F.seek(offset[,whence])
#将文件打操作标记移到offset的位置。这个offset一般是相对于文件的开头来计算的，一般为正数。但如果提供了whence参数就不一定了，whence可以为0表示从头开始计算，1表示以当前位置为原点计算。2表示以文件末尾为原点进行计算。需要注意，如果文件以a或a+的模式打开，每次进行写操作时，文件操作标记会自动返回到文件末尾。
F.truncate([size])
#把文件裁成规定的大小，默认的是裁到当前文件操作标记的位置。如果size比文件的大小还要大，依据系统的不同可能是不改变文件，也可能是用0把文件补到相应的大小，也可能是以一些随机的内容加上去。

http://www.cnblogs.com/allenblogs/archive/2010/09/13/1824842.html

#}}}

# vim folded
vim折叠设置（转载）
set foldmethod=indent "set default foldmethod
"zi 打开关闭折叠
"zv 查看此行
zm 关闭折叠
zM 关闭所有
zr 打开
zR 打开所有
zc 折叠当前行
zo 打开当前折叠
zd 删除折叠
zD 删除所有折叠


1. 折叠方式
可用选项 'foldmethod' 来设定折叠方式：set fdm=*****。
有 6 种方法来选定折叠：
manual           手工定义折叠
indent             更多的缩进表示更高级别的折叠
expr                用表达式来定义折叠
syntax             用语法高亮来定义折叠
diff                  对没有更改的文本进行折叠
marker            对文中的标志折叠
注意，每一种折叠方式不兼容，如不能即用expr又用marker方式，我主要轮流使用indent和marker方式进行折叠。

使用时，用：set fdm=marker 命令来设置成marker折叠方式（fdm是foldmethod的缩写）。
要使每次打开vim时折叠都生效，则在.vimrc文件中添加设置，如添加：set fdm=syntax，就像添加其它的初始化设置一样。

2. 折叠命令
选取了折叠方式后，我们就可以对某些代码实施我们需要的折叠了，由于我使用indent和marker稍微多一些，故以它们的使用为例：
如果使用了indent方式，vim会自动的对大括号的中间部分进行折叠，我们可以直接使用这些现成的折叠成果。
在可折叠处（大括号中间）：
zc      折叠
zC     对所在范围内所有嵌套的折叠点进行折叠
zo      展开折叠
zO     对所在范围内所有嵌套的折叠点展开
[z       到当前打开的折叠的开始处。
]z       到当前打开的折叠的末尾处。
zj       向下移动。到达下一个折叠的开始处。关闭的折叠也被计入。
zk      向上移动到前一折叠的结束处。关闭的折叠也被计入。

当使用marker方式时，需要用标计来标识代码的折叠，系统默认是{{{和}}}，最好不要改动之：）
我们可以使用下面的命令来创建和删除折叠：
zf      创建折叠，比如在marker方式下：
zf56G，创建从当前行起到56行的代码折叠；
10zf或10zf+或zf10↓，创建从当前行起到后10行的代码折叠。
10zf-或zf10↑，创建从当前行起到之前10行的代码折叠。
在括号处zf%，创建从当前行起到对应的匹配的括号上去（（），{}，[]，<>等）。
zd      删除 (delete) 在光标下的折叠。仅当 'foldmethod' 设为 "manual" 或 "marker" 时有效。
zD     循环删除 (Delete) 光标下的折叠，即嵌套删除折叠。
仅当 'foldmethod' 设为 "manual" 或 "marker" 时有效。
zE     除去 (Eliminate) 窗口里“所有”的折叠。
仅当 'foldmethod' 设为 "manual" 或 "marker" 时有效。

关于vim的代码折叠，小弟也是初学，仅做参考。


使用Vim的折叠功能书写程序代码

折行的用处：
2 创建折行进行大纲预览
2 移动到某处进行编辑
2 使用jzij打开文本进行编辑
2 编辑完毕后再用jzij打开折行进行移动

打开vim的折叠功能，请在~/.vimrc 中加入:set foldmethod=marker ，使用vim默认的折叠标签进行处理。使用方法如下：
1、加折叠标签
在normal模式下，从键盘输入zf并回车，您就会看到折叠在一起的两行标签如下：
/*{{{*/
.....这里输入您 的程序代码
/*}}}*/
2、输入程序代码后，将代码折叠起来使用如下命令(normal模式)：
zc 回车
3、打开折叠的程序有以下几种方法
a、在折叠的行上移动光标
b、在normal模式下输入zo并回车
4、给一段文字加折行（normal 模式）
zfap
5、zr命令可以打开折叠几层的内容 zm使用内容折叠的更多一些（多层折叠操作时可反复使用）。
6、嵌套了多层的折行, 也可以用zR命令一次打开所有折行
7、关闭所有的嵌套折行使用zM
8、可以用jznj命令来禁用一个折行. 然后用jzNj还可以恢复它. jzij命令则可以在两者之间切换.
" 其它的，请参考vim的使用手册。


# VimDebug requires +perl and +signs

vim --version


# Linux添加环境变量与GCC编译器添加INCLUDE与LIB环境变量
对所有用户有效在/etc/profile增加以下内容。只对当前用户有效在Home目录下的
.bashrc或.bash_profile里增加下面的内容：
(注意：等号前面不要加空格,否则可能出现 command not found)

#在PATH中找到可执行文件程序的路径。
export PATH =$PATH:$HOME/bin

#gcc找到头文件的路径
C_INCLUDE_PATH=/usr/include/libxml2:/MyLib
export C_INCLUDE_PATH

#g++找到头文件的路径
CPLUS_INCLUDE_PATH=$CPLUS_INCLUDE_PATH:/usr/include/libxml2:/MyLib
export CPLUS_INCLUDE_PATH

#找到动态链接库的路径
LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/MyLib
export LD_LIBRARY_PATH

#找到静态库的路径
LIBRARY_PATH=$LIBRARY_PATH:/MyLib
export LIBRARY_PATH

库 文件在连接（静态库和共享 库）和运行（仅限于使用共享库的程序）时被使用，其搜索路径是在系统中进行设置的。一般 Linux 系统把 /lib 和 /usr/lib 两个目录作为默认的库搜索路径，所以使用这两个目录中的库时不需要进行设置搜索路径即可直接使用。对于处于默认库搜索路径之外的库，需要将库的位置添加到 库的搜索路径之中。设置库文件的搜索路径有下列两种方式，可任选其一使用：

在环境变量 LD_LIBRARY_PATH 中指明库的搜索路径。

在 /etc/ld.so.conf 文件中添加库的搜索路径。

将自己可能存放库文件的路径都加入到/etc/ld.so.conf中是明智的选择

添加方法也极其简单，将库文件的绝对路径直接写进去就OK了，一行一个。例如：

/usr/X11R6/lib

/usr/local/lib

/opt/lib

需 要注意的是：第二种搜索路径的设置方式对于程序连接时的库（包括共享库和静态库） 的定位已经足够了，但是对于使用了共享库的程序的执行还是不够的。这是因为为了加快程序执行时对共享库的定位速度，避免使用搜索路径查找共享库的低效率， 所以是直接读取库列表文件 /etc/ld.so.cache 从中进行搜索的。/etc/ld.so.cache 是一个非文本的数据文件，不能直接编辑，它是根据 /etc/ld.so.conf 中设置的搜索路径由 /sbin/ldconfig 命令将这些搜索路径下的共享库文件集中在一起而生成的（ldconfig 命令要以 root 权限执行）。因此，为了保证程序执行时对库的定位，在 /etc/ld.so.conf 中进行了库搜索路径的设置之后，还必须要运行 /sbin/ldconfig 命令更新 /etc/ld.so.cache 文件之后才可以。ldconfig ,简单的说，它的作用就是将/etc/ld.so.conf列出的路径下的库文件缓存到/etc/ld.so.cache 以供使用。因此当安装完一些库文件，(例如刚安装好glib)，或者修改ld.so.conf增加新的库路径后，需要运行一下 /sbin/ldconfig使所有的库文件都被缓存到ld.so.cache中，如果没做，即使库文件明明就在/usr/lib下的，也是不会被使用 的，结果编译过程中抱错，缺少xxx库，去查看发现明明就在那放着，搞的想大骂computer蠢猪一个。

在程序连接时，对于库文件（静态库和共享库）的搜索路径，除了上面的设置方式之外，还可以通过 -L 参数显式指定。因为用 -L 设置的路径将被优先搜索，所以在连接的时候通常都会以这种方式直接指定要连接的库的路径。

前 面已经说明过了，库搜索路径的设置有两种方式：在环境变量 LD_LIBRARY_PATH 中设置以及在 /etc/ld.so.conf 文件中设置。其中，第二种设置方式需要 root 权限，以改变 /etc/ld.so.conf 文件并执行 /sbin/ldconfig 命令。而且，当系统重新启动后，所有的基于 GTK2 的程序在运行时都将使用新安装的 GTK+ 库。不幸的是，由于 GTK+ 版本的改变，这有时会给应用程序带来兼容性的问题，造成某些程序运行不正常。为了避免出现上面的这些情况，在 GTK+ 及其依赖库的安装过程中对于库的搜索路径的设置将采用第一种方式进行。这种设置方式不需要 root 权限，设置也简单：

$ export LD_LIBRARY_PATH=/opt/gtk/lib:$LD_LIBRARY_PATH

可以用下面的命令查看 LD_LIBRAY_PATH 的设置内容：

$ echo $LD_LIBRARY_PATH

至此，库的两种设置就完成了。

# compile perl

https://www.zhihu.com/question/52722964
https://serverfault.com/questions/145288/make-error-when-compiling-perl-5-12-1-rhel-5-5

I am trying to compile Perl 5.12.1 in my home directory on Red Hat Enterprise Linux 5.5. However, when I try to make, I eventually receive the following error:

    Making IO (all)
make[1]: Entering directory '/users/rmi1/build/perl-5.12.0/dist/IO'
make[1]: Leaving directory '/users/rmi1/build/perl-5.12.0/dist/IO'
Making all in dist/IO
 make all PERL_CORE=1 LIBPERL_A=libperl.a LINKTYPE=dynamic
make[1]: Entering directory '/users/rmi1/build/perl-5.12.0/dist/IO'
cc -c   -fno-strict-aliasing -pipe -fstack-protector -I/usr/local/include -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64 -O2   -DVERSION=\"1.25_02\" -DXS_VERSION=\"1.25_02\" -fPIC "-I../.."   IO.c
IO.xs: In function ‘XS_IO__Poll__poll’:
IO.xs:249: error: invalid application of ‘sizeof’ to incomplete type ‘struct pollfd’

I just ran into this same problem and tracked down the root cause: the C_INCLUDE_PATH environment variable. Mine happened to be set as follows:

% printenv C_INCLUDE_PATH
C_INCLUDE_PATH=/home/me/REDACTED/include:
This came from a login script somewhere that was doing something like

export C_INCLUDE_PATH=$HOME/REDACTED/include:$C_INCLUDE_PATH
while setting up my environment. That looks correct at first glance; unfortunately, it seems to be the case that foo: is equivalent to foo:. in this context-- that is, the empty string in that two-item colon-separated list seems to be implicitly treated the same as .. Which effectively adds the current directory to the system include path, which makes #include <poll.h> do the same thing as #include "poll.h", which is bad.

In Perl's case, the rogue include path causes Perl's poll.h to include itself instead of /usr/include/poll.h. Since Perl's poll.h has a guard against multiple inclusion, the second include silently does nothing, and you end up with no poll.h at all, which quickly leads to the compiler error we both saw. This also explains why your patch makes the problem go away: there is no ./sys/poll.h in the build directory, so the compiler ends up finding /usr/include/sys/poll.h, which ultimately happens to be what you wanted.

My solution was to get rid of the stray colon in C_INCLUDE_PATH. In my case, I found the script that was setting it incorrectly and fixed it so that it explicitly checks for the case where the previous C_INCLUDE_PATH was empty, and not add a colon in that case. Of course, as a quick one-off fix, I could also have manually run export C_INCLUDE_PATH=/home/me/REDACTED/include or just "unset C_INCLUDE_PATH" before building Perl.

#=> install PDL
/usr/bin/x86_64-linux-gnu-ld: ../groupsock/libgroupsock.a(inet.o): relocation R_X86_64_32S against .rodata' can not be used when making a PIE object; recompile with -fPIC
/usr/bin/x86_64-linux-gnu-ld: final link failed: Nonrepresentable section on output
在 COMPILE_OPTS 和 CONSOLE_LINK_OPTS 都加上 -fPIC
https://www.cnblogs.com/shawn-meng/p/9733831.html

#=> install PDL in fedora31 successfully
work good when using hdf5 1.8.20

1. install hdf5 1.8.20
then modify the bash file as below:

export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/root/hdf/1.8.20/lib
export C_INCLUDE_PATH=$C_INCLUDE_PATH:/root/hdf/1.8.20/include
export HDF5_INCLUDE_PATH=/root/hdf/1.8.20/include
export HDF5_PATH=/root/hdf/1.8.20/

2. cpan PDL::IO::HDF5
may be failed
then goto the directory compile


# octave

configure: WARNING: I couldn''t find -ltermcap, -lterminfo, -lncurses,
dnf install readline-devel.x86_64


# dnf
dnf list docker-ce --showduplicates | sort -r 

dnf source setting
/etc/yum.repos.d/fedora-updates.repo


# run firefox in docker
/home/leon/data/docker/firefox
docker build --rm -t firefox .
docker run -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix --privileged firefox


运行firefox时提示“libGL error: unable to load driver: swrast_dri.so”有卡顿
yum install -y mesa-libGLES-devel.x86_64 mesa-dri-drivers

    Index
        » Applications & Desktop Environments
            » SOLVED - WARNING **: Couldn't connect to accessibility bus
    export NO_AT_BRIDGE=1

# ADS
#=> 集成情况：

root password: HTHTPIEStack2008


# visa
AA009EGBKV
730124554573020627327168

using noaa amsu/msu data to set up temperature record to study the globe warming.


# rpm
    #=> extract rpm file
        rpm2cpio myrpmfile.rpm | cpio -idmv
        #^> check the dependency of rpm
            # How to check RPM package dependencies on Fedora, CentOS or RHEL:
            # in http://xmodulo.com/check-rpm-package-dependencies-fedora-centos-rhel.html
            repoquery --requires --resolve gcc-gfortran
        #^> download rpm file
            yumdownloader --downloadonly --downloaddir=./ glibc --resolve
            # yumdownloader --resolve --destdir=./rpm  gcc-c++
            # yumdownloader + --resolve(可选，意为下依赖包) + --destdir=软件存放位置 (可选) +软件包名
        #^> 强行安装当地rpm不下载依赖
            rpm -ivh *.rpm --nodeps --force
        #^> 在不能联网的服务器上安装程序
        pull一个干净的centos的docker，用yumdownloader --downloadonly --downloaddir=./ dnf --resolve 
        下载所有的依赖，然后考到1045的docker里面，用`rpm -ivh *.rpm --nodeps --force安装`

# docker
    mv docker /run/media/leon/data/docker_lib
    #=> download image
        docker pull centos:7.7.1908

    #=> start the docker service
        systemctl start docker
        systemctl status docker

    #=> load the image
        cat docker.tar | docker import - ads:1.0
        docker images

    #=> run image
        #^> set a container and run image
            docker run -it -v /:/home/ads/root --privileged=true ads:1.0 /bin/bash
        #^> back
            exit # back but will stop the container
        #^> restart the container
            docker ps -a
            docker start containerID
            #^> generate the image tar file
                docker export containerID > /home/ads/docker.tar
        #^> get into the container
            docker exec -it containerID bash # get into the container

    #=> stop and rm docker
        #^> stop docker
            docker stop containerID
        #^> rm docker
            docker rm containerID
        #^> rm image
            docker rmi imageID

docker add user
Docker 创建docker用户组，应用用户加入docker组
1. 创建docker用户组
 sudo groupadd docker
2. 应用用户加入docker用户组
 sudo usermod -aG docker ${USER}
3. 重启docker服务
 sudo systemctl restart docker
 systemctl restart docker.service

4. 切换或者退出当前账户再从新登入
su root             切换到root用户
su ${USER}          再切换到原来的应用用户以上配置才生效

docker基础操作说明.pdf
dmsetup table

echo 0 88080384 thin 253:7 11 | dmsetup load docker-253:1-184549824-95f242e4fe2fef132ab1a706ebf8eecbb1c6db19547c3f12b34b76a5dee96c7e
dmsetup resume docker-253:1-184549824-95f242e4fe2fef132ab1a706ebf8eecbb1c6db19547c3f12b34b76a5dee96c7e
resize2fs /dev/mapper/docker-253:1-184549824-95f242e4fe2fef132ab1a706ebf8eecbb1c6db19547c3f12b34b76a5dee96c7e
docker 内安装idl:

激活的时候出现：
WIDGET_BASE: Unable to connect to X Windows display: :0.0

solution:
直接拷贝外面的文件到里面：
docker cp idl/license/license.dat bf121ec92fd1:/idl/idl/license/

quick pull image:
docker pull 9cpn8tt6.mirror.aliyuncs.com/library/centos:8

HTHTPIEStack2008


Job for docker.service failed because the control process exited with error code. See "systemctl status docker.service" and "journalctl -xe" for details.
 这个可以通过如下方式解决:

查看文件系统 /etc/docker/daemon.json 有没有这个文件，没有测创建它包括二级目录 docker

在daemon.json文件中输入以下内容:


{
"storage-driver" : "devicemapper"
}


如果daemon.json
文件包含格式不正确的JSON，Docker将无法启动。

# arch docker images
docker pull archlinux


# singularity
#{{{


#}}}

# python
debug python

ipdb:
pip install ipdb

pudb:
pip install pudb


ipdb （python调试工具）
        n(下一个)
        ENTER(重复上次命令)
        q(退出)
        p<变量>(打印变量)
        c(继续)
        l(查找当前位于哪里)
        s(进入子程序)
        r(运行直到子程序结束)
        !


# pip install offline

pip 离线下载安装
原创shuai_wow 最后发布于2019-08-01 20:41:30 阅读数 1288  收藏
展开
1. online的机器上下载安装包（如tensorflow 1.10.0）：

pip download tensorflow==1.10.0
2. 将安装包拷贝至offline的机器，并在offline的机器上安装：

pip install --no-index --find-links=/path/to/package tensorflow==1.10.0
注：如果使用requirements.txt，只需将tensorflow改成“ -r requirements.txt ”.

以上为online机器和offline机器环境相同的情况下的方法，非常简单。但如果两台机器的环境不同，则比较麻烦，具体可参考：

https://imshuai.com/python-pip-install-package-offline-tensorflow


# install YouCompleteMe
错误提示：The ycmd server SHUT DOWN (restart with ':YcmRestartServer'). Unexpected exit code 1.

在路径

yum install python-devel
yum Search python | grep devel
yum install python3-devel...

yum install gcc
yum install cmake

 ~/.vim/plugged/YouCompleteMe
1
下执行

/usr/bin/python install.py

参考：https://github.com/Valloric/YouCompleteMe/issues/2831

in vimrc
let g:ycm_server_python_interpreter= '/usr/bin/python'


# error of envi
error:
ENVI_BATCH_INIT
% DEVICE: Unable to connect to X Windows display: :0.0
% DEVICE: Unable to open X Windows display.
          Is your DISPLAY environment variable set correctly?
% Execution halted at: ENVI_INIT
%                      ENVI_BATCH_INIT
%                      FY4A_ANGLE          4
solved:
add '/NO_STATUS_WINDOW' in the end:
ENVI_BATCH_INIT,/NO_STATUS_WINDOW


# read win data from linux
    https://blog.csdn.net/niying/article/details/13770939

# ads sever
    IP: 10.24.237.32
    user: ads
    pwd: htht@ads

# firefox 下载文件名乱码

Firefox下载中文文件名乱码--2017-12-18
码游哥
2017.12.18 09:17:02
字数 139阅读 1,715

在Web版微信和好基友聊天,要传给我一个神秘代码文件,下载下来文件名是一长串'%E6%96' 之类的数字.老鸟一看就是编码问题.先搜搜看吧.下面这张比较全:

之前解决方案
https://link.jianshu.com/?t=https://www.cnblogs.com/godtrue/p/4333262.html

    可不完美啊,还得写点java代码,虽然能抄,可还是不爽快.懒人大法发现Firefox里面有addon可以自动转... Download Filename Encoding. 下载安装,配置成自动检测utf和GBK. Ok了.

     太简单的都不好意思显摆了.


# install matlab 2018a
    https://blog.csdn.net/m0_37775034/article/details/80876362
    /swapdata/tcpie/iso/install -inputFile /root/matlab/installer_input.txt -mode silent -licensePath /swapdata/tcpie/Crack/Matlab906_Linux/FilesForR2019a/licenses/license.lic -agreeToLicense yes -fileInstallationKey 09806-07443-53955-64350-21751-41297 -destinationFolder /root/matlab/R2019a

# huawei
    http://www.huaweicloud.com/product/modelarts.com

# ssh without password (if want to ssh B from A)
        # 2 steps
    #=> in A's ~/.ssh/, run: ssh-keygen -t rsa
    #=> copy the centent to B:~/.ssh/authorized_keys

    sign_and_send_pubkey: signing failed: agent refused operation
    chmod 600 ~/.ssh/id_rsa
    chmod 644 ~/.ssh/id_rsa.pub

    in B: chmod 744 authorized_keys
    #

    
# git
git init
git remote add origin ssh://git@git.piesat.cn:27022/QXYG/algorithm/ADS_AOD.git
git add .
git commit -m 'first commit'
git push
# git push -u origin master


# install matlab
        https://blog.csdn.net/m0_37775034/article/details/80876362
    cd ~
    sudo mkdir Crack
    cd ~
    tar -xvf Matlab2018aLinux64Crack.tar.gz -C Crack
    cd /mnt
    sudo mkdir iso
    cd ~
    sudo mount -t auto -o loop R2018a_glnxa64_dvd1.iso /mnt/iso
    
# change the bottom and top panel
      http://blog.chinaunix.net/uid-20620288-id-5750914.html
  1、备份文件夹
  cp  window-list@gnome-shell-extensions.gcampax.github.com bak_window-list@gnome-shell-extensions.gcampax.github.com
  2、删除文件夹
  rm /usr/share/gnome-shell/extensions/window-list@gnome-shell-extensions.gcampax.github.com
  3. shrink the bottom panel
  /usr/share/gnome-shell/extensions/window-list@gnome-shell-extensions.gcampax.github.com/classic.css
  4. shrink the top panel
  /usr/share/gnome-shell/theme/gnome-classic.css
  
# shrink the title width
    Create a file ~/.config/gtk-3.0/gtk.css containng the following CSS

# mount ISO
    sudo mount -t auto -o loop R2018a_glnxa64_dvd2.iso /mnt/iso

# some information for CPAN
    cpan Bundle::CPAN

# can not input Chinese in CentOS WPS, just added in head of /usr/bin/wps
export XMODIFIERS="@im=ibus"
export GTK_IM_MODULE="ibus"
export QT_IM_MODULE="ibus"

# install gdal
    sudo yum install gdal
    sudo yum-config-manager --enable epel
    sudo yum install gdal-python

# change the modes
    /usr/share/gnome-shell/modes/classic.json

# changed
    /gnome-shell/extensions/apps-menu@gnome-shell-extensions.gcampax.github.com/stylesheet.css
    /usr/share/gnome-shell/modes/classic.json

# 气象中心对接
    #=> 预研
    #=> FY3 降水 大风 对流
    #=> 数据链入
    #=> progress
    



    
# unicode
🦂 🏹  🦀⏾ 🌙 🏺 💙⛏  ⚒  🛠 ☤ 🕏 🌷 🛑 💒🔑 🚧 ⚒ 🚫🏥 h ⛩  ⛪🏰 🏭⚙ 🏔 🏖 🚩🚢🏦⛽ ☕ 5 🍵 t⌚ 🌂🔆⏰⬽3 🏣
🎶🎵 ⚓⚖  🔑 ⛪ ⛺ 🦂🎲
🪐🦯 🦎 🦋 🦢 🪂 🦥🦩 🥆🛸🛫 🚁 🚀 📎📅📀💬💎🐜 🐠🔭🌈🍇🎢🐃🐎🐦🐧🐦 🐝🐞
🐾🌾
🗃️💼📂🗄️🛰️🎈 
🐛🐌🐾🦎🐋🐳🐜🌿🌱🍂🍒🍌🍋🌶🌶🥚🦞🦀🦐🧉🏜🏜🗼🛹⚓🛫🪂🧊🎐🥏🪁🎻📞🦯🪑📯👣
⚓✒🚲🎡🎠🎨🎪🎬

📺🎛️🔋💻🖥️    📝🗒️ 📇 📆 📅 📸 🪔 🏮 🔦 🏷️  🔖 💰 📧 📨 ✏️  📝 📉 ✂️ 📏 📐 ⚙️ ⛓️  🔗 🧲 🧰 🧪 🧬 🧫 ⚗️  🔬 🔭 📡 💉 🩸 💊 🩹 🩺 🚪 🪒 🧷 🧹 🧺 🧻 🧯 🛒  
🥄 🍴 🍽️   🔪 🏺🧊  🕸️  🔱 ➰ 〽️ 〰️ 🎗️  🎈 🧨 ✨ 🪁 🧱 🏚️  🏡 🏠 🏚️  🏘️  🏢 🪂 🛎️  🧳  🌦️  🌫️   💧 💭 ✉️ ⚗️  🔬 🔭 📡 💉 🩸 💊 🩹 🩺 🚪 🪒 🧷 🧹 🧺 🧻 🧯 🛒 ◻◼ 📺🎛️🔋💻🖥️    📝🗒️ 📇 📆 📅 📸 🪔 🏮 🔦 🏷️  🔖 💰 📧 📨 ✏️  📝 📉 ✂️ 📏 📐 ⚙ ⛓️  🔗 🧲 🧰 🧪 🧬 🧫 ⚗️  🔬 🔭 📡 💉 🩸 💊 🩹 🩺 🚪 🪒 🧷 🧹 🧺 🧻 🧯 🛒 🥄

🪡  🪄  🎰 🧩 🪗  🪘 🧮 🎞 🕯 🧾 💳 🗑 🔧 🪚  🪝  🪞 🪧  ⚧ ♂ 🪶  🪵  🏍 🪂 🪄  🪢 🖲 🔩
 🪦  🍄 🥔 🥕 🧂 🥟 🦀 🦐 🦞 🫖  🌐 🦟 🐚

List of Olympics-related emojis.


🏃 Person Running
🤺 Person Fencing
🏊 Person Swimming
🏋 Person Lifting Weights
🚴 Person Biking
🤸 Person Cartwheeling
🤼 People Wrestling
🤽 Person Playing Water Polo
🤾 Person Playing Handball
🌍 Globe Showing Europe-Africa
🌎 Globe Showing Americas
🌏 Globe Showing Asia-Australia
🌐 Globe With Meridians
🗺 World Map
🛶 Canoe
☀ Sun
🏅 Sports Medal
🏐 Volleyball
🏑 Field Hockey
🏓 Ping Pong
🏸 Badminton
🥊 Boxing Glove
🥋 Martial Arts Uniform
🥅 Goal Net
◯◯◯◯◯ Olympic Rings

🕸
https://emojipedia.org/nature/

# vim
    #=> remove the tmux :%s/\s*[│├].*//

# tmux
  [fig1](viewnior /home/leon/doc/note/fig/2021-02-0516-32-13.png)
viewnior /home/leon/doc/note/fig/2021-02-0516-32-13.png
# for baby's visa
    # 201908070341073
    730124554573020627327168

# change the time of centos
    cp /usr/share/zoneinfo/Asia/Chongqing /etc/localtime
    /etc/localtime -> ../usr/share/zoneinfo/Asia/Chongqing

# Extract files from an RPM (quick start)
    rpm2cpio p.rpm | cpio -idmv

# mount ntfs error (undefined symbol: ntfs_xattr_build_mapping)
    mount  挂载ntfs 报错 解决方案 (2017-06-06 16:33) 转载▼
标签： linux server    分类： computerScience
报错内容：
/sbin/mount.ntfs: symbol lookup error: /sbin/mount.ntfs: undefined symbol: ntfs_xattr_build_mapping

解决方案
mv /lib/libntfs-3g.so.87 /lib/libntfs-3g.so.87.unwanted
ldd $(which ntfs-3g)

原理
fedora升级 : ntfs-3g-2016.2.22-3.fc25.x86_64.rpm 通过--enable-xattr-mappings 编译。链接库应该是 /lib64/libntfs-3g.so.87, 而不是 /lib/libntfs-3g.so.87 ，系统很有可能安装了两个库，引起冲突。对原油的苦重命名即可

cp: cannot open  reading: Stale file handle
mount -o username=DMZRSAPP -o noserverino //10.0.66.163/MAS 163
https://unix.stackexchange.com/questions/606406/linux-smb-cifs-stale-cp-cannot-open-file-jpg-for-reading-stale-file-handle


# linux mount linux 
一.linux挂载windows
　　1.windows目录打开共享；
　　2.mount -t cifs -o username=admin***tor,password=abc //192.168.***.***/目录 /home/sharestore/windows/
二.linux挂载linux
　　1.检查是否安装以下服务：
　　　　rpm -qa | grep nfs-utils
　　　　rpm -qa | grep rpcbind
　　2.若没有则安装：
　　　　yum -y install nfs-utils
　　　　yum -y install rpcbind
　　3.配置nfs访问目录/etc/exports，默认为空，添加一行(开放目录权限给指定主机)：
　　　　/test 192.168.***.102(rw,no_root_squash,no_all_squash,async)
　　   刷新配置：
　　　　exportfs -a
　　4.启动以下服务：
        systemctl start rpcbind.service
        systemctl start nfs.service
　　5.服务器创建挂载点：
　　　　mkdir /mnt/test102
　　6.挂载nfs：
　　　　mount -t nfs 192.168.***.101:/test /home/test102

ubuntu:
sudo mount -o username=qixiangyaogan //10.1.100.26/qixiang /qixiang
sudo apt-get install cifs-utils


# mount 163
sudo mount -t cifs //10.0.66.163/MAS/DATA/MAS/ProductFile /mnt/DATA/ -o username=DMZRSAPP,password='Rsappmas>209',ro


# compile GCC (deal with mpr lib)

首先安装以下包,不然，你有可能会收获链接不到libc.a的错误
sudo yum install glibc-static libstdc++-static

wget http://ftp.gnu.org/gnu/gcc/gcc-4.7.0/gcc-4.7.0.tar.gz
tar xvf gcc-4.7.0.tar.gz
cd gcc-4.7.0
./contrib/download_prerequisites
cd ..
mkdir build_gcc4.7
cd build_gcc4.7
../gcc-4.7.0/configure --enable-checking=release --enable-languages=c,c++ --disable-multilib
make -j4
sudo make install

can
{
  我在服务器用了一个多小时后就可以了。。机器慢点，你就看开吧。。

  很多文章都说自己去下载mpr等等三个库的源码，自己编译，这是相当不理智的，浪费了不少时间，因为我们自己去下载包括安装都有可能碰到版本问题，以及路径问题，好好的方案还是使用./contrib/download_prerequisites  ,他会自动下载，自动编译，何乐而不为
}
or
{
  yum install  gmp  gmp-devel  mpfr  mpfr-devel  libmpc  libmpc-devel
}
gcc版本切换

1.查看你的gcc版本 ls /usr/bin/gcc -l
2.查看当前GCC版本 gcc --dumpversion
3.下载安装所需版本的gcc
4.查看当前安装的gcc版本 ls /usr/bin/gcc* -l
5.增加gcc可选项（假如你增加的为gcc－3.3）
update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-4.3 40
update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-3.3 30
6选择你的gcc
update-alternatives --config gcc
7最后查看gcc版本

简单来说就是
1）确定新安装的GCC的路径，之前安装时记下最后mv时的路径即可，我是默认安在了/usr/local/bin
ls /usr/local/bin | grep gcc
2）添加新GCC到可选项，倒数第二个参数为新GCC路径，最后一个参数为优先级，设大一些之后就自动使用新版了
update-alternatives --install /usr/bin/gcc gcc x86_64-unknown-linux-gnu-gcc-4.7.2 40
3）gcc -v确认当前版本已经切换为新版

gcc update
 yum install centos-release-scl -y
 yum install devtoolset-7 -y
 scl enable devtoolset-7 bash
 gcc --version
 注释：
 在centos的devtoolset库中 最新的为 devtoolset-7，所以我们以后可以自己改数字安装最新的版本
 scl enable devtoolset-7 bash 如果使用的是zsh则使用
 scl enable devtoolset-7 zsh
 如果不知道什么是zsh那么默认的就好了


# 雨-雪-冻雨成因
冻雨：
冻雨厚度一般可达10～20毫米，最厚的有30～40毫米。冻雨发生时，风力往往较大。
据气象专家分析，冻雨是在特定的天气背景下产生的降水现象。在此期间，江淮流域上空的西北气流和西南气流都很强，地面有冷空气侵入，1500至3000米上空又有暖气流北上，大气垂直结构呈上下冷、中间暖的状态，自上而下分别为冰晶层、暖层和冷层。即3000米以上高空大气温度往往在－10℃以下，2000米左右高空，大气温度一般为0℃左右，而2000米以下温度又低于0℃。 [3]

雪：
上下都冷 < 0 ?

雨：
下暖 > 0 ?


# vim plugin https://blog.csdn.net/gbxvip/article/details/51744489

================================
使用vim打造IDE， 针对C语言开发者
建议使用gvim
================================

# 安装ruby, command-t插件会用到
  sudo apt install ruby ruby-dev

# 安装vim, vim-gtk
  sudo apt install vim vim-gtk

# 在home目录下创建 .vimrc 并编辑
  1. 将附录1中 vimrc 的内容拷贝进去

# 在home目录下创建 .vim 目录
  1. 进入 .vim 目录
  2. 创建目录 autoload  bundle  colors  syntax

# 在 ~/.vim/colors 目录中创建 mycolor.vim 并编辑
  1. 将附录2中 mycolor.vim 的内容拷贝进去

# 在 ~/.vim/syntax 目录中创建 c.vim 并编辑
  1. 将附录3中 c.vim 的内容拷贝进去

# 下载插件 vundle 到 ~/.vim/bundle
  1. git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
  2. 需要安装 git
  3. vundle 可以自动安装和更新其他vim插件

# 下载插件 pathogen 到 ~/.vim/autoload
  1. curl -LSso ~/.vim/autoload/pathogen.vim https://tpo.pe/pathogen.vim
  2. 需要安装 curl
  3. pathogen 可以自动加载插件

# 安装其余 vim 插件
  1. 打开 vim 或 gvim
  2. 执行 :PluginInstall

# 编译 command-t插件
  1. 进入 ~/.vim/bundle/command-t/ruby/command-t目录
  2. 执行 ruby extconf.rb
  3. 执行 make

# 编译 YouCompleteMe 插件
  1. 进入 ~/.vim/bundle/YouCompleteMe
  2. 执行 ./install.py --clang-completer
  3. 需要安装 cmake
cd ~/.vim/bundle
git clone https://github.com/Valloric/YouCompleteMe.git
cd YouCompleteMe
git submodule update --init --recursive
./install.sh --clang-completer

# 安装ctags
1. 下载地址: http://ctags.sourceforge.net/

# 安装cscope
1. 下载地址: http://cscope.sourceforge.net/
2. 修改源码，使其支持递归搜索文件夹的软链接
   修改文件: dir.c
   修改方式: 替换函数调用 lstat 全部替换为 stat
3. 编译源码可能出现的错误
   错误: fatal error: curses.h: No such file or directory
   解决: sudo apt install libncurses5-dev libncursesw5-dev

# 创建 tag 生成和高亮脚本
  1. 找一个地方创建 htags.sh 文件，注意同时修改 .vimrc 中该脚本的路径
  2. 将附录4中 htags.sh 的内容拷贝进去
  3. 给htags.sh增加执行权限 chmod u+x htags.sh

# 生成 ctags 和 cscope 的标签并高亮
  1. 在工程的根目录打开 gvim 或 vim
  2. 使用快捷键 \bt 创建 ctags的标签
  3. 使用快捷键 \bc 创建 cscope的标签
  4. 使用快捷见 \ht 对重新高亮标签
     *每次启动vim时会自动导入一次, 如果没有
      重新生成标签就不要重新导入

# 使用YouCompleteMe的自动补全功能
  1. 在工程的根目录或创建 .ycm_extra_conf.py
  2. 将附录5中 .ycm_extra_conf.py 内容拷贝到其中
  3. 根据工程修改其中的头文件路径

# .vimrc
"===================通用配置======================

"文件搜索路径
set path=.,/usr/include,,

" 控制
set nocompatible              "关闭vi兼容
filetype off                  "关闭文件类型侦测,vundle需要
set fileencodings=utf-8,gbk   "使用utf-8或gbk编码方式
syntax on                     "语法高亮
set backspace=2               "退格键正常模式
set whichwrap=<,>,[,]         "当光标到行首或行尾，允许左右方向键换行
set autoread                  "文件在vim外修改过，自动重载
set nobackup                  "不使用备份
set confirm                   "在处理未保存或只读文件时，弹出确认消息
set scrolloff=3               "光标移动到距离顶部或底部开始滚到距离
set history=1000              "历史记录数
set mouse=                    "关闭鼠标
set selection=inclusive       "选择包含最后一个字符
set selectmode=mouse,key      "启动选择模式的方式
set completeopt=longest,menu  "智能补全,弹出菜单，无歧义时才自动填充
set noswapfile                "关闭交换文件
set hidden                    "允许在有未保存的修改时切换缓冲区

"显示
" colorscheme mycolor           "选择配色方案
set t_Co=256                  "可以使用的颜色数目
" set number                    "显示行号
set laststatus=2              "显示状态行
set ruler                     "显示标尺
set showcmd                   "显示输入的命令
set showmatch                 "高亮括号匹配
set matchtime=1               "匹配括号高亮的时间(十分之一秒)
set matchpairs={:},(:)        "匹配括号"{}""()"
set hlsearch                  "检索时高亮匹配项
set incsearch                 "边检索边显示匹配
set go-=T                     "去除gvim的toolbar

"格式
set noexpandtab               "不要将tab转换为空格
set shiftwidth=4              "自动缩进的距离,也是平移字符的距离
set tabstop=4                 "tab键对应的空格数
set autoindent                "自动缩进
set smartindent               "智能缩进


"===================按键映射======================

"按键映射的起始字符
let mapleader = '\'

"使用Ctrl-l 和 Ctrl+h 切换标签页
nnoremap <C-l> gt
nnoremap <c-h> gT

"在行末加上分号
nnoremap <silent> <Leader>; :<Esc><End>a<Space>;<Esc><Down>
"保存
nnoremap <C-s> :w<CR>
"替换
nnoremap <C-h> :%s/<C-R>=expand("<cword>")<CR>/<C-R>=expand("<cword>")<CR>
"===================插件管理======================

" 下载vundle
" git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim

" 下载pathogen
" curl -LSso ~/.vim/autoload/pathogen.vim https://tpo.pe/pathogen.vim

" 将vundle加入到runtime path
set rtp+=~/.vim/bundle/Vundle.vim

" 下载到bundle目录的插件
call vundle#begin()

" plugin on GitHub repo
Plugin 'VundleVim/Vundle.vim'
Plugin 'scrooloose/nerdtree'
Plugin 'Lokaltog/vim-powerline.git'
Plugin 'wincent/command-t'
Plugin 'Valloric/YouCompleteMe'
Plugin 'tomtom/tlib_vim'
Plugin 'tomtom/viki_vim'

" plugin from http://vim-scripts.org/vim/scripts.html
Plugin 'taglist.vim'
Plugin 'EasyGrep'

" Git plugin not hosted on GitHub
" Plugin 'git://...'

" git repos on your local machine
" Plugin 'file://...'

call vundle#end()

filetype plugin indent on    " required

"===================插件配置======================

"-----pathogen-----
execute pathogen#infect()

"-----NERDTree-----
let g:NERDTreeCaseSensitiveSort = 1
let g:NERDTreeWinSize = 25
let g:NERDTreeWinPos = "right"
nnoremap <silent> <Leader>t :NERDTreeToggle<CR>
nnoremap <silent> <Leader>o :NERDTreeFind<CR>

"-----Powerline-----
set fillchars+=stl:\ ,stlnc:\
let g:Powerline_symbols = 'compatible'
let g:Powerline_stl_path_style = 'filename'  "只显示文件名

"-----Command-T-----
let g:CommandTFileScanner = 'ruby'   "使用ruby作为文件浏览器
let g:CommandTTraverseSCM = 'dir'    "根目录为执行vim时所在的目录
"打开文件跳转
nnoremap <silent> <Leader>f :CommandT<CR>

"-----taglist-----
let Tlist_Show_One_File = 1           "只显示当前文件的taglist
let Tlist_Exit_OnlyWindow = 1         "taglist是最后一个窗口时退出vim
let Tlist_Use_Left_Window = 1         "在左侧窗口显示taglist
let Tlist_GainFocus_On_ToggleOpen = 1 "打开taglist时，光标停在taglist窗口
let Tlist_Auto_Update = 1             "自动更新
" 打开标签浏览器
nnoremap <silent><Leader>dt :Tlist<CR>
" 重新生成标签
nnoremap <silent><Leader>bt :!~/Myfiles/Tool/sh/ctags/hitags.sh<CR>
" 高亮标签
nnoremap <silent><Leader>ht :so tags.vim<CR>

"-----cscope-----
"加载cscope库
if filereadable("cscope.out")
    cs add cscope.out
endif
set cscopequickfix=s-,c-,d-,i-,t-,e- "使用quickfix窗口显示结果
set cst                              "跳转时也使用cscope库
"打开引用窗口
nnoremap <silent><Leader>cw :cw<CR>
"重新生成索引文件
nnoremap <silent><Leader>bc :!cscope -Rbq<CR>
"s: 查找本C符号
"g: 查找本定义
"d: 查找本函数调用的函数
"c: 查找调用本函数的函数
"t: 查找本字符串
"e: 查找本egrep模式
"f: 查找本文件
"i: 查找包含本文件的文件
nnoremap <C-\>s :scs find s <C-R>=expand("<cword>")<CR><CR>
nnoremap <C-\>g :scs find g <C-R>=expand("<cword>")<CR><CR>
nnoremap <C-\>c :scs find c <C-R>=expand("<cword>")<CR><CR>
nnoremap <C-\>t :scs find t <C-R>=expand("<cword>")<CR><CR>
nnoremap <C-\>e :scs find e <C-R>=expand("<cword>")<CR><CR>
nnoremap <C-\>f :scs find f <C-R>=expand("<cfile>")<CR><CR>
nnoremap <C-\>i :scs find i <C-R>=expand("<cfile>")<CR><CR>
nnoremap <C-\>d :scs find d <C-R>=expand("<cword>")<CR><CR>

"-----YouCompleteMe-----
let g:ycm_server_python_interpreter= '/usr/bin/python2'
let g:ycm_global_ycm_extra_conf = '~/.ycm_extra_conf.py' "默认配置文件
let g:ycm_key_invoke_completion = '<C-Tab>'         "跨文件补全
let g:ycm_confirm_extra_conf = 0                    "关闭加载配置文件提示
let g:ycm_cache_omnifunc = 0                        "关闭补全缓存
let g:ycm_enable_diagnostic_signs = 0               "关闭诊断提示符
let g:ycm_enable_diagnostic_highlighting = 1        "关闭诊断高亮
"let g:ycm_show_diagnostics_ui = 0                   "关闭诊断ui
let g:ycm_min_num_of_chars_for_completion = 3       "n字符开始自动补全
"获取变量类型
nnoremap <silent><Leader>yt :YcmCompleter GetType<CR>
"跳转定义或声明
nnoremap <silent><Leader>yg :YcmCompleter GoTo<CR>
"跳转包含文件
nnoremap <silent><Leader>yi :YcmCompleter GoToInclude<CR>
"打开诊断信息
nnoremap <silent><Leader>yd :YcmDiags<CR>

"-----EasyGrep-----
let EasyGrepMode = 2        "根据文件类型搜索相应文件
let EasyGrepRecursive = 1   "递归搜索
let EasyGrepCommand = 1     "使用grep
let EasyGrepJumpToMatch = 0 "不要跳转
color.vim
" Vim color file
" Maintainer:   Hans Fugal <hans@fugal.net>
" Last Change:  $Date: 2004/06/13 19:30:30 $
" Last Change:  $Date: 2004/06/13 19:30:30 $
" URL:      http://hans.fugal.net/vim/colors/desert.vim
" Version:  $Id: desert.vim,v 1.1 2004/06/13 19:30:30 vimboss Exp $

" cool help screens
" :he group-name
" :he highlight-groups
" :he cterm-colors

set background=dark
if version > 580
    " no guarantees for version 5.8 and below, but this makes it stop
    " complaining
    hi clear
    if exists("syntax_on")
    syntax reset
    endif
endif
let g:colors_name="desert"

hi Normal   guifg=White guibg=grey20

" highlight groups
hi Cursor   guibg=khaki guifg=slategrey
"hi CursorIM
"hi Directory
"hi DiffAdd
"hi DiffChange
"hi DiffDelete
"hi DiffText
"hi ErrorMsg
hi VertSplit    guibg=#c2bfa5 guifg=grey50 gui=none
hi Folded   guibg=grey30 guifg=gold
hi FoldColumn   guibg=grey30 guifg=tan
hi IncSearch    guifg=slategrey guibg=khaki
"hi LineNr
hi ModeMsg  guifg=goldenrod
hi MoreMsg  guifg=SeaGreen
hi NonText  guifg=LightBlue guibg=grey30
hi Question guifg=springgreen
hi Search   guibg=peru guifg=wheat
hi SpecialKey   guifg=yellowgreen
hi StatusLine   guibg=#c2bfa5 guifg=black gui=none
hi StatusLineNC guibg=#c2bfa5 guifg=grey50 gui=none
hi Title    guifg=indianred
hi Visual   gui=none guifg=khaki guibg=olivedrab
"hi VisualNOS
hi WarningMsg   guifg=salmon
"hi WildMenu
"hi Menu
"hi Scrollbar
"hi Tooltip

" syntax highlighting groups
hi Comment  guifg=SkyBlue
hi Constant guifg=#ffa0a0
hi Identifier   guifg=palegreen
hi Statement    guifg=khaki
hi PreProc  guifg=indianred
hi Type     guifg=darkkhaki
hi Special  guifg=navajowhite
"hi Underlined
hi Ignore   guifg=grey40
"hi Error
hi Todo     guifg=orangered guibg=yellow2

" color terminal definitions
hi SpecialKey   ctermfg=darkgreen
hi NonText  cterm=bold ctermfg=darkblue
hi Directory    ctermfg=darkcyan
hi ErrorMsg cterm=bold ctermfg=7 ctermbg=1
hi IncSearch    cterm=NONE ctermfg=yellow ctermbg=green
hi Search   cterm=NONE ctermfg=grey ctermbg=blue
hi MoreMsg  ctermfg=darkgreen
hi ModeMsg  cterm=NONE ctermfg=brown
hi LineNr   ctermfg=3
hi Question ctermfg=green
hi StatusLine   cterm=bold,reverse
hi StatusLineNC cterm=reverse
hi VertSplit    cterm=reverse
hi Title    ctermfg=5
hi Visual   cterm=reverse
hi VisualNOS    cterm=bold,underline
hi WarningMsg   ctermfg=1
hi WildMenu ctermfg=0 ctermbg=3
hi Folded   ctermfg=darkgrey ctermbg=NONE
hi FoldColumn   ctermfg=darkgrey ctermbg=NONE
hi DiffAdd  ctermbg=4
hi DiffChange   ctermbg=5
hi DiffDelete   cterm=bold ctermfg=4 ctermbg=6
hi DiffText cterm=bold ctermbg=1
hi Comment  ctermfg=darkcyan
hi Constant ctermfg=brown
hi Special  ctermfg=5
hi Identifier   ctermfg=6
hi Statement    ctermfg=3
hi PreProc  ctermfg=5
hi Type     ctermfg=2
hi Underlined   cterm=underline ctermfg=5
hi Ignore   cterm=bold ctermfg=7
hi Ignore   ctermfg=darkgrey
hi Error    cterm=bold ctermfg=7 ctermbg=1

"vim: sw=4

# c.vim
"not wrap
set nowrap

if filereadable("tags.vim")
    so tags.vim
endif

hi cFunction guifg=LightGreen
hi cMacro    guifg=LightRed
hi cGlobal   guifg=LightBlue
hi cMember   guifg=LightMagenta
hi def link cTypedef cType

# Makefile for C++
Copied from a wiki post I wrote for physics grad students.

Since this is for unix the executables have no extensions.

One thing to note is that root-config is a utility which provides the right compilation and linking flags; and the right libraries for building applications against root. That's just a detail related to the original audience for this document.

Make Me Baby
or You Never Forget The First Time You Got Made

A introductory discussion of make, and how to write a simple makefile

What is Make? And Why Should I Care?

The tool called make is a build dependency manager. That is, it takes care of knowing what commands need to be executed in what order to take your software project from a collection of source files, object files, libraries, headers, etc. etc.---some of which may have changed recently---and turning them into a correct up-to-date version of the program.

Actually you can use make for other things too, but I'm not going to talk about that.

A Trivial Makefile

Suppose that you have a directory containing: tool tool.cc tool.o support.cc support.hh, and  support.o which depend on root and are supposed to be compiled into a program called tool, and suppose that you've been hacking on the source files (which means the existing tool is now out of date) and want to compile the program.

To do this yourself you could

1) check if either support.cc or support.hh is newer than support.o, and if so run a command like

g++ -g -c -pthread -I/sw/include/root support.cc
2) check if either support.hh or tool.cc are newer than tool.o, and if so run a command like

g++ -g  -c -pthread -I/sw/include/root tool.cc
3) check if tool.o is newer than tool, and if so run a command like

g++ -g tool.o support.o -L/sw/lib/root -lCore -lCint -lRIO -lNet -lHist -lGraf -lGraf3d -lGpad -lTree -lRint \
  -lPostscript -lMatrix -lPhysics -lMathCore -lThread -lz -L/sw/lib -lfreetype -lz -Wl,-framework,CoreServices \
  -Wl,-framework,ApplicationServices -pthread -Wl,-rpath,/sw/lib/root -lm -ldl
Phew! What a hassle! There is a lot to remember and several chances to make mistakes. (BTW-- The particulars of the command lines exhibited here depend on our software environment. These ones work on my computer.)

Of course, you could just run all three commands every time. That would work, but doesn't scale well to a substantial piece of software (like DOGS which takes more than 15 minutes to compile from the ground up on my MacBook).

Instead you could write a file called makefile like this:

tool: tool.o support.o
    g++ -g -o tool tool.o support.o -L/sw/lib/root -lCore -lCint -lRIO -lNet -lHist -lGraf -lGraf3d -lGpad -lTree -lRint \
        -lPostscript -lMatrix -lPhysics -lMathCore -lThread -lz -L/sw/lib -lfreetype -lz -Wl,-framework,CoreServices \
        -Wl,-framework,ApplicationServices -pthread -Wl,-rpath,/sw/lib/root -lm -ldl

tool.o: tool.cc support.hh
    g++ -g  -c -pthread -I/sw/include/root tool.cc

support.o: support.hh support.cc
    g++ -g -c -pthread -I/sw/include/root support.cc
and just type make at the command line. which will perform the three steps shown above automatically.

The un-indented lines here have the form "target: dependencies" and tell make that the associated commands (indented lines) should be run if any of the dependencies are newer than the target. That is the dependency lines describe the logic of what needs to be rebuilt to accommodate changes in various files. If support.cc changes that means that support.o must be rebuilt, but tool.o can be left alone. When support.o changes tool must be rebuilt.

The commands associated with each dependency line are set off with a tab (see below) should modify the target (or at least touch it to update the modification time).

Variables, Built In Rules, and Other Goodies
At this point, our makefile is simply remembering the work that needs doing, but we still had to figure out and type each and every needed command in its entirety. It does not have to be that way: make is a powerful language with variables, text manipulation functions, and a whole slew of built-in rules which can make this much easier for us.

Make Variables

The syntax for accessing a make variable is $(VAR).

The syntax for assigning to a make variable is: VAR = A text value of some kind (or VAR := A different text value but ignore this for the moment).

You can use variables in rules like this improved version of our makefile:

CPPFLAGS=-g -pthread -I/sw/include/root
LDFLAGS=-g
LDLIBS=-L/sw/lib/root -lCore -lCint -lRIO -lNet -lHist -lGraf -lGraf3d -lGpad -lTree -lRint \
       -lPostscript -lMatrix -lPhysics -lMathCore -lThread -lz -L/sw/lib -lfreetype -lz \
       -Wl,-framework,CoreServices -Wl,-framework,ApplicationServices -pthread -Wl,-rpath,/sw/lib/root \
       -lm -ldl

tool: tool.o support.o
    g++ $(LDFLAGS) -o tool tool.o support.o $(LDLIBS)

tool.o: tool.cc support.hh
    g++ $(CPPFLAGS) -c tool.cc

support.o: support.hh support.cc
    g++ $(CPPFLAGS) -c support.cc
which is a little more readable, but still requires a lot of typing

Make Functions

GNU make supports a variety of functions for accessing information from the filesystem or other commands on the system. In this case we are interested in $(shell ...) which expands to the output of the argument(s), and $(subst opat,npat,text) which replaces all instances of opat with npat in text.

Taking advantage of this gives us:

CPPFLAGS=-g $(shell root-config --cflags)
LDFLAGS=-g $(shell root-config --ldflags)
LDLIBS=$(shell root-config --libs)

SRCS=tool.cc support.cc
OBJS=$(subst .cc,.o,$(SRCS))

tool: $(OBJS)
    g++ $(LDFLAGS) -o tool $(OBJS) $(LDLIBS)

tool.o: tool.cc support.hh
    g++ $(CPPFLAGS) -c tool.cc

support.o: support.hh support.cc
    g++ $(CPPFLAGS) -c support.cc
which is easier to type and much more readable.

Notice that

We are still stating explicitly the dependencies for each object file and the final executable
We've had to explicitly type the compilation rule for both source files
Implicit and Pattern Rules

We would generally expect that all c++ source files should be treated the same way, and make provides three ways to state this

suffix rules (considered obsolete in GNU make, but kept for backwards compatibility)
implicit rules
pattern rules
Implicit rules are built in, and a few will be discussed below. Pattern rules are specified in a form like

%.o: %.c
    $(CC) $(CFLAGS) $(CPPFLAGS) -c $<
which means that object files are generated from c source files by running the command shown, where the "automatic" variable $< expands to the name of the first dependency.

Built-in Rules

Make has a whole host of built in rules that mean that very often, a project can be compile by a very simple makefile, indeed.

The GNU make built in rule for c source files is the one exhibited above. Similarly we create object files from c++ source files with a rule like $(CXX) -c $(CPPFLAGS) $(CFLAGS)

Single object files are linked using $(LD) $(LDFLAGS) n.o $(LOADLIBES) $(LDLIBS), but this won't work in our case, because we want to link multiple object files.

Variables Used By Built-in Rules

The built in rules use a set of standard variables that allow you to specify local environment information (like where to find the ROOT include files) without re-writing all the rules. The ones most likely to be interesting to us are:

CC -- the c compiler to use
CXX -- the c++ compiler to use
LD -- the linker to use
CFLAGS -- compilation flag for c source files
CXXFLAGS -- compilation flags for c++ source files
CPPFLAGS -- flags for the c-preprocessor (typically include file paths and symbols defined on the command line), used by c and c++
LDFLAGS -- linker flags
LDLIBS -- libraries to link
A Basic Makefile

By taking advantage of the built in rules we can simplify our makefile to:

CC=gcc
CXX=g++
RM=rm -f
CPPFLAGS=-g $(shell root-config --cflags)
LDFLAGS=-g $(shell root-config --ldflags)
LDLIBS=$(shell root-config --libs)

SRCS=tool.cc support.cc
OBJS=$(subst .cc,.o,$(SRCS))

all: tool

tool: $(OBJS)
    $(CXX) $(LDFLAGS) -o tool $(OBJS) $(LDLIBS)

tool.o: tool.cc support.hh

support.o: support.hh support.cc

clean:
    $(RM) $(OBJS)

distclean: clean
    $(RM) tool
We have also added several standard targets that perform special actions (like cleaning up the source directory).

Note that when make is invoked without an argument, it uses the first target found in the file (in this case all), but you can also name the target to get which is what makes make clean remove the object files in this case.

We still have all the dependencies hard-coded.

Some Mysterious Improvements

CC=gcc
CXX=g++
RM=rm -f
CPPFLAGS=-g $(shell root-config --cflags)
LDFLAGS=-g $(shell root-config --ldflags)
LDLIBS=$(shell root-config --libs)

SRCS=tool.cc support.cc
OBJS=$(subst .cc,.o,$(SRCS))

all: tool

tool: $(OBJS)
    $(CXX) $(LDFLAGS) -o tool $(OBJS) $(LDLIBS)

depend: .depend

.depend: $(SRCS)
    $(RM) ./.depend
    $(CXX) $(CPPFLAGS) -MM $^>>./.depend;

clean:
    $(RM) $(OBJS)

distclean: clean
    $(RM) *~ .depend

include .depend
Notice that

There are no longer any dependency lines for the source files!?!
There is some strange magic related to .depend and depend
If you do make then ls -A you see a file named .depend which contains things that look like make dependency lines
Other Reading

GNU make manual
Recursive Make Considered Harmful on a common way of writing makefiles that is less than optimal, and how to avoid it.
Know Bugs and Historical Notes

The input language for make is whitespace sensitive. In particular the action lines following dependencies must start with a tab. But a series of spaces can look the same (and indeed there are editors that will silently convert tabs to spaces or vice versa), which results in a make file that looks right and still doesn't work. This was identified as a bug early on but (the story goes) was not fixed because there were already 10 users.
'

# Makefile basic

    #=> Makefile由浅入深--教程、干货
    https://zhuanlan.zhihu.com/p/47390641
        
    #=> 跟我一起写 Makefile
    https://blog.csdn.net/ruglcc/article/details/7814546
该篇文章为转载，是对原作者系列文章的总汇加上标注。
支持原创，请移步陈浩大神博客：
http://blog.csdn.net/haoel/article/details/2886

makefile很重要

      什么是makefile？或许很多Winodws的程序员都不知道这个东西，因为那些Windows的IDE都为你做了这个工作，但我觉得要作一个好的和professional的程序员，makefile还是要懂。这就好像现在有这么多的HTML的编辑器，但如果你想成为一个专业人士，你还是要了解HTML的标识的含义。特别在Unix下的软件编译，你就不能不自己写makefile了，会不会写makefile，从一个侧面说明了一个人是否具备完成大型工程的能力。因为，makefile关系到了整个工程的编译规则。一个工程中的源文件不计数，其按类型、功能、模块分别放在若干个目录中，makefile定义了一系列的规则来指定，哪些文件需要先编译，哪些文件需要后编译，哪些文件需要重新编译，甚至于进行更复杂的功能操作，因为makefile就像一个Shell脚本一样，其中也可以执行操作系统的命令。makefile带来的好处就是——“自动化编译”，一旦写好，只需要一个make命令，整个工程完全自动编译，极大的提高了软件开发的效率。make是一个命令工具，是一个解释makefile中指令的命令工具，一般来说，大多数的IDE都有这个命令，比如：Delphi的make，Visual C++的nmake，Linux下GNU的make。可见，makefile都成为了一种在工程方面的编译方法。

      现在讲述如何写makefile的文章比较少，这是我想写这篇文章的原因。当然，不同产商的make各不相同，也有不同的语法，但其本质都是在“文件依赖性”上做文章，这里，我仅对GNU的make进行讲述，我的环境是RedHat Linux 8.0，make的版本是3.80。必竟，这个make是应用最为广泛的，也是用得最多的。而且其还是最遵循于IEEE 1003.2-1992 标准的（POSIX.2）。

    在这篇文档中，将以C/C++的源码作为我们基础，所以必然涉及一些关于C/C++的编译的知识，相关于这方面的内容，还请各位查看相关的编译器的文档。这里所默认的编译器是UNIX下的GCC和CC。

0.1 关于程序的编译和链接

   在此，我想多说关于程序编译的一些规范和方法，一般来说，无论是C、C++、还是pas，首先要把源文件编译成中间代码文件，在Windows下也就是 .obj 文件，UNIX下是 .o 文件，即 Object File，这个动作叫做编译（compile）。然后再把大量的Object File合成执行文件，这个动作叫作链接（link）。

       编译时，编译器需要的是语法的正确，函数与变量的声明的正确。对于后者，通常是你需要告诉编译器头文件的所在位置（头文件中应该只是声明，而定义应该放在C/C++文件中），只要所有的语法正确，编译器就可以编译出中间目标文件。一般来说，每个源文件都应该对应于一个中间目标文件（O文件或是OBJ文件）。
       链接时，主要是链接函数和全局变量，所以，我们可以使用这些中间目标文件（O文件或是OBJ文件）来链接我们的应用程序。链接器并不管函数所在的源文件，只管函数的中间目标文件（Object File），在大多数时候，由于源文件太多，编译生成的中间目标文件太多，而在链接时需要明显地指出中间目标文件名，这对于编译很不方便，所以，我们要给中间目标文件打个包，在Windows下这种包叫“库文件”（Library File)，也就是 .lib 文件，在UNIX下，是Archive File，也就是 .a 文件。

      总结一下，源文件首先会生成中间目标文件，再由中间目标文件生成执行文件。在编译时，编译器只检测程序语法，和函数、变量是否被声明。如果函数未被声明，编译器会给出一个警告，但可以生成Object File。而在链接程序时，链接器会在所有的Object File中找寻函数的实现，如果找不到，那到就会报链接错误码（Linker Error），在VC下，这种错误一般是：Link 2001错误，意思说是说，链接器未能找到函数的实现。你需要指定函数的ObjectFile.

       好，言归正传，GNU的make有许多的内容，闲言少叙，还是让我们开始吧。


1 Makefile 介绍
      make命令执行时，需要一个 Makefile 文件，以告诉make命令需要怎么样的去编译和链接程序。

      首先，我们用一个示例来说明Makefile的书写规则。以便给大家一个感兴认识。这个示例来源于GNU的make使用手册，在这个示例中，我们的工程有8个C文件，和3个头文件，我们要写一个Makefile来告诉make命令如何编译和链接这几个文件。我们的规则是：


            1.如果这个工程没有编译过，那么我们的所有C文件都要编译并被链接。

            2.如果这个工程的某几个C文件被修改，那么我们只编译被修改的C文件，并链接目标程序。

            3.如果这个工程的头文件被改变了，那么我们需要编译引用了这几个头文件的C文件，并链接目标程序。


      只要我们的Makefile写得够好，所有的这一切，我们只用一个make命令就可以完成，make命令会自动智能地根据当前的文件修改的情况来确定哪些文件需要重编译，从而自己编译所需要的文件和链接目标程序。



1.1 Makefile的规则
   在讲述这个Makefile之前，还是让我们先来粗略地看一看Makefile的规则。

          target... : prerequisites ...

          command

          ...

          ...
         -------------------------------------------------------------------------------

       target也就是一个目标文件，可以是Object File，也可以是执行文件。还可以是一个标签（Label），对于标签这种特性，在后续的“伪目标”章节中会有叙述。

       prerequisites就是，要生成那个target所需要的文件或是目标。

       command也就是make需要执行的命令。（任意的Shell命令）


       这是一个文件的依赖关系，也就是说，target这一个或多个的目标文件依赖于prerequisites中的文件，其生成规则定义在command中。说白一点就是说，prerequisites中如果有一个以上的文件比target文件要新的话，command所定义的命令就会被执行。这就是Makefile的规则。也就是Makefile中最核心的内容。

       说到底，Makefile的东西就是这样一点，好像我的这篇文档也该结束了。呵呵。还不尽然，这是Makefile的主线和核心，但要写好一个Makefile还不够，我会以后面一点一点地结合我的工作经验给你慢慢到来。内容还多着呢。：）



1.2 一个示例
正如前面所说的，如果一个工程有3个头文件，和8个C文件，我们为了完成前面所述的那三个规则，我们的Makefile应该是下面的这个样子的。

   edit : main.o kbd.o command.o display.o \

          insert.o search.o files.o utils.o

           cc -o edit main.o kbd.o command.o display.o \

                      insert.o search.o files.o utils.o



   main.o : main.c defs.h

           cc -c main.c

   kbd.o : kbd.c defs.h command.h

           cc -c kbd.c

   command.o : command.c defs.h command.h

           cc -c command.c

   display.o : display.c defs.h buffer.h

           cc -c display.c

   insert.o : insert.c defs.h buffer.h

           cc -c insert.c

   search.o : search.c defs.h buffer.h

           cc -c search.c

   files.o : files.c defs.h buffer.h command.h

           cc -c files.c

   utils.o : utils.c defs.h

           cc -c utils.c

   clean :

           rm edit main.o kbd.o command.o display.o \

              insert.o search.o files.o utils.o

        反斜杠（\）是换行符的意思。这样比较便于Makefile的易读。我们可以把这个内容保存在文件为“Makefile”或“makefile”的文件中，然后在该目录下直接输入命令“make”就可以生成执行文件edit。如果要删除执行文件和所有的中间目标文件，那么，只要简单地执行一下“make clean”就可以了。

        在这个makefile中，目标文件（target）包含：执行文件edit和中间目标文件（*.o），依赖文件（prerequisites）就是冒号后面的那些 .c 文件和 .h文件。每一个 .o 文件都有一组依赖文件，而这些 .o 文件又是执行文件 edit 的依赖文件。依赖关系的实质上就是说明了目标文件是由哪些文件生成的，换言之，目标文件是哪些文件更新的。

        在定义好依赖关系后，后续的那一行定义了如何生成目标文件的操作系统命令，一定要以一个Tab键作为开头。记住，make并不管命令是怎么工作的，他只管执行所定义的命令。make会比较targets文件和prerequisites文件的修改日期，如果prerequisites文件的日期要比targets文件的日期要新，或者target不存在的话，那么，make就会执行后续定义的命令。

        这里要说明一点的是，clean不是一个文件，它只不过是一个动作名字，有点像C语言中的lable一样，其冒号后什么也没有，那么，make就不会自动去找文件的依赖性，也就不会自动执行其后所定义的命令。要执行其后的命令，就要在make命令后明显得指出这个lable的名字。这样的方法非常有用，我们可以在一个makefile中定义不用的编译或是和编译无关的命令，比如程序的打包，程序的备份，等等。


1.3 make是如何工作的
在默认的方式下，也就是我们只输入make命令。那么，

  make会在当前目录下找名字叫“Makefile”或“makefile”的文件。
  如果找到，它会找文件中的第一个目标文件（target），在上面的例子中，他会找到“edit”这个文件，并把这个文件作为最终的目标文件。
  如果edit文件不存在，或是edit所依赖的后面的 .o 文件的文件修改时间要比edit这个文件新，那么，他就会执行后面所定义的命令来生成edit这个文件。
  如果edit所依赖的.o文件也存在，那么make会在当前文件中找目标为.o文件的依赖性，如果找到则再根据那一个规则生成.o文件。（这有点像一个堆栈的过程）
  当然，你的C文件和H文件是存在的啦，于是make会生成 .o 文件，然后再用 .o 文件声明make的终极任务，也就是执行文件edit了。
    这就是整个make的依赖性，make会一层又一层地去找文件的依赖关系，直到最终编译出第一个目标文件。在找寻的过程中，如果出现错误，比如最后被依赖的文件找不到，那么make就会直接退出，并报错，而对于所定义的命令的错误，或是编译不成功，make根本不理。make只管文件的依赖性，即，如果在我找了依赖关系之后，冒号后面的文件还是不在，那么对不起，我就不工作啦。
        通过上述分析，我们知道，像clean这种，没有被第一个目标文件直接或间接关联，那么它后面所定义的命令将不会被自动执行，不过，我们可以显示要make执行。即命令——“make clean”，以此来清除所有的目标文件，以便重编译。

      于是在我们编程中，如果这个工程已被编译过了，当我们修改了其中一个源文件，比如file.c，那么根据我们的依赖性，我们的目标file.o会被重编译（也就是在这个依性关系后面所定义的命令），于是file.o的文件也是最新的啦，于是file.o的文件修改时间要比edit要新，所以edit也会被重新链接了（详见edit目标文件后定义的命令）。

而如果我们改变了“command.h”，那么，kdb.o、command.o和files.o都会被重编译，并且，edit会被重链接。


1.4 makefile中使用变量
在上面的例子中，先让我们看看edit的规则：

     edit : main.o kbd.o command.o display.o \

                 insert.o search.o files.o utils.o

           cc -o edit main.o kbd.o command.o display.o \

                      insert.o search.o files.o utils.o

    我们可以看到[.o]文件的字符串被重复了两次，如果我们的工程需要加入一个新的[.o]文件，那么我们需要在两个地方加（应该是三个地方，还有一个地方在clean中）。当然，我们的makefile并不复杂，所以在两个地方加也不累，但如果makefile变得复杂，那么我们就有可能会忘掉一个需要加入的地方，而导致编译失败。所以，为了makefile的易维护，在makefile中我们可以使用变量。makefile的变量也就是一个字符串，理解成C语言中的宏可能会更好。

比如，我们声明一个变量，叫objects, OBJECTS, objs, OBJS, obj, 或是 OBJ，反正不管什么啦，只要能够表示obj文件就行了。我们在makefile一开始就这样定义：

    objects = main.o kbd.o command.o display.o \

             insert.o search.o files.o utils.o

于是，我们就可以很方便地在我们的makefile中以“$(objects)”的方式来使用这个变量了，于是我们的改良版makefile就变成下面这个样子：

   objects = main.o kbd.o command.o display.o \
             insert.osearch.o files.o utils.o
   edit : $(objects)
           cc -o edit $(objects)
   main.o : main.c defs.h
           cc -c main.c
   kbd.o : kbd.c defs.h command.h
           cc -c kbd.c
   command.o : command.c defs.h command.h
           cc -c command.c
   display.o : display.c defs.h buffer.h
           cc -c display.c
   insert.o : insert.c defs.h buffer.h
           cc -c insert.c
   search.o : search.c defs.h buffer.h
           cc -c search.c
   files.o : files.c defs.h buffer.h command.h
           cc -c files.c
   utils.o : utils.c defs.h
           cc -c utils.c
   clean :
           rm edit $(objects)
于是如果有新的 .o 文件加入，我们只需简单地修改一下 objects 变量就可以了。

关于变量更多的话题，我会在后续给你一一道来。


1.5 让make自动推导
GNU的make很强大，它可以自动推导文件以及文件依赖关系后面的命令，于是我们就没必要去在每一个[.o]文件后都写上类似的命令，因为，我们的make会自动识别，并自己推导命令。

    只要make看到一个[.o]文件，它就会自动的把[.c]文件加在依赖关系中，如果make找到一个whatever.o，那么whatever.c，就会是whatever.o的依赖文件。并且 cc -c whatever.c 也会被推导出来，于是，我们的makefile再也不用写得这么复杂。我们的是新的makefile又出炉了。

   objects = main.o kbd.o command.o display.o \
             insert.o search.o files.o utils.o

   edit : $(objects)
           cc -o edit $(objects)

   main.o : defs.h
   kbd.o : defs.h command.h
   command.o : defs.h command.h
   display.o : defs.h buffer.h
   insert.o : defs.h buffer.h
   search.o : defs.h buffer.h
   files.o : defs.h buffer.h command.h
   utils.o : defs.h

   .PHONY : clean
   clean :
           rm edit $(objects)
这种方法，也就是make的“隐晦规则”。上面文件内容中，“.PHONY”表示，clean是个伪目标文件。

关于更为详细的“隐晦规则”和“伪目标文件”，我会在后续给你一一道来。


1.6 另类风格的makefile
    即然我们的make可以自动推导命令，那么我看到那堆[.o]和[.h]的依赖就有点不爽，那么多的重复的[.h]，能不能把其收拢起来，好吧，没有问题，这个对于make来说很容易，谁叫它提供了自动推导命令和文件的功能呢？来看看最新风格的makefile吧。

   objects = main.o kbd.o command.o display.o \
             insert.o search.o files.o utils.o

   edit : $(objects)
           cc -o edit $(objects)

   $(objects) : defs.h
   kbd.o command.o files.o : command.h
   display.o insert.o search.o files.o : buffer.h

   .PHONY : clean
   clean :
           rm edit $(objects)
这种风格，让我们的makefile变得很简单，但我们的文件依赖关系就显得有点凌乱了。鱼和熊掌不可兼得。还看你的喜好了。我是不喜欢这种风格的，一是文件的依赖关系看不清楚，二是如果文件一多，要加入几个新的.o文件，那就理不清楚了。


1.7 清空目标文件的规则
      每个Makefile中都应该写一个清空目标文件（.o和执行文件）的规则，这不仅便于重编译，也很利于保持文件的清洁。这是一个“修养”（呵呵，还记得我的《编程修养》吗）。一般的风格都是：

       clean:

           rm edit $(objects)

更为稳健的做法是：

       .PHONY : clean

       clean :

               -rm edit $(objects)

前面说过，.PHONY意思表示clean是一个“伪目标”，。而在rm命令前面加了一个小减号的意思就是，也许某些文件出现问题，但不要管，继续做后面的事。当然，clean的规则不要放在文件的开头，不然，这就会变成make的默认目标，相信谁也不愿意这样。不成文的规矩是——“clean从来都是放在文件的最后”。

上面就是一个makefile的概貌，也是makefile的基础，下面还有很多makefile的相关细节，准备好了吗？准备好了就来。





2 Makefile 总述

2.1 Makefile里有什么？
Makefile里主要包含了五个东西：显式规则、隐晦规则、变量定义、文件指示和注释。

显式规则。显式规则说明了，如何生成一个或多的的目标文件。这是由Makefile的书写者明显指出，要生成的文件，文件的依赖文件，生成的命令。
隐晦规则。由于我们的make有自动推导的功能，所以隐晦的规则可以让我们比较粗糙地简略地书写Makefile，这是由make所支持的。
变量的定义。在Makefile中我们要定义一系列的变量，变量一般都是字符串，这个有点你C语言中的宏，当Makefile被执行时，其中的变量都会被扩展到相应的引用位置上。
文件指示。其包括了三个部分，一个是在一个Makefile中引用另一个Makefile，就像C语言中的include一样；另一个是指根据某些情况指定Makefile中的有效部分，就像C语言中的预编译#if一样；还有就是定义一个多行的命令。有关这一部分的内容，我会在后续的部分中讲述。
 注释。Makefile中只有行注释，和UNIX的Shell脚本一样，其注释是用“#”字符，这个就像C/C++中的“//”一样。如果你要在你的Makefile中使用“#”字符，可以用反斜框进行转义，如：“\#”。
最后，还值得一提的是，在Makefile中的命令，必须要以[Tab]键开始。


2.2Makefile的文件名
        默认的情况下，make命令会在当前目录下按顺序找寻文件名为“GNUmakefile”、“makefile”、“Makefile”的文件，找到了解释这个文件。在这三个文件名中，最好使用“Makefile”这个文件名，因为，这个文件名第一个字符为大写，这样有一种显目的感觉。最好不要用“GNUmakefile”，这个文件是GNU的make识别的。有另外一些make只对全小写的“makefile”文件名敏感，但是基本上来说，大多数的make都支持“makefile”和“Makefile”这两种默认文件名。

     当然，你可以使用别的文件名来书写Makefile，比如：“Make.Linux”，“Make.Solaris”，“Make.AIX”等，如果要指定特定的Makefile，你可以使用make的“-f”和“--file”参数，如：make -f Make.Linux或make --file Make.AIX。


2.3 引用其它的Makefile
    在Makefile使用include关键字可以把别的Makefile包含进来，这很像C语言的#include，被包含的文件会原模原样的放在当前文件的包含位置。include的语法是：

    include<filename>filename可以是当前操作系统Shell的文件模式（可以保含路径和通配符）

在include前面可以有一些空字符，但是绝不能是[Tab]键开始。include和可以用一个或多个空格隔开。举个例子，你有这样凶：

   %.d: %.c

           @set -e; rm -f $@; \

            $(CC) -M $(CPPFLAGS) $< > $@.
; \

            sed 's,$∗$∗\.o[ :]*,\1.o $@ : ,g' < $@.
> $@; \

            rm -f $@.

这个规则的意思是，所有的[.d]文件依赖于[.c]文件，“rm-f $@”的意思是删除所有的目标，也就是[.d]文件，第二行的意思是，为每个依赖文件“$<”，也就是[.c]文件生成依赖文件，“$@”表示模式“%.d”文件，如果有一个C文件是name.c，那么“%”就是“name”，“
”意为一个随机编号，第二行生成的文件有可能是“name.d.12345”，第三行使用sed命令做了一个替换，关于sed命令的用法请参看相关的使用文档。第四行就是删除临时文件。

总而言之，这个模式要做的事就是在编译器生成的依赖关系中加入[.d]文件的依赖，即把依赖关系：

   main.o : main.c defs.h

转成：

   main.o main.d : main.c defs.h

于是，我们的[.d]文件也会自动更新了，并会自动生成了，当然，你还可以在这个[.d]文件中加入的不只是依赖关系，包括生成的命令也可一并加入，让每个[.d]文件都包含一个完赖的规则。一旦我们完成这个工作，接下来，我们就要把这些自动生成的规则放进我们的主Makefile中。我们可以使用Makefile的“include”命令，来引入别的Makefile文件（前面讲过），例如：

   sources = foo.c bar.c



   include $(sources:.c=.d)

上述语句中的“$(sources:.c=.d)”中的“.c=.d”的意思是做一个替换，把变量$(sources)所有[.c]的字串都替换成[.d]，关于这个“替换”的内容，在后面我会有更为详细的讲述。当然，你得注意次序，因为include是按次来载入文件，最先载入的[.d]文件中的目标会成为默认目标


4 Makefile 书写命令
      每条规则中的命令和操作系统Shell的命令行是一致的。make会一按顺序一条一条的执行命令，每条命令的开头必须以[Tab]键开头，除非，命令是紧跟在依赖规则后面的分号后的。在命令行之间中的空格或是空行会被忽略，但是如果该空格或空行是以Tab键开头的，那么make会认为其是一个空命令。

我们在UNIX下可能会使用不同的Shell，但是make的命令默认是被“/bin/sh”——UNIX的标准Shell解释执行的。除非你特别指定一个其它的Shell。Makefile中，“#”是注释符，很像C/C++中的“//”，其后的本行字符都被注释。


4.1 显示命令
通常，make会把其要执行的命令行在命令执行前输出到屏幕上。当我们用“@”字符在命令行前，那么，这个命令将不被make显示出来，最具代表性的例子是，我们用这个功能来像屏幕显示一些信息。如：

   @echo 正在编译XXX模块......

当make执行时，会输出“正在编译XXX模块......”字串，但不会输出命令，如果没有“@”，那么，make将输出：

   echo 正在编译XXX模块......

   正在编译XXX模块......

如果make执行时，带入make参数“-n”或“--just-print”，那么其只是显示命令，但不会执行命令，这个功能很有利于我们调试我们的Makefile，看看我们书写的命令是执行起来是什么样子的或是什么顺序的。

而make参数“-s”或“--slient”则是全面禁止命令的显示。


4.2 命令执行
当依赖目标新于目标时，也就是当规则的目标需要被更新时，make会一条一条的执行其后的命令。需要注意的是，如果你要让上一条命令的结果应用在下一条命令时，你应该使用分号分隔这两条命令。比如你的第一条命令是cd命令，你希望第二条命令得在cd之后的基础上运行，那么你就不能把这两条命令写在两行上，而应该把这两条命令写在一行上，用分号分隔。如：

   示例一：

       exec:

               cd /home/hchen

               pwd



   示例二：

       exec:

               cd /home/hchen; pwd

当我们执行“何一个条件表达式都应该以endif结束。

当我们的变量$(CC)值是“gcc”时，目标foo的规则是：


foo: $(objects)
$(CC) -o foo $(objects) $(libs_for_gcc)


而当我们的变量$(CC)值不是“gcc”时（比如“cc”），目标foo的规则是：

foo: $(objects)
$(CC) -o foo $(objects) $(normal_libs)


当然，我们还可以把上面的那个例子写得更简洁一些：


libs_for_gcc = -lgnu
normal_libs =


ifeq ($(CC),gcc)
libs=$(libs_for_gcc)
else
libs=$(normal_libs)
endif


foo: $(objects)
$(CC) -o foo $(objects) $(libs)




二、语法


条件表达式的语法为：


<conditional-directive>
<text-if-true>
endif


以及：


<conditional-directive>
<text-if-true>
else
<text-if-false>
endif


其中<conditional-directive>表示条件关键字，如“ifeq”。这个关键字有四个。

第一个是我们前面所见过的“ifeq”


ifeq (<arg1>, <arg2> )
ifeq '<arg1>' '<arg2>'
ifeq "<arg1>" "<arg2>"
ifeq "<arg1>" '<arg2>'
ifeq '<arg1>' "<arg2>"


比较参数“arg1”和“arg2”的值是否相同。当然，参数中我们还可以使用make的函数。如：


ifeq ($(strip $(foo)),)
<text-if-empty>
endif


这个示例中使用了“strip”函数，如果这个函数的返回值是空（Empty），那么<text-if-empty>就生效。

第二个条件关键字是“ifneq”。语法是：


ifneq (<arg1>, <arg2> )
ifneq '<arg1>' '<arg2>'
ifneq "<arg1>" "<arg2>"
ifneq "<arg1>" '<arg2>'
ifneq '<arg1>' "<arg2>"


其比较参数“arg1”和“arg2”的值是否相同，如果不同，则为真。和“ifeq”类似。




第三个条件关键字是“ifdef”。语法是：


ifdef <variable-name>


如果变量<variable-name>的值非空，那到表达式为真。否则，表达式为假。当然，<variable-name>同样可以是一个函数的返回值。注意，ifdef只是测试一个变量是否有值，其并不会把变量扩展到当前位置。还是来看两个例子：


示例一：
bar =
foo = $(bar)
ifdef foo
frobozz = yes
else
frobozz = no
endif


示例二：
foo =
ifdef foo
frobozz = yes
else
frobozz = no
endif


第一个例子中，“$(frobozz)”值是“yes”，第二个则是“no”。


第四个条件关键字是“ifndef”。其语法是：


ifndef <variable-name>


这个我就不多说了，和“ifdef”是相反的意思。


在<conditional-directive>这一行上，多余的空格是被允许的，但是不能以[Tab]键做为开始（不然就被认为是命令）。而注释符“#”同样也是安全的。“else”和“endif”也
一样，只要不是以[Tab]键开始就行了。

特别注意的是，make是在读取Makefile时就计算条件表达式的值，并根据条件表达式的值来选择语句，所以，你最好不要把自动化变量（如“$@”等）放入条件表达式中，因为自动化变量是在运行时才有的。

而且，为了避免混乱，make不允许把整个条件语句分成两部分放在不同的文件中。





使用函数
————


在Makefile中可以使用函数来处理变量，从而让我们的命令或是规则更为的灵活和具有智能。make所支持的函数也不算很多，不过已经足够我们的操作了。函数调用后，函数的返回值可以当做变量来使用。


一、函数的调用语法


函数调用，很像变量的使用，也是以“$”来标识的，其语法如下：


$(<function> <arguments> )


或是


${<function> <arguments>}


这里，<function>就是函数名，make支持的函数不多。<arguments>是函数的参数，参数间以逗号“,”分隔，而函数名和参数之间以“空格”分隔。函数调用以“$”开头，以圆括号或花括号把函数名和参数括起。感觉很像一个变量，是不是？函数中的参数可以使用变量，为了风格的统一，函数和变量的括号最好一样，如使用“$(subst a,b,$(x))”这样的形式，而不是“$(subst a,b,${x})”的形式。因为统一会更清楚，也会减少一些不必要的麻烦。


还是来看一个示例：


comma:= ,
empty:=y-run”
“--recon”
仅输出执行过程中的命令序列，但并不执行。


“-o <file>”
“--old-file=<file>”
“--assume-old=<file>”
不重新生成的指定的<file>，即使这个目标的依赖文件新于它。


“-p”
“--print-data-base”
输出makefile中的所有数据，包括所有的规则和变量。这个参数会让一个简单的makefile都会输出一堆信息。如果你只是想输出信息而不想执行 makefile，你可以使用“make -q
p”命令。如果你想查看执行makefile前的预设变量和规则，你可以使用“make –p –f /dev/null”。这个参数输出的信息会包含着你的makefile文件的文件名和行号，所以，用
这个参数来调试你的makefile会是很有用的，特别是当你的环境变量很复杂的时候。

“-q”
“--question”
不运行命令，也不输出。仅仅是检查所指定的目标是否需要更新。如果是0则说明要更新，如果是2则说明有错误发生。


“-r”
“--no-builtin-rules”
禁止make使用任何隐含规则。


“-R”
“--no-builtin-variabes”
禁止make使用任何作用于变量上的隐含规则。


“-s”
“--silent”
“--quiet”
在命令运行时不输出命令的输出。


“-S”
“--no-keep-going”
“--stop”
取消“-k”选项的作用。因为有些时候，make的选项是从环境变量“MAKEFLAGS”中继承下来的。所以你可以在命令行中使用这个参数来让环境变量中的“-k”选项失效。


“-t”
“--touch”
相当于UNIX的touch命令，只是把目标的修改日期变成最新的，也就是阻止生成目标的命令运行。


“-v”
“--version”
输出make程序的版本、版权等关于make的信息。


“-w”
“--print-directory”
输出运行makefile之前和之后的信息。这个参数对于跟踪嵌套式调用make时很有用。


“--no-print-directory”
禁止“-w”选项。


“-W <file>”
“--what-if=<file>”
“--new-file=<file>”
“--assume-file=<file>”
假定目标<file>需要更新，如果和“-n”选项使用，那么这个参数会输出该目标更新时的运行动作。如果没有“-n”那么就像运行UNIX的“touch”命令一样，使得<file>的修改时
间为当前时间。


“--warn-undefined-variables”
只要make发现有未定义的变量，那么就输出警告信息。


隐含规则
————


在我们使用Makefile时，有一些我们会经常使用，而且使用频率非常高的东西，比如，我们编译C/C++的源程序为中间目标文件（Unix下是[.o] 文件，Windows下是[.obj]文件）。本章讲述的就是一些在Makefile中的“隐含的”，早先约定了的，不需要我们再写出来的规则。


“隐含规则”也就是一种惯例，make会按照这种“惯例”心照不喧地来运行，那怕我们的Makefile中没有书写这样的规则。例如，把[.c]文件编译成[.o]文件这一规则，你根本就
不用写出来，make会自动推导出这种规则，并生成我们需要的[.o]文件。

“隐含规则”会使用一些我们系统变量，我们可以改变这些系统变量的值来定制隐含规则的运行时的参数。如系统变量“CFLAGS”可以控制编译时的编译器参数。


我们还可以通过“模式规则”的方式写下自己的隐含规则。用“后缀规则”来定义隐含规则会有许多的限制。使用“模式规则”会更回得智能和清楚，但“后缀规则”可以用来保
证我们Makefile的兼容性。
我们了解了“隐含规则”，可以让其为我们更好的服务，也会让我们知道一些“约定俗成”了的东西，而不至于使得我们在运行Makefile时出现一些我们觉得莫名其妙的东西。当
然，任何事物都是矛盾的，水能载舟，亦可覆舟，所以，有时候“隐含规则”也会给我们造成不小的麻烦。只有了解了它，我们才能更好地使用它。


一、使用隐含规则


如果要使用隐含规则生成你需要的目标，你所需要做的就¡式中，我们把"%"所匹配的内容叫做"茎"，例如"%.c"所匹配的文件"test.c"中"test"就是"茎"。因为在目标和依赖目标中同时有"%"时，依赖目标的"茎"会传给目标，当做目标中的"茎"。

当一个模式匹配包含有斜杠（实际也不经常包含）的文件时，那么在进行模式匹配时，目录部分会首先被移开，然后进行匹配，成功后，再把目录加回去。在进行"茎"的传递时，我们需要知道这个步骤。例如有一个模式"e%t"，文件"src/eat" 匹配于该模式，于是"src/a"就是其"茎"，如果这个模式定义在依赖目标中，而被依赖于这个模式的目标中又有个模式"c%r"，那么，目标就是"src/car"。（"茎"被传递）

5、重载内建隐含规则


你可以重载内建的隐含规则（或是定义一个全新的），例如你可以重新构造和内建隐含规则不同的命令，如：


%.o : %.c
$(CC) -c $(CPPFLAGS) $(CFLAGS) -D$(date)


你可以取消内建的隐含规则，只要不在后面写命令就行。如：


%.o : %.s


同样，你也可以重新定义一个全新的隐含规则，其在隐含规则中的位置取决于你在哪里写下这个规则。朝前的位置就靠前。


六、老式风格的"后缀规则"


后缀规则是一个比较老式的定义隐含规则的方法。后缀规则会被模式规则逐步地取代。因为模式规则更强更清晰。为了和老版本的Makefile兼容，GNU make同样兼容于这些东西。后缀规则有两种方式："双后缀"和"单后缀"。

双后缀规则定义了一对后缀：目标文件的后缀和依赖目标（源文件）的后缀。如".c.o"相当于"%o : %c"。单后缀规则只定义一个后缀，也就是源文件的后缀。如".c"相当于"% : %.c"。


后缀规则中所定义的后缀应该是make所认识的，如果一个后缀是make所认识的，那么这个规则就是单后缀规则，而如果两个连在一起的后缀都被make所认识，那就是双后缀规则。例如：".c"和".o"都是make所知道。因而，如果你定义了一个规则是".c.o"那么其就是双后缀规则，意义就是".c" 是源文件的后缀，".o"是目标文件的后缀。如下示例：


.c.o:
$(CC) -c $(CFLAGS) $(CPPFLAGS) -o $@ $<


后缀规则不允许任何的依赖文件，如果有依赖文件的话，那就不是后缀规则，那些后缀统统被认为是文件名，如：


.c.o: foo.h
$(CC) -c $(CFLAGS) $(CPPFLAGS) -o $@ $<


这个例子，就是说，文件".c.o"依赖于文件"foo.h"，而不是我们想要的这样：

%.o: %.c foo.h
$(CC) -c $(CFLAGS) $(CPPFLAGS) -o $@ $<


后缀规则中，如果没有命令，那是毫无意义的。因为他也不会移去内建的隐含规则。


而要让make知道一些特定的后缀，我们可以使用伪目标".SUFFIXES"来定义或是删除，如：


.SUFFIXES: .hack .win


把后缀.hack和.win加入后缀列表中的末尾。


.SUFFIXES: # 删除默认的后缀
.SUFFIXES: .c .o .h # 定义自己的后缀


先清楚默认后缀，后定义自己的后缀列表。


make的参数"-r"或"-no-builtin-rules"也会使用得默认的后缀列表为空。而变量"SUFFIXE"被用来定义默认的后缀列表，你可以用".SUFFIXES"来改变后缀列表，但请不要改变变量"SUFFIXE"的值。


七、隐含规则搜索算法

比如我们有一个目标叫 T。下面是搜索目标T的规则的算法。请注意，在下面，我们没有提到后缀规则，原因是，所有的后缀规则在Makefile被载入内存时，会被转换成模式规则。如果目标是"archive(member)"的函数库文件模式，那么这个算法会被运行两次，第一次是找目标T，如果没有找到的话，那么进入第二次，第二次会把"member"当作T来搜索。


1、把T的目录部分分离出来。叫D，而剩余部分叫N。（如：如果T是"src/foo.o"，那么，D就是"src/"，N就是"foo.o"）

2、创建所有匹配于T或是N的模式规则列表。

3、如果在模式规则列表中有匹配所有文件的模式，如"%"，那么从列表中移除其它的模式。

4、移除列表中没有命令的规则。

5、对于第一个在列表中的模式规则：


1）推导其"茎"S，S应该是T或是N匹配于模式中"%"非空的部分。

2）计算依赖文件。把依赖文件中的"%"都替换成"茎"S。如果目标模式中没有包含斜框字符，而把D加在第一个依赖文件的开头。

3）测试是否所有的依赖文件都存在或是理当存在。（如果有一个文件被定义成另外一个规则的目标文件，或者是一个显式规则的依赖文件，那么这个文件就叫"理当存在"）

4）如果所有的依赖文件存在或是理当存在，或是就没有依赖文件。那么这条规则将被采用，退出该算法。

6、如果经过第5步，没有模式规则被找到，那么就做更进一步的搜索。对于存在于列表中的第一个模式规则：

1）如果规则是终止规则，那就忽略它，继续下一条模式规则。

2）计算依赖文件。（同第5步）

3）测试所有的依赖文件是否存在或是理当存在。

4）对于不存在的依赖文件，递归调用这个算法查找他是否可以被隐含规则找到。

5）如果所有的依赖文件存在或是理当存在，或是就根本没有依赖文件。那么这条规则被采用，退出该算法。

7、如果没有隐含规则可以使用，查看".DEFAULT"规则，如果有，采用，把".DEFAULT"的命令给T使用。



一旦规则被找到，就会执行其相当的命令，而此时，我们的自动化变量的值才会生成。





使用make更新函数库文件
———————————


函数库文件也就是对Object文件（程序编译的中间文件）的打包文件。在Unix下，一般是由命令"ar"来完成打包工作。


一、函数库文件的成员


一个函数库文件由多个文件组成。你可以以如下格式指定函数库文件及其组成：


archive(member)


这个不是一个命令，而一个目标和依赖的定义。一般来说，这种用法基本上就是为了"ar"命令来服务的。如：

foolib(hack.o) : hack.o
ar cr foolib hack.o


如果要指定多个member，那就以空格分开，如：


foolib(hack.o kludge.o)


其等价于：


foolib(hack.o) foolib(kludge.o)


你还可以使用Shell的文件通配符来定义，如：

foolib(*.o)


二、函数库成员的隐含规则


当 make搜索一个目标的隐含规则时，一个特殊的特性是，如果这个目标是"a(m)"形式的，其会把目标变成"(m)"。于是，如果我们的成员是"%.o" 的模式定义，并且如果我们使用"make foo.a(bar.o)"的形式调用Makefile时，隐含规则会去找"bar.o"的规则，如果没有定义bar.o的规则，那么内建隐含规则生效，make会去找bar.c文件来生成bar.o，如果找得到的话，make执行的命令大致如下：


cc -c bar.c -o bar.o
ar r foo.a bar.o
rm -f bar.o


还有一个变量要注意的是"$%"，这是专属函数库文件的自动化变量，有关其说明请参见"自动化变量"一节。



三、函数库文件的后缀规则


你可以使用"后缀规则"和"隐含规则"来生成函数库打包文件，如：


.c.a:
$(CC) $(CFLAGS) $(CPPFLAGS) -c $< -o $*.o
$(AR) r $@ $*.o
$(RM) $*.o


其等效于：


(%.o) : %.c
$(CC) $(CFLAGS) $(CPPFLAGS) -c $< -o $*.o
$(AR) r $@ $*.o
$(RM) $*.o


四、注意事项


在进行函数库打包文件生成时，请小心使用make的并行机制（"-j"参数）。如果多个ar命令在同一时间运行在同一个函数库打包文件上，就很有可以损坏这个函数库文件。所以，在make未来的版本中，应该提供一种机制来避免并行操作发生在函数打包文件上。
但就目前而言，你还是应该不要尽量不要使用"-j"参数。



后序
——


终于到写结束语的时候了，以上基本上就是GNU make的Makefile的所有细节了。其它的产商的make基本上也就是这样的，无论什么样的make，都是以文件的依赖性为基础的，其基本是都是遵循一个标准的。这篇文档中80%的技术细节都适用于任何的make，我猜测"函数"那一章的内容可能不是其它make所支持的，而隐含规则方面，我想不同的make会有不同的实现，我没有精力来查看GNU的make和VC的nmake、BCB的make，或是别的UNIX下的make有些什么样的差别，一是时间精力不够，二是因为我基本上都是在Unix下使用make，以前在SCO Unix和IBM的AIX，现在在Linux、Solaris、HP-UX、AIX和Alpha下使用，Linux和Solaris下更多一点。不过，我可以肯定的是，在Unix下的make，无论是哪种平台，几乎都使用了Richard Stallman开发的make和cc/gcc的编译器，而且，基本上都是GNU的make（公司里所有的UNIX机器上都被装上了GNU的东西，所以，使用GNU的程序也就多了一些）。GNU的东西还是很不错的，特别是使用得深了以后，越来越觉得GNU的软件的强大，也越来越觉得GNU的在操作系统中（主要是Unix，甚至Windows）"杀伤力"。


对于上述所有的make的细节，我们不但可以利用make这个工具来编译我们的程序，还可以利用make来完成其它的工作，因为规则中的命令可以是任何Shell之下的命令，所以，在Unix下，你不一定只是使用程序语言的编译器，你还可以在Makefile中书写其它的命令，如：tar、awk、mail、sed、cvs、compress、ls、rm、yacc、rpm、 ftp……等等，等等，来完成诸如"程序打包"、"程序备份"、"制作程序安装包"、"提交代码"、"使用程序模板"、"合并文件"等等五花八门的功能，文件操作，文件管理，编程开发设计，或是其它一些异想天开的东西。比如，以前在书写银行交易程序时，由于银行的交易程序基本一样，就见到有人书写了一些交易的通用程序模板，在该模板中把一些网络通讯、数据库操作的、业务操作共性的东西写在一个文件中，在这些文件中用些诸如"@@@N、###N"奇怪字串标注一些位置，然后书写交易时，只需按照一种特定的规则书写特定的处理，最后在make时，使用awk和sed，把模板中的"@@@N、###N"等字串替代成特定的程序，形成C文件，然后再编译。这个动作很像数据库的"扩展C"语言（即在C语言中用"EXEC　SQL"的样子执行SQL语句，在用 cc/gcc编译之前，需要使用"扩展C"的翻译程序，如cpre，把其翻译成标准C）。如果
你在使用make时有一些更为绝妙的方法，请记得告诉我啊。

回头看看整篇文档，不觉记起几年前刚刚开始在Unix下做开发的时候，有人问我会不会写Makefile时，我两眼发直，根本不知道在说什么。一开始看到别人在vi中写完程序后输入"!make"时，还以为是vi的功能，后来才知道有一个Makefile在作怪，于是上网查啊查，那时又不愿意看英文，发现就根本没有中文的文档介绍Makefile，只得看别人写的Makefile，自己瞎碰瞎搞才积累了一点知识，但在很多地方完全是知其然不知所以然。后来开始从事UNIX下产品软件的开发，看到一个400人年，近200万行代码的大工程，发现要编译这样一个庞然大物，如果没有Makefile，那会是多么恐怖的一样事啊。于是横下心来，狠命地读了一堆英文文档，才觉得对其掌握了。但发现目前网上对Makefile介绍的文章还是少得那么的可怜，所以想写这样一篇文章，共享给大家，希望能对各位有所帮助。


现在我终于写完了，看了看文件的创建时间，这篇技术文档也写了两个多月了。发现，自己知道是一回事，要写下来，跟别人讲述又是另外一回事，而且，现在越来越没有时间专研技术细节，所以在写作时，发现在阐述一些细节问题时很难做到严谨和精练，而且对先讲什么后讲什么不是很清楚，所以，还是参考了一些国外站点上的资料和题纲，以及一些技术书籍的语言风格，才得以完成。整篇文档的提纲是基于GNU的 Makefile技术手册的提纲来书写的，并结合了自己的工作经验，以及自己的学习历程。因为从来没有写过这么长，这么细的文档，所以一定会有很多地方存在表达问题，语言歧义或是错误。因些，我迫切地得等待各位给我指证和建议，以及任何的反馈。

最后，还是利用这个后序，介绍一下自己。我目前从事于所有Unix平台下的软件研发，主要是做分布式计算/网格计算方面的系统产品软件，并且我对于下一代的计算机革命——网格计算非常地感兴趣，对于分布式计算、P2P、Web Service、J2EE技术方向也很感兴趣，同时，对于项目实施、团队管理、项目管理也小有心得，希望同样和我战斗在“技术和管理并重”的阵线上的年轻一代，能够和我多多地交流。我的MSN是：haoel@hotmail.com（常用），QQ是：753640（不常用）。（注：请勿给我MSN的邮箱发信，由于hotmail的垃圾
邮件导致我拒收这个邮箱的所有来信）


我欢迎任何形式的交流，无论是讨论技术还是管理，或是其它海阔天空的东西。除了政治和娱乐新闻我不关心，其它只要积极向上的东西我都欢迎！


最最后，我还想介绍一下make程序的设计开发者。

首当其冲的是： Richard Stallman

开源软件的领袖和先驱，从来没有领过一天工资，从来没有使用过Windows操作系统。对于他的事迹和他的软件以及他的思想，我无需说过多的话，相信大家对这个人并不比我陌生，这是他的主页：http://www.stallman.org/ 。



第二位是：Roland McGrath


个人主页是：http://www.frob.com/~roland/ ，下面是他的一些事迹：

1） 合作编写了并维护GNU make。
2） 和Thomas Bushnell一同编写了GNU Hurd。

3） 编写并维护着GNU C library。

4） 合作编写并维护着部分的GNU Emacs。


在此，向这两位开源项目的斗士致以最真切的敬意。



# paper
https://www.doc88.com/p-9542603342849.html
https://www.doc88.com/p-672124840657.html
https://www.doc88.com/p-7486313689894.html
https://www.doc88.com/p-513670289185.html
https://www.doc88.com/p-3069517569444.html
https://www.doc88.com/p-3981243160490.html
https://www.doc88.com/p-798379669786.html



# every day's work
      #=> 2019-5-7
    1 translate the swap

  #=> 2019-4-24 Tue:
    1 Intergration of program of TC forecast *
    2 data fusion of cloud top wind **
    3 tool box of fortran HDF and NC *
    4 apply driver lisence *
    5 TCPIE position estimation validation ****
    6 let CMA check the algorithm documents **
    7 prepare the report for FANG ***
    8 paticipating the meetting with CMA (at 9:40) %
  #=> 2019-4-23 Mon:
    1 Intergration of program of TC forecast *
      "not finished"
    2 data fusion of cloud top wind **
      "not finished"
    3 tool box of fortran HDF and NC *
      "not finished"
    4 apply driver lisence *
      "not finished"
    5 TCPIE position estimation validation ****
      "not finished"
    6 let CMA check the algorithm documents **
      "not finished"
    7 prepare the report for FANG ***
      "not finished"
  #=> 2019-4-22 Mon:
    1 test the program of TC forecast
      "finished"
    2 data fusion of cloud top wind
      "not finished"
    3 tool box of fortran HDF and NC
      "not finished"
    4 apply driver lisence
      "not finished"
    5 TCPIE position estimation validation
      "not finished"
    6 let CMA check the algorithm documents
      "not finished"
    7 report to FANG
      "on Thursday"
  #=> 2019-4-20 Sat:
    1 test the program of TC forecast
      "not finished"
    2 data fusion of cloud top wind
      "not finished"
    3 tool box of fortran HDF and NC
      "not finished"
    4 apply driver lisence
      "not finished"
  #=> 2019-4-19 Fri:
    1 finish the PPT for the wind monitoring, position and instensity esitmation of TC system
      "finished"
    2 finish the wind program for ERA data
      "not finished"
    3 finish the position monitoring validation
      "not finished"
    4 prepare the matiral for the driver lisence
      "not finished"
    
# pbs links
        https://www.youtube.com/watch?v=FMb7Z2C1Tqw

    https://www.youtube.com/watch?v=ouq9FxGks48
    https://www.youtube.com/watch?v=WBQ4i9E_5RY
    https://www.youtube.com/watch?v=0Y8BTTEwWyw
    https://www.youtube.com/watch?v=fFOSUBFhwW4
    https://www.youtube.com/watch?v=B2NEBEwUJSc
    https://www.youtube.com/watch?v=C7O1Xns1jNw

https://www.youtube.com/watch?v=n_0Rv6l9ZWs
https://www.youtube.com/watch?v=-fVIZAELvdA
https://www.youtube.com/watch?v=ZsLgDOZqRN0
https://www.youtube.com/watch?v=9R0MYU35KPQ
https://www.youtube.com/watch?v=m5ljhHsKDec
https://www.youtube.com/watch?v=jaN8GP0A1to
https://www.youtube.com/watch?v=6PWz6yEGPlg
https://www.youtube.com/watch?v=6b4VLMlI9Uw
https://www.youtube.com/watch?v=r5UouaCsZGc
https://www.youtube.com/watch?v=JhW7fw8a0Lc
https://www.youtube.com/watch?v=O7us1yywij4
https://www.youtube.com/watch?v=iy-CSdpZmLw
https://srv67.clipconverter.cc/download/y9jKb4CCt4qwZ29omZSVb3Bg5KWmqW9v4pSYbnJgnWVta260qc%2FMqHyf1qiZpa2d2A%3D%3D/PBS%20NewsHour%20full%20episode%20September%2010%2C%202019.mp3

https://www.youtube.com/watch?v=AVNxw1gnC68
https://www.youtube.com/watch?v=4LpjwgqvR2E

https://www.youtube.com/watch?v=0znwu7CVlZg
https://www.youtube.com/watch?v=Tcj93BO07Ps
https://www.youtube.com/watch?v=_RpTFmKvH60
https://www.youtube.com/watch?v=qZuVzT7yMjw
https://www.youtube.com/watch?v=YLkwRtySBww
https://www.youtube.com/watch?v=CjYDlpqF7hk
https://www.youtube.com/watch?v=ClSMoc9Hfxo
https://www.youtube.com/watch?v=1z7i3q2JJJE
https://www.youtube.com/watch?v=F9Tlm8oLOXk
https://www.youtube.com/watch?v=uWTbAOTjsEg
https://www.youtube.com/watch?v=6HlsK5TemjM
https://www.youtube.com/watch?v=9Kqkdz3Tg5Q
https://www.youtube.com/watch?v=NBM6-y0afBw

https://www.youtube.com/watch?v=2FULCIiLeas
https://www.youtube.com/watch?v=I0XZ4XhKV5o
https://www.youtube.com/watch?v=WMCtKfko89M
https://www.youtube.com/watch?v=h9EWfHZCw5g
https://www.youtube.com/watch?v=acGhHjp65uY
https://www.youtube.com/watch?v=0RPeKmrGKsc
https://www.youtube.com/watch?v=7jjdi0-rT2Q
https://www.youtube.com/watch?v=m1BrnlaXdyY
https://www.youtube.com/watch?v=3BPBHRNhdfI
https://www.youtube.com/watch?v=UmNcRJ--Cwo
https://www.youtube.com/watch?v=qZuVzT7yMjw
https://www.youtube.com/watch?v=3nglzG-x_6A

https://www.youtube.com/watch?v=bdn2JpBNJSw
https://www.youtube.com/watch?v=EovAAvoVEVI
https://www.youtube.com/watch?v=1K5xqPUcvIA
https://www.youtube.com/watch?v=mTavCq-4GmY

1025
https://www.youtube.com/watch?v=OV4xdHRGgNQ
https://www.youtube.com/watch?v=cuvuiDnlMsg
1027
https://www.youtube.com/watch?v=SBHMo8PHbzg
https://www.youtube.com/watch?v=9n_uRv9T7tU
https://www.youtube.com/watch?v=kSFRq5uH6_M
1030
https://www.youtube.com/watch?v=UcCC3aggiw0
1031
https://www.youtube.com/watch?v=d8hoD4_QWGQ
1101
https://www.youtube.com/watch?v=6dmV4KO5lOU
https://www.youtube.com/watch?v=1l3Aw5nKGcU
1103
https://www.youtube.com/watch?v=PhUfX2z9cOU
1104
https://www.youtube.com/watch?v=2z-84zoO2TY
1105
https://www.youtube.com/watch?v=lqjluODT0rw
1106
https://www.youtube.com/watch?v=c_RAFFhClqM



1107
https://www.youtube.com/watch?v=6oAZSg-HIo4
https://www.youtube.com/watch?v=xK7qv5lK51k
https://www.youtube.com/watch?v=hXAcFGWPbIM
https://www.youtube.com/watch?v=pxrX5_UJsfY
1111
https://www.youtube.com/watch?v=D6yVNHooZ9A
https://www.youtube.com/watch?v=O0W_2iScvZ0
https://www.youtube.com/watch?v=d4VJMqRGbDo
https://www.youtube.com/watch?v=WC_yFu2M5cE
https://www.youtube.com/watch?v=9k6IDtSuzzk
https://www.youtube.com/watch?v=Sok0GANtUdQ
https://www.youtube.com/watch?v=BDvzixQvG8s
https://www.youtube.com/watch?v=1eRJX9ixde4
https://www.youtube.com/watch?v=BH_c9VEmBm4
1120
https://www.youtube.com/watch?v=YmN5yVyeUzo

https://www.youtube.com/watch?v=1Q3bmrv-Zno
https://www.youtube.com/watch?v=T7KeAXys6l4
https://www.youtube.com/watch?v=jzPR95Exe-g

https://www.youtube.com/watch?v=ZDIyAy9Pckg
https://www.youtube.com/watch?v=noRjWRdzAe8
https://www.youtube.com/watch?v=yTiy41veZXM
https://www.youtube.com/watch?v=O4_5HyA_QDQ
https://www.youtube.com/watch?v=wYLwjfcJISI
https://www.youtube.com/watch?v=nAWUg_TtSxg
https://www.youtube.com/watch?v=pquk7GrkP1k
https://www.youtube.com/watch?v=mL1mipSLp6o
https://www.youtube.com/watch?v=dVe0fTUAnA8

https://www.youtube.com/watch?v=PhpF4aTQo88
https://www.youtube.com/watch?v=5TbDZvvzNCI
https://www.youtube.com/watch?v=hx896THLKs8
https://www.youtube.com/watch?v=3JmvBlGeEjA
https://www.youtube.com/watch?v=5rjTvLjj43U
https://www.youtube.com/watch?v=2IVqc87qlA8
https://www.youtube.com/watch?v=_bHni89uBYE
1210
https://www.youtube.com/watch?v=N61T6rIsoKk
https://www.youtube.com/watch?v=qgQn9EATl_Y
https://www.youtube.com/watch?v=8Tj5lZX9QY8

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=2ahUKEwiQkuvU0bznAhXPc94KHTecCTIQuAIwAHoECAQQBg&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DzeAhFuuSlQ0&usg=AOvVaw3DuBBBoitW60smqaN0Mf9E

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=2&cad=rja&uact=8&ved=2ahUKEwiXy73w0bznAhWEc3AKHa63DmMQtwIwAXoECAoQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3D5KAa9nSg6dc&usg=AOvVaw0oyRoNLgjxyr0Izwm_xe56

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=3&cad=rja&uact=8&ved=2ahUKEwiXy73w0bznAhWEc3AKHa63DmMQtwIwAnoECAkQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DAwhYPHnfCHc&usg=AOvVaw1vfq4Q1JDFu0SQVAjPBuyc

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=2ahUKEwiHrrb90bznAhUJE4gKHZafBNAQtwIwAHoECAMQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DjIF24V_S7sQ&usg=AOvVaw3S6hGXCMo6YdnsypLkLGc9

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=2ahUKEwiB0YmD0rznAhWJHXAKHREnARUQtwIwAHoECAMQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DQ1FIOw8JqdE&usg=AOvVaw1LIb_B81nd71dk6w0hfQim

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=2ahUKEwillfSI0rznAhXBE4gKHdDzCysQtwIwAHoECAsQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3D3Tg-tnQZ6OY&usg=AOvVaw3aVPG9u4J9DYurCe6wNHCq

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=2ahUKEwiehqKP0rznAhUEUd4KHaYeCMMQtwIwAHoECAsQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3Dc2tovUvZuWY&usg=AOvVaw1WzI3NL7VbZ_7tUHJ7barf

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=2ahUKEwjXjdyT0rznAhWOfd4KHdByAT0QtwIwAHoECAYQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DnUWyZ9dS_w0&usg=AOvVaw3KJfC5C3sgjfMV2svGUuHs

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=2ahUKEwjbpfyX0rznAhUYH3AKHXrJDkkQtwIwAHoECAMQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DpYPWWbq5yT4&usg=AOvVaw0HlsbE0mhwLk5OVHECw1XL

1.15
https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=2ahUKEwi9w4qe0rznAhWWMd4KHfaqA-UQtwIwAHoECAsQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DHBaWZL6Q3LM&usg=AOvVaw1g_MAHAL1bXBSsncX4679_

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=2&cad=rja&uact=8&ved=2ahUKEwi9w4qe0rznAhWWMd4KHfaqA-UQtwIwAXoECAoQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DeLQOqeRg6os&usg=AOvVaw3gBHchTQcGW-JZ0aY8fcZV

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=2ahUKEwiEs_Gl0rznAhWI-2EKHZjcCvgQtwIwAHoECAUQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3Dqr4T3vwAoW0&usg=AOvVaw0KMQP6mHNjOQW05xz5iDAW

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=2&cad=rja&uact=8&ved=2ahUKEwj3ybOr0rznAhWWPXAKHX73BywQFjABegQIBRAB&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3Duh7NMkWvqvA&usg=AOvVaw21xWa1HEogCompxyBSQt8O


https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=2ahUKEwi2wbSz0rznAhVDE4gKHZnQBS0QtwIwAHoECAsQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DHZO14jobzl0&usg=AOvVaw1mQmjs3ZmQ1aaY_yT1goxn

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=2ahUKEwiw4Ia50rznAhUCM94KHVanDhEQtwIwAHoECAsQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DrXZ1CGSAIgU&usg=AOvVaw2tcTjbj4tKho9nGDcO3Ap8

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=2ahUKEwj04Pq90rznAhUMA4gKHQ9wAfsQtwIwAHoECAsQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DZsluK-qVG0E&usg=AOvVaw2neAWOM-e4GauEfQhQSSq-

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=2ahUKEwjG8ZzD0rznAhWW7WEKHabpD_IQtwIwAHoECAUQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3D8qWnOKy35h0&usg=AOvVaw12ne7oblW8OLX5qN7rpgXz

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=2&cad=rja&uact=8&ved=2ahUKEwjG8ZzD0rznAhWW7WEKHabpD_IQtwIwAXoECAsQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3De-gCyBUVvwk&usg=AOvVaw2LiIjO0vjE9sbxC4hHegJE

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=2ahUKEwje9Yfj0rznAhXIad4KHQZfCxQQtwIwAHoECAYQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3D5_Mz7Z8C8AQ&usg=AOvVaw0dKxZ5PWE0MwIkuH71vMPn

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=2ahUKEwidsebn0rznAhVSFogKHbZ7C_wQtwIwAHoECAQQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3Dr3DKj5KT5Ts&usg=AOvVaw3Jj95wep7JqzhMiWifU4H3

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=2ahUKEwjExb7s0rznAhWK7WEKHVn-DNIQtwIwAHoECAYQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DXDL_FYdywSM&usg=AOvVaw325tIaaG5jYuntu1ZggJD8

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=3&cad=rja&uact=8&ved=2ahUKEwjExb7s0rznAhWK7WEKHVn-DNIQtwIwAnoECAoQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3D9KQQU969d7Q&usg=AOvVaw3wOl10CX_kKXDZaEh_XHsj

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=4&cad=rja&uact=8&ved=2ahUKEwjExb7s0rznAhWK7WEKHVn-DNIQtwIwA3oECAkQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DWmBfcgBCkzg&usg=AOvVaw2MW2J6fex_DWdHI2IMiOb1

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=2ahUKEwiKxs_30rznAhUKc3AKHf-xDwoQtwIwAHoECAQQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3D6AT_GqUGLTQ&usg=AOvVaw1sN8R1emVPlVDKDxJugkju

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=5&cad=rja&uact=8&ved=2ahUKEwiKxs_30rznAhUKc3AKHf-xDwoQtwIwBHoECAgQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DvFAdrhw4YVI&usg=AOvVaw23tsQK_TRQOz00ZCreSgYa

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=4&cad=rja&uact=8&ved=2ahUKEwiKxs_30rznAhUKc3AKHf-xDwoQtwIwA3oECAoQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DxK1QK2C0xpQ&usg=AOvVaw0PBoYnj6SnC-cetTFWXJby

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=2ahUKEwj68buB07znAhWEMN4KHaWRCcsQtwIwAHoECAYQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DSJT6L-wDBhc&usg=AOvVaw39aMo4Et92cyuWjEpiB1e8

https://www.youtube.com/watch?v=Pl3DApEF6Hc

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=3&cad=rja&uact=8&ved=2ahUKEwj9yMCF07znAhWNdd4KHXUNDKgQtwIwAnoECAQQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DW6ecaQMjONA&usg=AOvVaw3LbA0krFllyWghPMuq8g3p

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=5&cad=rja&uact=8&ved=2ahUKEwj9yMCF07znAhWNdd4KHXUNDKgQtwIwBHoECAsQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3Dlh17n-zYXKo&usg=AOvVaw3z-psyXhJ4LVF3CBQUqZCl

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=2&cad=rja&uact=8&ved=2ahUKEwj9yMCF07znAhWNdd4KHXUNDKgQtwIwAXoECAwQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3D1z8ImO_EDDw&usg=AOvVaw2J03IrppRaXRZUqbwGF5s6



1-16
https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=2&cad=rja&uact=8&ved=2ahUKEwiX9P_cgdnnAhXVBIgKHRdfDw8QtwIwAXoECAoQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DOsdYq3b1gPU&usg=AOvVaw3h4W31-_CWerJV_qBTVknd
1-19
https://www.youtube.com/watch?v=HZO14jobzl0

2-16
https://www.youtube.com/watch?v=OsdYq3b1gPU

1-6
https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=2ahUKEwiuseKC5OTnAhUiL6YKHVAMDtsQuAIwAHoECAcQBA&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DDohxnW-jGEU&usg=AOvVaw3yR3SpM0Pf-xoeTsHz16eP
1-7
https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=2&cad=rja&uact=8&ved=2ahUKEwjmn_WP5eTnAhXCy4sBHXarBsAQtwIwAXoECAsQAQ&url=
https://www.youtube.com/watch?v=VdLpm-paAMI
&usg=AOvVaw1IX8g8xptYUAuOqamUjJ65
1-9 1-11 1-13 1-15

1-9
https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=2ahUKEwjGisP3vurnAhUMHXAKHcBkBgkQtwIwAHoECAYQAQ&url=
https://www.youtube.com/watch?v=t3bC705592k
&usg=AOvVaw2LUSmAbQhiU1x3YA6bbPTU

1-16
https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=3&cad=rja&uact=8&ved=2ahUKEwiF6-zh4uTnAhUWA4gKHSVlBxgQtwIwAnoECAcQAQ&url=i
https://www.youtube.com/watch?v=aUto_Oeytbo

1-9 1-11 1-13 1-15 1-17 1-23

1-11
https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=7&cad=rja&uact=8&ved=2ahUKEwiAq-SfvurnAhXm-GEKHWqMBc8QtwIwBnoECAcQAQ&url=
https://www.pbs.org/newshour/show/january-11-2020-pbs-newshour-weekend-full-episode
&usg=AOvVaw1ofrb7cDCVnC-bMCh1L8Of
https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=12&cad=rja&uact=8&ved=2ahUKEwiDjcCzvurnAhVOIIgKHYV8ACQ4ChC3AjABegQIChAB&url=
https://www.kcts9.org/show/newshour/episode/january-11-2020-pbs-newshour-weekend-full-episode-1578784449i
&usg=AOvVaw2n_XRuyTC_-GBwtsi-k8pQ

1-17
https://www.youtube.com/watch?v=MX0ULguviQo

1-15
https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=2ahUKEwjj98GEvernAhWWZt4KHSTYBOIQtwIwAHoECAYQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DIouc0aQTGDo&usg=AOvVaw0srpTuqJY118NTsKcuqqeK
https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=2&cad=rja&uact=8&ved=2ahUKEwjj98GEvernAhWWZt4KHSTYBOIQtwIwAXoECAkQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DDm11uH6UzWE&usg=AOvVaw0srQ0QrL2USRbQcoZuiNre
https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=2&cad=rja&uact=8&ved=2ahUKEwjj98GEvernAhWWZt4KHSTYBOIQtwIwAXoECAkQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DDm11uH6UzWE&usg=AOvVaw0srQ0QrL2USRbQcoZuiNre

1-13
https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=2ahUKEwiT5sGkvOrnAhVOFogKHRgCCAUQtwIwAHoECAMQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3Dy4Mw0Tzd4wM&usg=AOvVaw04Zly9s_lOEHYIJZ4EZ_Y6

https://www.youtube.com/watch?v=7VI4K1OBcqQ
https://www.youtube.com/watch?v=Tg1QdNxYz2M
https://www.youtube.com/watch?v=rFk6h9YXHvQ


21
https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=3&cad=rja&uact=8&ved=2ahUKEwi9zsqcwOfnAhVOUd4KHY1jBQsQtwIwAnoECAcQAQ&url=
https://www.youtube.com/watch?v=akVRaDZYLuw
&usg=AOvVaw1amAuiYo-SCIranNhw5wOJ

22
https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=4&cad=rja&uact=8&ved=2ahUKEwi9zsqcwOfnAhVOUd4KHY1jBQsQtwIwA3oECAwQAQ&url=
https://www.youtube.com/watch?v=fTM_w2s18vI
&usg=AOvVaw2Ia_4I9iXwHYzVOxj8X6DG

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=6&cad=rja&uact=8&ved=2ahUKEwj85aqXuurnAhXYc3AKHVDlD2YQtwIwBXoECAoQAQ&url=
https://www.youtube.com/watch?v=3KEqHXyi2lY
&usg=AOvVaw1coObxPWdUGjDmYtApqyZO

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=7&cad=rja&uact=8&ved=2ahUKEwjlmqTVuurnAhUPUd4KHffTAKIQFjAGegQICBAB&url=
https://www.youtube.com/watch?v=qSoYZyfIE-A
&usg=AOvVaw04jAF_3r-QCQ1jd7vp369U


https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=6&cad=rja&uact=8&ved=2ahUKEwiWwszegO3nAhUMyosBHfJ7Aw4QtwIwBXoECAsQAQ&url=
https://www.youtube.com/watch?v=3KEqHXyi2lY
&usg=AOvVaw1coObxPWdUGjDmYtApqyZO
https://www.youtube.com/watch?v=YdntD3R18Ok


26
https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=3&cad=rja&uact=8&ved=2ahUKEwj69pPfoffnAhUFEqYKHSjwBuYQtwIwAnoECAQQAQ&url=
https://www.youtube.com/watch?v=rjhSOZmc7rY
&usg=AOvVaw0LohA-RYy6YPX1y51mohCl
https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=2&cad=rja&uact=8&ved=2ahUKEwj69pPfoffnAhUFEqYKHSjwBuYQtwIwAXoECAwQAQ&url=
https://www.youtube.com/watch?v=oW4_tdmIXyA
&usg=AOvVaw1wbwp0XAgm-wx2KvnwAZMb

3-2
https://www.youtube.com/watch:v=BwsxT3G-9v0

3-1
https://www.youtube.com/watch:v=Ew1SBptqoGc

2-28
https://www.youtube.com/watch:v=z5sNSwkmTqQ

2-29
https://www.youtube.com/watch:v=aXGywXVEEGQ

2-25
https://www.youtube.com/watch?v=-69Fra-sN9k

3-3
https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=2ahUKEwiu-_fawYLoAhVRyosBHUxLCmYQtwIwAHoECAsQAQ&url=
https://www.youtube.com/watch?v=RkAJnUos97g
&usg=AOvVaw1gJ_mKv8u1OOSR8VqzKLvN
https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=5&cad=rja&uact=8&ved=2ahUKEwiu-_fawYLoAhVRyosBHUxLCmYQFjAEegQIAhAB&url=https%3A%2F%2Fwww.youtube.com%2Fembed%2FBUAqCanBxxM%3Fiv_load_policy%3D3&usg=AOvVaw2HCKK-z23cCCJhL3SW9IFz

3-4
https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=2ahUKEwjsi6rFwYLoAhWvBKYKHeVlCYIQtwIwAHoECAUQAQ&url=
https://www.youtube.com/watch?v=cG0OAJWTlKw
&usg=AOvVaw3k7YgSgJwiuWxSE9MlOk7S

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=14&cad=rja&uact=8&ved=2ahUKEwjonqGDsYroAhXJad4KHcDCCcMQtwIwDXoECAkQAQ&url=
https://www.youtube.com/watch?v=kTH6FsYJc0c
&usg=AOvVaw345k4ZS8oH-bXMFHzXVW2-

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=13&cad=rja&uact=8&ved=2ahUKEwjonqGDsYroAhXJad4KHcDCCcMQtwIwDHoECAcQAQ&url=
https://www.youtube.com/watch?v=SpbdUnBHxjA
&usg=AOvVaw3_YV6cXZBfsCLMIolzN7OX

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=16&cad=rja&uact=8&ved=2ahUKEwjonqGDsYroAhXJad4KHcDCCcMQtwIwD3oECAgQAQ&url=
https://www.youtube.com/watch?v=RC6AsvrrKks
&usg=AOvVaw1Z5yoA_F7_QaD2A3mcvO2P

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=6&cad=rja&uact=8&ved=2ahUKEwjor_2DxozoAhW7IqYKHUZAApcQtwIwBXoECAcQAQ&url=
https://www.youtube.com/watch?v=VlykIvArSoI
&usg=AOvVaw11rV_fMVS20DUvxwhtwgey

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=2ahUKEwil-dXGy5HoAhXUfXAKHWepCIQQtwIwAHoECAQQAQ&url=
https://www.youtube.com/watch?v=vvJJbwJJx5A
&usg=AOvVaw1dM1iuP9wlyesot_EHBRhi

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=3&cad=rja&uact=8&ved=2ahUKEwia552vy5HoAhXJAYgKHRJ2ARcQtwIwAnoECAcQAQ&url=
https://www.youtube.com/watch?v=4lYEp-IQ030
&usg=AOvVaw3QeuAZB8hC0XMkqqJ6lcqE

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=5&cad=rja&uact=8&ved=2ahUKEwjisIzL65foAhVNIqYKHUn5C8QQtwIwBHoECAwQAQ&url=
https://www.youtube.com/watch?v=1B1Y2kUcA4g
&usg=AOvVaw05ctXEh9i2SXZ59_KQ0Phy

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=2ahUKEwiQiJ2n7JfoAhW9JaYKHQQZCSgQtwIwAHoECAUQAQ&url=
https://www.youtube.com/watch?v=8FQ9tRZa9hQ
&usg=AOvVaw1PgvhhuWmtMKEc_r_xHVCR


https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=9&cad=rja&uact=8&ved=2ahUKEwjc05C7wZvoAhXuy4sBHWVfBxwQtwIwCHoECAMQAQ&url=
https://www.youtube.com/watch?v=mbnFCGTF3IM
&usg=AOvVaw37CIHNDBJ4H_h2NB_xOtrk


https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=3&cad=rja&uact=8&ved=2ahUKEwjc05C7wZvoAhXuy4sBHWVfBxwQtwIwAnoECAYQAQ&url=
https://www.youtube.com/watch?v=-_k4E84owFc
&usg=AOvVaw2DoEuUU9hkpxrTcdDqCjiV


https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=2ahUKEwim0r_fkaPoAhWFc3AKHf3vCc4QtwIwAHoECAUQAQ&url=
https://www.youtube.com/watch?v=AiqDiRrlydo
&usg=AOvVaw2Ipzyli2Ry8__rzO7EcHPR

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=3&cad=rja&uact=8&ved=2ahUKEwim0r_fkaPoAhWFc3AKHf3vCc4QtwIwAnoECAcQAQ&url=
https://www.youtube.com/watch?v=ESz0NikUXAw
&usg=AOvVaw2M9c_MKRfDPTMUis6kC4Ro

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=5&cad=rja&uact=8&ved=2ahUKEwim0r_fkaPoAhWFc3AKHf3vCc4QtwIwBHoECAsQAQ&url=
https://www.youtube.com/watch?v=qoO6c2CjsYw
&usg=AOvVaw2dNZcfERUCljCRwyPJpmEr

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=7&cad=rja&uact=8&ved=2ahUKEwjf59OrlaPoAhXUy4sBHSpsA-cQtwIwBnoECAIQAQ&url=
https://www.youtube.com/watch?v=qH8OH1a_GVQ
&usg=AOvVaw34blySTgHj6_q_TXGP8hbe

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=2ahUKEwiE8Ya946_oAhUYfnAKHQC7DwEQtwIwAHoECAYQAQ&url=https://www.youtube.com/watch?v=ahPQtyJZ-lk
&usg=AOvVaw3WuudMw4xGGSj0rVMrxUVW

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=5&cad=rja&uact=8&ved=2ahUKEwiE8Ya946_oAhUYfnAKHQC7DwEQtwIwBHoECAkQAQ&url=
https://www.youtube.com/watch?v=btLLDFDUveo
&usg=AOvVaw18Sab78IYDlSSeSQgGaVg0

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=2&cad=rja&uact=8&ved=2ahUKEwjRt8Owv9XoAhUQyYsBHUFCDmgQtwIwAXoECAkQLQ&url=
https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DiREVIyBW4kE
&usg=AOvVaw04Djrny18ClqQcYmbKNGZo
i

https://www.google.com/url?sa=t&nrct=j&q=&esrc=s&source=web&cd=1&ved=2ahUKEwjv-7m0wNXoAhX_xosBHQoFCtMQtwIwAHoECAkQLw&url=
https://www.youtube.com/watch?v=nfnO3Ch9_gU
i

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=3&ved=2ahUKEwiR3Yzrrp7pAhVFyYsBHWaaCEEQtwIwAnoECAMQAQ&url=
https://www.youtube.com/watch?v=usD9hoqPvgQ
https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&ved=2ahUKEwjRlZTz1ujpAhWNBogKHbhyCbwQtwIwAHoECAQQAQ&url=
https://www.youtube.com/watch?v=3mCu4rXka-4
https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&cad=rja&uact=8&ved=2ahUKEwjRlZTz1ujpAhWNBogKHbhyCbwQtwIwA3oECAUQAQ&url=
https://www.youtube.com/watch?v=L29_9yg5NK4
https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=3&ved=2ahUKEwiR3Yzrrp7pAhVFyYsBHWaaCEEQtwIwAnoECAMQAQ&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DusD9hoqPvg


https://www.youtube.com/watch?v=LT3XJ_X8MTU&list=PLgawtcOBBjr9w4YGiJrPD8f6MXTCIUfK9&index=2&t=0s

https://www.youtube.com/watch?v=TWojA5LyBtQ&list=PLgawtcOBBjr9w4YGiJrPD8f6MXTCIUfK9&index=3&t=0s

https://www.youtube.com/watch?v=IyUnC1lsX3o&list=PLgawtcOBBjr9w4YGiJrPD8f6MXTCIUfK9&index=4&t=0s



# math
Question:
已知三点坐标,求平面方程.
已知三点A（x1,y1,z1）、B（x2,y2,z2）、C（x3,y3,z3）
我想知道平面公式里aX+bY+cZ+d=0
的a、b、c、d怎样用x1,y1,z1,x2,y2,z2,x3,y3,z3来表示.
也就是帮我解下没有具体数字4元1次方程.数学不好实在算不清.
怎么算无所谓啦。就是把a、b、c、d用坐标x1,y1,z1,x2,y2,z2,x3,y3,z3表示出来就好。
我要的是结果不是方法……
这个问题本身不是很难，就是很麻烦就是了……

Answer:
要结果是吧,OK
向量AB=向量OB-向量OA=(x2-x1,y2-y1,z2-z1)
向量AC=向量OC-向量OA=(x3-x1,y3-y1,z3-z1)
向量AB×向量AC=([y1z2-y1z3-y2z1+y2z3+y3z1-y3z2],[-x1z2+x1z3+x2z1-x2z3-x3z1+x3z2],[x1y2-x1y3-x2y1+x2y3+x3y1-x3y2])
即a=y1z2-y1z3-y2z1+y2z3+y3z1-y3z2,b=-x1z2+x1z3+x2z1-x2z3-x3z1+x3z2,c=x1y2-x1y3-x2y1+x2y3+x3y1-x3y2
带入(x1,y1,z1),得到(y1z2-y1z3-y2z1+y2z3+y3z1-y3z2)x1+(-x1z2+x1z3+x2z1-x2z3-x3z1+x3z2)y1+(x1y2-x1y3-x2y1+x2y3+x3y1-x3y2)z1+d=0,即x1y1z2-x1y1z3-x1y2z1+x1y2z3+x1y3z1-x1y3z2-x1y1z2+x1y1z3+x2y1z1-x2y1z3-x3y1z1+x3y1z2+x1y2z1-x1y3z1-x2y1z1+x2y3z1+x3y1z1-x3y2z1+d=0,即x1y2z3-x1y3z2-x2y1z3+x2y3z1+x3y1z2-x3y2z1+d=0,即d=-x1y2z3+x1y3z2+x2y1z3-x2y3z1-x3y1z2+x3y2z1
所以
a=y1z2-y1z3-y2z1+y2z3+y3z1-y3z2
b=-x1z2+x1z3+x2z1-x2z3-x3z1+x3z2
c=x1y2-x1y3-x2y1+x2y3+x3y1-x3y2
d=-x1y2z3+x1y3z2+x2y1z3-x2y3z1-x3y1z2+x3y2z1




# Wu zong

Many thanks for your kind cooperation and flexibility.
We also highly appreciate all efforts you’ve made for Li-Ning.

In response, we will keep the promise for the original offer:
1)     We will provide Li-Ning products and USD$ 150K mandatory fee for COM for 2020 Tokyo Olympic Game, while Jardeleón shall be 100% responsible for the transportation and tariffs;
2)     We will allocate the items from 20Q1&Q2 to other clients, other than the Liverpool merchandise;

The only major concern to worry about is the deadline of payment.  Considering the Christmas Holiday and operate time of shipment, the 23rd of December will be the last day for payment without extension. We think it’s more reasonable and safe to set 20th of December(Friday) as the last deadline of payment. Anyway, I have already asked Juan’s team to select the items for USD 500K. We will prepare the goods in advance accordingly.

We are quite aware of your indicates about the cooperation for each other in the email. We also fully understand and respect Jardeleon, who is the best partner of us to represent Li-Ning over the Mexico. As response of Li-Ning, We are doing maximum possible effort from here to make it happen.

On behalf of Dwhite Bai, whom is the upper management of Li-Ning international department, I would like invite you to visit Beijing at your earliest convenience. Let’s fix the schedule of the meeting on early of next January.

# ads code renew using gitlab
1. 准备一份最新的代码，建立代码仓库
2. git clone 远程分支到中间机上 如：git clone ssh://git@git.piesat.cn:10002/QXYG/algorithm/ADS/ADS_ttt.git
3. in the dir, run
   git config receive.denyCurrentBranch ignore
   update_ads 或者 echo -e "cd /mnt/swapdata/ADSCODE/ADS/git/renew/ \n ./update.pl ADS_tttt" | ssh 10.24.237.31
4. 

git init  # 生成.git
git remote add origin ssh://git@git.piesat.cn:10002/QXYG/algorithm/ADS/ADS_PM25_test.git  # 设置链接
git fetch --all  # 同步远程服务器
git reset --hard origin/master # 更新本地代码
git branch --set-upstream-to=origin/master master 

git remote set-url origin ssh://git@git.piesat.cn:27022/QXYG/algorithm/ADS/ADS_PM25_test.git  # 改变链接

echo 'cd /home/ads/ADS_PM25_test && git pull && update_ads 10.24.237.31' | ssh -p 3377 ads@toothedsword.natapp1.cc

git push --all lab -u  # push all

# for Dr. Wang
谢谢王总，回国工作一年了，是应该有个总结和展望了。总体来说，我还是很适应公司的工作，自己比较喜欢技术类的工作。不足的地方是太关注自己的任务，对算法部的交流抓的不够，团队的作用发挥的不够，后期要加强，避免个人长期调研，增加组员对部长的反馈和交流，提高团队的效率。目前接任ADS算法项目的项目经理，目前还是要多积累项目经验，公司后期肯定是会有更多类似的项目。对自己的定位和发展方向，就是不仅要在算法开发和工程化等方面能够指导组员，同时也能做到高效地对接和引导客户。以后也考虑利用自己的人脉，为公司扩展项目。

建议方面：主要是感到最近公司失血有点严重，所以还是建议公司能够尽量采取措施留住现有的核心人员和能干的年轻人。招聘新人有培训和适应的成本，也有不适用的风险，留住现有业务骨干对公司的业绩和竞争力很重要。刚毕业的年轻人在北京面临的压力较大，能稳定数年就不容易了，人力在招人的时候不能强求太多。另外，公司为卫星中心定制软件的时候，在充分利用研究院技术积累的基础上，也应该多让总工和技术负责人制定比较高效的复用与对接模式，增加开发速度。

以上为个人不成熟的建议，对公司的管理，其实我们也一直在向阎总以及宋毅博士反馈。
#{{{
王总，有件事情还要再向您汇报一下。这次碰见我师兄周昕佳，他说目前noaa对中国人气氛不是特别友好，因此我们对兼职同事的身份还是要多加保密。目前何宇翔在周昕佳手下工作，周昕佳上次看到您给何宇翔点赞，见面问我何宇翔是不是和我们公司有联系。

#}}}
王总，您好，有件事情想请您帮忙。目前我正在想办法把我的户口从老家转出来，可以利用大气所的政策，随我老婆转到我现在的房子里面。现在就是需要公司开一个工作证明，证明我18年7月开始在公司工作。有一点比较麻烦，需要在证明里面写本人档案在公司里面。上次我去大气所查档案的时候，档案袋里面材料严重不全，应该是他们给我弄丢了（同届班里相似的人名太多，四个叫什么亮的），但是经手人早已经换了，难以找到当事人弥补这件事情，事业单位的人就是换届了就没人负责了。按照以往同事的经验，材料主要是走过场，没有调查的风险。所以想请王总能不能给人事部门打个招呼，帮忙开这么一个工作证明，谢谢！明天您有时间的话，我可以给您当面解释一下这个事情，打扰了！

# weekly report
    #=> ADS
    
1.算法评审汇报（宋毅、赵海博、all: 确定于周五进行算法正式评审）
2.完成算法统计功能集成部署（笪宏志）
3.台风降水算法集成（牛太阳，完成在气象局的部署）
4.地表温度算法工程化改造和集成（陈彦红，完成在气象局的部署）
5.台风大风及台风降水算法的测试和部署（彭亮、牛太阳，董冠男，完成降水在气象局的部署，完成大风程序的测试）
6.继续能量平衡及太阳能算法工程化改造（卢婷婷、刘方伟）
7.云图解译算法准备集成代码（石玉立）
8.台风暖核算法优化和台风三维展示（彭亮，袁国言，利用FY3资料测试，确保算法的适用性）
9. 沙尘完成气象局服务器集成部署和测试（笪宏志，陈明天）
10.干旱工程化改造（王金英）
11.对流算法服务端工程化改造（康晖）
12.数值预报对流适用算法工程化改造和集成（孙乃秀）
13.对朱老师提供火山灰云判识算法中的方法b进行学习并尝试实现（牛太阳）

1.算法评审汇报（宋毅、赵海博，all，已完成算法汇报）
2.完成地表温度算法工程化改造和集成，正在开展热岛环境算法编码（陈彦红）
3.干旱工程化改造（王金英，进行中）
4.对流算法服务端工程化改造（康晖，进行中）
5.数值预报对流适用算法工程化改造和集成（孙乃秀，进行中）

1.算法评审汇报意见整理（宋毅）
2.完成算法统计功能集成部署（笪宏志）
3.台风降水算法集成（牛太阳，完成在气象局的部署）
4.地表热岛环境算法工程化改造和集成（陈彦红）
5.台风大风及台风降水算法的测试和部署（彭亮、牛太阳，董冠男）
6.云图解译算法准备集成代码（石玉立）
7.干旱工程化改造（王金英）
8.对流算法服务端工程化改造（康晖）
9.数值预报对流适用算法工程化改造和集成（孙乃秀）
10.一带一路中 积雪算法集成显示、统计功能增加。（宋毅协调）

2019-AUG-16
本周工作计划：
1.沙尘沉降算法集成与测试（刘方伟）
2.测试并优化算法统计功能（笪宏志）
3.台风降水算法集成（牛太阳，气象局服务器集成）
4.地表热岛环境算法工程化集成（陈彦红）
5.台风大风的测试和部署（彭亮、牛太阳，董冠男）
6.云图解译算法准备集成代码（石玉立）
7.干旱工程化改造（王金英）
8.对流算法服务端工程化改造（康晖）
9.数值预报对流适用算法工程化改造和集成（孙乃秀）
10.一带一路中 积雪算法集成显示、统计功能增加。（宋毅协调）

本周工作进展：
1.沙尘沉降算法工程化改造（刘方伟）
2.完成日统计功能集成（笪宏志，陈明天）
3.气象局服务器gfortran环境配置（董冠男，彭亮，宋毅）
4.地表热岛环境算法工程化集成（陈彦红）
5.台风暖核算法调试（彭亮）
6.云图解译算法工程化改造（石玉立）
7.干旱工程化改造（王金英
8.对流算法服务端工程化改造（康晖）
9.数值预报对流适用算法工程化改造和集成（孙乃秀）
10.完成日统计功能集成（笪宏志，陈明天）

下周工作计划：
1.继续沙尘沉降算法工程化改造（刘方伟）
2.优化完善统计功能（笪宏志）
3.测试气象局Docker环境（董冠男，彭亮，宋毅）
4.地表热岛环境算法工程化集成（陈彦红）
5.完善台风子系统算法集成（彭亮）
6.继续云图解译算法工程化改造（石玉立）
7.干旱工程化改造（王金英）
8.对流算法服务端工程化改造（康晖）
9.数值预报对流适用算法工程化改造和集成（孙乃秀）
10.火山灰工程化改造（牛太阳）

本周工作计划
1.继续沙尘沉降算法工程化改造（刘方伟）
2.优化完善统计功能（笪宏志）
3.测试气象局Docker环境（董冠男，彭亮，宋毅）
4.地表热岛环境算法工程化集成（陈彦红）
5.完善台风子系统算法集成（彭亮）
6.继续云图解译算法工程化改造（石玉立）
7.干旱工程化改造（王金英）
8.对流算法服务端工程化改造（康晖）
9.数值预报对流适用算法工程化改造和集成（孙乃秀）
10.火山灰工程化改造（牛太阳）

本周工作进展
1.完成了沙尘沉降算法工程化改造（刘方伟，彭亮）
2.完善了区域面积功能（笪宏志）
3.Docker测试成功（董冠男，陈明天，彭亮，宋毅）
4.地表温度适配中国区算法工程化完成公司服务器的测试（陈彦红）
5.台风子系统工程化测试完成，修改了降水算法的bug（降水，预测）（牛太阳，彭亮）
6.云图解译算法工程化改造（石玉立）
7.干旱工程化改造（王金英）
8.对流算法服务端工程化改造（康晖）
9.数值预报对流适用算法工程化改造（孙乃秀）
10.继续对接了火山灰工程化改造（牛太阳）
11.优化积雪算法并完成部署（赵海博）
12.火情算法工程化改造（谢振雷）

下周工作计划
1.修复沙尘沉降算法中的bug及centos系统改造和测试（刘方伟，彭亮）
2.继续完善统计功能（笪宏志）
3.完成气象局Docker的部署（董冠男，陈明天，彭亮，宋毅）
4.完成地表温度中国区的适配与部署（陈彦红）
5.台风子系统工程化测试完成（降水，预测）（彭亮）
6.云图解译算法工程化改造（石玉立）
7.干旱工程化改造（王金英）
8.对流算法服务端工程化改造（康晖）
9.继续数值预报对流适用算法工程化改造和集成（孙乃秀）
10.继续火山灰工程化改造（牛太阳）
11.积雪算法完成部署（赵海博）
12.继续火情算法工程化改造（谢振雷）

:
1.修复沙尘沉降算法中的bug及centos系统改造和测试（刘方伟，彭亮）
2.继续完善统计功能（笪宏志）
3.完成气象局Docker的部署（董冠男，陈明天，彭亮，宋毅）
4.完成地表温度中国区的适配与部署（陈彦红）
5.台风子系统工程化测试完成（降水，预测）（彭亮）
6.云图解译算法工程化改造（石玉立）
7.干旱工程化改造（王金英）
8.对流算法服务端工程化改造（康晖）
9.继续数值预报对流适用算法工程化改造和集成（孙乃秀）
10.继续火山灰工程化改造（牛太阳）
11.积雪算法完成部署（赵海博）
12.继续火情算法工程化改造（谢振雷）

2019-Sep-6
本周工作计划
1.沙尘沉降算法docker部署（刘方伟，彭亮）
2.在公司的服务器上测试统计算法（笪宏志，董冠男，彭亮）
3.优化docker算法包，根据需要添加算法（董冠男，陈明天，彭亮，宋毅）
4.继续城市热岛的工程化改造；大雾集合预报部署测试（陈彦红）
5.完成台风子系统算法在docker中的部署与运行，并完成接口的修改（降水，预测）（彭亮，陈明天）
6.继续开发云图解译软件包（石玉立）
7.继续干旱工程化改造，预计做完算法框架加ndvi（王金英）
8.将剩余对流子系统中的算法给布置到公司服务器上测试（康晖）
9.继续在公司测试数值预报对流适用算法修改Bug（孙乃秀）
10.火山灰云判识工作、火山灰云高度和浓度的工程化改造（牛太阳）
11.完成优化后的积雪算法的部署（赵海博）
12.完成火蔓延修改工作，并进行服务器测试（谢振雷）
13.梳理太阳能算法的工程化（刘方伟，彭亮）
14.梳理项目概设模板（彭亮、宋毅）

本周工作进展
1.沙尘沉降算法测试（刘方伟，彭亮）
2.制作大雾日合成统计结果图（笪宏志，董冠男，彭亮）
3.docker中文乱码问题解决，公司服务器及docker中scikit-learn库升级（董冠男，陈明天，彭亮，宋毅）
4.完成了城市热岛分级计算和缩略图生成，完成了城市热场强度指数分级计算和缩略图生成，城市群热场聚集度和优势度计算完成（陈彦红）
5.优化了台风定位定强算法输出文件的命名（彭亮，陈明天）
6.继续开发云图解译软件包（石玉立）
7.ndvi及各干旱指数命名规则确认并实现工程化编码（王金英）
8.将对流外推、快速发展对流、地理信息提取等三个算法布置到服务器上（康晖）
9.改进了数值预报释用代码，加快了预报速度，输出了NC和PNG结果，编写了工程化接口脚本（孙乃秀）
10.沟通了火山灰云判识和火山热点判识算法验证方法；火山热点通过修改算法降低误报率，火山灰正在切换到H8数据进行验证（牛太阳）
11.修改ads积雪产品程序， 优化读取数值天气预报数据的策略， 优化云检测的阈值， 完成积雪产品代码（赵海博）
12.初步完成火蔓延修改工作（谢振雷）
13.梳理太阳能算法的工程化（刘方伟，彭亮）
14.梳理出了项目概设模板（彭亮、宋毅）
15.完成PM2.5少量训练数据小模型的构建，基于小模型完成算法在公司服务器上的调试部署（张晗）

下周工作计划
1.沙尘沉降算法log和json生成和docker部署（刘方伟，彭亮）
2.沙尘判识出图修改（笪宏志，董冠男，彭亮）
3.公司服务器docker容器中部署算法（董冠男，陈明天，彭亮，宋毅）
4.城市群热场聚集度和优势度bug修改（陈彦红）
5.完成台风子系统算法在docker中的部署与运行（降水，预测）（彭亮，陈明天）
6.继续开发云图解译软件包（石玉立）
7.ndvi全圆盘及等经纬产品公司服务器部署，中国区等经纬干旱指数公司服务器部署（王金英）
8.计划把对流追踪算法布置到服务器（康晖）
9.完善数值预报释用代码绘图结果（孙乃秀）
10.读取H8数据验证火山灰判识算法；火山灰高度和浓度算法工程化（牛太阳）
11.完成优化后的积雪算法的部署（赵海博）
12.完成火蔓延部署工作（谢振雷）
13.梳理太阳能算法的工程化（刘方伟，彭亮）
14.开展概要设计文档的编写（彭亮、宋毅）
15.PM10的算法适配（张晗）

本周工作计划：
1.沙尘沉降算法log和json生成和docker部署（刘方伟，彭亮）
2.沙尘判识出图修改（笪宏志，董冠男，彭亮）
3.公司服务器docker容器中部署算法（董冠男，陈明天，彭亮，宋毅）
4.城市群热场聚集度和优势度bug修改（陈彦红）
5.完成台风子系统算法在docker中的部署与运行（降水，预测）（彭亮，陈明天）
6.继续开发云图解译软件包（石玉立）
7.ndvi全圆盘及等经纬产品公司服务器部署，中国区等经纬干旱指数公司服务器部署（王金英）
8.计划把对流追踪算法布置到服务器（康晖）
9.完善数值预报释用代码绘图结果（孙乃秀）
10.读取H8数据验证火山灰判识算法；火山灰高度和浓度算法工程化（牛太阳）
11.完成优化后的积雪算法的部署（赵海博）
12.完成火蔓延部署工作（谢振雷）
13.梳理太阳能算法的工程化（刘方伟，彭亮）
14.开展概要设计文档的编写（彭亮、宋毅）
15.PM10的算法适配（张晗）

本周工作进展
1.修改部分代码以生成沙尘沉降算法log和json（刘方伟，彭亮）
2.修改沙尘专题图 （笪宏志，董冠男，彭亮）
3.台风外推算法docker部署测试（董冠男，陈明天，彭亮，宋毅）
4.完成城市群热场聚集度和优势度bug修改（陈彦红）
5.台图解译风外推算法问题解决（董冠男，彭亮，陈明天）
6.继续开发云图解译软件包（石玉立）
7.完成部分干旱算法服务器部署（王金英）
8.开展了对流追踪算法布置到服务器（康晖）
9.预报资料对流释用调试编译脚本，完善绘图结果（孙乃秀）
10.读取H8数据验证火山灰判识算法；火山灰高度和浓度算法工程化（牛太阳）
11.按照工程化的要求, 修改积雪文件输出的变量属性, 添加全局属性, 优化变量存储格式和压缩选项（赵海博）
12.完成部分火蔓延部署工作（谢振雷）
13.完成部分概要设计文档（台风和云图解译）（彭亮、宋毅）
14.完成PM10模型的构建，算法的编写，以及算法在服务器上部署测试（张晗）

下周工作计划：
1.沙尘沉降算法log和json生成和docker部署（刘方伟，彭亮）
2.去条带工程化（笪宏志，赵海博，宋毅）
3.公司服务器docker容器中部署算法（董冠男，陈明天，彭亮，宋毅）
4.完成城市群热场聚集度和优势度bug修改（陈彦红）
5.完成台风子系统算法在docker中的部署与运行（降水，预测）（彭亮，陈明天）
6.继续开发云图解译软件包（石玉立）
7.完成干旱算法部署（王金英）
8.对流追踪算法布置到服务器（康晖）
9.预报资料对流释用开展服务器部署（孙乃秀，陈明天）
10.用H8数据做火山灰RGB合成和验证火山灰判识，给出火山灰判识中间变量（牛太阳）
11.完成优化后的积雪算法的部署（赵海博）
12.完成火蔓延部署工作（谢振雷）
13.开展概要设计文档的编写（彭亮、宋毅，所有人）
14.编写气溶胶子系统概要设计文档（张晗)

2019-09-22
本周工作计划
1.沙尘沉降算法log和json生成和docker部署（刘方伟，彭亮）
2.去条带工程化（笪宏志，赵海博，宋毅）
3.公司服务器docker容器中部署算法（董冠男，陈明天，彭亮，宋毅）
4.完成城市群热场聚集度和优势度bug修改（陈彦红）
5.完成台风子系统算法在docker中的部署与运行（降水，预测）（彭亮，陈明天）
6.继续开发云图解译软件包（石玉立）
7.完成干旱算法部署（王金英）
8.对流追踪算法布置到服务器（康晖）
9.预报资料对流释用开展服务器部署（孙乃秀，陈明天）
10.用H8数据做火山灰RGB合成和验证火山灰判识，给出火山灰判识中间变量（牛太阳）
11.完成优化后的积雪算法的部署（赵海博）
12.完成火蔓延部署工作（谢振雷）
13.开展概要设计文档的编写（彭亮、宋毅，所有人）
14.编写气溶胶子系统概要设计文档（张晗)

本周工作进展
1.完成云图解译产品释用部件概要设计编写（卢婷婷）
2.完成部分去条带工程化，修改沙尘专题图bug，增加国界线（笪宏志，赵海博，宋毅）
3.协助同事集成部署ADS算法，并在docker中集成测试了火点判识算法、大雾算法、地表温度算法、AOD算法、PM2.5算法、PM10算法（董冠男，陈明天，彭亮，宋毅）
4.完成雾判识和地表温度反演算法在docker的部署测试，编写雾监测部件概要设计部分内容（陈彦红）
5.完成台风大风监测部分工程化及测试（牛太阳，彭亮）
6.继续开发云图解译软件包（石玉立）
7.完成部分干旱算法部署，完成ADS概要设计文档的干旱部分（王金英，杜进慧）
8.完成追踪算法的部署（康晖）
9.预报资料对流释用开展服务器部署（孙乃秀，陈明天）
10.沟通火山灰判识结果；修改算法进行改进并提供结果（牛太阳）
11.积雪：在气象局ADS测试服务器上更新源代码编译源代码（赵海博）
12.火评估算法完成改写；火险算法修改工作完成部分（谢振雷）
13.概设文档编写，除类设计、时序图和界面设计，其他部分完成；AOD算法进行了优化并完成公司服务器测试，将测试成功后的AOD PM2.5 PM10调用接口和样例编写文>档发给陈明天和董冠男，用于算法部署（张晗）

下周工作计划
1.完成能量平衡监测部件概要设计编写（卢婷婷）
2.继续完成去条带工程化，完成蓝藻概要设计文档（笪宏志，赵海博，宋毅）
3.docker容器算法部署（董冠男，陈明天，彭亮，宋毅）
4.雾监测部件和地表温度部件概要设计编写和修改；雾特征量反演算法工程化；确定雾特征量反演算法部署调用方案及在服务器部署测试（陈彦红）
5.完成台风大风监测工程化及测试（牛太阳，彭亮）
6.继续开发云图解译软件包以及概要设计文档的编写（石玉立，宋毅）
7.完成部分干旱算法部署（王金英，杜进慧）
8.完成对流算法的docker部署（康晖）
9.预报资料对流释用开展服务器部署（孙乃秀，陈明天）
10.沟通火山灰判识工作，完成火山高度和浓度算法文档并完成概要设计（牛太阳）
11.积雪：公司docker部署（赵海博）
12.火险其它局部问题的修改（谢振雷）
13.完成气溶胶部件概设文档剩余部分编写（张晗）
14.概要设计文档总册编写（彭亮，宋毅）

2019-9-30
本周工作计划
1.完成能量平衡监测部件概要设计编写（卢婷婷）
2.继续完成去条带工程化，完成蓝藻概要设计文档（笪宏志，赵海博，宋毅）
3.docker容器算法部署（董冠男，陈明天，彭亮，宋毅）
4.雾监测部件和地表温度部件概要设计编写和修改；雾特征量反演算法工程化；确定雾特征量反演算法部署调用方案及在服务器部署测试（陈彦红）
5.完成台风大风监测工程化及测试（牛太阳，彭亮）
6.继续开发云图解译软件包以及概要设计文档的编写（石玉立，宋毅）
7.完成部分干旱算法部署（王金英，杜进慧）
8.完成对流算法的docker部署（康晖）
9.预报资料对流释用开展服务器部署（孙乃秀，陈明天）
10.沟通火山灰判识工作，完成火山高度和浓度算法文档并完成概要设计（牛太阳）
11.积雪：公司docker部署（赵海博）
12.火险其它局部问题的修改（谢振雷）
13.完成气溶胶部件概设文档剩余部分编写（张晗）
14.概要设计文档总册编写（彭亮，宋毅）

本周工作进展
1.完成能量平衡监测部件概要设计编写（卢婷婷）
2.完成沙尘判识算法的docker封装与气象局服务器的部署（笪宏志，赵海博，宋毅）
3.docker容器集成大部分算法并移植到气象局服务器（董冠男，陈明天，彭亮，宋毅）
4.完成了大雾和地表温度概要设计文档的初稿；docker继承了雾判识算法（陈彦红）
5.台风大风监测输出产品算法工程化（牛太阳，彭亮）
6.云图解译软件包工程化以及概要设计文档的编写（石玉立，宋毅）
7.完成部分干旱算法部署（王金英，杜进慧）
8.完成对流算法的docker部署（康晖）
9.预报资料对流释用docker部署完毕（孙乃秀，陈明天）
10.沟通火山灰判识工作，完成火山高度和浓度算法文档并编写概要设计（牛太阳）
11.完成积雪算法公司docker部署（赵海博）
12.完成火蔓延部署工作（谢振雷）
13.完成气溶胶部件概设文档剩余部分编写（张晗）
14.概要设计文档总册梳理完毕（彭亮，宋毅）

下周工作计划
1.完成能量平衡监测部件概要设计编写（卢婷婷）
2.完成蓝藻概要设计文档（笪宏志，赵海博，宋毅）
3.完善docker容器算法部署，完成算法对接（董冠男，陈明天，彭亮，宋毅）
4.完成雾和地表温度算法的概要设计文档（陈彦红）
5.完成台风大风监测数据融合的工程化测试（牛太阳，彭亮）
6.继续开发云图解译软件包以及概要设计文档的编写（石玉立，宋毅）
7.继续干旱算法部署和概要设计文档的修改（王金英，杜进慧）
8.测试docker部署的对流算法（康晖，陈明天）
9.测试docker部署的预报资料对流释用（孙乃秀，陈明天）
10.完成火山高度和浓度算法文档并完成概要设计（牛太阳）
11.测试和优化docker部署的积雪算法（赵海博）
12.火险算法服务器测试（谢振雷）
13.完成气溶胶部件概设文档的修改（张晗）
14.概要设计文档总册编写（彭亮，宋毅）

本周工作计划
1.完成能量平衡监测部件概要设计编写（卢婷婷）
2.完成蓝藻概要设计文档（笪宏志，赵海博，宋毅）
3.完善docker容器算法部署，完成算法对接（董冠男，陈明天，彭亮，宋毅）
4.完成雾和地表温度算法的概要设计文档（陈彦红）
5.完成台风大风监测数据融合的工程化测试（牛太阳，彭亮）
6.继续开发云图解译软件包以及概要设计文档的编写（石玉立，宋毅）
7.继续干旱算法部署和概要设计文档的修改（王金英，杜进慧）
8.测试docker部署的对流算法（康晖，陈明天）
9.测试docker部署的预报资料对流释用（孙乃秀，陈明天）
10.完成火山高度和浓度算法文档并完成概要设计（牛太阳）
11.测试和优化docker部署的积雪算法（赵海博）
12.火险算法服务器测试（谢振雷）
13.完成气溶胶部件概设文档的修改（张晗）
14.概要设计文档总册编写（彭亮，宋毅）

本周工作进展
1.梳理了概要设计图表,部分完成了能量平衡监测部件概要设计初稿（卢婷婷）
2.完成蓝藻概要设计文档初稿（笪宏志）
3.完善docker容器算法部署（增加了对流追踪，释用等算法）（董冠男，陈明天，彭亮，宋毅）
4.完成雾和地表温度算法的概要设计文档初稿（陈彦红）
5.测试了EMDO降水融合算法，完成了台风概要设计文档的初稿（牛太阳，彭亮）
6.完成了云图解译概要设计文档初稿（宋毅）
7.完成了干旱部分概要设计文档的修改（杜进慧）
8.部分完成了对流系统概要设计文档的编写（康晖，陈明天）
9.完成了火山高度和浓度算法文档并完成概要设计（牛太阳）
10.进行了ADS地表温度算法的优化（赵海博）
11.修改火情方面的概要设计（谢振雷）
12.完成了气溶胶部件概设文档的修改（张晗）

下周工作计划
1.完成能量平衡监测部件概要设计编写（卢婷婷）
2.配合修改蓝藻概要设计文档（笪宏志）
3.继续增加docker容器算法，配合java组调用（董冠男，陈明天，彭亮，宋毅）
4.配合修改雾和地表温度算法的概要设计文档（陈彦红）
5.测试EMDO FY4-FY3降水反演代码，风场融合工程化改造（牛太阳，彭亮）
6.配合修改概要设计文档（宋毅）
7.配合概要设计文档的修改，干旱算法docker部署（杜进慧，王金英）
8.测试调用气象局docker部署的对流算法，完善对流部分概要设计（康晖，陈明天）
9.测试调用气象局docker部署的预报资料对流释（孙乃秀，陈明天）
10.火山灰云高度和浓度的工程化改造（牛太阳）
11.继续优化地表温度算法（赵海博）
12.服务器部署火判识算法，协助测试火蔓延、火评估（谢振雷）
13.配合修改气溶胶部件概设文档的修改（张晗）
14.完善并修改概要设计文档总册，准备ADS概要设计PPT（彭亮，宋毅）

本周工作计划
1.完成能量平衡监测部件概要设计编写（卢婷婷）
2.配合修改蓝藻概要设计文档（笪宏志）
3.继续增加docker容器算法，配合java组调用（董冠男，陈明天，彭亮，宋毅）
4.配合修改雾和地表温度算法的概要设计文档（陈彦红）
5.测试EMDO FY4-FY3降水反演代码，风场融合工程化改造（牛太阳，彭亮）
6.配合修改概要设计文档（宋毅）
7.配合概要设计文档的修改，干旱算法docker部署（杜进慧，王金英）
8.测试调用气象局docker部署的对流算法，完善对流部分概要设计（康晖，陈明天）
9.测试调用气象局docker部署的预报资料对流释（孙乃秀，陈明天）
10.火山灰云高度和浓度的工程化改造（牛太阳）
11.继续优化地表温度算法（赵海博）
12.服务器部署火判识算法，协助测试火蔓延、火评估（谢振雷）
13.配合修改气溶胶部件概设文档的修改（张晗）
14.完善并修改概要设计文档总册，准备ADS概要设计PPT（彭亮，宋毅）

本周工作进展
1.完成能量平衡监测部件概要设计编写（卢婷婷）
2.完成蓝藻概要设计文档的修改（笪宏志）
3.增加火情算法到docker容器（董冠男，陈明天，彭亮，宋毅）
4.完成修改雾Y和地表温度算法的概要设计文档（陈彦红）
5.完成了EMDO FY4-GPM降水反演代码的测试（牛太阳，彭亮）
6.修改了云图解译方面的概要设计文档（宋毅）
7.完成了干旱部分概要设计文档的修（杜进慧，王金英）
8.继续修改了对流部分概要设计（康晖）
9.测试了调用气象局docker部署的预报资料对流释用（孙乃秀，陈明天）
10.火山灰云高度和浓度的工程化改造（牛太阳）
11.完成了地表温度算法的优化（赵海博）
12.测试了服务器火判识算法，协助测试火蔓延、火评估（谢振雷）
13.配合修改了气溶胶部件概设文档的修改（张晗）

下周工作计划
1.能量平衡代码工程化改造（卢婷婷）
2.统计算法工程化测试与部署（笪宏志）
3.配合java组部署算法（董冠男，陈明天，彭亮，宋毅）
4.工程化优化后的地表温度算法（陈彦红）
5.风场融合工程化改造（牛太阳，彭亮）
6.配合修改云图解译概要设计PPT（宋毅）
7.继续干旱算法工程化和docker部署（杜进慧，王金英）
8.测试调用气象局docker部署的对流算法，完善对流部分概要设计（康晖，陈明天）
9.测试调用气象局docker部署的预报资料对流释（孙乃秀，陈明天）
10.继续火山灰云高度和浓度的工程化改造（牛太阳）
11.生成生态分系统概要设计汇报PPT（赵海博）
12.继续服务器部署火判识算法，协助测试火蔓延、火评估，消除算法Bug（谢振雷）
13.完成气溶胶配置项的工程化（张晗）
14.完善概要设计文档总册，修改ADS概要设计PPT（彭亮，宋毅）

本周工作计划
1. 雾判识算法问题查找和修改（陈彦红）。
2. 完成火山灰监测部分文档（牛太阳）。
3. 完成火判识所有算法的改造（谢振雷）。
4. 继续太阳能子系统的工程化改造（刘方伟）。
5. 完成概要设计文档与甲方的对接（彭亮，宋毅）。

本周工作进展
1. 梳理了气溶胶配置项的缺项和解决方案（张晗）。
2. 完成火山灰监测部分文档（牛太阳）。
3. 完成部分火判识算法的改造（谢振雷）。
4. 完成部分太阳能子系统的工程化改造（刘方伟）。
5. 完成概要设计文档与甲方的对接（彭亮，宋毅）。
6. 完成了对流系统概要设计文档的修改（康晖，孙乃秀）
7. 完成部分积雪统计算法的工程化（赵海博）。

下周工作计划
1. 雾判识算法问题查找和修改（陈彦红）。
2. 继续完善火山灰监测部分文档（牛太阳）。
3. 完成火判识机器学习部分算法的改造（谢振雷）。
4. 继续太阳能子系统的工程化改造（刘方伟）。
5. 完成概要设计PPT（彭亮，宋毅）。
6. 集成部署对流配置项所缺的单元（陈明天）。
7. 继续积雪统计算法的工程化（赵海博）。
8. 风场融合代码集成（彭亮，牛太阳）

本周工作计划
1. 雾判识算法问题查找和修改（陈彦红）。
2. 继续完善火山灰监测部分文档（牛太阳）。
3. 完成火判识机器学习部分算法的改造（谢振雷）。
4. 继续太阳能子系统的工程化改造（刘方伟）。
5. 完成概要设计PPT（彭亮，宋毅）。
6. 集成部署对流配置项算法问题查找和修改（陈彦红）。
2. 继续完善火山灰监测部分文档（牛太阳）。
3. 完成火判识机器学习部分算法的改造（谢振雷）。
4. 继续太阳能子系统的工程化改造（刘方伟）。
5. 完成概要设计PPT（彭亮，宋毅）。
6. 集成部署对流配置项所缺的单元（陈明天）。
7. 继续积雪统计算法的工程化（赵海博）。
8. 风场融合代码集成（彭亮，牛太阳）。
9. 继续干旱子系统工程化改造（王金英）。

下周工作计划
1. 雾判识算法问题查找和修改（陈彦红）。
2. 继续完善火山灰监测部分文档（牛太阳）。
3. 完成火判识机器学习部分算法的改造（谢振雷）。
4. 继续太阳能子系统的工程化改造（刘方伟）。
5. 完成概要设计PPT（彭亮，宋毅）。
6. 集成部署对流配置项所缺的单元（陈明天）。
7. 继续积雪统计算法的工程化（赵海博）。
8. 风场融合代码集成（彭亮，牛太阳）。
9. 继续干旱子系统工程化改造（王金英）。

本周工作计划
1. 雾判识算法问题查找和修改（陈彦红）。
2. 继续完善火山灰监测部分文档（牛太阳）。
3. 完成火判识机器学习部分算法的改造（谢振雷）。
4. 继续太阳能子系统的工程化改造（刘方伟）。
5. 完成概要设计PPT（彭亮，宋毅）。
6. 集成部署对流配置项所缺的单元（陈明天）。
7. 继续积雪统计算法的工程化（赵海博）。
8. 风场融合代码集成（彭亮，牛太阳）。
9. 继续干旱子系统工程化改造（王金英）。

本周工作进展
1. 完成雾判识算法问题查找和修改（陈彦红）。
2. 完成火山灰多源数据融合和光谱交叉订正单元、火山热点监测单元、火山爆发预警单元工程化改造（牛太阳）。
3. 完成火判识部分单元的工程化改造（谢振雷）。
4. 完成部分太阳能配置项的改造（刘方伟）。
5. 完成概要设计PPT初稿并与甲方完成对接（彭亮，宋毅）。
6. 完成集成所缺配置项的梳理与对接（彭亮，陈明天，王占省）。
7. 完成积雪算法的优化（赵海博）。
8. 完成部分代码的改造（彭亮，牛太阳）。
9. 继续干旱子系统工程化改造（王金英）。

下周工作计划
1. 大雾融合集成单元工程化（陈彦红）。
2. 完成火山灰多源数据融合和光谱交叉订正单元、火山热点监测单元、火山爆发预警单元集成（牛太阳）。
3. 完成火判识四个单元的集成（谢振雷）。
4. 继续太阳能子系统的工程化改造（刘方伟）。
5. 完成概要设计出所评审和ppt的优化（彭亮，宋毅）。
6. 集成部署对流配置项所缺的单元（陈明天）。
7. 继续积雪配置项的积雪覆盖动态变化监测单元的工程化改造和集成（赵海博）。
8. 风场融合代码集成（彭亮，牛太阳）。
9. 继续干旱子系统工程化改造（王金英）。

本周ADS项目拟完成以下事情：
1. 大雾融合集成单元工程化（陈彦红）。
2. 完成火山灰多源数据融合和光谱交叉订正单元、火山热点监测单元、火山爆发预警单元集成（牛太阳）。
3. 完成火判识四个单元的集成（谢振雷）。
4. 完成太阳能子系统的工程化改造（刘方伟）。
5. 完成概要设计出所评审和ppt的优化（彭亮，宋毅）。
6. 集成部署对流配置项所缺的单元（陈明天）。
7. 积雪配置项的积雪覆盖动态变化监测单元的工程化改造和集成（赵海博）。
8. 风场融合代码集成（彭亮，牛太阳）。
9. 干旱子系统工程化改造和集成（王金英，白罩峰）。
10. 能量平衡代码工程化改造（卢婷婷）。
11. 气溶胶配置项集成（刘方伟，姚蓓蓓，彭亮）。
大家有问题随时和我沟通。

本周工作计划:
1. 大雾融合集成单元工程化（陈彦红）。
2. 完成火山灰多源数据融合和光谱交叉订正单元、火山热点监测单元、火山爆发预警单元集成（牛太阳）。
3. 完成火判识四个单元的集成（谢振雷）。
4. 继续太阳能子系统的工程化改造（刘方伟）。
5. 完成概要设计出所评审和ppt的优化（彭亮，宋毅）。
6. 集成部署对流配置项所缺的单元（陈明天）。
7. 继续积雪配置项的积雪覆盖动态变化监测单元的工程化改造和集成（赵海博）。
8. 风场融合代码集成（彭亮，牛太阳）。
9. 继续干旱子系统工程化改造（王金英）。
10. 能量平衡配置项工程化改造和集成（卢婷婷）。

本周工作进展:
1. 完成大雾融合集成单元工程化和测试（陈彦红）。
2. 完成火山灰多源数据融合和光谱交叉订正单元、火山热点监测单元、火山爆发预警单元工程化改造和测试（牛太阳）。
3. 完成火判识配置项的集成（谢振雷）。
4. 完成太阳能子系统部分工程化改造（刘方伟）。
5. 完成概要设计出所评审（彭亮，宋毅）。
6. 完成风场融合代码的工程化和测试（彭亮，牛太阳）。
7. 继续干旱子系统工程化改造（王金英，白罩峰）。
8. 继续能量平衡配置项工程化改造和集成（卢婷婷）。

下周工作计划:
1. 完成大雾融合集成单元的集成和集合预报方面的集成（陈彦红）。
2. 完成火山灰配置项的部分集成部署（牛太阳）。
3. 完成火判识配置项的集成部署（谢振雷）。
4. 继续太阳能子系统的工程化改造（刘方伟）。
5. 完成概要设计ppt的修改并随时准备正式概要设计评审（彭亮，宋毅）。
6. 台风配置项算法集成部署（彭亮，牛太阳）。
7. 继续干旱子系统工程化改造（王金英，白罩峰）。
8. 继续能量平衡配置项工程化改造和集成（卢婷婷）。


本周工作计划
1. 完成大雾融合集成单元的集成和集合预报方面的集成（陈彦红）。
2. 完成火山灰配置项的部分集成部署（牛太阳）。
3. 完成火判识配置项的集成部署（谢振雷）。
4. 继续太阳能子系统的工程化改造（刘方伟）。
5. 完成概要设计ppt的修改并随时准备正式概要设计评审（彭亮，宋毅）。
6. 台风配置项算法集成部署（彭亮，牛太阳）。
7. 继续干旱子系统工程化改造（王金英，白罩峰）。
8. 继续能量平衡配置项工程化改造和集成（卢婷婷）。

本周工作进展
1. 完成大雾融合集成单元的集成和集合预报方面的docker测试（陈彦红）。
2. 完成火山灰配置项的docker测试（牛太阳）。
3. 完成火判识配置项的测试（谢振雷）。
4. 继续太阳能子系统的工程化改造（刘方伟）。
5. 完成概要设计正式评审（项目组所有成员）。
6. 台风配置项算法测试完毕（彭亮，牛太阳）。
7. 完成ndvi的工程化改造（王金英，白罩峰）。
8. 继续能量平衡配置项工程化改造和集成（卢婷婷）。

下周工作计划
1. 完成大雾融合集成单元的集成（陈彦红）。
2. 完成火山灰配置项的集成部署（牛太阳）。
3. 完成火判识配置项的集成部署（谢振雷）。
4. 继续太阳能子系统的工程化改造（刘方伟）。
5. 根据甲方意见修改概要设计材料（项目组所有成员）。
6. 完成台风配置项部署（彭亮，牛太阳）。
7. 继续干旱子系统全圆盘NDVI的工程化改造（王金英，白罩峰）。
8. 继续能量平衡配置项工程化改造和集成（卢婷婷）。

本周工作计划
1. 完成大雾融合集成单元的集成（陈彦红）。
2. 完成火山灰配置项的集成部署（牛太阳）。
3. 完成火判识配置项的集成部署（谢振雷）。
4. 继续太阳能子系统的工程化改造（刘方伟）。
5. 根据甲方意见修改概要设计材料（项目组所有成员）。
6. 完成台风配置项部署（彭亮，牛太阳）。
7. 继续干旱子系统全圆盘NDVI的工程化改造（王金英，白罩峰）。
8. 继续能量平衡配置项工程化改造和集成（卢婷婷）。

本周工作进展
1. 雾检测配置项（陈彦红）：
    a. 大雾融合算法服务端测试对接。(已完成)
    b. 大雾集合预报算法服务端测试对接。(已完成)
    c. 城市热岛算法服务端测试对接。（对接已完成，批量测试出现随机问题，正在修改。）
2. 干旱配置项（白罩峰，杜进慧，王金英）：
    1.完成了NDVI产品反演算法100%
    2.完成了VSWI产品的反演算法100%
    3.完成了LST产品的反演算法100%
3. 火山检测配置项（牛太阳）：
    1.火山热点降低误报之后的代码进行工程化，完成其ads测试服务器和docker中测试，连同编辑好的接口文档交付于陈明天处；
    2.对ads和docker测试服务器进行维护，辅助做其他算法的测试工作；
4. 太阳能配置项（刘方伟）：
    代码工程化改造；
5. 台风配置项（彭亮，牛太阳）；
    a. 修改了台风降水监测代码的产品输出代码，测试通过，并集成到docker。
    b. 优化了台风大风监测高层风融合方案，测试通过，并集成到docker。
    c. 完成了台风大风监测配置项中大风区域提取，大风区域面积的算法。
6. 能量平衡配置项（卢婷婷）：
    修改完成显热通量计算部分代码（80%）
    修改完成地表蒸散发计算和地表相对蒸散发计算功能;
7. 火情配置项（谢振雷）：
    a. 完成了火情配置项的集成。
8. 概要设计文档（宋毅，彭亮）：
    a. 完成概要设计文档的修改。
    b. 完成会议纪要的整理。
    c. 完成产品清单。

下周工作计划
1. 雾检测配置项（陈彦红）：
    a. 大雾判识算法优化；
    b. 大雾统计分析和影响评估功能对接，测试、部署。
2. 干旱配置项（白罩峰，杜进慧，王金英）：
    a. 进行TVDI产品的算法反演
    b. 进行VCI产品的算法反演
    c. 进行TCI产品的算法反演
3. 火山检测配置项（牛太阳）：
    a. 对ads和docker测试服务器进行维护，辅助其他算法的测试工作；
    b. 跟踪火山热点进展；
4. 太阳能配置项（刘方伟）：
    a. 代码工程化改造。
5. 台风配置项（彭亮，牛太阳）：
    a. 气象局试运行台风配置项。
    b. 配合陈明天集成算法和网页展示。
6. 能量平衡配置项（卢婷婷）：
    a. 能量平衡算法集成测试;
7. 火情配置项（谢振雷）。
    a. 优化代码，解决算法过慢的问题。
    b. 配合java组解决显示方案。
8. 概要设计文档（宋毅，彭亮）；
    a. 与甲方讨论产品清单。
    b. 与甲方对接概设文档修改稿。

本周工作计划
1. 雾检测配置项（陈彦红）：
    a. 大雾判识算法优化；
    b. 大雾统计分析和影响评估功能对接，测试、部署。
2. 干旱配置项（白罩峰，杜进慧，王金英）：
    a. 进行TVDI产品的算法反演
    b. 进行VCI产品的算法反演
    c. 进行TCI产品的算法反演
3. 火山检测配置项（牛太阳）：
    a. 对ads和docker测试服务器进行维护，辅助其他算法的测试工作；
    b. 跟踪火山热点进展；
4. 太阳能配置项（刘方伟）：
    a. 代码工程化改造。
5. 台风配置项（彭亮，牛太阳）：
    a. 气象局试运行台风配置项。
    b. 配合陈明天集成算法和网页展示。
6. 能量平衡配置项（卢婷婷）：
    a. 能量平衡算法集成测试;
7. 火情配置项（谢振雷）。
    a. 优化代码，解决算法过慢的问题。
    b. 配合java组解决显示方案。
8. 概要设计文档（宋毅，彭亮）；
    a. 与甲方讨论产品清单。
    b. 与甲方对接概设文档修改稿。

本周工作进展
1. 雾检测配置项（陈彦红）：
    a. 大雾判识算法优化（完成30%）；
    b. 大雾统计分析和影响评估功能对接，测试、部署（完成80%，已部署测试，未对接）。
2. 干旱配置项（白罩峰，杜进慧，王金英）：
    a. 完成了NDVI、VSWI、TVDI的工程化改造以及测试和部署。
3. 火山检测配置项（牛太阳）：
    a. 完成了ads和docker测试服务器进行维护，辅助其他算法的测试工作；
    b. 优化了火山热点监测算法，提高了运算速度；
4. 太阳能配置项（刘方伟）：
    a. 代码工程化改造。
5. 台风配置项（彭亮，牛太阳）：
    a. 完善了大风圈算法的工程化。
    b. 设计了台风配置项的展示方案 。
6. 能量平衡配置项（卢婷婷）：
    a. 完成了能量平衡算法的工程化;
7. 火情配置项（谢振雷）。
    a. 优化代码解决了算法过慢的问题。
8. 概要设计文档（宋毅，彭亮）；
    a. 提交了产品清单。
    b. 提交了概设文档修改稿。

下周工作计划
1. 雾检测配置项（陈彦红）：
    a. 大雾判识算法优化；
    b. 大雾统计分析和影响评估功能测试和部署。
2. 干旱配置项（白罩峰，杜进慧，王金英）：
    a. 完成干旱配置项剩余指数的工程化和部署。
3. 火山检测配置项（牛太阳）：
    a. 测试部署优化的算法。
4. 太阳能配置项（刘方伟）：
    a. 代码工程化改造。
5. 台风配置项（彭亮，牛太阳）：
    a. 修改jason输出程序，完善配置项的输入输出细节。
    b. 设计辐合辐散的展示方式。
    c. 配合java组集成算法和网页展示。
6. 能量平衡配置项（卢婷婷）：
    a. 完成能量平衡算法的部署;
7. 火情配置项（谢振雷）。
    a. 部署测试优化代码。
8. 集成与维护（牛太阳，彭亮，陈明天）；
    a. 根据部署运行的情况，优化算法的部署和设计。


本周工作计划：
1. 雾检测配置项（陈彦红）：
    a. 大雾判识算法优化；
    b. 大雾统计分析和影响评估功能测试和部署。
2. 干旱配置项（白罩峰，杜进慧，王金英）：
    a. 完成干旱配置项剩余指数的工程化和部署。
3. 火山检测配置项（牛太阳）：
    a. 测试部署优化的算法。
4. 太阳能配置项（刘方伟）：
    a. 代码工程化改造。
5. 台风配置项（彭亮，牛太阳）：
    a. 修改jason输出程序，完善配置项的输入输出细节。
    b. 设计辐合辐散的展示方式。
    c. 配合java组集成算法和网页展示。
6. 能量平衡配置项（卢婷婷）：
    a. 完成能量平衡算法的部署;
7. 火情配置项（谢振雷）。
    a. 部署测试优化代码。
8. 集成与维护（牛太阳，彭亮，陈明天）；
    a. 根据部署运行的情况，优化算法的部署和设计。

本周工作进展：
1. 雾检测配置项（陈彦红）：
    a. 大雾判识算法优化完成；
    b. 大雾统计分析和影响完成测试。
2. 干旱配置项（白罩峰，杜进慧，王金英）：
    a. NDVI，VSWI，TVDI，ATI（候/周/旬/月/自定义）合成产品（等经纬投影/标称投影）反演算法100%
3. 火山检测配置项（牛太阳）：
    a. 完成算法的部署和对接。
4. 太阳能配置项（刘方伟）：
    a. 代码工程化改造。
5. 台风配置项（彭亮，牛太阳）：
    a. 修改了jason输出程序，完善了配置项的输入输出细节。
    b. 设计了辐合辐散的展示方式。
6. 完成了与甲方的对接，梳理了概要设计文档产品清单。
7. 集成与维护（牛太阳，卢婷婷）；
    a. 修改了算法产品命名规范。

下周工作计划：
1. 雾检测配置项（陈彦红）：
    a. 大雾判识优化算法测试和集成；
    b. 大雾统计分析和影响评估功能部署；
    c. 与外协方商讨集合预报算法的修改方案；
2. 干旱配置项（白罩峰，杜进慧，王金英）：
    a. VCI,TCI,VHI,MVSWI这几个产品的算法工程化及部署
3. 太阳能配置项（刘方伟）：
    a. 代码工程化改造和集成。
4. 台风配置项（彭亮，牛太阳）：
    a. 完成接口文档的编写。
    b. 配合java组集成算法和网页展示。
5. 能量平衡配置项（卢婷婷）：
    a. 完成能量平衡算法的集成部署;
6. 解决对流算法运行出现的问题（康晖）。
7. 集成与维护（牛太阳，彭亮，陈明天）；
    a. 根据部署运行的情况，优化算法的部署和设计。
8. 完善算法接口文档（算法开发人员）。

# 本周工作计划
1. 雾检测配置项（陈彦红）：
    a. 依据集合预报算法调整预报时长和频次。
2. 干旱配置项（白罩峰，杜进慧，王金英）：
    a. 开始干旱配置项算法的集成和上线。
3. 台风配置项（彭亮，牛太阳）：
    a. 完成算法的集成和测试。
4. 气溶胶配置项（刘方伟，姚蓓蓓，彭亮）
    a. 集成修改插值bug的算法。
5. 解决对流算法运行出现的问题（康晖，彭亮）。
    a. 开始部署对流配置项。
6. 集成与维护（牛太阳，彭亮，陈明天）；
    a. 继续集成与更新代码。

# 本周工作进展
1. 雾检测配置项（陈彦红）：
    a. 完成依据集合预报算法调整预报时长和频次。
2. 干旱配置项（白罩峰，杜进慧，王金英）：
    a. 完成了干旱配置项算法的集成，完成了把部分接口文档。
3. 台风配置项（彭亮，牛太阳）：
    a. 完成算法的集成。
4. 气溶胶配置项（刘方伟，姚蓓蓓，彭亮）
    a. 修改了AOD计算中出现的bug。
5. 解决对流算法运行出现的问题（康晖，彭亮）。
    a. 测试了外推的算法，并在docker中进行了更新。
6. 集成与维护（牛太阳，彭亮，陈明天）；
    a. 继续集成与更新代码。
7. 云图解译：
    a. 测试了部分外协代码（宋毅，谢振雷，卢婷婷）。

# 下周工作计划
1. 雾检测配置项（陈彦红）：
    a. 集成部署调整预报时长和频次的集成预报算法。
2. 干旱配置项（白罩峰，杜进慧，王金英）：
    a. 开始干旱配置项算法上线。
3. 台风配置项（彭亮，牛太阳）：
    a. 周一完成集成。
4. 气溶胶配置项（刘方伟，姚蓓蓓，彭亮）
    a. 部署修改后的算法。
5. 解决对流算法运行出现的问题（康晖，彭亮）。
    a. 部署对流配置项。
6. 集成与维护（牛太阳，彭亮，陈明天）；
    a. 继续集成与更新代码。
7. 云图解译：
    a. 继续测试外协代码（宋毅，谢振雷，卢婷婷）。

本周工作计划
1. 能量平衡配置项（卢婷婷）
    a. 代码调试与修改
    b. 编写接口文档
    c. 服务器部署测试算法
2. 火情配置项
    a. 上线测试（张亚男，谢振雷）
    b. 火情统计产品（谢振雷）
    c. 火判识调研调优（谢振雷）
3. 地表温度
    a. 修改城市热岛数据在切图发布中的数据范围、数据与色标不一致问题修改（陈彦红）
    b. 统计产品开发（陈彦红）
4. 太阳能配置项（刘方伟）
    a. 修改bug并进行代码工程化

本周工作计划:
1.能量平衡配置项（卢婷婷）
  a.算法上线测试
  b.优化算法，适配全圆盘
2.火情配置项
  a.继续火判识调研调优（谢振雷）
3.地表温度
  b.统计产品开发（陈彦红）（完成）
4.太阳能配置项（刘方伟）
  a.修改bug并进行代码工程化（80%）
5.云图解译配置项（谢振雷，宋毅）
  b.继续代码工程化
  c.服务器测试
6. 火山灰配置项（牛太阳）
  a.梳理新的算法文档，开始工程化
7. 优化统计算法功能（笪宏志）
  a.根据各个算法反馈的需求，优化统计代码

本周工作进展
1.能量平衡配置项（卢婷婷）
  a.算法上线测试
  b.开始解析预报场资料，适配全圆盘
2.火情配置项
  a.火判识调研调优（完成50%）（谢振雷）
3.地表温度
  b.开始编写试运行报告（30%）（陈彦红）
4.太阳能配置项（刘方伟）
  a.修改bug并进行代码工程化（80%）
  b.开始准备试运行报告
5.云图解译配置项（谢振雷，宋毅）
  a.开始进行试运行报告
  b.继续代码工程化
  c.服务器测试完成工程化的算法
6. 火山灰配置项（牛太阳）
  a.梳理新的算法文档，开始工程化
7. 优化统计算法功能（笪宏志）
  a.根据各个算法反馈的需求，优化统计代码(完成70%)

下周工作计划
1.能量平衡配置项（卢婷婷）
  a.与java组继续进行上线测试
  b.继续完善适配全圆盘的算法
2.火情配置项
  a.继续火判识调研调优（谢振雷）
  b.准备试运行报告
3.地表温度
  b.继续试运行报告（陈彦红）（完成）
4.太阳能配置项（刘方伟）
  a.修改bug并进行代码工程化（80%）
5.云图解译配置项（谢振雷，宋毅）
  b.继续代码工程化
  c.服务器测试
6. 火山灰配置项（牛太阳）
  a.根据算法文档进行工程化
7. 优化统计算法
  a.完成对算法的优化
8. 台风配置项
  a. 与java组核实格式，测试上线、显示新的配置项

本周工作计划：
1.能量平衡配置项（卢婷婷）
  a.与java组继续进行上线测试
  b.继续完善适配全圆盘的算法
2.火情配置项
  a.继续火判识调研调优（谢振雷）
  b.准备试运行报告
3.地表温度
  b.继续试运行报告（陈彦红）（完成）
4.太阳能配置项（刘方伟）
  a.修改bug并进行代码工程化（80%）
5.云图解译配置项（谢振雷，宋毅）
  a.继续代码工程化
  b.服务器测试
   c.完成示例结果切图、上线
6. 火山灰配置项（牛太阳）
  a.根据新收到的算法文档进行工程化
7. 优化统计算法
  a.完成对算法的优化
8. 台风配置项
  a. 与java组核实格式，测试上线、显示新的配置项
   b. 完成台风界面设计梳理，并将专题设计方案与美工对接，落实
9. 对流专题界面设计
10. 开始沙尘、火山灰路径预测hysplit(宋毅)

本周工作进展：
1.能量平衡配置项（卢婷婷）
  a.修改地表相对蒸散产品生成代码，流程走通（80%）
  b.TBB、OLR绘图完善(100%)
2.火情配置项
  a.熟悉烟雾idl代码并修改（谢振雷）
3.地表温度
  b.完成了部分试运行报告（陈彦红）（完成）
4.太阳能配置项（刘方伟）
  a.修改bug并进行代码工程化（80%）
5.云图解译配置项（谢振雷，宋毅）
  a.督促南信大提供新的代码
  b.工程化和测试发过来的新的代码
6. 火山灰配置项（牛太阳）
  a.根据新收到的算法文档进行工程化
7. 优化统计算法
  a.完成对算法的优化
8. 对流专题界面设计
  a.梳理了对流专题界面

下周工作计划
1.能量平衡配置项（卢婷婷）
  a.继续完善适配全圆盘的算法
  b.完善出图程序
2.火情配置项
  a.继续调式收到烟雾判识idl代码（谢振雷）
3.太阳能配置项（刘方伟）
  a.修改bug并进行代码工程化
4.云图解译配置项（谢振雷，宋毅）
  a.继续督促南信大修改代码
  b.继续代码工程化
5. 火山灰配置项（牛太阳）
  a.继续根据新收到的算法文档进行工程化
6. 优化统计算法
  a.和java组以及子系统负责人测试统计算法
7. 台风配置项
  a. 与java组核实格式，测试上线、显示新的配置项
  b. 完成台风界面设计梳理，并将专题设计方案与美工对接，落实
8. 对流专题界面设计
  a.上线测试梳理好的对流界面
9. 开始沙尘、火山灰路径预测hysplit(宋毅)
10. 完陈沙尘沉降代码的修改（彭亮，刘方伟）


本周工作计划：
1.能量平衡配置项（卢婷婷）
  a.继续完善适配全圆盘的算法
  b.完善出图程序
2.火情配置项
  a.继续调式收到烟雾判识idl代码（谢振雷）
3.太阳能配置项（刘方伟）
  a.修改bug并进行代码工程化
4.云图解译配置项（谢振雷，宋毅）
  a.继续督促南信大修改代码
  b.继续代码工程化
5. 火山灰配置项（牛太阳）
  a.继续根据新收到的算法文档进行工程化
6. 优化统计算法
  a.和java组以及子系统负责人测试统计算法
7. 台风配置项
  a. 与java组核实格式，测试上线、显示新的配置项
  b. 完成台风界面设计梳理，并将专题设计方案与美工对接，落实
8. 对流专题界面设计
  a.上线测试梳理好的对流界面
9. 开始沙尘、火山灰路径预测hysplit(宋毅)
10. 完成沙尘沉降代码的修改（彭亮，刘方伟）

本周工作进展：
1.能量平衡配置项（卢婷婷）
  a.适配全圆盘的算法（完成）
2.火情配置项
  a.调式成功烟雾判识idl代码（100%）（谢振雷）
  b.梳理了缺项（宋毅，谢振雷）
3.太阳能配置项（刘方伟）
  a.修改bug并进行代码工程化(90%)
4.云图解译配置项（谢振雷，宋毅）
  a.完成了70%代码的测试，并提交给了JAVA组（谢振雷）
  b.已完成云图解译代码的测试（张亚男，谢振雷）
5. 火山灰配置项（牛太阳）
  a.火山热点切图上线（张亚男，牛太阳）
  b.完成火山灰算法的开发和测试（需要优化）
6. 优化统计算法
  a.完成了统计算法的优化（笪宏志）
7. 台风配置项
  a. 与java组核实了格式输出，docker中完成测试（彭亮）
8. 对流专题界面设计
  a.上线测试梳理好的对流界面
9. 完成沙尘沉降代码的修改（彭亮，刘方伟）

下周工作计划：
1.能量平衡配置项（卢婷婷）
  a.Docker测试成功
  b.切图上线
2.火情配置项
  a.对缺项进行补充（谢振雷）
  b.对接发布（谢振雷）
3.太阳能配置项（刘方伟）
  a.修改完bug并在linux下调试
  b.切图上线
4.云图解译配置项（谢振雷，宋毅）
  a.云分类代码工程化和测试
  b.分类代码的上线切图
5. 火山灰配置项（牛太阳）
  a.继续根据新收到的算法文档进行工程化
6. 统计算法结果切图上线
  a.各个子系统统计结果上线。
7. 台风配置项
  a.降水大风切图上线
8. 对流专题界面设计
  a.上线测试梳理好的对流界面
9. 开始沙尘、火山灰路径预测hysplit(宋毅)
10. 完成沙尘沉降上线切图（彭亮，刘方伟）

云图解译：
完成现有版本公司集成测试， 输出结果与切图、前端对接，在test_geofy上线（谢振雷）； 确认（宋毅）
与南信大明确剩余任务开发计划及提交成果（宋毅）

台风：
完成台风界面梳理（彭亮、宋毅）
完成台风大风、降水等样例结果 与 切图、前端对接，在test_geofy上线（彭亮）；确认（宋毅）

强对流：
前端对流专题界面修改 （宋毅对接Java）
完成对流城市统计结果 入库， 城市统计结果上线显示 （宋毅对接java）

闪电子系统：
任务梳理完成（彭亮），分配任务给具体算法人员（杜进慧），开始研发工作（杜进慧，彭亮）
正常，目前接近完成对流强度与闪电频次的开发。

太阳能：
完成工程化，在公司服务器部署测试完成，输出结果与切图、前端对接，在test_geofy上线（刘方伟、彭亮）； 确认（宋毅）


亚洲夏季风：
确认亚洲夏季风指数计算，在test_geofy上线；（袁国言、宋毅）
纬向、径向算法集成、结果在前端对接上线 （笪宏志、宋毅）


能量平衡：
完成全圆盘算法工程化，在公司服务器部署测试完成，输出结果与切图、前端对接，在test_geofy上线（卢婷婷、彭亮）； 确认（宋毅）
进展顺利，流程走通，正在修改bug

沙尘沉降
完成工程化，在公司服务器部署测试完成，输出结果与切图、前端对接，在test_geofy上线（刘方伟、彭亮）； 确认（宋毅）

火山灰：
火山热点结果 入库，结果上线显示（牛太阳、宋毅）
火山浓度预测算法调研确认（宋毅）
正常

火情：
火点判识结果 入库，结果上线显示（谢振雷、宋毅）
正常

生态各个子系统（太阳能：刘方伟，沙尘：刘方伟，大雾：陈彦红，气溶胶：姚蓓蓓，火情：谢振雷，积雪：赵海博，干旱：白罩峰，能量平衡：卢婷婷，地表温度：陈彦红，蓝藻：笪宏志）统计分析功能，在公司服务器测试（各子系统负责人，彭亮、笪宏志），统计结果与切图、前端对接，在test_geofy上线。


本周工作计划：
1.能量平衡配置项（卢婷婷）
   a.Docker测试成功
   b.切图上线
2.火情配置项
   a.对缺项进行补充（谢振雷）
   b.对接发布（谢振雷）
3.太阳能配置项（刘方伟）
   a.修改完bug并在linux下调试
   b.切图上线
4.云图解译配置项（谢振雷，宋毅）
   a.云分类代码工程化和测试
   b.分类代码的上线切图
5. 火山灰配置项（牛太阳）
   a.继续根据新收到的算法文档进行工程化
6. 统计算法结果切图上线
   a.各个子系统统计结果上线。
7. 台风配置项
   a.降水大风切图上线
8. 对流专题界面设计
   a.上线测试梳理好的对流界面
9. 开始沙尘、火山灰路径预测hysplit(宋毅)
10. 完成沙尘沉降上线切图（彭亮，刘方伟）
11. 闪电子系统算法工程化（杜进慧）

本周工作进展：
1.能量平衡配置项（卢婷婷）
   a.Docker测试成功
   b.完成统计算法测试
2.火情配置项
   a.完成了对缺项（火点强度变化、火点空间变化、火线长度、火势类型；火点持续时间、火区中各种地类占比）的补充（谢振雷）
   b.对接发布（与前端进行了对接，需要跟进效果）
3.太阳能配置项（刘方伟）
   a.修改了C++程序中的bug，并调试成功（刘方伟，王峰，彭亮）
   b.完成了python对程序的封装和调用，并完成了输出NC的python代码（彭亮，陈彦红）
4.云图解译配置项（谢振雷，宋毅）
   a.云分类代码工程化和测试
   b.分类代码的上线切图
5. 火山灰配置项（牛太阳）
   a.对丙方的代码和文档进行了梳理
6. 统计算法结果切图上线
   a.各个子系统负责人完成了测试数据的生成和工程化文档的完善（包括单日和多日的）。
7. 闪电子系统算法工程化（杜进慧）
   a.完成了闪电频数与对流初生关系的算法（后续要对算法进行速度优化）

下周工作计划：
1.能量平衡配置项（卢婷婷）
   a.切图上线（与张亚男对接完成test网页端的展示）
   b.算法精度检验和优化（对比临近时次的中国区和全圆盘的产品，判断是否需要采用融合算法）
2.火情配置项
   a.完成火点强度变化、火点空间变化、火线长度、火势类型；火点持续时间、火区中各种地类占比的工程化文档（谢振雷）
   b.和张亚男对接并跟进完成切图上线工作（谢振雷）
3.太阳能配置项（刘方伟）
   a.完成工程化代码的docker封装和测试（彭亮）。
   b.与前端完成对接（工程化文档的撰写，跟进测试上线）（刘方伟）
4.云图解译配置项（谢振雷，宋毅）
   a.云分类代码工程化和测试
   b.分类代码的上线切图
5. 火山灰配置项（牛太阳）
   a.火山灰云的判识需要明确方案（彭亮，宋毅，牛太阳）
   b.确立方案完成火山灰云的判识和扩散算法的融合展示（彭亮，宋毅，牛太阳）
6. 统计算法结果切图上线
   a.提交统计工程化文档，并跟进前端的展示（笪宏志）
7. 台风配置项
   a.台风配置项的展示和其他算法有较大差异，下周需要和java组尽快确认展示方式以明确数据最终输出格式（彭亮）。
8. 对流专题界面设计
   a.和孙乃秀完成对流释用算法的测试（彭亮，孙乃秀）
   b.梳理对流配置项的缺项，明确补充方案（彭亮，宋毅）
9. 完成沙尘沉降上线切图（彭亮，刘方伟）
10. 闪电子系统算法工程化（杜进慧）
   a.闪电与深对流关系分析算法工程化（杜进慧，彭亮）

明确能量平衡算法中的”距平“。
明确统计算法中的图片的开发。

本周工作计划
1.能量平衡配置项（卢婷婷）
    a.切图上线（与张亚男对接完成test网页端的展示）
    b.算法精度检验和优化（对比临近时次的中国区和全圆盘的产品，判断是否需要采用融合算法）
    c.明确缺项的开发路线（如“距平”的明确含义和算法）
2.火情配置项
    a.完成火点强度变化、火点空间变化、火线长度、火势类型；火点持续时间、火区中各种地类占比的工程化文档（谢振雷）
    b.和张亚男对接并跟进完成切图上线工作（谢振雷）
3.太阳能配置项（刘方伟）
    a.完成工程化代码的docker封装和测试（彭亮）。
    b.与前端完成对接（工程化文档的撰写，跟进测试上线）（刘方伟）
4.云图解译配置项（谢振雷，宋毅）
    a.继续工程化和测试（谢振雷）。
    b.督促丙方完成算法的统计，梳理缺项，明确缺项的开发方案（宋毅，彭亮）。
5. 火山灰配置项（牛太阳）
    a.火山灰云的判识需要明确方案（彭亮，宋毅，牛太阳）
    b.确立方案完成火山灰云的判识和扩散算法的综合展示（彭亮，宋毅，牛太阳）
6. 统计算法结果切图上线
    a.提交统计工程化文档，并跟进前端的展示（笪宏志）
    b.明确统计算法中图片产品的开发路线（彭亮，宋毅）
7. 台风配置项
    a.台风配置项的展示和其他算法有较大差异，下周需要和java组尽快确认展示方式以明确数据最终输出格式（彭亮）。
8. 对流专题
    a.和孙乃秀完成对流释用算法的测试（彭亮，孙乃秀）
    b.梳理对流配置项的缺项，明确补充方案（彭亮，宋毅）
9. 完成沙尘沉降上线切图（彭亮，刘方伟）
10. 闪电子系统算法工程化（杜进慧）
    a.闪电与深对流关系分析算法工程化（杜进慧，彭亮）
    b.明确闪电与对流关系展示方式（具体的图表形式，彭亮，杜进慧）

本周工作进展：
2.火情配置项
    a.火判识优化开发：完成潜在火点部分优化工作；
3.太阳能配置项（刘方伟）
    b.与前端完成切图上线的对接（彭亮）
4.云图解译配置项（谢振雷，宋毅）
    a.继续工程化和测试（谢振雷）。
    b.督促丙方完成算法的统计，梳理缺项，明确缺项的开发方案（宋毅，彭亮）。
5. 火山灰配置项（牛太阳）
    a.调试了扩散模型；
    b.明确火山灰云的判识按照区域阈值的方案进行。
6. 统计算法结果切图上线
    a.提交了统计工程化文档，正在切图（笪宏志）
9. 完成沙尘沉降上线切图（彭亮，刘方伟）
    a.已提交测试样例，发现问题需要修改（彭亮）。
10. 闪电子系统算法工程化（杜进慧）
    完成闪电频数与对流强度算法运行效率优化，并调整散点图样式；


1.能量平衡配置项（卢婷婷）
    a.切图上线（与张亚男对接完成test网页端的展示）
    b.算法精度检验和优化（对比临近时次的中国区和全圆盘的产品，判断是否需要采用融合算法）
    c.明确缺项的开发路线（如“距平”的明确含义和算法）
2.火情配置项
    a.完成火点强度变化、火点空间变化、火线长度、火势类型；火点持续时间、火区中各种地类占比的工程化文档（谢振雷）
    b.和张亚男对接并跟进完成切图上线工作（谢振雷）
3.太阳能配置项（刘方伟）
    a.完成工程化代码的docker封装和测试（彭亮）。
    b.完善工程化文档的撰写（刘方伟）
4.云图解译配置项（谢振雷，宋毅）
    a.继续工程化和测试（谢振雷）。
    b.督促丙方完成算法的统计，梳理缺项，明确缺项的开发方案（宋毅，彭亮）。
5. 火山灰配置项（牛太阳）
    a.继续调试扩散算法（牛太阳）
    b.确立方案完成火山灰云的判识和扩散算法的综合展示（彭亮，宋毅，牛太阳）
6. 统计算法结果切图上线
    a.跟进前端的展示（笪宏志）
    b.明确统计算法中图片产品的开发路线（彭亮，宋毅）
7. 台风配置项
    a.台风配置项的展示和其他算法有较大差异，下周需要和java组尽快确认展示方式以明确数据最终输出格式（彭亮）。
8. 对流专题
    a.和孙乃秀完成对流释用算法的测试（彭亮，孙乃秀）
    b.梳理对流配置项的缺项，明确补充方案（彭亮，宋毅）
9. 跟进核实沙尘沉降上线切图（彭亮，刘方伟）
10. 闪电子系统算法工程化（杜进慧）
    a.实现中国区域闪电落区与暴雨强对流落区相关性分析功能；

本周工作计划:
1.能量平衡配置项（卢婷婷）
     a.切图上线（与张亚男对接完成test网页端的展示）
     b.算法精度检验和优化（对比临近时次的中国区和全圆盘的产品，判断是否需要采用融合算法）
     c.明确缺项的开发路线（如“距平”的明确含义和算法）
2.火情配置项
     a.完成火点强度变化、火点空间变化、火线长度、火势类型；火点持续时间、火区中各种地类占比的工程化文档（谢振雷）
     b.和张亚男对接并跟进完成切图上线工作（谢振雷）
3.太阳能配置项（刘方伟）
     a.完成工程化代码的docker封装和测试（彭亮）。
     b.完善工程化文档的撰写（刘方伟）
4.云图解译配置项（谢振雷，宋毅）
     a.继续工程化和测试（谢振雷）。
     b.督促丙方完成算法的统计，梳理缺项，明确缺项的开发方案（宋毅，彭亮）。
5. 火山灰配置项（牛太阳）
     a.继续调试扩散算法（牛太阳）
     b.确立方案完成火山灰云的判识和扩散算法的综合展示（彭亮，宋毅，牛太阳）
6. 统计算法结果切图上线
     a.跟进前端的展示（笪宏志）
     b.明确统计算法中图片产品的开发路线（彭亮，宋毅）
7. 台风配置项
     a.台风配置项的展示和其他算法有较大差异，下周和java组尽快确认展示方式以明确数据最终输出格式（彭亮）。
8. 对流专题
     a.和孙乃秀完成对流释用算法的测试（彭亮，孙乃秀）
     b.梳理对流配置项的缺项，明确补充方案（彭亮，宋毅）
9. 跟进核实沙尘沉降上线切图（彭亮，刘方伟）
10. 闪电子系统算法工程化（杜进慧）
     a.实现中国区域闪电落区与暴雨强对流落区相关性分析功能；
11. 沙尘判识：
     确立沙尘计算区域并升级代码（刘方伟）

本周工作进展：
1.能量平衡配置项（卢婷婷）
     a.切图上线（与张亚男对接完成test网页端的展示）
     b.算法精度检验和优化（对比临近时次的中国区和全圆盘的产品，判断是否需要采用融合算法）
     c.明确缺项的开发路线（如“距平”的明确含义和算法）
2.火情配置项
     a.完成火点强度变化、火点空间变化、火线长度、火势类型；火点持续时间、火区中各种地类占比的工程化文档（谢振雷）
     b.和张亚男对接并跟进完成切图上线工作（谢振雷）
3.太阳能配置项（刘方伟）
     a.完成工程化代码的docker封装和测试（彭亮）。
     b.完善工程化文档的撰写（刘方伟）
4.云图解译配置项（谢振雷，宋毅）
     a.继续工程化和测试（谢振雷）。
     b.督促丙方完成算法的统计，梳理缺项，明确缺项的开发方案（宋毅，彭亮）。
5. 火山灰配置项（牛太阳）
     a.继续调试扩散算法（牛太阳）
     b.确立方案完成火山灰云的判识和扩散算法的综合展示（彭亮，宋毅，牛太阳）
6. 统计算法结果切图上线
     a.跟进前端的展示（笪宏志）
     b.明确统计算法中图片产品的开发路线（彭亮，宋毅）
7. 台风配置项
     a.台风配置项的展示和其他算法有较大差异，下周和java组尽快确认展示方式以明确数据最终输出格式（彭亮）。
8. 对流专题
     a.和孙乃秀完成对流释用算法的测试（彭亮，孙乃秀）
     b.梳理对流配置项的缺项，明确补充方案（彭亮，宋毅）
9. 跟进核实沙尘沉降上线切图（彭亮，刘方伟）
10. 闪电子系统算法工程化（杜进慧）
     a.实现中国区域闪电落区与暴雨强对流落区相关性分析功能；
11. 沙尘判识：
     确立沙尘计算区域并升级代码（刘方伟）

下周工作计划：
1.能量平衡配置项（卢婷婷）
     a.切图上线（与张亚男对接完成test网页端的展示）
     b.算法精度检验和优化（对比临近时次的中国区和全圆盘的产品，判断是否需要采用融合算法）
     c.明确缺项的开发路线（如“距平”的明确含义和算法）
2.火情配置项
     a.完成火点强度变化、火点空间变化、火线长度、火势类型；火点持续时间、火区中各种地类占比的工程化文档（谢振雷）
     b.和张亚男对接并跟进完成切图上线工作（谢振雷）
3.太阳能配置项（刘方伟）
     a.完成工程化代码的docker封装和测试（彭亮）。
     b.完善工程化文档的撰写（刘方伟）
4.云图解译配置项（谢振雷，宋毅）
     a.继续工程化和测试（谢振雷）。
     b.督促丙方完成算法的统计，梳理缺项，明确缺项的开发方案（宋毅，彭亮）。
5. 火山灰配置项（牛太阳）
     a.继续调试扩散算法（牛太阳）
     b.确立方案完成火山灰云的判识和扩散算法的综合展示（彭亮，宋毅，牛太阳）
6. 统计算法结果切图上线
     a.跟进前端的展示（笪宏志）
     b.明确统计算法中图片产品的开发路线（彭亮，宋毅）
7. 台风配置项
     a.台风配置项的展示和其他算法有较大差异，下周和java组尽快确认展示方式以明确数据最终输出格式（彭亮）。
8. 对流专题
     a.和孙乃秀完成对流释用算法的测试（彭亮，孙乃秀）
     b.梳理对流配置项的缺项，明确补充方案（彭亮，宋毅）
9. 跟进核实沙尘沉降上线切图（彭亮，刘方伟）
10. 闪电子系统算法工程化（杜进慧）
     a.实现中国区域闪电落区与暴雨强对流落区相关性分析功能；
11. 沙尘判识：
     确立沙尘计算区域并升级代码（刘方伟）

本周工作计划：
1.能量平衡配置项（卢婷婷）
      a.继续其他产品的切图上线（与张亚男对接完成test网页端的展示）
2.火情配置项
      a.根据试集成的结果，优化代码。
3.太阳能配置项（刘方伟）
      a.继续集成并检查问题。
4.云图解译配置项（谢振雷，宋毅）
      a.继续工程化和测试（谢振雷）。
      b.试集成。
5. 火山灰配置项（牛太阳）
      a.火山灰扩散、火山灰浓度的工程化改造。
6. 统计算法结果切图上线
      a.继续跟进前端的展示（笪宏志）
7. 台风配置项
      a.集成完整版。
8. 对流专题
      b.测试剩余项，准备集成
9. 跟进核实沙尘沉降上线切图（彭亮，刘方伟）
     a.切图上线.
     b.集成。
10. 闪电子系统算法工程化（杜进慧）
      a.实现闪电频次跃变与对流强度相关性分析功能；
11. 沙尘判识：
      确立沙尘计算区域并升级代码（刘方伟）
本周工作进展：
1.能量平衡配置项（卢婷婷）
      a.在气象局服务器进行了部署和测试。
2.火情配置项
      b.在气象局进行了部署，发现bug，进行了修改。
3.太阳能配置项（刘方伟）
      a.在气象局服务器进行了部署。
4.云图解译配置项（谢振雷，宋毅）
      a.继续工程化和测试（谢振雷）。
5. 火山灰配置项（牛太阳）
      a.进行火山灰判识和高度算法的封装和测试。
6. 统计算法结果切图上线
      a.部署了统计算法。
7. 台风配置项
      a.气象局部署了完整版。
8. 跟进核实沙尘沉降上线切图（彭亮，刘方伟）
      a.气象局服务器进行了试集成。
10. 闪电子系统算法工程化（杜进慧）
      a.实现了闪电频次跃变与对流强度相关性分析功能；
# 1}}}
下周工作计划：
1.能量平衡配置项（卢婷婷）
      a.根据试集成的结果完善算法。
2.火情配置项
      a.根据试集成的结果优化代码。
3.太阳能配置项（刘方伟，彭亮，白罩峰）
      a.继续集成并检查问题，并开始填补缺项。
4.云图解译配置项（谢振雷，宋毅）
      a.继续工程化和测试（谢振雷）。
      b.试集成。
5. 火山灰配置项（牛太阳）
      a.根据试集成的结果修改问题。
6. 统计算法结果切图上线
      a.跟进统计的集成结果。
7. 台风配置项（彭亮）
      a.根据试集成的结果调整数据输出等问题。
8. 对流专题（彭亮，宋毅，康晖，孙乃秀）
      b.集成新的算法，并且修改出现的问题。
9. 跟进核实沙尘沉降上线切图（彭亮，刘方伟）
     b.集成沙尘沉降的算法并修改问题。
10. 闪电子系统算法工程化（杜进慧）
      a.继续闪电工程化（闪电频数变化与强对流强度估计功能,闪电频数变化与强对流强度估计功能）
11. AOD 融合
      a. 优化融合算法（彭亮，姚蓓蓓）。
      b. 优化沙尘判识算法（姚蓓蓓，赵海博）。

# 1}}}

本周工作计划：
1.能量平衡配置项（卢婷婷）
        a.根据试集成的结果完善算法。
2.火情配置项
        a.根据试集成的结果优化代码。
3.太阳能配置项（刘方伟，彭亮，白罩峰）
        a.继续集成并检查问题，并开始填补缺项。
4.云图解译配置项（谢振雷，宋毅）
        a.继续工程化和测试（谢振雷）。
        b.试集成。
5. 火山灰配置项（牛太阳）
        a.根据试集成的结果修改问题。
6. 统计算法结果切图上线
        a.跟进统计的集成结果。
7. 台风配置项（彭亮）
        a.根据试集成的结果调整数据输出等问题。
8. 对流专题（彭亮，宋毅，康晖，孙乃秀）
        b.集成新的算法，并且修改出现的问题。
9. 跟进核实沙尘沉降上线切图（彭亮，刘方伟）
        b.集成沙尘沉降的算法并修改问题。
10. 闪电子系统算法工程化（杜进慧）
        a.继续闪电工程化（闪电频数变化与强对流强度估计功能,闪电频数变化与强对流强度估计功能）
11. AOD 融合
		a. 优化融合算法（彭亮，姚蓓蓓）。
		b. 优化沙尘判识算法（姚蓓蓓，赵海博）。
本周工作进展
1.云图解译配置项（谢振雷，宋毅）
        a.部署了云图解译部分算法到气象局服务器。
2. 台风配置项（彭亮）
        a.修改了台风配置项中风场输出格式。
        b.提交了工程化文档和测试数据给前端。
        c.在气象局部署了新的算法。
3. 对流专题（彭亮，宋毅，康晖，孙乃秀）
        a.在气象局服务器更新了算法。
4. 沙尘沉降（彭亮，刘方伟）
        a.修改了代码，避免并行运算出错。
5. AOD 融合
		a. 利用海陆掩膜去掉了海面上的灰霾气溶胶（姚蓓蓓，刘方伟）。
下周工作计划
1.能量平衡配置项（卢婷婷）
        a.测试几天的数据，检查算法精度。
2.火情配置项
        a.跟进部署后的结果。
3.太阳能配置项（刘方伟，彭亮，白罩峰）
        a.修改代码，将天文总辐射量输出。
4.云图解译配置项（谢振雷，宋毅）
        a.跟进集成结果，出部分测试报告（谢振雷）。
5. 火山灰配置项（牛太阳）
        a.继续跟进集成结果。
6. 统计算法结果切图上线
        a.配合JAVA组进行部署。
7. 台风配置项（彭亮）
        a.测试2019年整年的数据，调整部分算法。
8. 对流专题（彭亮，宋毅，康晖，孙乃秀）
        b.检查部署后的运算结果。
9. 跟进核实沙尘沉降上线切图（彭亮，刘方伟）
        b.集成沙尘沉降的算法并修改问题。
10. 闪电子系统算法工程化（杜进慧）
        a.继续闪电工程化（闪电频数变化与强对流强度估计功能,闪电频数变化与强对流强度估计功能）
11. AOD 融合
		a. 测试多时次数据（彭亮，姚蓓蓓）。

本周工作计划
1.能量平衡配置项（卢婷婷）
        a.测试几天的数据，检查算法精度。
2.火情配置项
        a.跟进部署后的结果。
3.太阳能配置项（刘方伟，彭亮，白罩峰）
        a.修改代码，将天文总辐射量输出。
4.云图解译配置项（谢振雷，宋毅）
        a.跟进集成结果，出部分测试报告（谢振雷）。
5. 火山灰配置项（牛太阳）
        a.继续跟进集成结果。
6. 统计算法结果切图上线
        a.配合JAVA组进行部署。
7. 台风配置项（彭亮）
        a.测试2019年整年的数据，调整部分算法。
8. 对流专题（彭亮，宋毅，康晖，孙乃秀）
        b.检查部署后的运算结果。
9. 跟进核实沙尘沉降上线切图（彭亮，刘方伟）
        b.集成沙尘沉降的算法并修改问题。
10. 闪电子系统算法工程化（杜进慧）
        a.继续闪电工程化（闪电频数变化与强对流强度估计功能,闪电频数变化与强对流强度估计功能）
11. AOD 融合
        a. 测试多时次数据（彭亮，姚蓓蓓）。
12. 部署亚洲夏季风
本周工作进展
1.能量平衡配置项（卢婷婷）
        a.测试几天的数据，检查算法精度。
2.火情配置项
        a.跟进部署后的结果。
3.太阳能配置项（刘方伟，彭亮，白罩峰）
        a.修改代码，将天文总辐射量输出。
4.云图解译配置项（谢振雷，宋毅）
        a.完成服务器上的测试，出现环境不全的问题，正在解决。
5. 统计算法结果切图上线
        a.进行了部署测试，对传参方式进行了修改。
6. 台风配置项（彭亮）
        a.在气象局部署了算法，并测试了2019年的数据，修改了部分代码。
7. 对流专题（彭亮，宋毅，康晖，孙乃秀）
        a.测试了对流中国区的算法。
		b.修改了城市信息算法，出了专题图，支持了林芝地区的人工天气作业。
8. 闪电子系统算法工程化（杜进慧）
        a.完成了闪电与降水落区的相关性开发。
9. AOD 融合
        a. 进行了服务器上的代码更新。
下周工作计划
1.能量平衡配置项（卢婷婷）
        a.拷贝已经运行的结果，测试算法精度。
2.火情配置项
        a.继续优化算法。
3.太阳能配置项（刘方伟，彭亮，白罩峰）
        a.修改代码，将天文总辐射量输出。
4.云图解译配置项（谢振雷，宋毅）
        a.完成服务器环境的配置。
5. 火山灰配置项（牛太阳）
        a.火山灰浓度算法工程化。
6. 统计算法结果切图上线
        a.根据新的算法工程化文档和代码重新集成。
7. 台风配置项（彭亮）
        a.和java组对接数据，切图上线。
8. 对流专题（彭亮，宋毅，康晖，孙乃秀）
        a.解决中国区出错的问题。
9. 跟进核实沙尘沉降上线切图（彭亮，刘方伟）
        b.集成沙尘沉降的算法。
10. 闪电子系统算法工程化（杜进慧）
        a.继续闪电工程化。
11. AOD 融合
        a.拷贝运行结果开始准备试运行报告。
12. 部署亚洲夏季风


本周工作计划
1.能量平衡配置项（卢婷婷）
        a.拷贝已经运行的结果，测试算法精度。
2.火情配置项
        a.继续优化算法。
3.太阳能配置项（彭亮，白罩峰）
        a.修改代码，将天文总辐射量输出。
4.云图解译配置项（谢振雷，宋毅）
        a.完成服务器环境的配置。
5. 火山灰配置项（牛太阳）
        a.火山灰浓度算法工程化。
6. 统计算法结果切图上线
        a.根据新的算法工程化文档和代码重新集成。
7. 台风配置项（彭亮）
        a.和java组对接数据，切图上线。
8. 对流专题（彭亮，宋毅，康晖，孙乃秀）
        a.解决中国区出错的问题。
9. 跟进核实沙尘沉降上线切图（彭亮）
        a.集成沙尘沉降的算法。
10. 闪电子系统算法工程化（杜进慧）
        a.继续闪电工程化。
11. AOD 融合
        a.拷贝运行结果开始准备试运行报告。
12. 部署亚洲夏季风
本周工作进展
1.火情配置项
        a.算法的优化效果不明显。
2.云图解译配置项（谢振雷，宋毅）
        a.完成了服务器docker环境的升级。
        b.测试了云图分类代码。
3. 统计算法结果切图上线
        a.集成了更新后的代码。
4. 台风配置项（彭亮，袁国言）
        a.测试数据，目前降水的数据需要转化成等经纬。
5. 对流专题（彭亮，宋毅，康晖，孙乃秀）
        a.完成了对流城市信息算法的修正。
6. 跟进核实沙尘沉降上线切图（彭亮）
        a.修改了NC输出程序。
7. 闪电子系统算法工程化（杜进慧）
        a.完成闪电频数分布密集区与强对流强度估计功能算法研制。
下周工作计划
1.能量平衡配置项（卢婷婷）
        a.开始写算法试运行报告。
2.火情配置项
        a.试运行报告素材准备。
3.太阳能配置项（彭亮，白罩峰）
        a.修改代码，将天文总辐射量输出。
4.云图解译配置项（谢振雷，宋毅）
        a.云图分类代码工程化。
6. 统计算法结果切图上线
        a.开始准备试运行报告。
7. 台风配置项（彭亮，袁国言）
        a.修改降水数据格式，切图上线。
        b.梳理台风界面。
8. 对流专题（彭亮，宋毅，康晖，孙乃秀，卢婷婷）
        a.完成对流释用的测试与集成。
9. 跟进核实沙尘沉降上线切图（彭亮）
        a.集成沙尘沉降的算法。
10. 闪电子系统算法工程化（杜进慧）
        a.将已有的算法进行工程化，添加到城市信息中。
11. AOD 融合 （姚蓓蓓，张晗，彭亮）
        a.边缘处仍然需要优化。
12. 部署亚洲夏季风（笪宏志）
13. 梳理产品的缺项，布置下一步任务。

本周工作计划
1.能量平衡配置项（卢婷婷）
      a.开始写算法试运行报告。
2.火情配置项
      a.试运行报告素材准备。
3.太阳能配置项（彭亮，白罩峰）
      a.修改代码，将天文总辐射量输出。
4.云图解译配置项（谢振雷，宋毅）
      a.云图分类代码工程化。
6. 统计算法结果切图上线
      a.开始准备试运行报告。
7. 台风配置项（彭亮，袁国言）
      a.修改降水数据格式，切图上线。
      b.梳理台风界面。
8. 对流专题（彭亮，宋毅，康晖，孙乃秀，卢婷婷）
      a.完成对流释用的测试与集成。
9. 跟进核实沙尘沉降上线切图（彭亮）
      a.集成沙尘沉降的算法。
10. 闪电子系统算法工程化（杜进慧）
      a.将已有的算法进行工程化，添加到城市信息中。
11. AOD 融合 （姚蓓蓓，张晗，彭亮）
      a.边缘处仍然需要优化。
12. 部署亚洲夏季风（笪宏志）
13. 梳理产品的缺项，布置下一步任务。
本周工作进展
1. 沙尘能见度
      a. 根据运行的情况对代码进行了更新，重新部署。
2. 台风配置项（彭亮，袁国言）
      a. 完成了降水数据格式的修改。
      b. 对台风展示界面进行了梳理。
3. 对流专题（彭亮，宋毅，康晖，孙乃秀，卢婷婷）
      a. 根据出现的问题更新了城市信息算法。
      b. 更新了深对流和快速发展对流的代码。
4. 闪电子系统算法工程化（杜进慧）
      a. 完成了相关性分析展示方式的梳理。
5. AOD 融合
      a. 梳理了灰霾判识的优化思路。
下周工作计划
1.能量平衡配置项（卢婷婷，彭亮）
      a. 确认试运行报告思路。
2.火情配置项（谢振雷，彭亮）
      a. 梳理试运行报告思路。
3.太阳能配置项（彭亮，田乐）
      a. 集成，上线测试。
4.云图解译配置项（谢振雷，宋毅）
      a. 云图分类代码工程化。
5. 台风配置项（彭亮，袁国言）
      a. 和java组对接新的调用方式（对程序做微调）
      b. 负责确认台风的上线和展示
      c. 根据运行的情况，修正可能出现的问题。
6. 对流专题（彭亮，宋毅，康晖，孙乃秀，卢婷婷）
      a. 梳理试运行报告的思路。
7. 闪电子系统算法工程化（杜进慧）
      a. 对算法运行过慢的问题进行优化。
      b. 根据梳理的思路，完善算法框架，推进算法工程化。
8. AOD 融合 （姚蓓蓓，张晗，彭亮）
      a. 优化灰霾判识。
9. 亚洲夏季风（笪宏志）
      a. 集成测试

本周工作计划
1.能量平衡配置项（卢婷婷，彭亮）
      a. 确认试运行报告思路。
2.火情配置项（谢振雷，彭亮）
      a. 梳理试运行报告思路。
3.太阳能配置项（彭亮，田乐）
      a. 集成，上线测试。
4.云图解译配置项（谢振雷，宋毅）
      a. 云图分类代码工程化。
5. 台风配置项（彭亮，袁国言）
      a. 和java组对接新的调用方式（对程序做微调）
      b. 负责确认台风的上线和展示
      c. 根据运行的情况，修正可能出现的问题。
6. 对流专题（彭亮，宋毅，康晖，孙乃秀，卢婷婷）
      a. 梳理试运行报告的思路。
7. 闪电子系统算法工程化（杜进慧）
      a. 对算法运行过慢的问题进行优化。
      b. 根据梳理的思路，完善算法框架，推进算法工程化。
8. AOD 融合 （姚蓓蓓，张晗，彭亮）
      a. 优化灰霾判识。
9. 亚洲夏季风（笪宏志）
      a. 集成测试
本周工作进展
1.能量平衡配置项（卢婷婷，彭亮）
      a. 确认试运行报告思路。
2.火情配置项（谢振雷，彭亮）
      a. 梳理试运行报告思路。
3.云图解译配置项（谢振雷，宋毅）
      a. 云图分类代码工程化。
4.台风配置项（彭亮，袁国言）
      a. 对程序进行了python改造。
5.对流专题（彭亮，宋毅，康晖，孙乃秀，卢婷婷）
      a. 梳理试运行报告的思路。
      b. 修改了深对流的代码（卢婷婷）。
7.闪电子系统算法工程化（杜进慧）
      b. 完成城市闪电信息统计。
8.AOD 融合 （姚蓓蓓，张晗，彭亮）
      a. 微调了灰霾判识的算法。
下周工作计划
1.能量平衡配置项（卢婷婷，彭亮）
      a. 编写试运行报告PPT和文档。
2.火情配置项（谢振雷，彭亮）
      a. 完成试运行报告文档和相关PPT。
3.太阳能配置项（彭亮，田乐）
      a. 完成试运行报告文档和相关PPT。
      b. 测试上线。
4.云图解译配置项（谢振雷，宋毅）
      a. 云图分类代码工程化。
      b. 协助完成试运行报告（云系识别，分类）。
5. 台风配置项（彭亮，牛太阳，袁国言）
      a. 负责确认台风的上线和展示
      b. 台风试运行报告：
      c. 定位定强：彭亮，大风：彭亮，降水，牛太阳
6. 对流专题（彭亮，宋毅，康晖，孙乃秀，卢婷婷）
      a. 编写试运行报告（包括对流判识，深对流判识，快速发展对流，对流外推，追踪）。
7. 闪电子系统算法工程化（杜进慧）
      a. 整理试运行报告（闪电频数时间变化与对流强度相关性等）
8. AOD配置项:
      a. 试运行报告：AOD判识(张晗)，PM分布（张晗，姚蓓蓓）
9. 亚洲夏季风（笪宏志）
      a. 试运行报告
10. 沙尘判识试运行报告（笪宏志）：
11. 火情配置项试运行报告（谢振雷）
      a. 火判识
      b. 火蔓延
12. 大雾判识试运行报告(陈彦红)
13. 积雪百分比试运行报告(赵海博)
14. 地表温度精度试运行报告(陈彦红，赵海博)
15. 蓝藻判识试运行报告(笪宏志)
16. 统计算法试运行报告（笪宏志）


本周工作计划
1.能量平衡配置项（卢婷婷，彭亮）
      a. 编写试运行报告PPT和文档。
2.火情配置项（谢振雷，彭亮）
      a. 完成试运行报告文档和相关PPT。
3.太阳能配置项（彭亮，田乐）
      a. 完成试运行报告文档和相关PPT。
      b. 测试上线。
4.云图解译配置项（谢振雷，宋毅）
      a. 云图分类代码工程化。
      b. 协助完成试运行报告（云系识别，分类）。
5. 台风配置项（彭亮，牛太阳，袁国言）
      a. 负责确认台风的上线和展示
      b. 台风试运行报告：
      c. 定位定强：彭亮，大风：彭亮，降水，牛太阳
6. 对流专题（彭亮，宋毅，康晖，孙乃秀，卢婷婷）
      a. 编写试运行报告（包括对流判识，深对流判识，快速发展对流，对流外推，追踪）。
7. 闪电子系统算法工程化（杜进慧）
      a. 整理试运行报告（闪电频数时间变化与对流强度相关性等）
8. AOD配置项:
      a. 试运行报告：AOD判识(张晗)，PM分布（张晗，姚蓓蓓）
9. 亚洲夏季风（笪宏志）
      a. 试运行报告
10. 沙尘判识试运行报告（笪宏志）：
11. 火情配置项试运行报告（谢振雷）
      a. 火判识
      b. 火蔓延
12. 大雾判识试运行报告(陈彦红)
13. 积雪百分比试运行报告(赵海博)
14. 地表温度精度试运行报告(陈彦红，赵海博)
15. 蓝藻判识试运行报告(笪宏志)
16. 统计算法试运行报告（笪宏志）

本周工作进展
1.能量平衡配置项（卢婷婷，彭亮）
      a. 完成初稿。
2.火情配置项（谢振雷，彭亮）
      a. 完成初稿。
4.云图解译配置项（谢振雷，宋毅）
      b. 完成初稿。
5. 台风配置项（彭亮，牛太阳，袁国言）
      b. 台风试运行报告：完成初稿。
6. 对流专题（彭亮，宋毅，康晖，孙乃秀，卢婷婷）
      a. 完成初稿。
7. 闪电子系统算法工程化（杜进慧）
      a. 完成初稿
8. AOD配置项:
      a. 试运行报告：AOD完成初稿
10. 沙尘判识试运行报告（笪宏志）：
      a. 完成初稿。
11. 火情配置项试运行报告（谢振雷）
      a. 完成初稿。
12. 大雾判识试运行报告(陈彦红)
      a. 完成初稿。
13. 积雪百分比试运行报告(赵海博)
      a. 完成初稿。
14. 地表温度精度试运行报告(陈彦红，赵海博)
      a. 完成初稿。
15. 蓝藻判识试运行报告(笪宏志)
      a. 完成初稿。
下周工作计划
1.能量平衡配置项（卢婷婷，彭亮）
      a. 更新验证结果。
2.火情配置项（谢振雷，彭亮）
      a. 更新验证结果。
3.太阳能配置项（彭亮，田乐）
      a. 完成试运行报告文档和相关PPT。
      b. 测试上线。
4.云图解译配置项（谢振雷，宋毅）
      a. 云图分类代码工程化。
      b. 更新验证结果。
5. 台风配置项（彭亮，牛太阳，袁国言）
      a. 完成PYTHON代码BUG修正。
      b. 台风试运行报告验证结果更新。
6. 对流专题（彭亮，宋毅，康晖，孙乃秀，卢婷婷）
      a. 更新验证结果。
7. 闪电子系统算法工程化（杜进慧）
      a. 核对验证结果。
8. AOD配置项:
      a. 更新验证结果。
9. 亚洲夏季风（笪宏志）
      a. 试运行报告
10. 沙尘判识试运行报告（笪宏志）：
      a. 更新验证数据。
11. 火情配置项试运行报告（谢振雷）
      a. 更新验证数据。
12. 大雾判识试运行报告(陈彦红)
      a. 更新验证数据。
13. 积雪百分比试运行报告(赵海博)
      a. 更新验证数据。
14. 地表温度精度试运行报告(陈彦红，赵海博)
      a. 更新验证数据。
15. 蓝藻判识试运行报告(笪宏志)
      a. 更新验证数据。
16. 统计算法试运行报告（笪宏志）
      a. 更新验证数据。


本周工作计划
1.能量平衡配置项（卢婷婷，彭亮）
      a. 更新验证结果。
2.火情配置项（谢振雷，彭亮）
      a. 更新验证结果。
3.太阳能配置项（彭亮，田乐）
      a. 完成试运行报告文档和相关PPT。
      b. 测试上线。
4.云图解译配置项（谢振雷，宋毅）
      a. 云图分类代码工程化。
      b. 更新验证结果。
5. 台风配置项（彭亮，牛太阳，袁国言）
      a. 完成PYTHON代码BUG修正。
      b. 台风试运行报告验证结果更新。
6. 对流专题（彭亮，宋毅，康晖，孙乃秀，卢婷婷）
      a. 更新验证结果。
7. 闪电子系统算法工程化（杜进慧）
      a. 核对验证结果。
8. AOD配置项:
      a. 更新验证结果。
9. 亚洲夏季风（笪宏志）
      a. 试运行报告
10. 沙尘判识试运行报告（笪宏志）：
      a. 更新验证数据。
11. 火情配置项试运行报告（谢振雷）
      a. 更新验证数据。
12. 大雾判识试运行报告(陈彦红)
      a. 更新验证数据。
13. 积雪百分比试运行报告(赵海博)
      a. 更新验证数据。
14. 地表温度精度试运行报告(陈彦红，赵海博)
      a. 更新验证数据。
15. 蓝藻判识试运行报告(笪宏志)
      a. 更新验证数据。
16. 统计算法试运行报告（笪宏志）
      a. 更新验证数据。

本周工作进展
1. 台风配置项（彭亮，牛太阳，袁国言）
      a. 完成PYTHON代码BUG修正。
      b. 对接了台风配置项的输出格式与路径。
2. 闪电子系统算法工程化（杜进慧）
      a. 完成了算法功能化
3. 沙尘判识试运行报告（笪宏志）：
      a. 测试了在线算法。
4. 试运行报告：
      a. 梳理了缺项，明确了任务。
下周工作计划
1.能量平衡配置项（卢婷婷，彭亮）
      a. 更新验证结果。
2.火情配置项（谢振雷，彭亮）
      a. 更新验证结果。
3.太阳能配置项（彭亮，田乐）
      a. 完成试运行报告文档和相关PPT。
4.云图解译配置项（谢振雷，宋毅）
      b. 协助完成试运行报告。
5. 台风配置项（彭亮，牛太阳，袁国言）
      a. 台风试运行报告验证结果更新。
6. 对流专题（彭亮，宋毅，康晖，孙乃秀，卢婷婷）
      a. 更新验证结果。
7. 闪电子系统算法工程化（杜进慧）
      a. 完成试运行报告。
8. AOD配置项:
      a. 更新验证结果。
9. 亚洲夏季风（笪宏志）
      a. 试运行报告
10. 沙尘判识试运行报告（笪宏志）：
      a. 更新验证数据。
11. 火情配置项试运行报告（谢振雷）
      a. 更新验证数据。
12. 大雾判识试运行报告(陈彦红)
      a. 更新验证数据。
13. 积雪百分比试运行报告(彭亮，赵海博)
      a. 更新验证数据。
14. 地表温度精度试运行报告(陈彦红，赵海博)
      a. 更新验证数据。
15. 蓝藻判识试运行报告(笪宏志)
      a. 更新验证数据。
16. 统计算法试运行报告（笪宏志）
      a. 更新验证数据。


本周工作计划
1.能量平衡配置项（卢婷婷，彭亮）
    a. 更新验证结果。
2.火情配置项（谢振雷，彭亮）
    a. 更新验证结果。
3.太阳能配置项（彭亮，田乐）
    a. 完成试运行报告文档和相关PPT。
4.云图解译配置项（谢振雷，宋毅）
    b. 协助完成试运行报告。
5. 台风配置项（彭亮，牛太阳，袁国言）
    a. 台风试运行报告验证结果更新。
6. 对流专题（彭亮，宋毅，康晖，孙乃秀，卢婷婷）
    a. 更新验证结果。
7. 闪电子系统算法工程化（杜进慧）
    a. 完成试运行报告。
8. AOD配置项:
    a. 更新验证结果。
9. 亚洲夏季风（笪宏志）
    a. 试运行报告
10. 沙尘判识试运行报告（笪宏志）：
    a. 更新验证数据。
11. 火情配置项试运行报告（谢振雷）
    a. 更新验证数据。
12. 大雾判识试运行报告(陈彦红)
    a. 更新验证数据。
13. 积雪百分比试运行报告(彭亮，赵海博)
    a. 更新验证数据。
本周工作进展
1. 台风配置项
    a. 台风配置项数据展示方案确认。
    b. 台风配置项2019结果测试。
2. 闪电子系统算法工程化（杜进慧）
    a. 完成试运行报告。
    b. 更新了测试结果。
3. AOD配置项:
    a. 更新了验证结果。
4. 沙尘判识试运行报告（笪宏志）：
    a. 更新验证数据。
5. 火情配置项试运行报告（谢振雷）
    a. 更新验证数据。
6. 大雾判识试运行报告(陈彦红)
    a. 更新验证数据。
下周工作计划
1.能量平衡配置项（卢婷婷，彭亮）
    a. 更新验证结果。
2.火情配置项（谢振雷，彭亮）
    a. 更新验证结果。
3.太阳能配置项（彭亮，田乐）
    a. 服务器部署测试。
4.云图解译配置项（谢振雷，宋毅）
    b. 协助完善试运行报告。
5. 台风配置项（彭亮，牛太阳，袁国言）
    a. 台风试运行报告验证结果更新。
6. 对流专题（彭亮，宋毅，康晖，孙乃秀，卢婷婷）
    a. 更新验证结果。
7. 亚洲夏季风（笪宏志）
    a. 部署测试。
8. 沙尘判识试运行报告（笪宏志）：
    a. 更新验证数据。

本周工作计划：
本周工作进展：
云图解译： 
1.梳理web界面；
2.云图分类集成调试、完成业务调度。
3.云图解译算法业务测试问题修改
强对流：
1.强对流相关判识产品regc切图发布；
台风：
1.台风相关产品输出格式调整；
2.对2019年台风进行了测试。
沙尘：
1.hysplit在docker中安装，用于扩散模型构建；
火情配置项：
1.查找和修改火情异常；
统计算法：
1.测试了日统计算法。

下周：
1.完成hysplit部署测试；
2.对流REGC产品上线；
3.云图解译产品修改后，上线发布；
4.夏季风专题产品进行集成；

本周工作计划：

云图解译：
1.修改云图解译适配REGC代码，并完成集成测试；
2.前端界面修改，集成五类云系解译结果；

亚洲夏季风：
1.前端集成夏季风相关算法结果；

台风：
1.完成台风相似代码集成；
2.台风配置项相关产品上线完成；

闪电：
1.闪电统计分析完成集成、上线；

气溶胶：
1.优化灰霾气溶胶、PM精度。


本周工作进展：

云图解译：
1.修改云图解译适配REGC代码，并完成集成测试；
2.完成前端界面修改，集成五类云系解译结果；

亚洲夏季风：
1.前端集成夏季风相关算法结果；
2.完成切图。

台风：
1.完成台风风场的产品上线。

闪电：
1.完成闪电算法测试结果与甲方的对接。

气溶胶：
1.优化灰霾气溶胶、PM精度。


下周工作计划：

云图解译：
1.生成更多测试数据，完成实时切图显示。

台风：
1.完成台风风雨图展示。
2.优化辐合辐散的展示方案。
3.台风降水上线。

闪电：
1.闪电统计分析完成集成、上线；

气溶胶：
1.继续优化灰霾气溶胶、PM精度。

对流：
1.对流释用部分算法集成、上线。
2.配合前端优化显示方案。

.....
1. 云图解译
   1). 对接micaps标绘展示 
   2). 明确解译报告规范
2. 台风
   1). 明确客户端算法开发
   2). 将台风定强代码交给志龙调试
3. 对流
    1). 配合java进行集成和展示
4. 火山灰
    1). hysplit调用
    2). 火山热点切图发布
5. 蓝藻 
    1). 分区面积统计功能入库
    2). 统计结果确认
6. 沙尘
    1). 沙尘能见度、loading前端展示
    2). 统计功能明确
7. 亚洲夏季风
    1). 确认指数显示完成
    2). 明确分析报告规范模板
.....
1. 云图解译
   1). 对接micaps标绘展示(完成) 
2. 对流
    1). 完成了释用算法和闪电的对接。
3. 火山灰
    1). hysplit调用（完成了）
    2). 火山热点切图发布
4. 蓝藻 
    1). 分区面积统计功能入库（完成）
5. 沙尘
    1). 沙尘能见度、loading前端展示
    2). 统计功能明确
6. 亚洲夏季风
    1). 确认指数显示完成（已完成）
7. 地表温度
    1). 优化城市热岛算法。
.....
1. 云图解译
   1). 明确解译报告规范
2. 台风
   1). 明确客户端算法开发
   2). 将台风定强代码交给志龙调试
3. 对流
    1). 
4. 火山灰
    1). hysplit与沙尘、火山灰的对接
5. 蓝藻 
    1). 统计结果确认
    2). 增加其他区域
6. 沙尘
    1). 沙尘能见度、loading前端展示
    2). 统计功能明确
7. 亚洲夏季风
    2). 明确分析报告规范模板
8. 气溶胶
    1). 与甲方对接验收材料


2020-7-17
本周工作计划：
云图解译：
	1.生成更多测试数据，完成实时切图显示。

台风：
	1.完成台风风雨图展示。
	2.优化辐合辐散的展示方案。
	3.台风降水上线。

闪电：
	1.闪电统计分析完成集成、上线；

气溶胶：
	1.继续优化灰霾气溶胶、PM精度。

对流：
	1.对流释用部分算法集成、上线。
	2.配合前端优化显示方案。

蓝藻：
	1.完成巢湖的算法开发。
本周工作进展：
台风配置项：
   1. 完成了2019年和2020年台风定位定强和风场数据的生成。
   2. 优化了风场产品的展示方式，和前端进行了对接。
   3. 台风相似度代码测试、部署
闪电：
    1. 调整后的闪电发生时间与对流初生发生时间相关性分析算法docker部署测试；
    2. 进行闪电强度与雷达反射率、云顶参数等产品相关性分析算法研制。
	3. 完成闪电频次与云顶参数以及雷达回波强度相关性分析算法服务器封装，以及docker中的测试
	4. 完成闪电频次与雷达反射率及云顶产品相关性分析算法接口说明；进行地基闪电与天基闪电融合算法研发
	5. 进行地基闪电与天基闪电5分钟产品融合
	6. 完善地基于天基闪电融合算法说明文档；
	7. 将闪电频次跃变与闪电持续时间算法从闪电频次分析算法中独立出来，以调整算法运行方案，缩短算法运行时间；
气溶胶配置项：
    1：灰霾监测算法优化，加入蓝波段晴空背景集进行霾识别，目前取得初步效果
    2：加入NDVI阈值解决云检测问题，目前云检测效果理想。
    3：加入DEM数据处理成4km圆盘标称投影格式，用于灰霾算法的输入。
	4：气溶胶子系统中灰霾监测算法优化增加晴空像元的识别
    5：灰霾监测算法优化加入太阳高度角校正。
火情：
	1.火情代码修改，统一不同时刻同一火区的ID，进行服务器测试，修改接口文档。
沙尘：
	2.提取沙尘检测中的云检测和沙尘检测代码提高灰霾判识的精度。
	3.对接沙尘伪彩色合成前后数据对比。
云图解译：
	4.云图联合解译，查找数值预报模式生成文件中无判识结果的问题。
蓝藻：
	1.巢湖蓝藻水华代码编写
	2.巢湖蓝藻水华专题图代码编写

下周工作计划：
台风配置项：
    1. 核实台风风场网页端的显示。
    2. 补充降水数据。

闪电：
    1. 协助java组同事进行闪电对对流影响应用算法的部署；

气溶胶配置项：
    1. 与甲方核实优化结果。

沙尘：
	2.提取沙尘检测中的云检测和沙尘检测代码提高灰霾判识的精度。
	3.对接沙尘伪彩色合成前后数据对比。

云图解译：
	1. 优化云图联合解译。
    2. 优化直接解译。

蓝藻：
	1. 与甲方对接目前的结果。



本周工作计划：
1. 云图解译
   1). 明确解译报告规范
2. 台风
   1). 明确客户端算法开发
   2). 将台风定强代码交给志龙调试
3. 对流   
    1).  
4. 火山灰
    1). hysplit与沙尘、火山灰的对接
5. 蓝藻 
    1). 统计结果确认
    2). 增加其他区域
6. 沙尘
    1). 沙尘能见度、loading前端展示
    2). 统计功能明确
7. 亚洲夏季风 
    2). 明确分析报告规范模板
8. 气溶胶 
    1). 与甲方对接验收材料

本周工作进展：
1. 云图解译
   1). 明确解译报告规范
3. 对流   
    1). 完成对流释用的上线  
4. 火山灰
    1). hysplit与沙尘、火山灰的对接
5. 蓝藻 
    1). 统计结果确认
    2). 增加其他区域
7. 亚洲夏季风 
    2). 明确分析报告规范模板
8. 气溶胶 
    1). 与甲方对接验收材料

下周工作计划：
1. 台风
   1). 明确客户端算法开发
   2). 将台风定强代码交给志龙调试
2. 对流   
    1). 配合前端进行对流释用的展示  
4. 火山灰
    1). hysplit与沙尘、火山灰的对接
5. 蓝藻 
    1). 统计结果确认
    2). 增加其他区域
6. 沙尘
    1). 沙尘能见度、loading前端展示
    2). 统计功能明确
7. 亚洲夏季风 
    2). 明确分析报告规范模板
8. 气溶胶 
    1). 与甲方对接验收材料


# to Meng
 孟总，您好：

看了刘老师的文档，有几个问题想请教一下：
1. 算法设计的很严谨，请大概预估一下，这个算法业务化运行的时效性如何？业务化实现的难度大不？
2. 另外，关于台风微波方面还有个问题。最近我们在用FY3D L2 温湿廓线产品做台风暖核强度的时候，发现L2级产品的质量较2018年有较大下降，所以想问问刘老师，之前解析ADT微波亮温估算台风强度的工作到什么程度了？适配到FY3D的难度大吗？
谢谢！

彭亮

# NMC
1. interface

2. data save

3. 缓存

4. documents


# doc
#=> ADS docker
wpspdf /home/leon/dc/ADS公司服务器docker算法部署说明.pdf

#=> Jinqun:
wps /home/leon/dc/概要设计说明书/*.docx

#=> Gaofen
#{{{
验收：
矫正方式
融合
对流，雷达数据用在什么地方

魏主任：
交互有点粗糙
与一期增加了哪些
与swap的对比
与任务书的对比，任务书的匹配度
测试报告
面向业务化，后台自动化，自动出图
时效性 <20sec?
综合多颗卫星，融合出结果
与风4风3对比体现增量
不需要重复建设，直接用swap/smart的成果
将系统给省市试用
对流结果自动化
和swap结合，便于推广
国庆保障

方主任：
探测仪的温度不用插值
继承性，升级点
新增的卫星，扩展应用
集约化设计，框架较散
与其他系统的关系，调用或者复用
材料的准备不够细致
不同卫星的组合监测，前期需要设计


#}}}

#=> 算法部工作安排

1.与java组对接沙尘沉降数据
2.与项目组成员明确本周工作计划
3.docker集成规范修改


任务认领:
笪宏志，赵海博，陈彦红，刘方伟
认领签名：

任务名称:
docker瘦身20191221
工作时间:
20191221~20191224
任务描述:
公司服务器docker环境下的代码包(如/home/ads/ADS_FIRE/)只保留源代码，所有的辅助数据都移到/home/ads/commondata/ 里面，原则上代码文件夹要低于100m, 请大家尽量缩减容量。
任务进度: (百分比/正常/顺利/完成)


#=> 算法部
杜进慧 {{{
{{{
^> ADS 闪电
^>
^>
}}}
牛太阳 {{{
^> ADS 降水反演
^> 1045,1064 降水反演
^> 风三强天气项目
        }}}
牛媛 {{{
^> 农气中心算法开发
        }}}
王彬彬 {{{
^> 农气中心算法开发
^> 林草局项目
        }}}
武于洁 {{{
^> SMART算法研发（ENSO, MJO, 空中云水资源）
        }}}
}}}
张晗 {{{
^> 臭氧
^> 减灾项目
陈彦红 {{{
^> 云顶温度
^> 云光学厚度
        }}}
白罩峰 {{{

        }}}
姚蓓蓓 {{{

        }}}
}}}
卢婷婷 {{{
笪宏志 {{{
^> SMART 赤潮
^> SMART
        }}}
谢振雷 {{{

        }}}
李鹏 {{{

        }}}
秦丽娟 {{{

        }}}
郭峰 {{{

        }}}
}}}

#}}}

# 与阎广建老师合作点
#{{{

1. 大气廓线定量遥感算法（可用于卫星中心、气象中心等项目）
2. 云参数（云高，云顶相态等）反演算法（可用于卫星中心、人影中心等项目）
3. 臭氧近地面浓度反演（可用户环境监测等项目）
4. 植被覆盖度，叶面积指数反演（可用于荒漠化监测等项目）
5. 太阳能和能量平衡等算法（可用卫星中心的项目）

#}}}

#=> 算法组会议纪要

1. 并行培训
2. 算法开发规范
   1) 代码编写
   2) 代码测试，单时次，并行
   3) 算法接口文档编写
   4) 界面展示确实
3. 管理文档化


任务名称:
ADS台风配置项算法上线20191216
工作时间:
20191218~20191225
任务描述:
协助Java组上线产品。（包括台风路径，强度及预报，台风大风风场及产品，台风降水等）
任务进度:
正常

刚刚和各位组长碰了一下。鉴于目前部门工作较多，近期算法部的工作管理也确实有很多不到位的地方，交代的工作往往不能落实，原因很多，比如对工作难度预估不够，或者有其他任务打断等。刚刚我们讨论了一下，决定采用任务表格的形式来对工作进行梳理，当有新的任务或者任务发生变更的时候，大家就马上更新表格。对每个任务，大家参照刘方伟的表格，严格的按照格式来写，比如“任务名称”“任务时间”之后需要换行，时间的变更说明需要放在时间之前等，顺序也不要打乱，具体不明白的可以找我和组长咨询。时间的确定和变更需要找项目经理+部长或者组长沟通，组长也需要将变更的信息传给我，不能自己更改时间。目前的分组是这样：生态组：卢婷婷（组长），牛太阳，笪宏志，谢振雷；农气组，杜进慧（组长），王彬彬，牛媛；环境组：刘方伟（组长），张晗，陈彦红，白罩峰，姚蓓蓓

一会儿卢婷婷会给大家发一个在线表格的链接，大家按照要求填写一下。




# ftp

https://jingyan.baidu.com/article/15622f24106370fdfdbea547.html

send data to ftp site:
lftp -e "put infile; exit" -u username,passwd -p 21 ftp.xx.xx.xx
lftp -e "get -c data/s.gz; exit" -u username,passwd -p 21 ftp.xx.xx.xx


# unrar
wget http://www.rarlab.com/rar/rarlinux-x64-5.3.b4.tar.gz

# wjc
王金成，博士，高级工程师，中国气象局数值预报中心，模式研发室，资料同化科副科长。主要从事GRAPES全球同化系统研发工作。中国气象局“高分辨率资料同化与数值天气模式”攻关团队核心成员，2017年度获得中国气象学会气象科技成果奖一等奖，发表论文10余篇。

王金成，博士,毕业于兰州大学，目前为中国气象局数值预报中心模式研发室高级工程师，资料同化科副科长。一直主要从事GRAPES全球同化系统研发工作，中国气象局“高分辨率资料同化与数值天气模式”攻关团队核心成员，2017年度获得中国气象学会气象科技成果奖一等奖，发表论文10余篇。

@所有人，12月26日（本周四）下午航天宏图专家分享开课了！请大家积极参加，与专家博士面对面交流！
报告题目：资料同化理论方法和实践
报告时间：12月26日下午14:00-16:00
地点：
报告人：王金成 中国气象局数值预报中心
报告人简介：王金成，博士，毕业于兰州大学。目前为中国气象局数值预报中心模式研发室高级工程师，资料同化科副科长。一直主要从事GRAPES全球同化系统研发工作，中国气象局“高分辨率资料同化与数值天气模式”攻关团队核心成员，2017年度获得中国气象学会气象科技成果奖一等奖，发表论文10余篇。

今天非常荣幸，请到了中国气象局数值预报中心的王金成老师。王老师目前是中国气象局数值预报中心模式研发室高级工程师，是GRAPES同化方面的专家，是团队的核心成员，这些年一直是单位的优秀，我请他来一方面是看重他的专业水平，另外也是因为他的专业和我们遥感关系比较密切，尤其是我们气象遥感应用中心的工作比较密切。同化可以说是比较复杂的反演，也可以说是比较高级的数据融合。做好同化不仅要有扎实的气象学理论背景，熟悉天气预报模式，同时也要熟悉辐射传输理论和模式，也要擅长写代码，所以很高兴请到王老师过来作报告，大家欢迎，请王老师开始。


# 会议纪要
1）任务表格说明和改进
   a: 时间修改
   b: 任务描述

2）ADS
   a: 气溶胶概述
   b: 问题
   c: 更新代码脚本
   b: 其他配置项的推进

3）方向的确定
   a: 后期算法人员的职责
   b: 方向的分配

产品线：


smart新增算法文档帮助研发人员完成专题算法，形成具有实操的比较详细的工程化文档，每个专题一个文档，我已附带算法模板，专题算法包括如下：

ENSO事件监测、MJO事件监测、太阳能资源监测、空中云水资源监测、温室气体监测、森林草原火情影响评估、海洋赤潮监测、洪涝影响评估、雪灾影响评估、荒漠化监测、河口泥沙监测、地表土壤水分监测、积雪长序列、海冰长序列

CFE8CC

# HJJ
1、梳理zc环境技术方案的编写
2、整理闪电子系统的工程化
3、解决1045地表温度运算bug

1、基决确定了技术方案
3、地表温度确定是数据的问题，简化了排序算法，运算时间变成6秒左右

1、z场环境：下载再分析资料，做基本的测试。
2、梳理完成闪电子系统的工程化。

1、完成了资料的下载，对资料进行了预处理。
2、目前还没有完全梳理完闪电子系统。
3、和同事探讨1045里面docker里面不能删除的问题。
4、针对部分算法过慢的问题，利用perl简化了python numpy调用c语言的方式。

1、z场环境：完成辐射传输模式与资料的对接。
2、完成梳理完闪电子系统并形成禅道的任务分配。

1、z场环境：完成辐射传输模式调式与修改，能够输出从地面到中间任意层的transmitance
2、完成闪电子系统的梳理

1、完成z场环境的技术方案的编写。
2、禅道上形成闪电子系统的任务分配。


种是光机扫措成像

,

另一种是凝视成像。

先进近程空空导弹采用的是凝视成像。





它的工作波段一般选择在中波

3-5

和长波

8-12

的红外波段上。





这类系统在抗干扰能力、

探测灵敏度、

空间分辨率

# GF

高分辨率资料同化与数值天气模式
高分辨率资料监测衡量气体
高分辨率资料监测气溶胶
高分辨率资料刻画台风顶风场（台风顶的风场）
高分辨率资料结合静止气象卫星利用机器学习监测台风强度
高分辨率资料监测火点
高分辨率资料精准监测污染源
高分图像结合光流法计算云导风，计算散度监测对流
高分辨率资料结合天气雷达、探空、GPS掩星监测分析对流不稳定
高分辨率资料结合云雷达监测云微物理过程和特性
高分辨率资料结合云雷达、天气雷达在人工影响天气当中的应用
高分辨率资料结合地基空基闪电资料研究闪电
高分辨率资料结合雷达、闪电资料监测强天气
高分辨率资料监测龙卷风

高分结合地基云雷达、降水雷达、闪电探测仪建立三维天气观测系统。
高分卫星结合cloudsat、calipso等天基雷达建立深对流分析数据库和监测系统。
高分卫星结合光流法分析雾/云顶矢量建立雾监测系统。
高分卫星结合闪电成像仪建立闪电对流数据库。
高分卫星高光谱探测仪获取超高时空分辨率的三维大气廓线。
高分卫星凝视模式研究快速发展对流。
高分图像分析大气层结并结合探空或GPS分析对流不稳定。
高分图像得到的云顶运动矢量结合微波成像仪精确分析台风的辐合辐散、动力结构。


# YHJ
进展：

本项目计划采用辐射传输模型，结合卫星云产品和再分析资料经过模拟计算和统计分析，形成武器制导云环境影响产品。

目前完成了辐射传输模型的改造和调试，并用一个月的ERA-interim再分析资料的大气温湿廓线进行了模拟试验，利用ERA的云水和冰水含量产品进行了敏感性试验，初步分析了晴空和有云情况下，不同高度下武器的制导精度。

下一步拟下载更多的再分析资料和卫星云产品，统计分析云的类型和时空分布，并结合模型生成云环境统计产品。


# wjq

光流法云导风计算插件：
窗区亮温读取功能
窗区亮温插值功能
窗区亮温拼接功能
数据时间匹配功能
光流模型设计功能
光流模型适配功能
光流模型适配功能
光流计算功能
光流矢量转化功能
云导风聚类功能
云导风质量控制功能
云导风输出功能

水汽导风计算插件:
水汽亮温读取功能
水汽亮温插值功能
水汽亮温拼接功能
数据时间匹配功能
风矢量聚类功能
光流模型适配功能
光流计算功能
水汽导风矢量聚类功能
水汽导风质量控制功能
水汽导风输出功能

云导风高度计算插件：
红外高光谱云上大气廓线反演功能
数据融合功能
云顶高度计算功能


水汽导风高度计算插件：
红外高光谱晴空大气廓线反演功能
云检测功能
数据融合功能
权重函数计算功能
水汽导风高度输出功能








红外高光谱晴空大气廓线反演功能

云检测功能

数据融合功能

权重函数计算功能

水汽导风高度输出功能






# 35
需求，评估
验证
水深反演，实测


# ADS Test
云图解译：石玉立，谢振雷
1 五大云系
2 分类

台风： 定位定强：彭亮 大风：彭亮 降水：牛太阳

对流判识： 快速发展对流： 深对流： 追踪： 外推：
卢婷婷

闪电频数时间变化与对流强度相关性：
杜进慧

灰霾气溶胶：张晗
PM 张晗，姚蓓蓓

沙尘判识：
笪宏志

火判识：
谢振雷

大雾判识：
陈彦红

积雪百分比：
赵海博

地表温度精度：
陈彦红，赵海博

蓝藻判识：
笪宏志

统计：

# sources

大气所：
大气化学：
潘小乐：研究员
157 1106 6096

中层实验室：
范学花：
副研，气溶胶
155 1067 1650
张金强：
副研，大气物理与大气环境
136 6118 5843

气科院：
姚展予：
研究员，人工影响天气，微波遥感
136 8310 8982

王飞：
副研究员，大气电学
138 1143 6265

中山大学：
徐伟新 教授
中山大学大气科学学院
珠海校区海滨红楼3-108
广东省珠海市唐家湾
电子邮箱: xuwx25@mail.sysu.edu.cn
办公电话(0756)3668182

闵敏，理学博士，中山大学大气科学学院副教授，博士生导师。
办公电话
0756-3668610
电子邮件
minm5@mail.sysu.edu.cn
http://atmos.sysu.edu.cn/teacher/2097
(之前是甲方，在卫星中心工作)

兰州大学：
王天河：
副教授
189 1992 7285

雒佳丽：
副教授：
181 9421 1987

南信大：
大气物理学院
张其林：
教授，博导，雷电方向，15852915826
夏俊荣：
副教授，18251909239

大气科学学院：
王慧：
副教授
13921429985

环境学院：
吴丹：
副教授：
13814172190

成信大：
王维：
13568971642


# number
8000 1120 1101 0714 28
80001 2  2011 0714 28

https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&ved=2ahUKEwjRlZTz1ujpAhWNBogKHbhyCbwQtwIwAHoECAQQAQ&url=


# working

# ipdb

# hjj

3-5 8-12 

0.75~3 15~1000

常用大气窗口
由于大气对电磁波散射和吸收等因素的影响，使一部分波段的太阳辐射在大气层中的透过率很小或根本无法通过。电磁波辐射在大气传输中透过率较高的波段称为大气窗口。为了利用地面目标反射或辐射的电磁波信息成像，遥感中对地物特性进行探测的电磁波“通道”应选择在大气窗口内。目前在遥感中使用的一些大气窗口为：
1、0.3～1.155μm，包括部分紫外光、全部可见光和部分近红外，即紫外、可见光、近红外波段。这一波段是摄影成像的最佳波段，也是许多卫星遥感器扫描成像的常用波段。比如，Landsat卫星的TM的1～4波段；SPOT卫星的HRV波段等。其中：0.3～0.4μm，透过率约为70%；0.4~0.7μm，透过率大于95%；0.7~1.1μm，透过率约为80%。
2、1.4~1.9μm，近红外窗口，透过率为60%~95%，其中1.55~1.75μm透过率较高。该波段在白天日照条件好的时候扫描成像常用这些波段。比如，TM的5、7b波段等用以探测植物含水量以及云、雪或用于地质制图等。
3、2.0~2.5μm，近红外窗口，透过率约80%。
4、3.5~5.0μm，中红外窗口，透过率为60%~70%。该波段物体的热辐射较强。这一区间除了地面物体反射太阳辐射外，地面物体自身也有长波辐射。比如，NOVV卫星的AVHRR遥感器用3.55~3.93μm探测海面温度，获得昼夜云图。
5、8.0~14.0μm，热红外窗口，透过率约80%。主要来自物体热辐射的能量，适于夜间成像，测量探测目标的地物温度。
6、1.0~1.8mm，微波窗口，透过率约35%~40%。
7、2.0~5.0mm，微波窗口，透过率约50%~70%。
8、8.0~1000.0mm，微波窗口，透过率约100%。由于微波具有穿云透雾的特性，因此具有全天候、全天时的工作特点。而且由前面的被动遥感波段过渡到微波的主动遥感波段。

进展情况：
利用2018年1-6月中国NH区域的ECMWF再分析大气廓线数据作为输入，结合和WQ的频率，利用辐射传输模型CRTM，分别计算每个月的晴空各个高度层的大气光学厚度以及不同观测高度的大气透过率。并且根据云水含量和云掩膜数据，计算了不同观测高度到地面的云分布概率，并根据云的分布概率和大气透过率生成了ZD影响因子。并生成了年平均、月平均、季平均的数据集。

下一步工作计划：
对目前云高计算出现的偏差，需要重新修正算法。下载2008至2019年的ECMWF再分析数据，利用CRTM计算每个月各层的大气光学厚度，并统计每个月各层的云分布概率。


# 1043

下周算法开发计划：

台风：
    1. 在ADS的算法框架下，集成现有红外机器学习算法；
    2. 利用FY4A可见光数据，测试台风中心识别算法；
云顶温度：
    1. 测试线性回归算法的精度；
    2. 根据测试的结果优化算法；
对流：
    1. 完成算法框架搭建；
    2. 测试算法精度；
云分类：
    1. 建立神经网络训练模型；
海面温度：
    1. 核实辐射传输模型的搭建情况和算法开发进展；
    2. 建立初步的拟合系数，并利用模拟数据进行初步的验证；
海冰：
    1. 完成算法的开发与工程化；


# jixiao

ADS:
1. 梳理闪电子系统算法。梳理任务书，和同事一起设计算法开发方案，核实算法开发结果。

2. 优化台风风场产品和展示方案。参考威斯康星大学的风场产品，平滑和优化产品，并设计产品的展示方案。

3. 完成沙尘沉降与太阳能的工程化与对接文档。完成NC输出的代码，完善调用bash，完成工程化文档。

4. 编写、修改台风3D展示方案。对程序功能进行拆分，并编写代码完成算法的设计，编写展示方案。

1043:
1. 梳理云迹风算法并指导算法开发。梳理算法文档和思路，核实算法开发结果。

2. 协助调试辐射传输方程。协助RTTOV代码的调试和结果的核实。

3. 协助服务器环境的调试与运维。协助服务器系统的安装以及环境的配置与维护。

4. 修改台风插件文档。修改算法文档，协助算法汇报PPT，修改台风插件需求、概设文档。

1014:
1. 编写代码批量下载ERA5和ERA-interim数据。修改开源库并编写脚本实现ERA数据的自动与批量下载。

2. 完成近十年的光学厚度的计算。利用正向模拟结合线性回归的方法实现近十年的光学厚度的计算。

3. 完成近十年的云环境产品的生成。利用概率统计的方式结合光学厚度和云分布产品计算云环境产品。

多源卫星融合项目：
1. 与甲方沟通解决服务器的升级等问题。

2. 和项目组同事梳理验收材料。

其他:
1. 协助该写和调试大数据中心的IDL代码。

 10.1.6.68
root 密码： htht
100~145 4~50

# convert png to gif
   convert -delay 100 *.png out.gif

# vim 1.Alternate

在 C 或 C++ 项目中，源文件和头文件常常成对出现。例如，utils.c和utils.h，你经常需要同时编辑这两个文件。使用 Alternate，你可以输入:A命令，在.c 和.h 文件之间快速切换。如果你在.c 文件中，就会切换到.h 文件，如果你在.h 文件中，就会切换到.c 文件。
2.Bufexplorer

要高效地处理多个文件，你需要使用几个不同的命令，如:ls（列出缓冲区）、:b（编辑缓冲区）、:bn（下一个缓冲区）和:bp（前一个缓冲区）。然而，通常情况下，在找到正确的文件之前，你的大部分时间都在键入:bn、:bn、:bn。

Bufexplorer 使得在 vim 中处理多个文件变得轻而易举。它添加了\be键绑定（\是前导键），它会打开一个所有缓冲区的列表，移动到显示文件名的行并按回车键，你就可以快速切换到另一个缓冲区。
3.Bufferize

许多 vim 命令继承自 vi，它们的输出非常简陋。它们把输出打印到屏幕上，不能搜索或复制。如果你按空格太多次，内容就消失了。几乎不可能搜索这个文本，有时你甚至不知道如何让 vim 再次显示它。

Bufferize 解决了这个问题。它接受一个 vim 命令并从其输出创建一个临时缓冲区，然后在一个分屏窗口中打开它。例如:Bufferize map将在一个新窗口中显示所有键盘映射，你可以搜索它们。要退出新窗口，只需使用常规的:q命令。
4.Bufferline

Bufferline 补充了 Bufexplorer（见上文），使它更容易处理多个文件 / 缓冲区。它在状态行中打印所有打开的文件及其缓冲区编号的列表。你只需要浏览一下这个列表，输入:b 5就可以切换到第 5 个文件 / 缓冲区，或者使用 Bufexporer，点击\be后面跟/5，然后回车。
5.Bufkill

如果你在一个分割中打开了两个缓冲区，并且你想要关闭一个缓冲区，那么你可以使用:bd命令。不幸的是，这个命令也关闭了分割。通常，你不想关闭分割，而只想关闭缓冲区。在这种情况下，使用 Buffkill 的:BD命令，该命令将关闭缓冲区，但保留分割。
6.Characterize

Characterize 添加了ga快捷方式，显示光标下 Unicode 字符的名称、代码点值和十六进制值。
7.Clever-f

此扩展改进了用于查找下一个 / 前一个字符的f和F快捷键。按下fa会转到下一个a。按下Fa会转到前一个a。没有这个扩展，你必须再次输入fa来找到下一个a或者按下分号;。类似地，你必须输入Fa或，才能再次找到前面的a。如果你是一个 vim 老手，你已经在用;和,，你最终会fafafafa或FaFaFaFa。

有了这个扩展，你可以再按一次f，它会搜索下一个字符，你可以再按一次F，它会搜索前一个a，所以，不用fafafafa，你现在可以用fafaff代替FaFaFaFa，你可以FaFFF。此外，当你按下f或F时，它将显示下一个 / 前一个匹配项，你立即就知道光标将跳转到哪。
8.Colorscheme-gruvbox

深色系主题。灰色背景，浅绿色文字和功能。
9.Colorscheme-jellybeans

深色系主题。黑色背景，浅绿色文字，浅黄色功能。
10.Colorscheme-seoul256

深色系主题。灰色背景，淡蓝色文字，淡黄色功能。
11.Commentary

最简单、最快捷的注释插件之一。按gcc将整个行注释掉。按gc注释掉一个可视化选中部分。再次按下相同的快捷键取消注释。
12.Conflicted

这个插件有助于解决 git 合并冲突。假设你刚从 github 上的项目主分支中取出代码，遇到了一个合并冲突错误。要解决这个问题，可以运行这个插件提供的:Conflicted命令。该命令创建一个三向 diff，并将结果放在三个垂直分割的窗口中。左边的分割是上游更改，中间的分割是工作更改，右边的分割是本地更改。你可以接受上游 diff 或本地 diff 来解决冲突。为快速接受正确的 diff, Conflicted 提供了两个键映射。dgu命令将使用上游 diff，dgl将使用本地 diff。要解决下一个冲突，使用:GitNextConflict命令。如果没有更多的冲突，vim 将退出，你可以git commit已解决冲突的文件。
13.Ctrlp

这个插件添加了ctrl+p绑定来打开一个模糊文件打开对话框。例如，如果你需要编辑math-config.json文件，你可以键入文件名的一些字母，如mat.js、mjson，甚至thfig（“th”是“math”的最后两个字母，“fig”是“config”的最后三个字母）。Ctrlp 将立即缩小搜索范围，并提供最佳匹配。它还可以用来打开 mru 文件（最近使用的文件）和缓冲区，你可以使用ctrl+r和ctrl+f快捷键在文件 /mru/ 缓冲区模式之间切换。
14.Ctrlp-funky

Ctrlp-funky 通过添加函数查找模式扩展了上面的 Ctrlp 插件。你可以运行:CtrlPFunky命令，立即在函数搜索模式下打开 Ctrlp，或按下ctrl+p打开 Ctrlp，然后按ctrl+r（或ctrl+f）几次，进入函数搜索模式。例如，如果你有一个void debug_print()函数，你可以输入vodepr（单词 void、debug、print 的前两个字母），然后回车，vim 将跳转到这个函数的定义。
15.Ctrlsf

有了这个插件，你可以快速搜索和替换大量的文本。当你运行:CtrlSF模式命令时，它将在左侧创建一个包含所有匹配项的结果窗口。“结果”窗口中还有一些围绕匹配项的上下文行，方便你知道你正在查看的是否是正确的匹配项。现在，你可以直接在结果窗口中进行编辑。当你保存结果窗口时，更改也将保存在文件中。你也可以按下回车键，在右边的窗口中打开每个结果并在那里编辑它。
16.Delimitmate

Delimitmate 会自动关闭引号和括号。例如，你输入“会自动得到“”，而且光标位于两个引号之间。
17.Diff-enhanced

这个插件为 vimdiff 添加了一个新的 diff 可视化方法，它试图最小化差异的数量。当你处于 diff 模式时，输入:EnhancedDiff patience命令，你就能够更好地查看 diff。
18.Dirvish

Dirvish 支持惯用的缓冲区驱动开发，它作为一个文件浏览器补充了 Nerdtree（见下文）。当你按下-键时，当前缓冲区将变成一个文件浏览器。你将看到当前工作目录或当前打开的文件目录中的所有文件。然后可以使用箭头键 hjkl 和搜索操作符/导航这个目录并查找文件。当你按下回车键时，Dirvish 将退出，光标下的文件将在当前窗口中打开，作为一个新的缓冲区。当你有多个分割打开时，这个插件特别强大，因为你可以指定下一个文件在哪个分割中打开。你只需导航到分割，点击-，找到文件，然后点击回车，就可以在希望的分割中打开它了。
19.Dsf

Dsf 是删除周围函数的缩写。通过在函数调用中按下dsf，它将删除周围的函数名。例如，如果你有像print_r(get_post|s(true))这样的代码，并且你的光标位于|字符所在的位置，那么当你按下dsf时，你将获得输出get_posts(true)。
20.Easy-align

有了这个扩展，你就可以整齐地将文本对其到列中。它添加了:EasyAlign命令，你可以将其绑定到你想要绑定的任何键盘快捷键。当你执行它时，它会要求你输入列分隔符字符，然后对所选文本进行格式化。例如，要对齐代码使所有=符号都在同一列中，你可以使用V命令直观地选择行，然后运行:EasyAlign，接着=，然后回车。
21.Easymotion

Easymotion 让你可以更快地在文件中导航。它添加了\\ w快捷方式，允许你快速跳转到光标之后的任何单词。它为每个单词分配一个唯一的字母，当你下次按下它时，光标会立即跳转到该单词。它还添加了\\b快捷方式，让你可以快速地向后导航。类似地，如果你需要跳转到上面或下面的任何一行，你可以使用\\k和\\j快捷键。
22.Exchange

使用 Exchange 插件，你可以非常快速地交换两个单词。转到第一个单词并按cxw，然后转到第二个单词并再次按cxw。你就完成了这两个词位置的交换！

实际上，你不仅可以交换两个词，还可以交换任何两个 motion。按下cx后，下一个快捷键是 motion（motion 是移动光标的键盘快捷键）。例如，要交换两个字符，可以执行cxl，然后再执行cxl（l 是将光标向右移动一个位置的动作）。类似地，要交换两个句子，你可以执行cxis，然后对第二个句子也执行cxis操作。在这种情况下，motion 是选择整个句子。

同样，如果两个 motion 相同，只要按一下.重复第一个操作。
23.Expand-region

通常，你希望选择比刚刚选择的文本多一点的文本。例如，你使用viw选择了一个单词，但随后发现需要选择整个引用字符串。有了这个插件，你可以按+，它会把当前的选择扩展到下一个最大的文本对象。从字符到一个单词、一个带引号的字符串、一行、一段到整个文件。
24.Far

Far 使查找和替换多个文件中的文本变得很容易。它添加了:Far pattern1 pattern2命令。当你运行这个命令时，它将屏幕分成两半。在上半部分，它显示了pattern1匹配的所有文件和行。在下半部分，可以预览匹配的上下文。在上面的分割中，你可以使用 hjkl 键来导航匹配项。默认情况下，所有匹配项都将用pattern2替换，但你也可以使用t键取消匹配项的标记（并再次使用 t 标记它们）。选择要替换的所有匹配项之后，运行:Fardo命令。这个命令将执行实际的替换。

Far 也很适合于查找所有匹配项。你可以使用:F pattern命令，它将查找所有匹配的模式，并把它们显示在两个分割中，但是它不会执行替换。
25.Fugitive

使用 Fugitive，你可以直接从 vim 使用 git。它添加了:Git命令（或简写为:G），该命令运行git status，并在一个分割窗口中显示结果。然后，可以使用键盘快捷键s来暂存（git add）一个文件，使用u来恢复（git reset）一个文件。暂存文件之后，可以按cc创建提交。我还不知道如何进行 git 推送，所以这是我需要学习的内容。如果我能够在不离开 vim 的情况下进行代码推送和部署，那将非常方便。
26.Fzf

Fzf 是 Ctrlp（见上文）的一个替代方案。它为快速打开文件和切换缓冲区添加了几个命令。这些命令是:Files和:Buffers。如果你以前是按多次 tab 键来补全文件名和缓冲区名，那么现在你只需要键入文件名或缓冲区名的几个字母。例如，如果你需要打开options.c文件，你可以直接输入opt.c，甚至是oc，Fzf 都会为你提供最佳匹配。
27.Fzf-mru

Fzf-mru 增加了一个可以通过:FZFMru命令访问的 mru 模式。此模式允许你快速访问最近编辑的文件。假设你昨天在从事 scraper 项目相关的工作。今天，当你进入 mru 模式时，只需要输入scra，它就会显示你昨天处理的 scraper 项目的所有文件。
28.Gitgutter

Gitgutter 增加了两个有用的东西。第一个列位于 vim 最左边，它快速显示当前文件的 git diff 信息。你可以快速查看添加和更改了哪些行。第二个是]c和[c映射，让你可以在更改的行之间跳转。
29.Goyo

我最近切换到 Goyo 模式编程。当你输入:Goyo命令时，这个插件会将内容居中，并删除行号和状态行，这样你就可以专注于无干扰的编码了。如果还让 vim 全屏，那就更好了。
30.Grepper

Grepper 改进了 vim 中的查找，并增加了对 ripgrep 的支持。你可以输入:Grepper，然后输入你的搜索查询，它将找到所有匹配项并在 quickfix 窗口中加载它们。然后你可以使用 vim 的:cn和:cp命令来导航到下一个 / 前一个匹配项，或者使用 Unimpaired 插件（见下文）的快捷方式]q和[q。

这个插件的作者建议将它与 qfenter.vim 插件一起使用。这是我还要尝试的东西。
31.Gv

Gv 将 git 提交浏览器添加到 vim 中。你可以运行:GV命令，它将显示整个提交树。然后，你可以在提交窗口中按下回车或 o 来查看各个差异。要退出 diff 查看器，请按q。如果你只对当前文件的 git 日志感兴趣，那么可以使用:GV!命令。
32.Illuminate

Illuminate 高亮显示当前可见缓冲区中光标下这个单词的所有出现。例如，如果光标在单词var上，那么所有其他的var也将高亮显示。
33.Interestingwords

这个插件允许你同时高亮显示多个单词。它添加了快捷方式\k，可以更改光标下单词的背景颜色，以及文件中出现的所有相同单词。你还可以使用n和N来跳转到下一个 / 上一个高亮显示的单词。当你处理复杂的代码并需要跟踪多个变量的使用情况时，它非常有用。
34.Linediff

Linediff 让你可以快速比较两个文本块。可视地选择第一个文本块并运行:Linediff命令。然后可视地选择第二个块并再次运行相同的命令。这个插件将创建一个新的标签页，将两个文本块的差异垂直分割。如果结果看起来太冗长，运行:EnhancedDiff patience命令（来自上面的 Diff-enhanced 插件）来改进差异。

你还可以使用这个插件快速解决 git 合并冲突。如果你打开的文件中存在合并冲突，将光标放在合并冲突标记<<<<<<和>>>>>之间，并运行:LinediffMerge命令。接下来，插件会自动创建一个垂直分割，分割合并冲突差异，你可以在左边或右边的分割中进行编辑，并通过运行:LinediffPick命令来自动解决合并。
35.Listtoggle

一旦你对 vim 的熟练达到了一定的程度，你将开始一直使用 quickfix 窗口（以及位置列表窗口）。查找结果将在 quickfix 中，linting 错误将在 quickfix 中，编译错误将在 quickfix 中，待办事项列表将在 quickfix 中。一切都会很快解决。你会一直关闭和打开 quickfix。不幸的是，没有简单的方法来切换 quickfix 窗口和位置列表窗口。你必须使用:copen和:cclose命令来打开 / 关闭 quickfix，以及:lopen和:lclose来打开 / 关闭位置列表。这打字太多了。

Listtoggle 使它更加简单，并增加了两个快捷方式来快速切换它们。\q绑定将切换 quickfix 窗口，而\l绑定将切换位置列表窗口。
36.Locate

通常，你需要查找当前文件中的所有出现。你不想来一次全局搜索，你不想搜索和替换，你不想要任何分割，你只想要一个所有结果的总览。Locate 通过:Locate命令（或简写为:L）提供完全相同的功能。只需键入:L pattern，这个插件就会打开一个快速位置列表，其中包含当前文件中所有出现该模式的地方。你可以使用快捷方式\l切换位置列表（由 Listtoggle 插件提供，见上文），你还可以通过快捷方式]l（下一个结果）和[l（前一个结果）（由 Unimpaired 插件提供，见下文）来浏览结果。
37.Matchtagalways

这个插件突出显示了光标所在位置最内层的 HTML 打开和关闭标记。例如，如果光标在<div class="post">cursor here</div>，那么这个插件将突出显示<div>和</div>标签。
38.Matchup

Matchup 添加了快捷方式%，允许你在匹配的括号对之间快速跳转。如果你的光标在{字符上，那么按 % 后它将跳到}。如果你再次按 %，它将跳回{。它还添加了快捷方式z%，使你可以向前跳转到下一对圆括号内。假设你有一个函数pri|nt_data("hi"， 7)和你的光标在|。然后，在按下z%之后，光标将出现在函数参数中。
39.Nerdcommenter

Nerdcommenter 是另一个代码注释插件。借助 Commentary （见上文），你可以使用gc快捷方式快速切换注释，但是 Nerdcommenter 提供了对注释的更多控制。例如，你可以使用\cm快捷方式执行多行注释，并使用\cA快捷方式在行尾添加注释。
40.Nerdtree

Nerdtree 是一个文件管理器。它在 vim 的左侧显示当前项目的完整目录和文件树结构。要打开和关闭 Nerdtree，请运行:NERDTreeToggle命令。方便起见，你可以将它绑定到快捷方式\t。当它打开时，你可以使用常规的 hjkl 键进行导航。使用键O打开项目中的所有目录，然后使用常规的/search 操作符搜索文件。要在右侧打开光标下的文件，请按下 ok 键。要查看隐藏的文件，请使用 I 键。与 Dirvish（见上文）相比，它支持文件管理器驱动的开发。Nerdtree 总是在右侧打开文件，而不是指定在哪里打开文件。
41.Nerdtree-syntax-highlight

这个插件将语法高亮显示添加到 Nerdtree 中。现在，文件和目录有了不同的颜色。
42.Peekaboo

Vim 有许多不同的寄存器。当你复制文本时，它会进入"寄存器。当你删除文本时，它会进入数字寄存器。然后还有小写和大写等寄存器供你个人使用。

当你要使用寄存器时，这个插件会预览它们。当你按下"键时，它会在右侧打开一个寄存器备忘单，你可以看到每个寄存器的内容并选择正确的寄存器。你还可以按空格键加大寄存器备忘单。
43.Qfgrep

Quickfix 是 vim 最大的特性之一。不幸的是，一旦用结果填充了 quickfix 列表，它就会被冻结。你无法进一步过滤 quickfix 列表。这种行为不太合理，因为你总是希望细化结果。

Qfgrep 允许你这样做。现在，你可以在 quickfix 窗口中过滤结果。使用\g快捷方式过滤结果，\v转换过滤结果，\r 还原原始条目。它还添加了:QFGrepPat命令，该命令执行与\g 相同的操作，:QFGrepPatV则执行与\v相同的操作。
44.Qlist

Qlist 添加了:Ilist函数，它是 vim 内置的:Ilist函数的改进版本。内置的:ilist 函数来自一个计算机没有多少内存的时代，所以它当时不是很有用，因为它会一股脑把所有东西都打印到屏幕上，你无法使用这样的结果（见上文的 Bufferize 插件）。改进后的:Ilist函数从结果中创建一个 quickfix 列表。你现在可以运行:Ilist pattern，这个插件将在当前以及包括的项目文件中找出所有用到的单词模式，并把它们放在 quickfix 窗口中，正是你想要显示所有结果的地方。
45.Quickfix-reflector

你不仅希望筛选 quickfix 结果（上面的 Qfgrep），还希望编辑 quickfix 窗口，就好像它只是另一个缓冲区一样。这个插件使得 quickfix 窗口可以修改。现在可以使用dd删除 quickfix 条目，使用i添加新条目。你还可以直接编辑 quickfix 结果，当你通过:w 保存 quickfix 窗口时，文件也会得到更新。
46.Ranger

这个插件让你可以跳转到外部 Ranger 文件管理器，在 vim 中打开一个文件。它类似于 Dirvish（见上文），让你可以轻松地进行缓冲区驱动的开发。当你在任何窗口中运行:Ranger命令时，它将启动ranger进程。然后，当你选择一个文件时，它将在选择的文件中作为一个新的缓冲区打开。
47.Repeat

Repeat 改进了.命令。它让你可以重复其他插件的命令和动作。例如，如果你使用 Surround 插件（见下文）将文本括在引号中，那么按下.会重复这个动作。
48.Rooter

由于 vim 不是 IDE，所以它几乎没有项目的概念，也不知道项目的根目录是什么。当你尝试打开一个文件时，vim 会搜索主目录或其他目录，而不是项目目录。

这个插件会自动将 vim 的当前工作目录设置为项目目录，使得处理项目变得更加简单。它通过查找最根部的.git目录来实现。通常，此类目录表明了项目的起点。
49.Scratch

Vim 的文档提到了一种称为 scratch 缓冲区的特殊缓冲区类型。这个插件实现了它。Scratch 缓冲区是临时丢弃缓冲区。当你在做一个项目的时候，快速笔记是很有用的。使用:Scratch命令打开它。光标将跳转到顶部的 scratch 窗口。当你将光标移动到另一个窗口时，scratch 窗口将自动关闭。
50.Signature

当使用标记时，没有一种可视化的方式来告诉你在哪里添加了它们。你可能记得一两个标记，但当你再加的时候，你就迷失了。这个插件解决了这个问题，它会在最左边的列中显示标记。你可以用默认快捷方式ma、mb、…添加和切换标记，用dma、dmb、…删除单个标记，用m-删除所有标记，用]'和['跳到下一个和前一个标记，用m/将所有标记放到位置列表窗口中。
51.Speeddating

在正常模式下，ctrl+a和ctrl+x可以实现数值递增和递减。这个插件使这些键盘快捷键也可以实现日期和时钟时间的增加。例如，如果光标位于字符串2000-01-31上时，按ctrl+a将使其变为2000-02-01，按ctrl+z将使其变为2000-01-30。
52.Swap

Swap 让你可以快速地交换单词或逗号分隔的函数参数。例如，如果你有一个函数 print(a, b, c)，那么你可以按 g>，它会变成print(b, a, c)。按g<，它会再次变成print(a, b, c)。你还可以通过按gs进入可视化交换模式。然后使用 hjkl 键来交换参数。
53.Syntax-css3

CSS3 语法高亮插件。
54.Syntax-dockerfile

Dockerfile 语法高亮插件。
55.Syntax-html5

HTML5 语法高亮插件。
56.Syntax-i3config

i3 窗口管理器配置文件语法高亮插件。
57.Syntax-javascript

JavaScript 语法高亮插件。
58.Syntax-json

JSON 语法高亮插件。
59.Syntax-nginx

Nginx 配置文件语法高亮插件。
60.Syntax-php

PHP 语法高亮插件。
61.Syntax-tmux

tmux 配置文件语法高亮插件。
62.System-copy

Vim 终端没有用于从系统剪贴板复制和粘贴的寄存器*或+。这个插件添加了cp快捷方式，通过调用外部实用程序xsel将所选文本或 motion 复制到系统剪贴板。它还具有从系统剪贴板粘贴的快捷方式cv。
63.Tabular

Tabular 的功能与 EasyAlign（见上文）相同。它对文本进行列对齐。与 EasyAlign 相比，它的一个优点是，你可以直接将用于对齐的正则表达式传给它。与正则表达式相匹配的位置将会对齐。例如:Tabular /regex将创建整齐的regex列。
64.Targets

掌握 vim 的一个步骤是学习使用文本对象。文本对象允许你操作整个文本结构，而不是单个字符。Vim 已经附带了许多文本对象——你可以访问单词、句子、段落和代码块。这个插件增加了十几个文本对象。例如，你可以使用di删除逗号分隔的项，或者你可以使用cin和cil来更改前一个和后一个逗号分隔的项，你可以使用ci+来更改 sum 元素，等等。
65.Textobj-user

从头编写自己的文本对象非常困难，因为在调用文本对象时必须精确复制 vim 的行为，并了解所有的陷阱和缺陷。这个插件提供了一个快速简单的接口，让你可以实现自己的文本对象。“textobj”插件有一个完整的生态系统，使用这个插件可以添加各种有用的文本对象。
66.Textobj-entire

这个插件使用 Textobj-user（见上文）创建一个文本对象 ie 和 ae 来操作整个文件。例如，要选择整个文件，你可以执行 vae，要删除整个文件，你可以执行 vaed 或 dae。
67.Textmanip

这个插件让你可以直观地移动选中的文本。例如，你能可视化地选择一个单词，然后使用快捷键 ctrl+h 和 ctrl+l 将其向左或向右移动。类似地，你可以使用快捷键 ctrl+j 和 ctrl+k 向下移动整个行。
68.Thesaurus-query

有了这个插件，你可以访问 Libreoffice 同义词典。一旦配置了它，你可以使用:Thesaurus word命令来查找与 word 相关的所有单词，你还可以使用:ThesaurusW来查找与光标下的单词相关的所有单词。
69.Tmux-complete

当你处于流程中时，会同时发生许多事情，并且会打开许多 tmux 窗口和窗格。一个显示 git 日志，另一个用于测试，还有一个显示帮助手册，等等。通常，你需要从 tmux 窗格获取信息到 vim。通常，你必须用鼠标来复制它，但这非常低效。有了这个插件，你可以在插入模式下按下 ctrl+x ctrl+u，从任何 tmux 窗口 / 窗格补全单词。它将提供来自所有 tmux 窗口 / 窗格的所有单词的列表。
70.Traces

当用:s/old/new命令替换文本时，执行这个命令后才能看到更改。这个插件让你可以在输入时预览 old 匹配和用于替换的部分 new，你可以直接看到你是否做对了。
71.Undoquit

通常，你可能因为操作太快关闭了一个你不想关闭的窗口。有了这个插件，你现在可以按ctrl+w+u撤消关闭操作。
72.Unicode

这个插件让你可以快速搜索和插入 Unicode 字符。例如，如果你想插入一个 Unicode 兔子符号，你可以输入 rabbit，然后按下 ctrl+x ctrl+z。输入文字 rabbit 将被“兔子”的表情符号取代。
73.Unimpaired

许多命令都是成对的。例如:bn和:bp跳到下一个 / 前一个缓冲区，:cn和:cp跳到下一个 / 前一个 quickfix 列表项，:ln和:lp跳到下一个 / 前一个位置列表项，等等。此插件为这些命令添加了灵活的快捷方式。你现在可以用]b和[b跳到下一个/前一个缓冲区，用]q和[q跳到下一个 / 前一个 quickfix 条目，用]l和[l跳到下一个 / 前一个位置列表条目，等等。
74.vimade

当你使用多个分割窗口时，在短暂的分心之后，很容易忘记你在哪个分割窗口中工作。这个插件会淡化其他所有的分割线，使当前聚焦窗口的分割线清晰可见。
75.Visual-split

通常，你需要将注释、函数定义或代码片段在上方折叠，使其始终可见。通常的方法是用ctrl+w+s分割窗口，然后用10ctrl+w+-重新调整窗口大小。这个插件合并了这两个动作。现在你可以直观地选择该区域并按下ctrl+w+gss。该插件将分割窗口并调整大小，使其与所选的行完全匹配。
76.Visual-star-search

有两个操作符可以搜索光标下的单词。它们是*（向前搜索）和#（向后搜索）。不幸的是，在可视化模式中，它们不会搜索可视化选择部分，你也不能搜索包含特殊字符的单词。例如，如果单词是 h#e#l#l#o，那么这些操作符将选择并搜索这个单词中的一个字母，这不是你想要的。

使用此插件，你可以搜索可视化选择的序列，它可以包含任何特殊字符。使用v命令进行选择，然后按*或#进行搜索。
77.Writeable-search

Writeable-search 类似于 CtrlSF（见上文）。它让你可以快速查找结果并立即在结果窗口中编辑它们。当你运行:WritableSearch pattern命令时，它将在当前目录中的所有文件中搜索这个 pattern，并打开一个包含结果的新选项卡。然后，你可以编辑结果，当你在相同的结果窗口中执行:w操作时，它会更改更新文件。如果你已经在 quickfix 窗口中有一个要修复内容的列表，那么你可以通过:WritableSearchFromQuickfix命令将它们转移到这个插件中进行编辑。
Content
# Fold description {{{ #
1.Alternate

在C或C++项目中，源文件和头文件常常成对出现。例如，utils.c和utils.h，你经常需要同时编辑这两个文件。使用Alternate，你可以输入:A命令，在.c和.h文件之间快速切换。如果你在.c文件中，就会切换到.h文件，如果你在.h文件中，就会切换到.c文件。
2.Bufexplorer

要高效地处理多个文件，你需要使用几个不同的命令，如:ls（列出缓冲区）、:b（编辑缓冲区）、:bn（下一个缓冲区）和:bp（前一个缓冲区）。然而，通常情况下，在找到正确的文件之前，你的大部分时间都在键入:bn、:bn、:bn。

Bufexplorer使得在vim中处理多个文件变得轻而易举。它添加了\be键绑定（\是前导键），它会打开一个所有缓冲区的列表，移动到显示文件名的行并按回车键，你就可以快速切换到另一个缓冲区。
3.Bufferize

许多vim命令继承自vi，它们的输出非常简陋。它们把输出打印到屏幕上，不能搜索或复制。如果你按空格太多次，内容就消失了。几乎不可能搜索这个文本，有时你甚至不知道如何让vim再次显示它。

Bufferize解决了这个问题。它接受一个vim命令并从其输出创建一个临时缓冲区，然后在一个分屏窗口中打开它。例如:Bufferize map将在一个新窗口中显示所有键盘映射，你可以搜索它们。要退出新窗口，只需使用常规的:q命令。
4.Bufferline

Bufferline补充了Bufexplorer（见上文），使它更容易处理多个文件/缓冲区。它在状态行中打印所有打开的文件及其缓冲区编号的列表。你只需要浏览一下这个列表，输入:b 5就可以切换到第5个文件/缓冲区，或者使用Bufexporer，点击\be后面跟/5，然后回车。
5.Bufkill

如果你在一个分割中打开了两个缓冲区，并且你想要关闭一个缓冲区，那么你可以使用:bd命令。不幸的是，这个命令也关闭了分割。通常，你不想关闭分割，而只想关闭缓冲区。在这种情况下，使用Buffkill的:BD命令，该命令将关闭缓冲区，但保留分割。
6.Characterize

Characterize添加了ga快捷方式，显示光标下Unicode字符的名称、代码点值和十六进制值。
7.Clever-f

此扩展改进了用于查找下一个/前一个字符的f和F快捷键。按下fa会转到下一个a。按下Fa会转到前一个a。没有这个扩展，你必须再次输入fa来找到下一个a或者按下分号;。类似地，你必须输入Fa或，才能再次找到前面的a。如果你是一个vim老手，你已经在用;和,，你最终会fafafafa或FaFaFaFa。

有了这个扩展，你可以再按一次f，它会搜索下一个字符，你可以再按一次F，它会搜索前一个a，所以，不用fafafafa，你现在可以用fafaff代替FaFaFaFa，你可以FaFFF。此外，当你按下f或F时，它将显示下一个/前一个匹配项，你立即就知道光标将跳转到哪。
8.Colorscheme-gruvbox

深色系主题。灰色背景，浅绿色文字和功能。
9.Colorscheme-jellybeans

深色系主题。黑色背景，浅绿色文字，浅黄色功能。
10.Colorscheme-seoul256

深色系主题。灰色背景，淡蓝色文字，淡黄色功能。
11.Commentary

最简单、最快捷的注释插件之一。按gcc将整个行注释掉。按gc注释掉一个可视化选中部分。再次按下相同的快捷键取消注释。
12.Conflicted

这个插件有助于解决git合并冲突。假设你刚从github上的项目主分支中取出代码，遇到了一个合并冲突错误。要解决这个问题，可以运行这个插件提供的:Conflicted命令。该命令创建一个三向diff，并将结果放在三个垂直分割的窗口中。左边的分割是上游更改，中间的分割是工作更改，右边的分割是本地更改。你可以接受上游diff或本地diff来解决冲突。为快速接受正确的diff, Conflicted提供了两个键映射。dgu命令将使用上游diff，dgl将使用本地diff。要解决下一个冲突，使用:GitNextConflict命令。如果没有更多的冲突，vim将退出，你可以git commit已解决冲突的文件。
13.Ctrlp

这个插件添加了ctrl+p绑定来打开一个模糊文件打开对话框。例如，如果你需要编辑math-config.json文件，你可以键入文件名的一些字母，如mat.js、mjson，甚至thfig（“th”是“math”的最后两个字母，“fig”是“config”的最后三个字母）。Ctrlp将立即缩小搜索范围，并提供最佳匹配。它还可以用来打开mru文件（最近使用的文件）和缓冲区，你可以使用ctrl+r和ctrl+f快捷键在文件/mru/缓冲区模式之间切换。
14.Ctrlp-funky

Ctrlp-funky通过添加函数查找模式扩展了上面的Ctrlp插件。你可以运行:CtrlPFunky命令，立即在函数搜索模式下打开Ctrlp，或按下ctrl+p打开Ctrlp，然后按ctrl+r（或ctrl+f）几次，进入函数搜索模式。例如，如果你有一个void debug_print()函数，你可以输入vodepr（单词void、debug、print的前两个字母），然后回车，vim将跳转到这个函数的定义。
15.Ctrlsf

有了这个插件，你可以快速搜索和替换大量的文本。当你运行:CtrlSF模式命令时，它将在左侧创建一个包含所有匹配项的结果窗口。“结果”窗口中还有一些围绕匹配项的上下文行，方便你知道你正在查看的是否是正确的匹配项。现在，你可以直接在结果窗口中进行编辑。当你保存结果窗口时，更改也将保存在文件中。你也可以按下回车键，在右边的窗口中打开每个结果并在那里编辑它。
16.Delimitmate

Delimitmate会自动关闭引号和括号。例如，你输入“会自动得到“”，而且光标位于两个引号之间。
17.Diff-enhanced

这个插件为vimdiff添加了一个新的diff可视化方法，它试图最小化差异的数量。当你处于diff模式时，输入:EnhancedDiff patience命令，你就能够更好地查看diff。
18.Dirvish

Dirvish支持惯用的缓冲区驱动开发，它作为一个文件浏览器补充了Nerdtree（见下文）。当你按下-键时，当前缓冲区将变成一个文件浏览器。你将看到当前工作目录或当前打开的文件目录中的所有文件。然后可以使用箭头键hjkl和搜索操作符/导航这个目录并查找文件。当你按下回车键时，Dirvish将退出，光标下的文件将在当前窗口中打开，作为一个新的缓冲区。当你有多个分割打开时，这个插件特别强大，因为你可以指定下一个文件在哪个分割中打开。你只需导航到分割，点击-，找到文件，然后点击回车，就可以在希望的分割中打开它了。
19.Dsf

Dsf是删除周围函数的缩写。通过在函数调用中按下dsf，它将删除周围的函数名。例如，如果你有像print_r(get_post|s(true))这样的代码，并且你的光标位于|字符所在的位置，那么当你按下dsf时，你将获得输出get_posts(true)。
20.Easy-align

有了这个扩展，你就可以整齐地将文本对其到列中。它添加了:EasyAlign命令，你可以将其绑定到你想要绑定的任何键盘快捷键。当你执行它时，它会要求你输入列分隔符字符，然后对所选文本进行格式化。例如，要对齐代码使所有=符号都在同一列中，你可以使用V命令直观地选择行，然后运行:EasyAlign，接着=，然后回车。
21.Easymotion

Easymotion让你可以更快地在文件中导航。它添加了\\ w快捷方式，允许你快速跳转到光标之后的任何单词。它为每个单词分配一个唯一的字母，当你下次按下它时，光标会立即跳转到该单词。它还添加了\\b快捷方式，让你可以快速地向后导航。类似地，如果你需要跳转到上面或下面的任何一行，你可以使用\\k和\\j快捷键。
22.Exchange

使用Exchange插件，你可以非常快速地交换两个单词。转到第一个单词并按cxw，然后转到第二个单词并再次按cxw。你就完成了这两个词位置的交换！

实际上，你不仅可以交换两个词，还可以交换任何两个motion。按下cx后，下一个快捷键是motion（motion是移动光标的键盘快捷键）。例如，要交换两个字符，可以执行cxl，然后再执行cxl（l是将光标向右移动一个位置的动作）。类似地，要交换两个句子，你可以执行cxis，然后对第二个句子也执行cxis操作。在这种情况下，motion是选择整个句子。

同样，如果两个motion相同，只要按一下.重复第一个操作。
23.Expand-region

通常，你希望选择比刚刚选择的文本多一点的文本。例如，你使用viw选择了一个单词，但随后发现需要选择整个引用字符串。有了这个插件，你可以按+，它会把当前的选择扩展到下一个最大的文本对象。从字符到一个单词、一个带引号的字符串、一行、一段到整个文件。
24.Far

Far使查找和替换多个文件中的文本变得很容易。它添加了:Far pattern1 pattern2命令。当你运行这个命令时，它将屏幕分成两半。在上半部分，它显示了pattern1匹配的所有文件和行。在下半部分，可以预览匹配的上下文。在上面的分割中，你可以使用hjkl键来导航匹配项。默认情况下，所有匹配项都将用pattern2替换，但你也可以使用t键取消匹配项的标记（并再次使用t标记它们）。选择要替换的所有匹配项之后，运行:Fardo命令。这个命令将执行实际的替换。

Far也很适合于查找所有匹配项。你可以使用:F pattern命令，它将查找所有匹配的模式，并把它们显示在两个分割中，但是它不会执行替换。
25.Fugitive

使用Fugitive，你可以直接从vim使用git。它添加了:Git命令（或简写为:G），该命令运行git status，并在一个分割窗口中显示结果。然后，可以使用键盘快捷键s来暂存（git add）一个文件，使用u来恢复（git reset）一个文件。暂存文件之后，可以按cc创建提交。我还不知道如何进行git推送，所以这是我需要学习的内容。如果我能够在不离开vim的情况下进行代码推送和部署，那将非常方便。
26.Fzf

Fzf是Ctrlp（见上文）的一个替代方案。它为快速打开文件和切换缓冲区添加了几个命令。这些命令是:Files和:Buffers。如果你以前是按多次tab键来补全文件名和缓冲区名，那么现在你只需要键入文件名或缓冲区名的几个字母。例如，如果你需要打开options.c文件，你可以直接输入opt.c，甚至是oc，Fzf都会为你提供最佳匹配。
27.Fzf-mru

Fzf-mru增加了一个可以通过:FZFMru命令访问的mru模式。此模式允许你快速访问最近编辑的文件。假设你昨天在从事scraper项目相关的工作。今天，当你进入mru模式时，只需要输入scra，它就会显示你昨天处理的scraper项目的所有文件。
28.Gitgutter

Gitgutter增加了两个有用的东西。第一个列位于vim最左边，它快速显示当前文件的git diff信息。你可以快速查看添加和更改了哪些行。第二个是]c和[c映射，让你可以在更改的行之间跳转。
29.Goyo

我最近切换到Goyo模式编程。当你输入:Goyo命令时，这个插件会将内容居中，并删除行号和状态行，这样你就可以专注于无干扰的编码了。如果还让vim全屏，那就更好了。
30.Grepper

Grepper改进了vim中的查找，并增加了对ripgrep的支持。你可以输入:Grepper，然后输入你的搜索查询，它将找到所有匹配项并在quickfix窗口中加载它们。然后你可以使用vim的:cn和:cp命令来导航到下一个/前一个匹配项，或者使用Unimpaired插件（见下文）的快捷方式]q和[q。

这个插件的作者建议将它与qfenter.vim插件一起使用。这是我还要尝试的东西。
31.Gv

Gv将git提交浏览器添加到vim中。你可以运行:GV命令，它将显示整个提交树。然后，你可以在提交窗口中按下回车或o来查看各个差异。要退出diff查看器，请按q。如果你只对当前文件的git日志感兴趣，那么可以使用:GV!命令。
32.Illuminate

Illuminate高亮显示当前可见缓冲区中光标下这个单词的所有出现。例如，如果光标在单词var上，那么所有其他的var也将高亮显示。
33.Interestingwords

这个插件允许你同时高亮显示多个单词。它添加了快捷方式\k，可以更改光标下单词的背景颜色，以及文件中出现的所有相同单词。你还可以使用n和N来跳转到下一个/上一个高亮显示的单词。当你处理复杂的代码并需要跟踪多个变量的使用情况时，它非常有用。
34.Linediff

Linediff让你可以快速比较两个文本块。可视地选择第一个文本块并运行:Linediff命令。然后可视地选择第二个块并再次运行相同的命令。这个插件将创建一个新的标签页，将两个文本块的差异垂直分割。如果结果看起来太冗长，运行:EnhancedDiff patience命令（来自上面的Diff-enhanced插件）来改进差异。

你还可以使用这个插件快速解决git合并冲突。如果你打开的文件中存在合并冲突，将光标放在合并冲突标记<<<<<<和>>>>>之间，并运行:LinediffMerge命令。接下来，插件会自动创建一个垂直分割，分割合并冲突差异，你可以在左边或右边的分割中进行编辑，并通过运行:LinediffPick命令来自动解决合并。
35.Listtoggle

一旦你对vim的熟练达到了一定的程度，你将开始一直使用quickfix窗口（以及位置列表窗口）。查找结果将在quickfix中，linting错误将在quickfix中，编译错误将在quickfix中，待办事项列表将在quickfix中。一切都会很快解决。你会一直关闭和打开quickfix。不幸的是，没有简单的方法来切换quickfix窗口和位置列表窗口。你必须使用:copen和:cclose命令来打开/关闭quickfix，以及:lopen和:lclose来打开/关闭位置列表。这打字太多了。

Listtoggle使它更加简单，并增加了两个快捷方式来快速切换它们。\q绑定将切换quickfix窗口，而\l绑定将切换位置列表窗口。
36.Locate

通常，你需要查找当前文件中的所有出现。你不想来一次全局搜索，你不想搜索和替换，你不想要任何分割，你只想要一个所有结果的总览。Locate通过:Locate命令（或简写为:L）提供完全相同的功能。只需键入:L pattern，这个插件就会打开一个快速位置列表，其中包含当前文件中所有出现该模式的地方。你可以使用快捷方式\l切换位置列表（由Listtoggle插件提供，见上文），你还可以通过快捷方式]l（下一个结果）和[l（前一个结果）（由Unimpaired插件提供，见下文）来浏览结果。
37.Matchtagalways

这个插件突出显示了光标所在位置最内层的HTML打开和关闭标记。例如，如果光标在<div class="post">cursor here</div>，那么这个插件将突出显示<div>和</div>标签。
38.Matchup

Matchup添加了快捷方式%，允许你在匹配的括号对之间快速跳转。如果你的光标在{字符上，那么按%后它将跳到}。如果你再次按%，它将跳回{。它还添加了快捷方式z%，使你可以向前跳转到下一对圆括号内。假设你有一个函数pri|nt_data("hi"， 7)和你的光标在|。然后，在按下z%之后，光标将出现在函数参数中。
39.Nerdcommenter

Nerdcommenter是另一个代码注释插件。借助Commentary （见上文），你可以使用gc快捷方式快速切换注释，但是Nerdcommenter提供了对注释的更多控制。例如，你可以使用\cm快捷方式执行多行注释，并使用\cA快捷方式在行尾添加注释。
40.Nerdtree

Nerdtree是一个文件管理器。它在vim的左侧显示当前项目的完整目录和文件树结构。要打开和关闭Nerdtree，请运行:NERDTreeToggle命令。方便起见，你可以将它绑定到快捷方式\t。当它打开时，你可以使用常规的hjkl键进行导航。使用键O打开项目中的所有目录，然后使用常规的/search操作符搜索文件。要在右侧打开光标下的文件，请按下ok键。要查看隐藏的文件，请使用I键。与Dirvish（见上文）相比，它支持文件管理器驱动的开发。Nerdtree总是在右侧打开文件，而不是指定在哪里打开文件。
41.Nerdtree-syntax-highlight

这个插件将语法高亮显示添加到Nerdtree中。现在，文件和目录有了不同的颜色。
42.Peekaboo

Vim有许多不同的寄存器。当你复制文本时，它会进入"寄存器。当你删除文本时，它会进入数字寄存器。然后还有小写和大写等寄存器供你个人使用。

当你要使用寄存器时，这个插件会预览它们。当你按下"键时，它会在右侧打开一个寄存器备忘单，你可以看到每个寄存器的内容并选择正确的寄存器。你还可以按空格键加大寄存器备忘单。
43.Qfgrep

Quickfix是vim最大的特性之一。不幸的是，一旦用结果填充了quickfix列表，它就会被冻结。你无法进一步过滤quickfix列表。这种行为不太合理，因为你总是希望细化结果。

Qfgrep允许你这样做。现在，你可以在quickfix窗口中过滤结果。使用\g快捷方式过滤结果，\v转换过滤结果，\r还原原始条目。它还添加了:QFGrepPat命令，该命令执行与\g相同的操作，:QFGrepPatV则执行与\v相同的操作。
44.Qlist

Qlist添加了:Ilist函数，它是vim内置的:Ilist函数的改进版本。内置的:ilist函数来自一个计算机没有多少内存的时代，所以它当时不是很有用，因为它会一股脑把所有东西都打印到屏幕上，你无法使用这样的结果（见上文的Bufferize插件）。改进后的:Ilist函数从结果中创建一个quickfix列表。你现在可以运行:Ilist pattern，这个插件将在当前以及包括的项目文件中找出所有用到的单词模式，并把它们放在quickfix窗口中，正是你想要显示所有结果的地方。
45.Quickfix-reflector

你不仅希望筛选quickfix结果（上面的Qfgrep），还希望编辑quickfix窗口，就好像它只是另一个缓冲区一样。这个插件使得quickfix窗口可以修改。现在可以使用dd删除quickfix条目，使用i添加新条目。你还可以直接编辑quickfix结果，当你通过:w保存quickfix窗口时，文件也会得到更新。
46.Ragtag

Ragtag为处理HTML标签添加了三个有用的键盘快捷键。第一个是ctrl+x/关闭任何打开的标签。例如，如果光标在

标签中，那么你可以立即闭合它并得到

…


。第二个是ctrl+ xSPACE，它根据刚刚输入的单词创建一个开始和结束标签。例如，如果你输入tag，然后立即按下这个快捷键，那么你将得到|，其中|是光标。第三种是ctrl+xENTER，它的工作方式与前一种快捷方式相同，但在两个标签之间放了一个空行。
47.Ranger

这个插件让你可以跳转到外部Ranger文件管理器，在vim中打开一个文件。它类似于Dirvish（见上文），让你可以轻松地进行缓冲区驱动的开发。当你在任何窗口中运行:Ranger命令时，它将启动ranger进程。然后，当你选择一个文件时，它将在选择的文件中作为一个新的缓冲区打开。
48.Repeat

Repeat改进了.命令。它让你可以重复其他插件的命令和动作。例如，如果你使用Surround插件（见下文）将文本括在引号中，那么按下.会重复这个动作。
49.Rooter

由于vim不是IDE，所以它几乎没有项目的概念，也不知道项目的根目录是什么。当你尝试打开一个文件时，vim会搜索主目录或其他目录，而不是项目目录。

这个插件会自动将vim的当前工作目录设置为项目目录，使得处理项目变得更加简单。它通过查找最根部的.git目录来实现。通常，此类目录表明了项目的起点。
50.Scratch

Vim的文档提到了一种称为scratch缓冲区的特殊缓冲区类型。这个插件实现了它。Scratch缓冲区是临时丢弃缓冲区。当你在做一个项目的时候，快速笔记是很有用的。使用:Scratch命令打开它。光标将跳转到顶部的scratch窗口。当你将光标移动到另一个窗口时，scratch窗口将自动关闭。
51.Signature

当使用标记时，没有一种可视化的方式来告诉你在哪里添加了它们。你可能记得一两个标记，但当你再加的时候，你就迷失了。这个插件解决了这个问题，它会在最左边的列中显示标记。你可以用默认快捷方式ma、mb、…添加和切换标记，用dma、dmb、…删除单个标记，用m-删除所有标记，用]'和['跳到下一个和前一个标记，用m/将所有标记放到位置列表窗口中。
52.Speeddating

在正常模式下，ctrl+a和ctrl+x可以实现数值递增和递减。这个插件使这些键盘快捷键也可以实现日期和时钟时间的增加。例如，如果光标位于字符串2000-01-31上时，按ctrl+a将使其变为2000-02-01，按ctrl+z将使其变为2000-01-30。
53.Splitjoin

Splitjoin让你可以将代码片段从单行语句切换到多行语句，反之亦然。假设你有一个单行HTML代码片段

 hi 


，然后按gS（分割），它将转换成一个多行HTML代码片段

\n hi \n


。如果你在这个多行代码段上按下gJ（合并），它将再次变为一个单行代码段。
54.Surround

借助Surround，你可以快速删除、更改和添加文本周围的匹配符号对。假设你有一个字符串"hello world"。按下ds"，引号将被删除，字符串将变成hello world。按下c"‘键，双引号会变成单引号，字符串会变成’hello world’。你还可以按下cs"

，这将把引号改为

HTML标签


，字符串将变成

hello world


。如果你有一个普通的字符串hello world，那么要将它括在引号中，请使用v选择它，然后按S并输入包围符号。如果你有一个单词hello，你想把它用单引号括起来，按ysiw'。
55.Swap

Swap让你可以快速地交换单词或逗号分隔的函数参数。例如，如果你有一个函数print(a, b, c)，那么你可以按g>，它会变成print(b, a, c)。按g<，它会再次变成print(a, b, c)。你还可以通过按gs进入可视化交换模式。然后使用hjkl键来交换参数。
56.Syntax-css3

CSS3语法高亮插件。
57.Syntax-dockerfile

Dockerfile语法高亮插件。
58.Syntax-html5

HTML5语法高亮插件。
59.Syntax-i3config

i3窗口管理器配置文件语法高亮插件。
60.Syntax-javascript

JavaScript语法高亮插件。
61.Syntax-json

JSON语法高亮插件。
62.Syntax-nginx

Nginx配置文件语法高亮插件。
63.Syntax-php

PHP语法高亮插件。
64.Syntax-tmux

tmux配置文件语法高亮插件。
65.System-copy

Vim终端没有用于从系统剪贴板复制和粘贴的寄存器*或+。这个插件添加了cp快捷方式，通过调用外部实用程序xsel将所选文本或motion复制到系统剪贴板。它还具有从系统剪贴板粘贴的快捷方式cv。
66.Tabular

Tabular的功能与EasyAlign（见上文）相同。它对文本进行列对齐。与EasyAlign相比，它的一个优点是，你可以直接将用于对齐的正则表达式传给它。与正则表达式相匹配的位置将会对齐。例如:Tabular /regex将创建整齐的regex列。
67.Tagalong

这个插件可以很容易地重命名HTML的开闭标签对。你只需要重命名其中一个，这个插件会自动重命名另一个。例如，如果你有

…


，你把开标签

重命名为

，那么闭标签会自动重命名为


，你将得到输出

…


。
68.Targets

掌握vim的一个步骤是学习使用文本对象。文本对象允许你操作整个文本结构，而不是单个字符。Vim已经附带了许多文本对象——你可以访问单词、句子、段落和代码块。这个插件增加了十几个文本对象。例如，你可以使用di删除逗号分隔的项，或者你可以使用cin和cil来更改前一个和后一个逗号分隔的项，你可以使用ci+来更改sum元素，等等。
69.Textobj-user

从头编写自己的文本对象非常困难，因为在调用文本对象时必须精确复制vim的行为，并了解所有的陷阱和缺陷。这个插件提供了一个快速简单的接口，让你可以实现自己的文本对象。“textobj”插件有一个完整的生态系统，使用这个插件可以添加各种有用的文本对象。
70.Textobj-entire

这个插件使用Textobj-user（见上文）创建一个文本对象ie和ae来操作整个文件。例如，要选择整个文件，你可以执行vae，要删除整个文件，你可以执行vaed或dae。
71.Textmanip

这个插件让你可以直观地移动选中的文本。例如，你能可视化地选择一个单词，然后使用快捷键ctrl+h和ctrl+l将其向左或向右移动。类似地，你可以使用快捷键ctrl+j和ctrl+k向下移动整个行。
72.Thesaurus-query

有了这个插件，你可以访问Libreoffice同义词典。一旦配置了它，你可以使用:Thesaurus word命令来查找与word相关的所有单词，你还可以使用:ThesaurusW来查找与光标下的单词相关的所有单词。
73.Tmux-complete

当你处于流程中时，会同时发生许多事情，并且会打开许多tmux窗口和窗格。一个显示git日志，另一个用于测试，还有一个显示帮助手册，等等。通常，你需要从tmux窗格获取信息到vim。通常，你必须用鼠标来复制它，但这非常低效。有了这个插件，你可以在插入模式下按下ctrl+x ctrl+u，从任何tmux窗口/窗格补全单词。它将提供来自所有tmux窗口/窗格的所有单词的列表。
74.Traces

当用:s/old/new命令替换文本时，执行这个命令后才能看到更改。这个插件让你可以在输入时预览old匹配和用于替换的部分new，你可以直接看到你是否做对了。
75.Ultisnips

Ultisnips是一个代码片段引擎。当你按下tab键时，它会检查最后键入的Token并将其扩展为代码段。为了让它发挥作用，你需要创建一个language.snippets文件，并在其中写入代码片段。例如，你可以创建php.snippets，加入一个if代码段if ($1) { $0 }。现在，当你在编写PHP代码键入if并按下tab键时，它将扩展为if(|){}，你的光标将位于|字符所在的位置。如果再次按下tab，它将跳转到if () { | }花括号之间的$0 Token。
76.Undoquit

通常，你可能因为操作太快关闭了一个你不想关闭的窗口。有了这个插件，你现在可以按ctrl+w+u撤消关闭操作。
77.Unicode

这个插件让你可以快速搜索和插入Unicode字符。例如，如果你想插入一个Unicode兔子符号，你可以输入rabbit，然后按下ctrl+x ctrl+z。输入文字rabbit将被“兔子”的表情符号取代。
78.Unimpaired

许多命令都是成对的。例如:bn和:bp跳到下一个/前一个缓冲区，:cn和:cp跳到下一个/前一个quickfix列表项，:ln和:lp跳到下一个/前一个位置列表项，等等。此插件为这些命令添加了灵活的快捷方式。你现在可以用]b和[b跳到下一个/前一个缓冲区，用]q和[q跳到下一个/前一个quickfix条目，用]l和[l跳到下一个/前一个位置列表条目，等等。
79.vimade

当你使用多个分割窗口时，在短暂的分心之后，很容易忘记你在哪个分割窗口中工作。这个插件会淡化其他所有的分割线，使当前聚焦窗口的分割线清晰可见。
80.Visual-split

通常，你需要将注释、函数定义或代码片段在上方折叠，使其始终可见。通常的方法是用ctrl+w+s分割窗口，然后用10ctrl+w+-重新调整窗口大小。这个插件合并了这两个动作。现在你可以直观地选择该区域并按下ctrl+w+gss。该插件将分割窗口并调整大小，使其与所选的行完全匹配。
81.Visual-star-search

有两个操作符可以搜索光标下的单词。它们是*（向前搜索）和#（向后搜索）。不幸的是，在可视化模式中，它们不会搜索可视化选择部分，你也不能搜索包含特殊字符的单词。例如，如果单词是h#e#l#l#o，那么这些操作符将选择并搜索这个单词中的一个字母，这不是你想要的。

使用此插件，你可以搜索可视化选择的序列，它可以包含任何特殊字符。使用v命令进行选择，然后按*或#进行搜索。
82.Writeable-search

Writeable-search类似于CtrlSF（见上文）。它让你可以快速查找结果并立即在结果窗口中编辑它们。当你运行:WritableSearch pattern命令时，它将在当前目录中的所有文件中搜索这个pattern，并打开一个包含结果的新选项卡。然后，你可以编辑结果，当你在相同的结果窗口中执行:w操作时，它会更改更新文件。如果你已经在quickfix窗口中有一个要修复内容的列表，那么你可以通过:WritableSearchFromQuickfix命令将它们转移到这个插件中进行编辑。
# }}} Fold description #

# zhejiang
台风数据库建设会议纪要
参会人员：
闫建忠，蒋关银，陈明天，彭亮，吕梦霞，沈翊（浙江省气象台）

项目的需求基本上比较明确，会上主要是针对一些的小的技术细节进行了交流。
以下是会上双方提问记录，以及沟通后得到的结果：

1、数据如何获取？
部分数据存储在本地，部分数据存储在其他单位如 --气候中心（登陆等） 网络中心（登陆，定位，中央台的报文，cimiss）
，经过统计整理后放到云平台；最终落地大数据平台，对数据进行归一化
硬件由由网络中心提供

2、区块链需要做什么应用？
主要用来对数据进行分发和追溯。

3、搜索规则如何制定？
常规方式：通过时间和地点、台风名称来搜索台风。
模糊搜索、智能搜索：通过台风的典型特征设置关键字等，来搜索和统计台风。

4、如何判断相似天气形势?
相似天气形势是相对最难的算法开发，目前还需要进一步和甲方对接。
目前的的初步思路是通过副高位置、平均温度、海面温度、水汽分布来进行相似天气形势的判断。

5、相似台风的匹配？
主要通过台风路径和强度、登陆位置、生成位置等进行匹配，目前公司有相应的算法积累，算法完善难度不大。



# lipeng
56, 57



# 
登陆气象局服务器步骤：
(1) 登陆公司内部ads服务器
(2) 登陆hp：
   ssh localhost -p 11111
(3) 登陆ads服务器
   ssh 10.24.237.32

下数据（ads计算结果：/mnt/swapdata/swapproduct/FY4A/AGRI/L3/）可以在hp上用scp下载，然后在ads上用scp -P 11111 localhost:/xx/xx下载到ads服务器上。
如果发现有连不上的情况，立即通知我。
不要直接操作服务器的容器（1.难以同步所有服务器的容器。2.docker权限太高，比较危险）如有操作，务必通知我，并做好记录！
如需要更新代码，请找我了解更新流程。

从气象局下载数据方法：
（1）登陆公司ADS服务器
（2）运行以下命令：
get <infile> <outpath>
<infile> 指的是气象局ADS服务器数据的名称，可以包含通配符
<outpath> 公司服务器的地址，如果没有，程序可以自动新建
如：
get_data /mnt/swapdata/swapproduct/FY4A/AGRI/L3/DISK/HHMM/LST---/NOM/2020/20200329/FY4A-_AGRI--_N_DISK_1047E_L3_LST---_MULT_NOM_202003292*.NC /mnt/swapdata/lfw/
注意：
1. 单次不要下载太多，可以自己写脚本调用这条命令。
2. 下之前注意查看剩余空间。

schemernn274
1471079987

# 遥感论团

大屏： 无交互，视频。主题的名字需要报给会务组。通过两行小字展示主题。
气象分论坛（20号上午）：补充专家，定好题目。邀请函，简介。本周必须敲定所有专家。



# 1014
目前提供了3～5微米和8～12微米共8个通道，涵盖了wq制导所用的频率。
云的分布概率，打算用cloudsat云分布数据来进行检验。
海拔高度用的是位势高度转换的。
影响分级综合考虑了透过率和云分布概率的影响，设立了不同的阈值进行影响的划分。

# daily report
2020-1116
1 台风客户端开发
2 风三大风算法完善
3 1043台风预报数据添加
4 应急部门项目梳理

2020-1117
1 台风客户端开发
2 风三大风算法完善
3 1043台风预报数据添加
4 应急部门项目梳理
5 风三项目PPT修改



# 刘玉明
刘总，天津气候中心


# 马耀明
经过二十余年的艰苦努力， 首套青藏高原地-气相互作用过程逐小时长时间序列综合观测数据集发布（https://data.tpdc.ac.cn/zh-hans/news/c05e03fd-aa87-4ee7-b5c1-d971f5953325），欢迎各位校友下载使用！



# ads test
1. 问题整理，调整电子版用例
2. 接口测试用例
3. 性能测试用例
4. 每个用例加实测结果和签字，文档需要添加测试结果。
5. 周五验收
6. `test`

# 503

http://18av.mm-cg.com/av_Broadcast/22910.html

# 
1. 登陆 模拟 tk  双向对抗 核心
2. 任务推演
3. 一台电脑（综合） VR，登陆模拟（重点）视角是装备，重点是装备（需要战场环境）。
   xxx另一台：台海， 浮标（与具体应用有差距）
   另一台：直观场景，数字球> 台湾海峡 > .. > 台湾省 > .. >登岛作战
4. 机场（飞机识别）码头（军港）（船只识别），并用ppt说明一下以提供保障能力（能提供飞机xxx架，能提供船只xxx架）的信息提取，覆盖范围，打击范围。并提供结论（作为项目需求）。
5. 展示 > 浮标 > 仿真模拟 > 协同数据展示 （VR眼镜）
6. 数据：数据融合，PPT介绍前瞻技术，PIE，SIT。PIE功能，技术特点，效率，各种数据整合。与其他软件对比。典型的系统界面。需要高清的视频界面。典型应用介绍。系统环境。
7. pie-engine 的数据处理流水线，4D数据处理。特点，和其他软件对比。。。部署一个系统，数据够多。对dim数据的处理。机场港口码头数据8. 数据融合：仿真平台体现？如何体现？
9. SAR，SIT低轨卫星
10. 数字地球，需要多少设备，优先部署系统，其次视频。BS免费注册。
11. 先看视频和ppt，然后部署系统。4D数据处理，任务编排。
12. 自主可控。

# 项目月报
test

# 2021年 02月 04日 星期四 13:29:26 CST

ADS：
项目进展：
完成了Tlog-P图的开发工作。
完善了太阳能的工程化。
升级了大雾集合预报的环境优化等工作。
完成了台风定位定强程序的优化，以中央气象台数据为输入。

项目计划：
完成Tlog-P图的上线和稳定运行。
太阳能子系统上线。
大雾集合预报上线。
推进大风和降水产品的切图发布和稳定运行。

全球陆地植被生态监测评估系统：
项目进展：
完成了项目的对接。

项目计划：
与客户对接，进一步明确需求。
推进调度工作的开发。
# }}}

# 农气
全球产量，[长势](逐县逐旬的观测，长势，面积，NDVI区域平均，下垫面，分布图，数字，序列)
国内作物产量，[长势](逐县逐旬的观测，长势，面积，NDVI区域平均，下垫面，分布图，数字，序列)
卫星监测[干旱](代替人工)
高分资料的应用
基础的处理
冬小麦，陕西，安徽，湖北等十个省面积的估算，利用高分
集成北师大全球叶面积指数反演 landsat FY3号叶面积指数全球[权威](和modis产品相比)产品
高分产品叶面积指数[序列](用高分代替人工观测，每个月每个旬的叶面积指数，形成序列) [面积](CS界面)

全球陆地植被生态监测评估系统
1 算法开发大概完成了70%
  全球植被生态评估产品制作 完成
  全球土壤水分评估产品制作 一带一路矢量
  [全球干旱产品制作](需提供的NDVI旬产品的最大值、最小值与平均值、LST旬产品的最大值、最小值与平均值尚未提供)
  [全球重点农牧区生态统计分析](分县产量数据由用户方提供)
2 主要是调度和前端展示的问题
3 提供一带一路的矢量
4 需要提供分县产量数据



# 临近空间阅读笔记
下面的文章较为清晰的论述了激光雷达测温的基本原理
wps ~/doc/paper/合肥上空中层大气密度和温度的激光雷达探测.pdf

