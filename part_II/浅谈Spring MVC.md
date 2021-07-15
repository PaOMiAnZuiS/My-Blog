---
layout: default


---

# 浅谈Spring MVC



MVC是一种设计模式。

M代表的是Model，模型层，在Spring中有Service，dao和entity

V代表的是View，视图渲染

C代表的是Controller，作用是接受请求->调用业务类->派发页面，直接和用户连接

### Spring MVC工作流程:

1.  客户端(浏览器)发送请求，直接请求到 DispatcherServlet 。
2. DispatcherServlet 根据请求信息调用 HandlerMapping ，解析请求对应的 Handler 。
3.  解析到对应的 Handler (也就是我们平常说的 Controller 控制器)后，开始由HandlerAdapter 适配器处理。
4. HandlerAdapter 会根据 Handler 来调用真正的处理器开处理请求，并处理相应的业务逻辑。 
5. 处理器处理完业务后，会返回一个 ModelAndView 对象， Model 是返回的数据对象， View 是 个逻辑上的 View 。
6. ViewResolver 会根据逻辑 View 查找实际的 View 。
7. DispaterServlet 把返回的 Model 传给 View (视图渲染)。 
8. 把 View 返回给请求者(浏览器)

[back](../)

