# 队列系统解决方案：Laravel Horizon
https://xueyuanjun.com/post/8492.html

- [Laravel 队列使用](https://www.jianshu.com/p/3371666b7880)
- [Laravel 队列系列 —— 基于 Redis 实现任务队列的基本配置和使用](https://blog.csdn.net/var_dz/article/details/73530720)
- [laravel 队列服务使用总结](https://www.cnblogs.com/frankltf/p/10205269.html)

## 简介

Horizon 为 Laravel 提供了基于 Redis 的、拥有美观后台的、代码驱动配置的队列系统。Horizon 让我们可以轻松监控队列系统的关键指标，例如任务吞吐量、运行时间和失败任务等。 所有的队列进程配置都存放在一个单独的简单配置文件中，这样的话配置文件就可以存放到源码控制以便团队所有成员的协作。

## 安装

注：由于 Horizon 使用了异步进程信号，所以 PHP 7.1+ 以上版本才可以使用。

我们使用 Composer 安装 Horizon 到 Laravel 项目：
```
composer require laravel/horizon
```
安装完成后，使用 Artisan 命令 vendor:publish 发布前端资源：
```
php artisan vendor:publish --provider="Laravel\Horizon\HorizonServiceProvider"
```

## 配置
发布好前端资源后，主配置文件就会出现在 config/horizon.php。在这个配置文件中，你可以配置队列进程选项以及每个包含目的描述的配置项，所以使用 Horizon 前务必浏览下这个配置文件。 balance 配置项 Horizon 提供了三种负载均衡策略以供选择：simple、auto 和 false，simple 是默认策略，在进程之间平均分配进入任务：

```
'balance' => 'simple',
```
auto 策略基于队列当前负载调整每个队列的工作进程数量。例如，如果 notifications 队列有 1000 个等待执行的任务而 render 队列是空的，那么 Horizon 将会为 notifications 队列分配更多的工作进程直到队列为空。 如果把 balance 选项设置为 false，就会使用默认的 Laravel 行为，也就是按照配置文件中的排列顺序处理队列。

## 后台认证
我们可以通过 /horizon 访问 Horizon 后台：