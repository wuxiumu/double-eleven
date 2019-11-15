## 命令行接口
PHP 是为开发 Web 应用而创建，不过它的命令行脚本接口(CLI)也非常有用。PHP 命令行编程可以帮你完成自动化的任务，如测试，部署和应用管理。

CLI PHP 编程非常强大，可以直接调用你自己的程序代码而无需创建 Web 图形界面，需要注意的是 不要 把 CLI PHP 脚本放在公开的 web 目录下！

在命令行下运行 PHP :
```
> php -i
```
选项 -i 将会打印 PHP 配置，类似于 phpinfo() 函数。

选项 -a 提供交互式 shell，和 Ruby 的 IRB 或 python 的交互式 shell 相似，此外还有很多其他有用的命令行选项。

接下来写一个简单的 “Hello, $name” CLI 程序，先创建名为 hello.php 的脚本：
```
<?php
if($argc != 2) {
    echo "Usage: php hello.php [name].\n";
    exit(1);
}
$name = $argv[1];
echo "Hello, $name\n";
```
PHP 会在脚本运行时根据参数设置两个特殊的变量，$argc 是一个整数，表示参数个数，$argv 是一个数组变量，包含每个参数的值， 它的第一个元素一直是 PHP 脚本的名称，如本例中为 hello.php。

命令运行失败时，可以通过 exit() 表达式返回一个非 0 整数来通知 shell，常用的 exit 返回码可以查看列表.

运行上面的脚本，在命令行输入：
```
> php hello.php
Usage: php hello.php [name]
> php hello.php world
Hello, world
```

>其他
- [CGI、FastCGI和PHP-FPM关系图解](https://www.php.cn/php-weizijiaocheng-392861.html)
    - CGI：是 Web Server 与 Web Application 之间数据交换的一种协议。
    - FastCGI：同 CGI，是一种通信协议，但比 CGI 在效率上做了一些优化。同样，SCGI 协议与 FastCGI 类似。
    - PHP-CGI：是 PHP （Web Application）对 Web Server 提供的 CGI 协议的接口程序。
    - PHP-FPM：是 PHP（Web Application）对 Web Server 提供的 FastCGI 协议的接口程序，额外还提供了相对智能一些任务管理。
- [PHP7内核剖析1之CGI与FastCGI](http://www.php.cn/php-weizijiaocheng-392474.html)
- [CGI、FastCGI 和 PHP_FPM到底有什么关系？](http://www.php.cn/php-weizijiaocheng-391559.html)    
- [PHP7内核CGI与FastCGI详解](https://www.jb51.net/article/159679.htm)