---
layout: default


---

# 浅谈JVM

JVM大致可以分为以下几个逻辑区域

## 线程私有：

### 本地方法栈（Native Method Stack）：

调用操作系统原生本地方法时，所需要的内存区域。

### 虚拟机栈（VM Stack）：

记录每个栈帧（Frame）中的局部变量，方法返回地址等。

#### 栈帧：每个栈帧包含以下信息：

- 本地变量数组（Local Variable Array）
- 操作数栈（Operand Stack）
- 常量池的地址（Reference to Constant Pool）

### 程序计数器（Program Counter Register）：

记录每个线程当前执行的指令信。

## 线程共享：

### 堆（Heap）：

用于存放类的实例对象及Arrays实例等，也是GC的主要区域。

### 方法区（Method Area）：

主要存放类结构，类成员定义，static静态成员等

其中方法区又包含了**运行时常量池（Runtime Constant Pool）**，比如int的范围，字符串的范围等常量。

[back](../)
