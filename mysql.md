数据库-树形结构
- database，db：比如mysql
-- table：表，表格
--- row 行
--- field：字段，列，column
---- 数据类型，长度

sql语句：结构化查询语言，structured query language
增、删、改、查
insert tb_test(name, age) values('moze', 19);
delete from tb_test where name='sf';
update tb_test set name='sf1' where name='sf';
select * from tb_test where name='moze' order by name desc limit 1

-----
mysql的安装与服务启动
-- 3306，用户名，密码
mysqld --initialize --console 
root@localhost: 
root@localhost: 
mysqld
mysqld --defaults-file="D:\software\mysql-8.0.33-winx64\my.ini"
mysql -u root -p
alter user 'root'@'localhost' identified by 'password' PASSWORD EXPIRE NEVER;
alter user 'root'@'localhost' identified with mysql_native_password by 'pwd123';

--- 必须编辑一个my.ini
select version();
show variables like '%sql_mode%';
set sql_mode='STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION';

mysql控制台的使用：Navicat

如何创建数据库？
mysql-8.0.33-winx64
https://dev.mysql.com/downloads/mysql/

如何创建表？修改表？
CREATE TABLE `tb_test` (
  `id` bigint(20) NOT NULL AUTO_INCREMENT COMMENT '自增1的唯一键id',
  `name` varchar(128) NOT NULL DEFAULT '' COMMENT '姓名',
  `age` int(10) NOT NULL DEFAULT 1 COMMENT '年龄',
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COMMENT='测试表';

使用java JDBC连接到数据库。
-- 连接字符串
-- 什么是数据库驱动，driver？
-- mybatis库

实现一个简单的增删改查的功能。
