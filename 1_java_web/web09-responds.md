# Response

## 1. Servlet 3.0

* 3.0之后,使用注解方式配置Servlet, 2.5版本之前使用配置web.xml方式配置.



Response中包含了响应行,响应头 相应体的信息

1. **响应行**  -->设置状态码

   > 响应行包括协议版本和状态码

   方法:

   ```java
   setStatus(int status)
       //参数 status 为状态码的值 302->重定向 304
   ```

   ```java
   sendError(int sc)
       // 参数 为状态码的值 404
   ```

2. **响应头**

   响应头是一组键值对,可以设置,可以修改已有的键值对

   ```java
   void setHeader(String name, String value)
       // String name,如果已经存在,则会覆盖
   ```

   ```java
   void setContentType(String type)
       // 设置响应编码
   ```

   **重定向**

   实现页面跳转

   * **两次请求 两次响应**
   * 代码的实现
     * 原始版
     * 简化版 `sendRedirect( 重定向的路径 )` 

   ```java
   protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
       // 1. 设置响应状态码
       response.setStatus(302);
       // 2. 设置响应头
       response.setHeader("Location","/web/demo3");
       
       // 简化版
       response.sendRedirect("/web/demo3")
   }
   ```

3. **响应体**

   方法

   ```java
   getWriter()
       // 只能向浏览器响应文本内容
   ```

   ```java
   getOutputstream()
       // 输出所有类型内容
   ```

   > getWriter() 下中文乱码问题
   >
   > Tomcat 内部编码为 ISO8859-1
   >
   > `response.setHeader("Content-Type","text/html;charset = UTF-8")` 
   >
   > 或者简化版
   >
   > `reponse.set	ContentType("text/html;charset = UTF-8")`






>  以附件形式下载,必须设置2个响应头
>
> 1. 下载文件类型 (MIME类型)
>
>    由下载文件的后缀名决定
>
> 2. 设置一个头部信息,这个信息用来指定附件下载时, 文件的名字

```java
response.setHeader("Content-Type","text/plain")
    // 手动设置MIME类型
getServletContent().getMimeType(filename);
// 根据文件名 ,获取文件MIme类型的方法

// 设置头部信息
response.setHeader("Content-Disposition","attachment;filename = xx.txt")
    
   // attachment;后面为下载时的文件名
```







解决响应头中文乱码问题

-->需要将中文转换为URL编码 %FD%JA.....

不同的浏览器编码方式不同-->封装工具类