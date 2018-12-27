## 1. Servlet 

### 1. 1 servlet概述

Servlet 运行在服务器端的java小程序,主要用于处理浏览器的请求和响应.

**JavaEE 三大组件 Servlet Filter Listener**  

### 1.2 servlet的作用 

1. 接收浏览器的请求和参数
2. 对数据进行处理
   * 将数据存入服务器
   * 将数据和数据库进行交互
3. 对浏览器响应
   * 给浏览器一个字符串
   * 页面
   * json串
4. servlet 的 2.5 版本 使用xml配置 3.1 使用java 的注解 配置





### 1.3 获取表单数据

--> request对象,存储了浏览器发出的请求中的一切信息

--> response对象 存储了浏览器响应中的一切信息

```java
request.getParameter("String name")
    // 参数是表单name属性的值
```



### 1.4 Servlet 生命周期

`init()` 方法在首次访问Servlet时执行

---> 将只需要执行一次的代码 ,刚在init()下



`service()`方法每次访问servlet时都会执行

​	父类也有service方法,每次执行时,父类的service会自动调用doget和dopost方法



`destory()`  服务器关闭时执行,放服务器关闭资源的方法 



### 1.5 urlPattern 配置方式 

1. 完全路径匹配
   * 访问的路径与设置的路径必须完全一致

2. 目录通配符匹配
   * `/url/*`  在地址栏中 * 输入任意字符均可

3. 扩展名匹配
   * `*.do`  * 号前面**一定不要加/**
   * `*.action` `*.jsp` 
4. 系统默认路径(系统使用)
   * `/`

### 

### 2. ServletContext

#### 2.1 概述

* 域对象
* 在首次访问Servlet是 系统自动创建的
* 类似于Map集合
* 一个项目只有一个ServletContext对象

#### 2.2 作用

* 可以实现多个servlet对象之间数据的共享
* 获取web文件夹下的文件内容
* 获取web.xml中的全局配置数据



> 文件放在src下 用反射获取输入流读
>
> 如果文件web下 使用ServletContext的getRea