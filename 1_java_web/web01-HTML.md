## 课程简介

### javaWeb阶段

* web前端
* web核心
* web案例
* web框架
* 综合项目

## HTML 基本语法

* 开发工具: 
  * Dreamview 
  * idea
  * HBuilder

1. ### html概述

   超文本标记语言  HyperText Markup Language

   * 标记语言: 由标签组成

   * 作用: 用来编写网页页面

   * 开发页面基础: HTML CSS样式 JavaScript  框架(如BootStrap)

   * **特点:** 

     1. 由标签组成
     2. 不需要编译,由浏览器解释运行
     3. HTML后缀  html  htm

   * HTML的基本标签

     ```html
     <html>根标签
     
     	<head>
     	    
     	</head>
     
     <body>
     </body>
     
     </html>
     
     ```

2. ### html标签--重点---文本标签

   #### 标题标签  < h1>

   ```html
   <h1>强东在美国</h1> 
   <h2>强东在美国</h2>
   <h3>强东在美国</h3>
   <h4>强东在美国</h4>
   <h5>强东在美国</h5>
   <h6>强东在美国</h6>
   ```

   <h1>强东在美国</h1> 
   <h2>强东在美国</h2>
   <h3>强东在美国</h3>
   <h4>强东在美国</h4>
   <h5>强东在美国</h5>
   <h6>强东在美国</h6>



   #### 水平标签 < hr/>

   ---自闭合标签 仅有结束

   * 标签属性

     1. size 表示水平线的高度  

     	单位为px--像素

     `<hr size=10/>` 或者`<hr size=10px/>`

     2. noshade 把空心变空心

        `<hr size=10/ noshade="noshade">`

        <hr size=10/ noshade="noshade">

     3. color: 表示颜色

        ``<hr size=10/ noshade="noshade">``

        单词表示法 : black

        十六进制表示法  #FF3CED

        		FF 红色的数值(00-FF)

        		3C 绿色的数值(00-FF)

        		ED 绿色的数值(00-FF)

        	`# 00 00 00` ----->黑色

        	`# FF FF FF`----->白色

        ```html
        <hr size=10 noshade="noshade" color="red"/>
        ```

     4. width 宽度 

        像素  200px

        百分比 50%

     5. align  对齐方式

        left  左对齐

        center  居中

        right  右对齐

   #### 字体标签 < font>

   ```html
   <font size="3" color="red">影魔</font> <b><i>幽鬼<i><b/>
       
   ```

   size属性: 设置字体属性 1-7 默认3

   color属性

   face 设置字体

   #### 格式化标签< b> < i>

   < b> < b/>  加粗或者< strong>< strong/>

   < i > <  i/>   斜体

   #### 分段标签< p>

   空格字符  `&nbsp;`

   #### 换行标签 < br> -->自闭合

   `<br>`与`<br/>` 都可以识别

3. ### 图片标签 < img>

   属性

   src : 指定图片显示的url(路径)

   ​	本地和互联网路径都可以

   alt  :  图片无法显示的替代文本

   title: 光标放在图片上显示的文本

   width  : 定义图像的宽度

   heigth  : 定义图片的高度



4. ### **列表标签**< ol> < ul>

   **< ul > 无序列表**

   type 

   	disc 实心圆点

   	square  方块

   ​	circle  空心圆点

   ```html
   <ul>
       <li>早年经历</li>
       <li>演艺经历</li>
       <li>个人生活</li>
   </ul>
   ```

   <ul>
       <li>早年经历</li>
       <li>演艺经历</li>
       <li>个人生活</li>
   </ul>

   ```html
   <ul type = "disc">
       <li>早年经历</li>
       <li>演艺经历</li>
       <li>个人生活</li>
   </ul>
   ```

   <ul type = "disc">
       <li>早年经历</li>
       <li>演艺经历</li>
       <li>个人生活</li>
   </ul>

   **< ol > 有序列表**

   ```html
   <ol>
       <li>早年经历</li>
       <li>演艺经历</li>
       <li>个人生活</li>
   </ol>
   ```

   <ol>
       <li>早年经历</li>
       <li>演艺经历</li>
       <li>个人生活</li>
   </ol>

   ```html
   <ol type = "a">
       <li>早年经历</li>
       <li>演艺经历</li>
       <li>个人生活</li>
   </ol>
   ```

   <ol type = "a">
       <li>早年经历</li>
       <li>演艺经历</li>
       <li>个人生活</li>
   </ol>

   ### 超链接标签 < a>< /a>

   属性:

   1. **href**   -->写网址 必须加http://说明协议

      ```html
      <a href="http://www.baidu.com">百度一下</a>
      ```

      <a href="http://www.baidu.com">百度一下</a>

   2. **target**  指定怎么打开页面

      当前页面打开 **_self**

      新页面打开  **_blank**

      ```html
      <a href="http://www.baidu.com" target = "_self">百度一下</a>
      ```


   ### 表格标签< table>< /table>

   **作用**: 页面整齐的布局可以使用两种方式

    	1. 表格
    	2. div



   < table> 表

   < tr> 行

   < rd> 列

   < th>表头

   ```html
   <table>
       <tr>
           <td>1-1</td>
           <td>1-2</td>
           <td>1-3</td>
       </tr>
       <tr>
           <td>2-1</td>
           <td>2-2</td>
           <td>2-3</td>
       </tr>
   <table>
   ```

   <table>
       <tr>
           <td>1-1</td>
           <td>1-2</td>
           <td>1-3</td>
       </tr>
       <tr>
           <td>2-1</td>
           <td>2-2</td>
           <td>2-3</td>
       </tr>
   <table>

   属性

   1. **表格边框  border** 

   ​	0代表没有边框 1代表由边框

   2. **文字对齐方式 align**

      	table后加 整个表格居中

      ​	tr上加 整个行中的文本居中

      ​	td 上加 当前列的文本居中

   3. **加背景色** **bgcolor****

   4. **列合并** **colspan**

   5. **行合并** **rowspan**

   6. **单元格边框与内容的间距cellpadding** 

   7. **单元格之间的留白 cellspacing**





   ```html
   <table border = "1" bgcorlor = "blue">
       <tr align = "center">
           <td colspan="2">1-1</td>
           <td>1-3</td>
       </tr>
       <tralign = "center">
           <td>2-1</td>
           <td rowspan="2">2-2</td>
           <td>2-3</td>
       </tr>
       <tr>
           <td>3-1</td>
           <td>3-2</td>
       </tr>
   <table>
   ```

   <table border = "1" bgcorlor = "blue">
       <tr align = "center">
           <td colspan="2">1-1</td>
           <td>1-3</td>
       </tr>
       <tralign = "center">
           <td>2-1</td>
           <td rowspan="2">2-2</td>
           <td>2-3</td>
       </tr>
       <tr>
           <td>3-1</td>
           <td>3-2</td>
       </tr>
   <table>






