
* 7种文件类型
  * 普通文件类型 
    * Linux中最多的一种文件类型, 包括 纯文本文件(ASCII)；二进制文件(binary)；数据格式的文件(data);各种压缩文件.第一个属性为 [-]
    * 目录文件，就是目录， 能用 # cd 命令进入的。第一个属性为 [d]（directory），例如 [drwxrwxrwx] 
    * 块设备文件，就是存储数据以供系统存取的接口设备，简单而言就是硬盘。例如一号硬盘的代码是 /dev/hda1等文件，第一个属性为 [b]（block）。
    * 字符设备，字符设备文件：即串行端口的接口设备，例如键盘、鼠标等等。第一个属性为 [c]（char）。
    * 套接字文件，这类文件通常用在网络数据连接。可以启动一个程序来监听客户端的要求，客户端就可以通过套接字来进行数据通信。第一个属性为 [s]（socke），最常在 /var/run目录中看到这种文件类型。
    * 管道文件，FIFO也是一种特殊的文件类型，它主要的目的是，解决多个程序同时存取一个文件所造成的错误。FIFO是first-in-first-out(先进先出)的缩写。第一个属性为 [p]（pile）。
    * 链接文件，类似Windows下面的快捷方式。第一个属性为 [l]（link），例如 [lrwxrwxrwx]


* 查看文件类型
  * ls-l/ls-ld
    ```
    ll anaconda-ks.cfg                       //看第一个字符
    -rw-------. 1 root root 2460 6月   1 23:37 anaconda-ks.cfg
    ls -ld /etc
    drwxr-xr-x. 81 root root 4096 Jan 29 03:25 /etc
    ```

* 查看文件状态
  * file、stat
    ```
    [root@localhost data]# file a.txt
    a.txt: ASCII text

    #stat a.txt  查看文件的详细属性（其中包括文件时间属性）
      File: `a.txt'
      Size: 3               Blocks: 8          IO Block: 4096   regular file
    Device: 803h/2051d      Inode: 544365      Links: 1
    Access: (0644/-rw-r--r--)  Uid: (    0/    root)   Gid: (    0/    root)
    Access: 2018-01-28 20:56:01.965885036 +0800
    Modify: 2018-01-28 20:55:27.181876154 +0800
    Change: 2018-01-28 20:55:27.181876154 +0800
    ```