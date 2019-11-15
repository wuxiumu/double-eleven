## 已读

Laravel-Admin 最全安装方法与汉化教程图解
https://xueyuanjun.com/post/19809.html

- [在 Laravel 5 中集成七牛云存储实现云存储功能](https://xueyuanjun.com/post/3850)
    - composer require zgldh/qiniu-laravel-storage
    - 注册服务提供者：zgldh\QiniuStorage\QiniuFilesystemServiceProvider::class
    - 接下来在config/filesystems.php里的disks中新增如下选项：
    - 本扩展包GitHub地址为https://github.com/zgldh/qiniu-laravel-storage，
    - 基于https://github.com/qiniu/php-sdk开发，
    - 更多详情请参考七牛官方PHP SDK使用指南：http://developer.qiniu.com/code/v7/sdk/php.html
- [在 Laravel 5 中使用 Laravel Excel 实现 Excel/CSV 文件导入导出功能](https://xueyuanjun.com/post/2024)
    - composer require maatwebsite/excel
    - 注册服务提供者到providers数组：'Excel' => Maatwebsite\Excel\Facades\Excel::class,
    - 注册门面到aliases数组：'Excel' => Maatwebsite\Excel\Facades\Excel::class,
    - Laravel Excel进行更多的自定义配置，执行如下Artisan命令：php artisan vendor:publish
    - 导出Excel文件
        - 控制器 
        - 路由
        - 定义export方法实现导出功能 
    - 导入Excel文件
        - 使用Excel门面上的load方法
- [Laravel 5 表单中如何集成使用 Google reCAPTCHA 验证码](https://xueyuanjun.com/post/3645)
    - composer require anhskohbo/no-captcha
    - 注册服务提供者到providers数组:Anhskohbo\NoCaptcha\NoCaptchaServiceProvider::class
    - 将扩展包的配置文件发布到 config 目录下：php artisan vendor:publish --provider="Anhskohbo\NoCaptcha\NoCaptchaServiceProvider" 
    - 为站点获取 Google recaptcha site key 和 secret key
    - 在表单中集成验证码
        
## 待读


Laravel 5 中使用 JWT（Json Web Token） 实现基于API的用户认证
https://xueyuanjun.com/post/3640

## 计划阅读

安全 （4）

后台 （4）

内容 （9）

货币&支付 （6）

邮件&通知   （6）
 
性能优化    （7）

