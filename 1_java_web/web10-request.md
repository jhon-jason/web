##Request

### 1. 获取请求行

* 请求方式+请求路径

  方法

  ```java
  // 获取请求方式 GET POST
  String getMethod()
  ```

  ```java
  // 获取项目路径-->/项目的访问路径
  String getContextPath()
      
      // 获取的结果不一定为项目名称
      // 由 Run-Edit config-deployment-application context决定
  ```

  > tomcat升级前 处理get和post请求的中文乱码方式不一致,需要判断请求方式



### 2. 获取请求头

* 方法

  ```java
  // 根据请求头键,获取值
  String getHeader(String name)
  ```

  ```java
  
  ```


### 3.获取请求体

* 只有post请求才有请求体

* 请求体中包含请求参数

  ```java
  // 根据参数名,获取一个参数的值
  String getParameter(String name)
  ```

  ```java
  // 根据参数名,获取参数的多个值
  String[] getParameterValues(String name)
      // 复选框不选,返回值为null
  ```

  ```java
  // 获取表单中所有的参数名和参数值
  Map<String,String[]> getParameterMap()
  ```

  ```java
  
  ```

  > 获取请求参数乱码问题
  >
  > 新版本tomcat 
  >
  > * **get**    请求 中文不乱码
  >
  > * **post** 请求中文乱码
  >
  >   解决乱码:
  >
  >   ```java
  >   request.setCharacterEncoding("UTF-8")
  >   ```
  >

### 4. BeanUtils

* 第三方工具类,需要导包使用

* 方法

  ```java
  // 将map集合中的数据,封装为bean对象
  void populate(Object bean, Map<String,String[]> properties)
  ```

* 在转发传递数据时,多数将数据封装成javabean对象传递.此时需要使用此工具类.



### 5. 转发 Dispatcher

* **转发定义**: 当浏览器向Servlet1 发出请求无法处理时,将这个请求转发给servlet2 可以处理,将响应反馈给浏览器.
* **一次请求(请求链) 一次响应**
* 转发使用: servlet给jsp页面传递数据

* **重定向和转发 对比**

  * 转发需要携带数据,否则可以直接使用重定向

  | 重定向            | 转发                          |
  | ----------------- | ----------------------------- |
  | 两次请求 两次响应 | **一次请求(请求链) 一次响应** |
  | 不需要携带数据    | 需要携带数据                  |
  | 地址栏发生跳转    | 地址栏不变换(一个请求)        |


```java
// 转发案列
// servlet 1 code:
protected void doGet(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
 	// 向请求中存数据
    request.setAttribute("proNAME","xiaomi");
    // 转发到另一个servlet
    request.getRequestDispatcher("/demo7").forward(request,response)
}

// servlet 2 code:
protected void doGet(HttpServletRequest request, HttpServletResponse response)
    throws ServletException, IOException {
    // 接受转发的数据
    String str = (String)request.getAttribute("productName");
    System.out.println("demo7接收到转发过来的数据:"+str);
    
}
```



> request对象可以存键值对
>
> 方法:`setAttribute(key,value)` 
>
> 可以将数据按照键值对的方式存入对象,如果需要取出元素,使用 `getAttribute(key)` 方法取出
>
> -->使用:转发时传递查询数据
>
>

> 域对象
>
> HttpServletContext()对象 -->作用范围  整个项目
>
> HttpServletRequest()对象  -->作用范围 一次请求
>
> 共有方法
>
> `setAttribute(key,value)` 
>
> `getAttribute(key)`
>
> `removeAttribute()` 