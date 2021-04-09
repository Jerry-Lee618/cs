1.Innodb页大小
>```sql
>show VARIABLES like 'innodb_page_size'
>```
![](https://github.com/Jerry-Lee618/cs/blob/main/resources/pics/innodb-page.png)
2.[B+树聚簇索引][2]
>_非叶子节点存放键值+指针（指针6字节，页地址）
>_叶子节点存放行数据，叶节点大小和内节点一般不一样大
>_增加相邻叶节点顺序访问指针




参考
[1]: [InnoDB 中一棵 B+ 树能存多少行数据？](https://mp.weixin.qq.com/s/IHdsLjoF8RLyDOYvfor81A)

[2]: [MySQL索引背后的数据结构及算法原理](http://blog.codinglabs.org/articles/theory-of-mysql-index.html)
