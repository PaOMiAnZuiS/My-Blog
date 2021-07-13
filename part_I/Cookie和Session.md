---
layout: default


---

# Cookie和Session

由于HTTP协议本身是无状态（stateless）协议，即 HTTP 协议自身不对请求和响应之间的通信状态进行保存。**Cookie**和**Session**的目的就是记录用户的状态。

## Cookie

**Cookie**数据储存在客户端（浏览器端）。**Cookie**的安全性较低。

**Cookie**的应用场景：

- 浏览器记录用户的账号密码
- 浏览器记录用户的基本信息（姓名电话住址等），下次填同样的问题时自动填充

## Session

**Session**数据储存在服务器端。**Session**的安全性更高。

**Seesion**典型的使用场景是购物车，同一账号换设备登录，购物车内的物品还是一样的，因为是记录在服务器端的数据。



### 如果Cookie被禁用怎么办？

最常用的办法是利用URL重写，把Session ID直接附加到URL路径后面。

[back](../)
