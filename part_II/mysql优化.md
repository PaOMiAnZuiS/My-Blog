---
layout: default


---

# mysql优化

以下是几种常见的优化方法：

1. 索引优化，添加符合索引
2. 索引不会包含有NULL值的列
3. 分表，把大表拆成小表
4. 尽量避免`select *`， 杜绝`select * from table_name
5. 避免在大表上的`group by`, `order by`, `offset`操作
6. WHERE查询条件，尽量按照添加的索引顺序来写
7. 选取最合适的字段属性

[back](../)

