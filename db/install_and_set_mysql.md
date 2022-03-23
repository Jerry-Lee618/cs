## 启动和关闭mysql

- alias mysqlstart='sudo /usr/local/mysql/support-files/mysql.server start'

- alias mysqlstop='sudo /usr/local/mysql/support-files/mysql.server stop'

## 创建用户
CREATE USER 'jeffrey'@'localhost' IDENTIFIED BY 'password';  [文档](https://dev.mysql.com/doc/refman/8.0/en/create-user.html)
## 创建数据库
CREATE DATABASE `jerry` /*!40100 DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci */; [文档](https://dev.mysql.com/doc/refman/8.0/en/create-database.html)
## 授权用户
GRANT ALL ON db1.* TO 'jeffrey'@'localhost'; [文档](https://dev.mysql.com/doc/refman/8.0/en/grant.html)
## 刷新
FLUSH PRIVILEGES； [文档](https://dev.mysql.com/doc/refman/8.0/en/flush.html)
