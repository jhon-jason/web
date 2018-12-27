# AJAX&json

## 1. AJAX的概念

* Ajax 即"Asynchronous Javascript And XML"（异步 JavaScript 和 XML），是指一种创建交互式网页应用的网页开 发技术。

* **同步与异步的区别** 

  | 同步发送请求                                                 | 异步发送请求                                                 |
  | ------------------------------------------------------------ | ------------------------------------------------------------ |
  | 发送一个请求，需要等待响应返回，然后才能够发送下一个请求，如果该请求没有响应，不能发送下一个请求，客 户端会处于一直等待过程中。 | 发送一个请求，不需要等待响应返回，随时可以再发送下一个请求，即不需要等待。 |

* 原生js的ajax
* jquery封装的ajax









## 2. json

### 2.1 什么是json

* json是一种轻量级数据交换格式,,采用完全独立于编程语言的文本格式存储和表示数据

### 2.2 json的语法格式

| 类型         | 语法                               | 解释                                    |
| ------------ | ---------------------------------- | --------------------------------------- |
| 对象类型     | {name:value,name:value...}         | 其中name是字符串类型，而value是任意类型 |
| 数组集合类型 | [value,value,value...]             | value是任意类型                         |
| 混合类型     | [{},{}... ...] 或 {name:[]... ...} | 合理包裹嵌套对象类型和数组类型          |

### 2.3 json的解析

#### 2.3.1 常用的解析工具

| 名称     | 介绍                                                 |
| -------- | ---------------------------------------------------- |
| Jsonlib  | Java 类库，需要导入的jar包较多                       |
| Gson     | google提供的一个简单的json转换工具                   |
| Fastjson | alibaba技术团队提供的一个高性能的json转换工具        |
| Jackson  | 开源免费的json转换工具，springmvc转换默认使用jackson |

#### 2.3.2 常用方法

* jackson

  * ```java
    // java对象转换为json
    new ObjectMapper().writeValueAsString(需要转换对象)
    ```

  * ```java
    // 由json转换为java对象
    ObjectMapper mapper = new ObjectMapper();
    mapper.readValue(jason对象,转换后的类对象
    // 实例:
    Cart cart = mapper.readValue(URLDecoder.decode(cartJson, "UTF-8"), Cart.class);
    ```

* Json-lib -->项目常用

  * **JSONObject.fromObject()**
  * **JSONArray.fromObject()**

