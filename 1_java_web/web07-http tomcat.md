## web 开发概述

1. **软件架构**

   1. c/s架构

      * 优点:  安全性好,服务器运行压力小

      * 缺点:  维护麻烦

   2. b/s架构

      * 优点:  升级维护简单,不用安装程序
      * 缺点:  信息安装控制较差,应用服务器压力大

2. **web通信**

   请求 request

   * 1.  接受请求,获取参数
   * 2. 对数据进行处理和解析
   * 3. 将处理后的结果响应给浏览器

   响应 response



3. **web资源介绍**

   * 静态资源

     web页面中始终不变的数据 HTML、CSS、JS、图片、多媒体

   * 动态资源

     指web页面中供人们浏览的数据是由程序产生的，不同时间点访问web页面看到的内容各不相同。比如：JSP/Servlet、ASP、PHP

4. **web服务器**

   * 装有web服务器软件的电脑

     常用的服务器软件

     * Tomcat  -->支持Servlet和jsp规范
     * WebLogic 
     * WebSphere
     * JBoss

5. **URL请求路径**

   ​	统一资源定位符  URL （Uniform Resource Locator） 

   `	协议://域名:端口号/资源位置?参数=值`



## Tomcat



#### 目录结构

1. bin 目录 startup.bat 启动服务器 shutdwn.bat 关闭服务器
2. conf 目录 
   * server.xml  服务器总配置文件
   * web.xml  web项目总配置文件

3. webapps  目录
   * 项目的发布目录

4. work 目录
   * jsp文件编译后的代码存放目录

#### idea 使用toncat

web项目的目录结构

src  存放java程序

web 存放所有的页面 ,jar包

​	WEB-INF   -->存放外界不需要访问的文件,

​		web.xml 当前项目的配置文件

​		lib   存放jar包

​	index.jsp  项目默认首页



## http 协议

* 超文本传输协议
* 用于浏览器和服务器之间的数据传输

* 基于请求和响应的协议,有请求必须有响应
* 端口默认为80
* 协议版本
  * 1.0 -->一个请求,一个响应
  * 1.1 -->一个请求  多个响应
  * 2.0 -->https

**请求包**

* 请求行  请求方式 请求路径
* 请求头  键值对组成
* 请求体  -->get请求没有请求体 post有
  * 向服务器发送请求时 ,如果没有指定post,全部默认为get

**响应包**

- 响应行  协议版本  响应状态码

- 响应头  键值对

- 响应体   页面

  > 响应状态码  
  >
  > * 200  正常
  > * 302  重定向  
  > * 304  访问缓存
  > * 404  服务器资源不存在
  > * 500  服务器程序错误
