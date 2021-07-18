---
layout: default


---

# mysql基础

## DDL(Data Definition Language):

对数据库里的数据进行操作的语言

- ### CREATE

  创建数据库

  `create database 数据库名；`

  **创建索引**

  `CREATE INDEX 索引名 ON 表名(字段1, 字段2...);`

- ### ALTER

  添加表字段

  `ALTER TABLE 表名 ADD 字段名 字段类型;`

  删除表字段

  `ALTER TABLE 表名 DROP 字段名;`

  修改字段类型

  `ALTER TABLE 表名 MODIFY 字段名 CHAR(10);`

  **创建索引**

  `ALTER TABLE 表名 ADD INDEX 索引名(字段1, 字段2...);`

  **删除索引**

  `ALTER TABLE 表名 DROP INDEX 索引名;`

- ### DROP

  删除数据表

  `drop table 表名;`

  **删除索引**

  `DROP INDEX 索引名 ON 表名;`

  

## DML(Data Manipulation Language):

用于定义或改变表结构，数据类型，表之间的连接和约束等初始化工作上，大多用在建立表的时候

- ### SELECT

  `SELECT 字段名 FROM 表名;`

- ### UPDATE

  `UPDATE 表名 SET 字段名 = 新值 WHERE 查找字段 = 所选值;`

- ### INSERT

  `INSERT INTO 表名 VALUES(值1, 值2...);`

- ### DELETE

  `DELETE FROM 表名 WHERE 字段名 = 所选值`

## DCL(Data Control Language):

数据库控制功能。用来设置或更改数据库用户或角色权限的语句

- ### grant

  数据库授权

  `grant all privileges on *,* to root@'%' identified by "root_pwd";`

- ### deny

- ### revoke

## TCL(Transaction Control Language):

事务控制语言

- ### set transaction

- ### rollback

- ### Save-pin

[back](../)

