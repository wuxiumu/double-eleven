# MYSQL数据库时间字段INT,TIMESTAMP,DATETIME性能效率比较
https://blog.csdn.net/adsadadaddadasda/article/details/78933784

- 索引
    - 数据库的索引就像一本书的目录，能够加快数据库的查询速度。
    - MYSQL索引有四种PRIMARY、INDEX、UNIQUE、FULLTEXT， 其中PRIMARY、INDEX、UNIQUE是一类，FULLTEXT是一类。

这四种都是单列索引，也就是他们都是作用于单个一列，所以也称单列索引；

但是所以一个索引也可以作用于多个列上，称为组合索引或复合索引。

- 索引不足之处
    - （1）索引提高了查询的速度，但是降低了INSERT、UPDATE、DELETE的速度，因为在插入、修改、删除数据时，还要同时操作一下索引文件；
    - （2）建立索引未见会占用一定的磁盘空间。

- 索引方式 HASH和 BTREE比较
    - （1）HASH  用于对等比较，如"="和" <=>"
    - （2）BTREE BTREE索引看名字就知道索引以树形结构存储，通常用在像 "=，>，>=，<，<=、BETWEEN、Like"等操作符查询效率较高；

通过比较发现，我们常用的是BTREE索引方式，当然Mysql默认就是BTREE方式。