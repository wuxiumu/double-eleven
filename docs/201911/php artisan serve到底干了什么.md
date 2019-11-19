# "php artisan serve"到底干了什么
https://segmentfault.com/a/1190000013025428

artisan serve
```
#!/usr/bin/env php
<?php

define('LARAVEL_START', microtime(true));

require __DIR__.'/vendor/autoload.php';

$app = require_once __DIR__.'/bootstrap/app.php';

$kernel = $app->make(Illuminate\Contracts\Console\Kernel::class);

$status = $kernel->handle(
    $input = new Symfony\Component\Console\Input\ArgvInput,
    new Symfony\Component\Console\Output\ConsoleOutput
);

$kernel->terminate($input, $status);

exit($status);
```
代码里，`require __DIR__.'/vendor/autoload.php';`的 `autoload.php` 文件是 composer 生成的文件，实际用处就是利用 php 提供 spl_autoload_register 函数注册一个方法，让执行时遇到一个未声明的类时会自动将包含类定义的文件包含进来，举个例子就是脚本当中并没有包含任何文件，但却可以直接 new 一个 `Symfony\Component\Console\Input\ArgvInput` 对象，就是这个 autoload.php 的功劳了。

接下来的这一行，`$app = require_once __DIR__.'/bootstrap/app.php';`，在脚本里实例化一个 `Illuminate\Foundation\Application` 对象，将几个重要的接口和类绑定在一起，然后将 Application 对象返回，其中接下来用到的 `Illuminate\Contracts\Console\Kernel::class` 就是在这里和 `App\Console\Kernel::class` 绑定在一起的。

`$kernel = $app->make(Illuminate\Contracts\Console\Kernel::class);`，直观的解释就是让 $app 制造出一个 `App\Console\Kernel::class` 实例（虽然括号里是 `Illuminate\Contracts\Console\Kernel::class`，但由于跟这个接口绑定在一起的是 `App\Console\Kernel::class` 所以实际上 $kernel 实际上是 `App\Console\Kernel::class`