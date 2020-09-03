#### 什么是shell

* shell用户和Linux（或者更准确的说，是和Linux内核）之间的接口程序。用户在提示符下输入的每个命令都由shell先解释然后传给Linux内核。

* shell 是一个命令语言解释器（command-language interpreter）。拥有自己内建的 shell 命令集。此外，shell也能被系统中其他有效的Linux 实用程序和应用程序（utilities and application programs）所调用。

#### shell执行的过程

* 不论何时你键入一个命令，它都被Linux shell所解释。一些命令，比如打印当前工作目录命令（pwd），是包含在Linux bash内部的（就象DOS的内部命令）。其他命令，比如拷贝命令（cp）和移动命令（rm），还是存在于文件系统中某个目录下的单独的程序。
* shell 首先检查命令是否是内部命令，不是的话再检查是否是一个应用程序，这里的应用程序可以是Linux本身的实用程序，比如ls 和 rm，也可以是购买的商业程序，比如 xv，或者是公用软件（public domain software），就象 ghostview。然后shell试着在搜索路径($PATH)里寻找这些应用程序。搜索路径是一个能找到可执行程序的目录列表。如果你键入的命令不是一个内部命令并且在路径里没有找到这个可执行文件，将会显示一条错误信息。而如果命令被成功的找到的话，shell的内部命令或应用程序将被分解为系统调用并传给Linux内核。
* shell的另一个重要特性是它自身就是一个解释型的程序设计语言，shell 程序设计语言支持在高级语言里所能见到的绝大多数程序控制结构，比如循环，函数，变量和数组。

#### shell启动程序

* shell在你成功地登录进入系统后启动，并始终作为你与系统内核的交互手段直至你退出系统。你系统上的每位用户都有一个缺省的shell。每个用户的缺省shell在系统里的passwd文件里被指定，该文件的路径是/etc/passwd。passwd文件里还包含有其他东西：每个人的用户ID号，一个口令加密后的拷贝和用户登录后立即执行的程序，（注：为了加强安全性，现在的系统一般都把加密的口令放在另一个文件--shadow中，而passwd中存放口令的部分以一个x字符代替）虽然没有严格规定这个程序必须是某个Linux shell，但大多数情况下都如此。

* 在Linux 和 UNIX系统里可以使用多种不同的shell可以使用。最常用的几种是 Bourne shell (sh), C shell (csh), 和 Korn shell (ksh)。

#### 指定shell解释器

* 当shell执行一个程序时，会要求UNIX内核启动一个新的进程，以便在该进程里执行所指定的程序。当系统只有一个shell时，退回到/bin/sh 的机制非常方便，但现行的UNIX系统都会拥有好几个shell，此时就需要一种方式，指定由那个shell来执行所指定的shell脚本。由此引入了#！这两个字符。当一个文件种的开头是#！时，内核会扫描改行的其余部分，看是否存在可用开执行程序的解释器的完整路径（注：中间出现任何空白符号都会略过）。

    ```shell
    #!/bin/bash
    # Text to the right of a '#' is treated as a comment - below is the shell command
    echo 'Hello, World!'
    ```

    ```shell
    #查看默认shell
    ps | grep $$
    #查看默认shell路径
    which bash
    ```