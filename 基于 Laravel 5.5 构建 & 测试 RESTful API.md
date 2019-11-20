# Laravel API 系列教程（一）: 基于 Laravel 5.5 构建 & 测试 RESTful API
https://xueyuanjun.com/post/9153.html#bkmrk-restful-api

## RESTful API
开始之前，我们先要了解什么是 RESTful API。

REST 是 REpresentational State Transfer 的缩写，表示一种应用之间网络通信的架构风格，依赖于无状态的协议（通常是HTTP）进行交互。

## 通过 HTTP 动词表示操作

在 RESTful API 中，我们使用 HTTP 动词表示操作，而端点是操作的资源，HTTP 动词的语义如下：
- GET：获取资源
- POST：创建资源
- PUT：更新资源
- DELETE：删除资源

## 设置一个新的 Laravel 项目
- 创建新应用
- 迁移和模型
- 数据库填充
    - php artisan make:seeder ArticlesTableSeeder
    - php artisan db:seed --class=ArticlesTableSeeder
    - php artisan db:seed
- 路由和控制器
    - 注册路由
    - 创建控制器
- 关于 HTTP 状态码的注意项
    - 200：OK，标准的响应成功状态码
    - 201：Object created，用于 store 操作
    - 204：No content，操作执行成功，但是没有返回任何内容
    - 206：Partial content，返回部分资源时使用
    - 400：Bad request，请求验证失败
    - 401：Unauthorized，用户需要认证
    - 403：Forbidden，用户认证通过但是没有权限执行该操作
    - 404：Not found，请求资源不存在
    - 500：Internal server error，通常我们并不会显示返回这个状态码，除非程序异常中断
    - 503：Service unavailable，一般也不会显示返回，通常用于排查问题用    
- 认证
    - 新增 api_token 字段
        - php artisan make:migration --table=users adds_api_token_to_users_table
        - php artisan migrate
    - 创建注册接口
    - 创建登录接口
    - 创建退出接口
- 使用中间件限制访问
- 测试接口            

>阅读延申
- [关于高并发和分布式中的幂等处理，你真的知道吗？](https://www.jianshu.com/p/cea3675a590b)
    - 一个操作，不管做多少次，产生效果或返回的结果都是一样的
- [数据库填充器：初始化测试数据的好帮手](https://xueyuanjun.com/post/8187.html)
- []()