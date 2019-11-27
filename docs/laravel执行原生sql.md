## laravle 执行原生sql
https://blog.csdn.net/weixin_41750790/article/details/85335206

1. 插入数据
```
DB::insert('insert into test (id,name,email,password) value (?,?,?,?)',[1,'laravle','laravel@test.com','Laravel']);
```
2. 查询数据
```
$user = DB::select('select * from test where id = ?',[1]);
$user = DB::select('select * from test where id = :id',[':id'=>1]);
```
3. 跟新数据
```
$re = DB::update('update test set name="laraveltest" where name = ?',['laravle']);
```

4. 删除语句
```
$deleted = DB::delete('delete from test');
```
Laravel限制条数再分页
- 1.需求
- 2.实现
- 3.解惑