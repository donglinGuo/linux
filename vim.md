## Vim

#### Buffers, Windows, and Tabs

* Buffers，指的是内存中用来加载文件以便读写的空间，每打开一个文件就会创建一个buffers用来加载这个文件的内容，写操作也是将内容写到buffer里。
  * vim 里创建一个新的buffer`:new`，如果一个buffer没有绑定到某个文件可以指定文件进行保存`w /path/to/file`
  * 同时打开多个文件`vim file1 file2`时会加载多个buffer，但只展示一个buffer的内容，此时可以通过`:ls`或者`:files`来查看已经加载的buffer。
  * 同时加载多个buffer时可以通过`bnext`, `buffer + n`, `buffer + filename`来切换不同buffer，或者通过快捷键`ctrl+o, ctrl+i, ctrl+^`来切换buffer。
  * buffer一旦建立就存在buffer list中，可以通过`bdelete + n/name`将其从buffer list中移除。

* windows, 指的是用来展示buffer中内容的窗口，一般情况下只有一个窗口展示一个buffer。
  * 可以通过`split filename`或者`vsplit filename`切分出多个窗口
  * 多个窗口时可以通过`ctrl+w h,j,k,l`来切换不同的窗口。
  * 如果想关闭窗口可以通过命令`:quit`或者`ctrl+w c`,此时窗口关闭但对应的buffer依然存在
  * 此外还可通过`ctrl+w v,s,o(only)`来控制窗口
  
* tabs,tab是windows的集合，和windows一样用于展示多个buffer，关闭时buffer依然存在。
  * 可以通过`vim -p file1 file2 file3`打开多个tab展示buffer。
  * vim中可以通过`tabnew filename,tabclose,tabnext,tabprevious，tablast,tabfirst`控制多个tab。

#### Opening and Searching Files



#### 参考
* https://github.com/iggredible/Learn-Vim