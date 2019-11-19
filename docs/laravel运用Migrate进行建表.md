# laravel运用Migrate进行建表
https://blog.csdn.net/dutiantian_csdn/article/details/88095747

- php artisan make:migration create_table_anke
- 编写migrate建表
- 表生成器包含一系列的字段类型用于构建表：

# laravel migrate数据迁移命令
https://blog.csdn.net/qq_21885337/article/details/81063069
- php artisan make:migration create_articles_table --create=articles
- php artisan migrate

# laravel的migrate指令集合
https://www.jianshu.com/p/a1b8ba41ad27

1、生成迁移
php artisan make:migration create_users_table --create=user

2、运行迁移
php artisan migrate

3、回滚迁移
php artisan migrate:rollback

4、回滚所有迁移
php artisan migrate:reset

5、回滚所有迁移，然后再运行迁移
php artisan migrate:refresh

php artisan migrate:refresh --seed

6、清除数据重新迁移
可以手动删除所有数据库，再运行php artisan migrate:refresh

7、查看当前的migrate的状态
php artisan migrate:status
 