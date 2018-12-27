## 主要内容

1. **表单**
2. **CSS样式**
3. **盒子模型**
4. **注册案例**

## 1. 表单 form标签

### 1.1 表单总标签< form>

**属性** 

* **action**   后面加服务器路径

* **method**  数据向服务器提交的方式

  * get 方式 ---不指定提交方式,默认get
    1. 把表单输入的数据,拼成字符串, 键=值&键=值 放在地址栏中
    2. 长度有限,数据不安全
  * post 方式
    1. 将表单数据拼接成字符串,放在请求包中发送回服务器
    2. 特点:数据安全,长度不限

  ```html
  <form action="192.168.1.211:3306 " method="get" >
     
  </form>
  ```


### 1.2 < input>标签

**属性**

* **type**  说明输入框的类型

  * text   文本

  * password  密码

  * radio  单选框

  * checkbox 复选框

  * file  文件上传 

  * button   按键

  * submit  提交按钮

  * image  图片按钮(作用同提交)

  * reset  重置

  * hidden  隐藏域

     ```html
      <form action="192.168.1.211:3306 " method="get" >
         用户名: <input type="test" />
      </form>
     ```

      <form action="192.168.1.211:3306 " method="get" >
         用户名: <input type="test" />
      </form>

* **name**   输入框 提交服务器时 的键值

* **value**   value值是表单的默认值,可以不加

* **placeholder** 提醒信息

* **checked**  表单的默认选中

* **readonly**  只读,表单的数据只能读不能修改

* **disable**   可以是表达那不可用-->按钮不可点,输入框不能点击输入.

  <form action="192.168.1.211:3306 " method="get" >
      <input type="button" value="我是按钮" disable="disable"/>
  </form>

  **普通按钮:**

  本身没有意义,需要结合JS绑定事件才有意义

  ```html
  <input type="button" value="我是按钮" />
  ```

  <form action="192.168.1.211:3306 " method="get" >
      <input type="button" value="我是按钮" />
  </form>

  **提交按钮**

  会将当前表单的内容拼接成字符串,提交给服务器

  ```html
  <input type="submit" value="提交" />
  ```

  <form action="192.168.1.211:3306 " method="get" >
      <input type="submit" value="提交" />
  </form>

  **图片按钮**

  和提交按钮一样,也会提交数据

  ```html
  <input type="image" src="img/注册.jpg"/>
  ```

  **重置按钮** 

  将输入框中的数据恢复默认值 ( 清空用户输入)

  ```html
  <input type="reset" value="重置"/>
  ```

  <form action="192.168.1.211:3306 " method="get" >
      <input type="reset" value="重置" />
  </form>

  **复选框**

  name必须为同一个 value值不同

  向服务器提交的字符串为

  hobby=money&hobby=gri&hobby=code

  ```html
   <form action="192.168.1.211:3306 " method="get" >
      爱好:<input type="checkbox" name="hobby" value="money"/>金钱 
       <input type="checkbox" name="hobby" value="gril"/>美女
       <input type="checkbox" name="hobby" value="code"/>代码
    </form>
  ```

   <form action="192.168.1.211:3306 " method="get" >
      爱好:<input type="checkbox" name="hobby" value="1"/>金钱 
       <input type="checkbox" name="hobby" value="2"/>美女
       <input type="checkbox" name="hobby" value="3"/>代码
    </form>

  ```html
    <form action="192.168.1.211:3306 " method="get" >
       用户名: <input type="test" name="username" placeholder="请输入用户名"/>
      密码: <input type="test" name="username" placeholder="请输入密码"/>
      性别<input type="radio" name="gender" value="male"/>男
      <input type="radio" name="gender" value="female"/>女 
    </form>
  ```

    <form action="192.168.1.211:3306 " method="get" >
       用户名: <input type="test" name="username" placeholder="请输入用户名"/>
      密码: <input type="test" name="username" placeholder="请输入用户名"/>
      性别<input type="radio" name="gender" value="male"/>男
      <input type="radio" name="gender" value="female"/>女 
    </form>



### 1.3 文件上传

```html
  <form action="192.168.1.211:3306 " method="post" >
     上传照片<input type="file" name= "file" />
  </form>
```

  <form action="192.168.1.211:3306 " method="post" >
     上传照片<input type="file" name= "file" />
  </form>

### 1.4 隐藏域

用户看不到,但会提交服务器

```html
 <form action="192.168.1.211:3306 " method="post" >
     <input type="hidden" name= "id" value="11" />
  </form>
```

### 1.5 下拉框 < select> 

 < select> 为总标签

* name  在select标签中写
* value  在option中写
* selected 默认选中

```html
<form action="192.168.1.211:3306 " method="post" >
     所在城市<select name="city">
         <option value="bj">北京</option>
         <option value="sh">上海</option>
         <option value="sz">深圳</option>
         <option value="gz">广州</option>
    </select>
  </form>
```

<form action="192.168.1.211:3306 " method="post" >
     所在城市 <select>
         <option>北京</option>
         <option>上海</option>
         <option>深圳</option>
         <option>广州</option>
    </select>
  </form>

### 1.6 文本域  < textarea>

属性:

* cols  可以写多少列
* rows 可以写多少行

```html
<form action="192.168.1.211:3306 " method="post" >
    <textarea name="text" cols="20" row="20"></textarea>
  </form>
```

<form action="192.168.1.211:3306 " method="post" >
    <textarea name="text" cols="20" row="20"></textarea>
  </form>

## 2. CSS

### 2.1 了解div和span

* div作用
  1. 用来对页面进行布局,可以替换table标签
  2. 本身没有任何效果,需要结合css使用
  3. 每个div 会独自占一行
* span作用
  1. 用来显示文本,可以替换font
  2. 不会独自占一行

### 2.2 css样式介绍

* html 设计页面总体架构
* css  页面装饰
* js  

CSS:  层叠样式表

**引入css的方式**

1. **行内样式**  style="键:值; 键:值; "

   仅对当前行起作用.

   ```html
   <div style="color:red;width:300px;">
       
   </div>
   ```

2. **内部样式**     当前文件中所有都起作用

    在head 标签内< style type = "text/css">

   ```html
   <!DOCTYPE html>
   <html lang="en">
   <head>
   	<meta charset="UTF-8">
   	<title>Document</title>
       <style type = "text/css">
           div{color:read;}
           </style>
   </head>
   <body>
   	
   </body>
   </html>
   ```

3. **外部样式**    对当前项目所有的html文件都起作用,必须单独写css文件,

   * 引入外部的css样式

   ```html
   <link rel="stylesheet" href="">
   ```


#### 选择器

* 要使用css样式对标签起作用,必须先找到该标签
* 如何找到这个标签,就被称为选择器

1. **标签选择器**  通过标签名来找到标签

2. **ID选择器**  通过定义在标签内的ID来选择标签

   		#开头,id唯一

3. **类选择器**  通过定义在标签内的class来选择标签

   		. 开头,标签可以重复

```html
<!--标签选择器-->
标签名字{}
<!--ID选择器-->
#id{}
<!--类选择器-->
.cl{}
```

#### 伪类选择器

* 顺序固定 l->v->h->a

#### 常见的css样式

##### 1. 边框 border

不可以单独使用

```htnl
 border-width: 10px;
 border-color: red;
 border-style: soild;
或者写成
border: 10px red soild;
```

独自占一行的元素称为块元素

不会独自占用一行的元素称为行元素

转换:

display: inline-block  将块元素转换为行元素

display: none   隐藏元素

diaplay: block  显示元素

字体

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
    <style type = "text/css">
        span{
            color:red;
            font-size: 300px;
            font-family:"楷体"
        }
        </style>
</head>
<body>
	<span> 我是span  </span>
</body>
</html>
```

background-image:url(img/xxx.jpg)

## css盒子模型

* 内边距 padding  上右下左
  * padding-top
  * padding-right
  * padding-bottom
  * padding-left

* 外边距 margin  上右下左
  * margin-top
  * margin-right
  * margin-bottom
  * margin-left





