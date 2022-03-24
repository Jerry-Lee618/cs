1、group by 查找分组中的最后一条记录的某个值
   substring(max(concat(create_time,auth_status)) from 14)

2、从本地文件加载数据
   server端/etc/my.cnf增加 [详情](https://computingforgeeks.com/how-to-solve-mysql-server-is-running-with-the-secure-file-priv-error/)
   ```
   [mysqld]
   secure-file-priv = ""
   ```
   client端
   ```
   mysql --local-infile=1 -u root -p1
   ```
   [sql](https://dev.mysql.com/doc/refman/5.7/en/load-data.html)
   ```sql
   LOAD DATA LOCAL INFILE 'abc.csv' INTO TABLE abc
FIELDS TERMINATED BY ',' 
ENCLOSED BY '"' 
LINES TERMINATED BY '\r\n'
IGNORE 1 LINES
(col1, col2, col3, col4, col5...);
```

3、用一个表更新另一个表的数据，[详情](https://stackoverflow.com/questions/11709043/mysql-update-column-with-value-from-another-table)
   ```
   UPDATE tableB
INNER JOIN tableA ON tableB.name = tableA.name
SET tableB.value = IF(tableA.value > 0, tableA.value, tableB.value)
WHERE tableA.name = 'Joe'
```
