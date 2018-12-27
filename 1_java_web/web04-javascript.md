# JavaScript DOM

* DOM 就是将HTML文档看作树形结构
* DOM就是对这个树形结构进行增删改查
* DOM就是使用函数对DOM树进行操作

## DOM操作函数

### 1. 操作元素

#### 	1.1 根据id获取元素对象	

​		 `getElementById(id属性值)`

#### 	1.2 根据标签名称获取元素

​		`getElementByTagName(标签名称)` 返回值为数组

#### 	1.3 根据class属性获得元素

​		`	getElementByClassName(class属性值)` 返回值为数组

#### 	1.4 根据name属性获得元素

​		`getElementByName(name属性值)` 返回值为数组

#### 	1.5 创建新的元素

​		`createElement()` 

#### 	1.6 将元素放到父元素的内部

​		`appendChild()` 

#### 	1.7 在标签体中添加内容

​		`innerHTML`

### 2.操作属性

#### 	2.3 获取属性的值

​		`getAtrribute(name)`

#### 	2.2 设置属性的值

​		`setAtrribute(name,value) `

#### 	2.3 删除某个属性

​		`removeAtrribute(name)`

### 3. JS内置对象

1.  String 对象
2. Date 对象
3. Math 对象
4. Array 对象

### 4. 正则表达式

* 是一个用于判断字符串是否符合规则的字符串

常用的

| 字符类         |                                                |
| -------------- | ---------------------------------------------- |
| [abc]          | a、b 或 c（简单类）                            |
| [ ^ abc]       | 任何字符，除了 a、b 或 c（否定）               |
| [a-zA-Z]       | a 到 z 或 A 到   Z，两头的字母包括在内（范围） |
| [a-d[m-p]]     | a 到 d 或 m 到   p：[a-dm-p]（并集）           |
| [a-z&&[def]]   | d、e 或 f（交集）                              |
| [a-z&&[ ^bc]]  | a 到 z，除了 b 和   c：[ad-z]（减去）          |
| [a-z&&[ ^m-p]] | a 到 z，而非 m 到   p：[a-lq-z]（减去）        |



| 预定义字符类 |                                                              |
| ------------ | ------------------------------------------------------------ |
| .            | 任何字符（与[行结束符](mk:@MSITStore:C:\Users\孙中剑\Desktop\JDK_API_1_6_zh_CN.CHM::/java/util/regex/Pattern.html#lt)可能匹配也可能不匹配） |
| \d           | 数字：[0-9]                                                  |
| \D           | 非数字： [ ^0-9]                                             |
| \s           | 空白字符：[ \t\n\x0B\f\r]                                    |
| \S           | 非空白字符：[ ^\s]                                           |
| \w           | 单词字符：[a-zA-Z_0-9]                                       |
| \W           | 非单词字符：[ ^\w]                                           |