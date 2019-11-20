# 看看 laravel-admin 的特性：
https://blog.csdn.net/yemeishu6033022/article/details/81229906

[推荐一个 Laravel admin 后台管理插件](https://blog.csdn.net/yemeishu6033022/article/details/81229906)

- 内置用户和权限系统
- model-grid 支持快速构建数据表格
- model-form 支持快速构建数据表单
- model-tree 支持快速构建树状数据
- 内置 40+ 种 form 元素组件、以及支持扩展组件
- 支持 Laravel 的多种模型关系
- mysql、mongodb、pgsql 等多数据库支持
- 支持引入第三方前端库
- 数据库和 artisan 命令行工具的 web 实现
- 支持自定义图表
- 多种常用 web 组件
- 支持本地和 oss 文件上传 

确认安装好laravel框架和连接好数据库

安装插件：
```
composer require encore/laravel-admin "1.5.*"
 
// 发布资源：
php artisan vendor:publish --provider="Encore\Admin\AdminServiceProvider"
 
// 安装
php artisan admin:install
```