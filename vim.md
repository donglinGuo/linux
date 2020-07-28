

1. 字符串替换, [addr]s/from/to/[option]
    * % 表示操作区间;%表示全文本; “n,m”表示从第n行到第m行, ".,$"表示从当前行到末尾; [addr]省略时表示当前行
    * s表示替换substitute
    * from表示要查找的字符串，若出现特殊字符，需要通过‘\’进行转义
    * to表示目的字符串
    * option表示操作类型
        * g:global，表示全局替换，如果没有配置该参数，则只替换每一行的第一个匹配
        * c:confirm,表示进行确认
        * p:表示替代结果逐行显示，Ctrl+L恢复屏幕
        * i:ignore,不区分大小写
        * n:统计匹配次数，并且不进行替换
        
2. cat file|greg –i pattern |wc –l