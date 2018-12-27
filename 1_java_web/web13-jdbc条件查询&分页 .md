项目中的页面

1. 前台页面 -->展示给用户
2. 后台页面 -->展示给管理员,对数据库数据进行更改



案例1 条件查询



获取项目访问路径

在servlet中: `request.getContextPath()` 

在JSP中: `${pageContext.request.contextPath}` 



案例2 分页查询

* 分页

  1. 设计一个javabean类,包含某一页显示需要的所有数据-->Pagebean

     >  当前页商品列表 : List< Product>  list
     >
     >  商品的总数  : int total
     >
     > 每一页显示的商品数 int pageTotal 
     >
     > 当前的页数 int currentPage
     >
     > 总页数 int totalPage


* 补充知识   

  类加载器-->classLoadder

  负责将类加载到内存

  1. 应用类加载器
  2. 扩展类加载器  -->C语言编写
  3. 根类加载器  -->C语言编写

  ```java
  public static Test{
      public static void main(String[] args){
          ClassLoader classLoader = Test.class.getClassLoader();
          // classLoader获取的是应用类加载器
      }
  }
  ```
