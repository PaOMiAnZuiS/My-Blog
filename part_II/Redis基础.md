---
layout: default


---

# Redis基础

## Redis的五种基本数据结构：

- **String**：字符串类型

  一个 key 对应一个 value。是二进制安全的，可以包含任何类型的数据，比如jpg图片或者序列化的对象。最大能储存512MB。

- **Hash**：散列表

  Redis hash 是一个 string 类型的 field 和 value 的映射表，hash 特别适合用于存储对象。

- **List**：列表

  Redis 列表是简单的字符串列表，按照插入顺序排序。你可以添加一个元素到列表的头部（左边）或者尾部（右边）。

- **Set**：集合

  Redis 的 Set 是 string 类型的无序集合。集合是通过哈希表实现的，所以添加，删除，查找的复杂度都是 O(1)。

- **Sorted Set（Zset）**：有序集合

  Redis zset 和 set 一样也是string类型元素的集合,且不允许重复的成员。

  不同的是每个元素都会关联一个double类型的分数。redis正是通过分数来为集合中的成员进行从小到大的排序。

  zset的成员是唯一的,但分数(score)却可以重复。

[back](./)

