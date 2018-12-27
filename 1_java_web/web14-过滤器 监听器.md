## 1. 过滤器 Filter

* Java Web三大组件  Servlet  Filter Listener

### 1.1 概述

* Filter 是过滤器 ,可以对向服务器发出的请求进行过滤

  ```java
  @WebFilter("/S1") // 请求路径写S1,说明如果访问S1,就过滤.
  public class demoFilter implements Filter {
      public void destroy() {
      }
  
      public void doFilter(ServletRequest req, ServletResponse resp, FilterChain chain) throws ServletException, IOException {
          chain.doFilter(req, resp);
      }
      /*
      1. 这个方法,在访问需要过滤的资源是自动执行
      2. FilterChain 为过滤器链
      3. chain.doFilter(req, resp); 放行方法
      */
      public void init(FilterConfig config) throws ServletException {
      }
  }
  ```


### 1.2 Filter的执行流程

请求和响应都经过过滤器,解决乱码只需要在过滤器中解决.

执行多个过滤器顺序

1. 注解方式:按照类名名称字母排序,
2. 存在web.xml,按照配置文件中的先后顺序执行



### 1.3 Filert 的配置

* URLPattern的配置

  #### 1.3.1 完全路径匹配

  ​	`@WebFilter("/S1")` 

  #### 1.3.2 目录匹配

  ​	`@WebFilter("/S1/*")` 

  #### 1.3.3 扩展名匹配

​		`@WebFilter("*.do")` 

​		`@WebFilter("*.html")` 

### 1.4 过滤器的过滤方式

* 资源的访问方式
  1. 直接访问
  2. 转发访问

* 过滤器 默认情况下,可以拦截直接访问的请求,不能拦截转发访问的请求

```java
@WebFilter(value = "/index",dispatcherTypes = {DispatcherType.FORWARD})
// 设置此条件只过滤转发访问的
```

```java
  @WebFilter(value = "/index",dispatcherTypes = {DispatcherType.FORWARD,DispatcherType.REQUEST})
  // 设置此条件过滤转发访问的和直接访问的
```

### 1.5 过滤器链

FilterChain

* 内部可以理解为一个集合,集合内部维持了一个过滤器链
* ,这个过滤器链中的过滤器,必须按照顺序一次执行
* 过滤器链中的只要有一个过滤器不通过,就不能获取到资源

### 1.6 实例 解决全局乱码

```java
@WebFilter(value = "/*",dispatcherTypes = {DispatcherType.FORWARD,DispatcherType.REQUEST})
public class demoFilter implements Filter {
    public void destroy() {
    }

    public void doFilter(ServletRequest req, ServletResponse resp, FilterChain chain) throws ServletException, IOException {
        req.setCharacterEncoding("UTF-8");        resp.setContentType("text/html:charset=UTF-8"); // 此语句需要在下面语句前
        chain.doFilter(req, resp);
    }
    public void init(FilterConfig config) throws ServletException {
    }
}
```



## 2. 监听器 Listener

* 概念

  * 监听某个对象状态变化的组件

* 监听器是用来监听域对象

* 监听域对象的创建和销毁,

* 监听域对象属性的变化

* 监听器作用的域对象

  1. HttpServletContext
  2. HttpSession
  3. HttpRequest

|                | 域对象的创建和销毁     | 域对象属性变化                  |
| -------------- | ---------------------- | ------------------------------- |
| ServletContext | ServletContextListener | ServletContextAttributeListener |
| HttpSession    | HttpSessionListener    | HttpSessionAttributeListener    |
| ServletRequest | ServletRequestListener | ServletRequestAttributeListener |



###2.1 ServletContextListener

实例:

```java

@WebListener()
public class Demo1Listener implements ServletContextListener{

    public Demo1Listener() {
    }

    //这个方法用来监听ServletContext域的创建
    /*
        这个域：服务器启动时创建
     */
    public void contextInitialized(ServletContextEvent sce) {
        //设置一个定时器
        Timer timer = new Timer();
        timer.schedule(new TimerTask() {
            @Override
            public void run() {
                try {
                    MailUtil.sendMail("baoqiang@itheima.com", "你好，晚上见!");
                } catch (Exception e) {
                    e.printStackTrace();
                }
            }
        }, 5000, 2000);
        System.out.println("ServletContext域的创建啦");
    }

    //这个方法用来监听ServletContext域的销毁
    /*
       这个域：服务器关闭时销毁
     */
    public void contextDestroyed(ServletContextEvent sce) {
        System.out.println("ServletContext域销毁啦");
    }

}

```





