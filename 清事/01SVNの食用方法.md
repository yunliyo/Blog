# SVN 简介

Subversion(SVN) 是一个开源的版本控制系統, 也就是说 Subversion 管理着随时间改变的数据。 这些数据放置在一个中央资料档案库(repository) 中。 这个档案库很像一个普通的文件服务器, 不过它会记住每一次文件的变动。 这样你就可以把档案恢复到旧的版本, 或是浏览文件的变动历史。  

<b>SVN 的一些概念</b>
- repository（源代码库）:源代码统一存放的地方
- Checkout（提取）:当你手上没有源代码的时候，你需要从repository checkout一份
- Commit（提交）:当你已经修改了代码，你就需要Commit到repository
- Update (更新):当你已经Checkout了一份源代码， Update一下你就可以和Repository上的源代码同步，你手上的代码就会有最新的变更
日常开发过程其实就是这样的（假设你已经Checkout并且已经工作了几天）：Update(获得最新的代码) -->作出自己的修改并调试成功 --> Commit(大家就可以看到你的修改了) 。  

如果两个程序员同时修改了同一个文件呢, SVN 可以合并这两个程序员的改动，实际上SVN管理源代码是以行为单位的，就是说两个程序员只要不是修改了同一行程序，SVN都会自动合并两种修改。如果是同一行，SVN 会提示文件 Conflict, 冲突，需要手动确认。  

<b>SVN 的主要功能</b>
- （1）目录版本控制  
CVS 只能跟踪单个文件的历史, 不过 Subversion 实作了一个 "虚拟" 的版本控管文件系统, 能够依时间跟踪整个目录的变动。 目录和文件都能进行版本控制。  
- （2）真实的版本历史  
自从CVS限制了文件的版本记录，CVS并不支持那些可能发生在文件上，但会影响所在目录内容的操作，如同复制和重命名。除此之外，在CVS里你不能用拥有同样名字但是没有继承老版本历史或者根本没有关系的文件替换一个已经纳入系统的文件。在Subversion中，你可以增加（add）、删除（delete）、复制（copy）和重命名（rename），无论是文件还是目录。所有的新加的文件都从一个新的、干净的版本开始。
- （3）自动提交  
一个提交动作，不是全部更新到了档案库中，就是不完全更新。这允许开发人员以逻辑区间建立并提交变动，以防止当部分提交成功时出现的问题。
- （4）纳入版本控管的元数据  
每一个文件与目录都附有一組属性关键字并和属性值相关联。你可以创建, 并儲存任何你想要的Key/Value对。 属性是随着时间来作版本控管的,就像文件內容一样。
- （5）选择不同的网络层  
Subversion 有抽象的档案库存取概念, 可以让人很容易地实作新的网络机制。 Subversion 可以作为一个扩展模块嵌入到Apache HTTP 服务器中。这个为Subversion提供了非常先进的稳定性和协同工作能力，除此之外还提供了许多重要功能: 举例来说, 有身份认证, 授权, 在线压缩, 以及文件库浏览等等。还有一个轻量级的独立Subversion服务器， 使用的是自定义的通信协议, 可以很容易地通过 ssh 以 tunnel 方式使用。
- （6）一致的数据处理方式  
Subversion 使用二进制差异算法来异表示文件的差异, 它对文字(人类可理解的)与二进制文件(人类无法理解的) 两类的文件都一视同仁。 这两类的文件都同样地以压缩形式储存在档案库中, 而且文件差异是以两个方向在网络上传输的。
- （7）有效的分支(branch)与标签(tag)  
在分支与标签上的消耗并不必一定要与项目大小成正比。 Subversion 建立分支与标签的方法, 就只是复制该项目, 使用的方法就类似于硬连接（hard-link）。 所以这些操作只会花费很小, 而且是固定的时间。
- （8）Hackability  
Subversion没有任何的历史包袱; 它主要是一群共用的 C 程序库, 具有定义完善的API。这使得 Subversion 便于维护, 并且可被其它应用程序与程序语言使用。

<b>优于CVS之处</b>
- 1、原子提交。一次提交不管是单个还是多个文件，都是作为一个整体提交的。在这当中发生的意外例如传输中断，不会引起数据库的不完整和数据损坏。
- 2、重命名、复制、删除文件等动作都保存在版本历史记录当中。
- 3、对于二进制文件，使用了节省空间的保存方法。（简单的理解，就是只保存和上一版本不同之处）
- 4、目录也有版本历史。整个目录树可以被移动或者复制，操作很简单，而且能够保留全部版本记录。
- 5、分支的开销非常小。
- 6、优化过的数据库访问，使得一些操作不必访问数据库就可以做到。这样减少了很多不必要的和数据库主机之间的网络流量。

# SVN 安装

<b>在windows下安装 SVN</b>  
1、准备svn的安装文件  
下载地址：https://sourceforge.net/projects/win32svn/  
2、下载完成后，在相应的盘符中会有一个Setup-Subversion-1.8.16.msi的文件，目前最新的版本是1.8.16， 这里就使用这个版本。然后双击安装文件进行安装。我们指定安装在D:\Program Files (x86)\Subversion目录里。  
3、查看目录结构  
把svn安装目录里的bin目录添加到path路径中，在命令行窗口中输入 svnserve --help ,查看安装正常与否。  
至此，windows下的SVN安装完成  

<b>在CentOS下安装 SVN</b>  
大多数 GNU/Linux 发行版系统自带了Subversion ，所以它很有可能已经安装在你的系统上了。可以使用下面命令检查是否安装了。
~~~
svn --version
~~~
如果 Subversion 客户端没有安装，命令将报告svn命令找不到的错误。
~~~
[runoob@centos6 ~]$ svn --version
bash: svn: command not found
~~~
我们可以使用 yum install subversion 命令进行安装。
~~~
[runoob@centos6 root]$ su -
密码：
[root@centos6 ~]# yum install subversion
已加载插件：fastestmirror, security
设置安装进程
Loading mirror speeds from cached hostfile
 * base: mirrors.aliyun.com
 * epel: mirrors.neusoft.edu.cn
 * extras: mirrors.zju.edu.cn
 * updates: mirrors.aliyun.com
解决依赖关系
--&gt; 执行事务检查
...
~~~
安装成功之后，执行 svn --version 命令。
~~~
[root@centos6 ~]# svn --version
svn，版本 1.6.11 (r934486)
   编译于 Aug 17 2015，08:37:43
~~~
至此，centos下的SVN安装完成。

<b>在Ubuntu下安装 SVN</b>  
如果 Subversion 客户端没有安装，命令将报告svn命令找不到的错误。
~~~
root@runoob:~# svn --version
The program 'svn' is currently not installed. You can install it by typing:
apt-get install subversion
我们可以使用 apt-get 命令进行安装

root@runoob:~# apt-get install subversion
Reading package lists... Done
Building dependency tree       
Reading state information... Done
The following packages were automatically installed and are no longer required:
  augeas-lenses hiera libaugeas0 libxslt1.1 ruby-augeas ruby-deep-merge ruby-json ruby-nokogiri ruby-rgen ruby-safe-yaml ruby-selinux ruby-shadow
Use 'apt-get autoremove' to remove them.
The following extra packages will be installed:
  libserf-1-1 libsvn1
...
~~~
安装成功之后，执行 svn --version 命令。
~~~
root@runoob:~# svn --version
svn, version 1.8.13 (r1667537)
   compiled Sep  8 2015, 14:59:01 on x86_64-pc-linux-gnu
~~~
至此，Ubuntu下的SVN安装完成。

# TortoiseSVN

TortoiseSVN 是 Subversion 版本控制系统的一个免费开源客户端，可以超越时间的管理文件和目录。  

下载地址：https://tortoisesvn.net/downloads.html  
页面里有语言包补丁的下载链接。  