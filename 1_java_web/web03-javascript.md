# JavaScript

## 介绍

1. 简称 JS
2. JS是脚本语言-->轻量级,不需要编译,直接解释运行
3. JS由浏览器解释运行
4. JS代码是嵌在HTML内部
5. JS主要实现用户交互

JS语言组成

1. JS基本语法-->变量,流程控制语句,函数-->符合ECMAScript 标准
2. BOM 对象 -->浏览器对象模型
3. DOM 对象 -->对HTML 进行增删改查

## 引入

* js 代码是由上到下顺序执行的

### 1. 内嵌式

* 在< script> 标签中写js代码

### 2. 外联式

* 将js代码单独写 .js文件,使用时引入
* 在< script src = "js文件路径" ....>



## 基本语法

### 1. 变量-->弱类型语言

* 对类型无严格要求,不需要声明,直接使用

* var num = 123; var str = "hello"  var bl = true; 

### 2. 数据类型

* js 定义变量时 ,不需要声明类型,但是 ,底层是由数据类型的
* 分为基本数据类型和引用数据类型

####  2.1, 基本类型

* **number类型**  -->数字类型,不区分整数小数

  var num =  123;   var num2 = 12.34;

* **undefined 类型** -->未定义类型

  var value; 如果一个变量没有赋值或是没有定义,就是undefined类型

* **boolean类型** -->

  var bl = true;

* **null类型** --> var n = null;

  -->打印出来是object -->设计时的错误

  ```javascript
  var abc = null;
  alert(typeof abc);
  ```

* **string 类型**

  var str = "hello"

 ####  2.2 引用类型 object

* 字符串 var str = new String("hello")
* 日期 var data = new Data()

### 3. 运算符

#### 3.1 算术运算符

同java

#### 3.2 赋值运算符

#### 3.3 逻辑速算符

```javascript
var num = 123;
var srt = "123"
alert(num == str); // 浅比较 输出为true
alert(num === str); // 深比较  输出 false
```



### 4. 流程控制语句

js流程控制语句于java 大体相同 if for while swith

```javascript
var num = 123;
if(num){
    alert("真")
}else{
    alert("假")
} // 如果是number类型--->非0即真
```

* 如果是String类型 ---> **空串为假**
* 如果是number类型--**->非0即真**
* 如果是null 类型 -->直接为假
* 如果是 Boolean类型 ---> true为真
* 如果是未定义类型 ---->直接为假



## 函数

* 关键字 `function` 

  ```javascript
  关键字 函数名 ( 参数a, 参数b){
  	语句
  }
  function sum(a,b){
      return a+b;
  }
  // 调用函数
  var result = sum(10,20);
  alert(result);
  ```

* **js中没有重载-**-->函数重名,新写的函数会将原来的覆盖掉.

* 分为**有名函数**和**匿名函数**

  匿名函数用来给函数传参


## 事件

* 事件源

* 事件源与事件绑定

* 事件执行



# BOM 对象

## 1. Window对象

### 1.1 window对象的弹框

* `alert()` 弹出消息框

* `confirm()` 确认框 又返回值

  ```javascript
  var flag = confirm("提示信息")
  // 点击确认 flag为true
  // 点击取消 flag为flase
  ```

* `prompt()`  输入框   类似于java的键盘录入

  ```javascript
  var str = prompt("提示信息")
  // 返回值为输入值
  ```


### 1.2 定时器

* **定时一次**

  `setTimeout(匿名函数,定时时间-毫秒值)`

  到了设定时间,执行一次.

* **重复定时**

  `setInterval(匿名函数,定时时间-毫秒值)`

  每隔设置值时间,就执行函数

* **清除定时器**

  `cleanTimeout()` 

  `cleanInterval()` 

  ```javascript
  var timer = setInterval(function(){
      alert("时间到了")
  },3000)
  clearInterval(timer);// 传入定时器的返回值即可清除定时器
  ```

### 1.3 全局方法

* `parseInt()` 转换为整数

* `parseFloat()` 转换为小数

* `eval()` 将字符串中的js代码执行

  ```javascript
  var str = "123";
  var num = parseInt(str);
  alert(typeof num);
  // ---------------
  var str = "123.45";
  var num = parseFloat(str);
  alert(typeof num);
  // --------------
  var str = "var a = 10; var b = 20;alert(a+b);";
  eval(str);
  ```



### 1.4 location对象

* 是window的对象
* 对location 的href 赋值,相当于在浏览器在地址栏输入
* 今后做页面跳转使用

```javascript
setTimeout(function(){
    location.href = "http://www.baidu.com"
},5000)
// 实现5秒后,跳转百度页面
```