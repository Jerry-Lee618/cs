##启动和关闭mysql

-alias mysqlstart='sudo /usr/local/mysql/support-files/mysql.server start'

-alias mysqlstop='sudo /usr/local/mysql/support-files/mysql.server stop'

##创建用户
CREATE USER 'jeffrey'@'localhost' IDENTIFIED BY 'password';
