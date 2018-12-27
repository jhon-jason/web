## 1. XML 概述

* 可扩展的标记语言 Extensible Markup Language 目前使用1.0版本

* 作用

  * 用来存储数据

  * 用来做配置文件

    > 配置文件
    >
    > 1. properites文件
    >
    >    键=值  ip=192.168.1.1
    >
    > 2. xml文件
    >
    >    < ip name="ip">192.168.1.1< p>

## 2 . xml的语法

* 所有xml的文件都是以 . xml为后缀

### 2.1 xml的组成

1. **文档声明**

```xml
<?xml version = "1.0" encoding = "UTF-8"?>
```

2. **元素**   (element)

   `< student> 元素体 < /students>`

   开始标签,元素体,加上结束标签就称为元素

   * 元素体既可以是子元素,也可以是字符串

   * 空元素 只有开始标签,没有结束标签,的那元素必须自闭合 < hr/>
   * 元素区分大小写,不能使用空格
   * 良好的xml,只能有一个根元素

3. **属性**  (attribute)

   `< student stuId="1234">< /student>`

   * 属性的值 可以用单引号,也可以双引号,
   * 属性的名字,必须字母或下划线开头

转义字符与 CDATA 区

常见转义字符

|   字符   |  <   |   >   |    "    |    '    |   &    |
| :------: | :--: | :---: | :-----: | :-----: | :----: |
| 转义字符 | &It; | &gt ; | &quot ; | &apos : | & amp; |

需要转义的字符放入CDATA区中 ,会自动转义

```xml
<![CDATA[
    任意内容
]]>
```

## 3. xml约束文件

* 缺点:

  * 标签名太随意,没有统一的规定,实际开发中,不能有效的整合

  * 解决方式:给xml加约束,限定必须使用指定的规范写xml

  * 约束规范

    1. DTD约束

       其实就是约束文件,后缀名为 `.dtd`

    2. Schema约束

       也是约束文件,后缀名为` .xsd`

    * 要求可以看懂,并按照规范书写符合要求的xml文件

#### 3.1 DTD约束

* 约束元素的名称 子元素的名称及顺序，元素的属性等。

  * 引入dtd

  ```dtd
  <!DOCTYPE beans SYSTEM "bean.dtd">
  <!--beans 为xml的根元素的名字-->
  <!--SYSTEM 表示本地DTD约束 ,如果需要引入网络上的DTD 此处需要写PUBLIC-->
  ```

  1. 创建文件夹 dtd
  2. 将dtd文件拷入文件夹

#### 3.2 Schema约束

* 引入约束

  建议使用idea-新建快捷键

  ```scheme
   <beans xmlns="http://www.itcast.cn/bean" 
  	    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  	    xsi:schemaLocation="http://www.itcast.cn/bean bean-schema.xsd">
   </beans>
  ```

##  4. dom4j --重点

* 将xml中存储的数据取出即使解析xml
* 1. DOM解析-->解析成Document对象
     * 元素与元素之间保留结构关系,方便进行增删改查
  2. SAX 解析 按照行解析--速度快
  3. PULL  -->安卓使用



解析步骤

1. 创建SAXReader对象  `new SAXReader();`

2. 将整个xml文件读取到内存中,得到document对象

   `.class.getClassLoader().getResourceAsStream("xxx.xml");` 

3. 获取doucument树的根元素  `getRootElement()` 

4. 获取根元素的子元素.

   `.elements() ` 

5. 遍历子元素

6. 获取属性值 `.attributeValue("id")`

7. 获取标签名`.getName()`

8. 获取文本值 `.getText()`

```java
public class Demo_Xml_Parse {
    public static void main(String[] args) throws DocumentException {
        // 1. 创建SAXReader对象
        SAXReader sr = new SAXReader();
        // 2. 将xml读取到内存中
        InputStream rs = Demo_Xml_Parse.class.getResourceAsStream("/books.xml");
        // 两种方式都可以
        // InputStream rs = Demo_Xml_Parse.class.getClassLoader().getResourceAsStream("books.xml");
        // 获取document对象
        Document books = sr.read(rs);

        // 3.获取根元素
        Element rootElement = books.getRootElement();
        // 4. 获取子元素
        List<Element> elements = rootElement.elements();
        // 5. 遍历子元素
        for (Element element : elements) {

            // 获取属性值
            String id = element.attributeValue("id");
            // 获取子元素
            List<Element> elements1 = element.elements();
            for (Element element1 : elements1) {
                // 获取标签名
                String name = element1.getName();
                System.out.println(name);
                // 获取文本值
                String text = element1.getText();
                System.out.println(text);
            }
        }
    }
}

```



## 5. XPATH 解析

-->类似于js中的选择器

*  获取多个节点

  ```java
  List<Node> selectNodes("xpath表达式")
  ```

  > Node 接口 Element 是Node的实现类

* 获取单个节点

  ```java
  Node selectSingleNode("xpath表达式")
  ```

  ​	Element方法：asXML() 以xml方式输出元素内容

* xpath表达式

        1: `/students/student/name`   获取students下的student下的name元素
        2: `//student`   获取xml中所有的student元素
        3:` /* `查询xml中的所有元素
        4: `//student[1]` 获取第一个student元素
           `//student[last()] `  获取最后一个student元素
        5：`//student[@id] `获取包含id属性的student
        6：`//student[@id='it001']`获取包含id属性的student

使用步骤

1. 创建SAXReader对象
2. 将xml文件读到内存中
3. 使用xpath解析

