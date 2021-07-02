---
layout: default

---

# HTTP请求简介

#### HTTP请求的格式：

HTTP GET请求的格式：`

```
GET /path HTTP/1.1
Header1: Value1
Header2: Value2
Header3: Value3
```

HTTP POST请求的格式：

```
POST /path HTTP/1.1
Header1: Value1
Header2: Value2
Header3: Value3

body data goes here...
```

HTTP响应的格式：`

```
200 OK
Header1: Value1
Header2: Value2
Header3: Value3

body data goes here...
```

响应代码：

- 200 -> 成功
- 3xx -> 重定向
- 4xx -> 客户端发送的请求有错误
- 5xx -> 服务端处理时发生了错误



#### HTTP请求的流程：

1. 浏览器向服务器发送HTTP请求
2. 服务器向浏览器返回HTTP相应
3. 如果浏览器还需要向服务器请求其他资源（例如图片），则重复步骤1，2

[back](./)

