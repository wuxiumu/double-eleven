# Laravel Redis的使用
https://blog.csdn.net/qq_43638176/article/details/88536764

 使用：字符串操作
1. composer require predis/predis
2. redis的配置文件是：config/database.php
3. .env文件 
4. use Illuminate\Support\Facades\Redis;
5. 基础
    1. Redis::set('key','value'); 
    2. Redis::get('key');
    3. Redis::del('key');
6. mset存储多个 key 对应的 value
    1. redis::mset($array); // 存储多个 key 对应的 value
    2. Mget返回所有(一个或多个)给定 key 的值,给定的 key 里面,key 不存在,这个 key 返回特殊值 nil
    3. var_dump(redis::mget (array_keys( $array))); //获取多个key对应的value
7. Strlen 命令用于获取指定 key 所储存的字符串值的长度。当 key存储不是字符串，返回错误。redis::strlen('key');
8. substr 获取第一到第三位字符 Redis::substr('key',0,2);
9. 根据键名模糊搜索 Redis::keys('use*');
10. 获取缓存时间 Redis::ttl('str2')
11. exists检测是否存在某值 Redis::exists ( 'foo' ) 

管理操作：

排序操作:

队列操作

set 集合操作  sadd增加set集合元素， 返回true， 重复返回false