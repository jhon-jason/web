# Redis

## 1. NOSQL

### 1.1 定义

* NOSQL = Not Only SQL --->泛指**非关系型数据库** 
* 包括键值(key-value)存储数据库,列存储数据库,文档型数据库,图形数据库

### 1.2 优势

针对三高问题的解决

1. **High performance**  -->**高并发读写** 需求
2. **Huge Storage**  -->对海量数据的高效率存储和访问需求
3. **High Scalability && High Availablity** -->高扩展性和高可用性需求

### 1.3 对比

| 关系型数据库                                                 | 非关系型数据库                                               |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| 数据是由一张张的表组成，而且这些表与表之间有关系（一对一，一对多，多对多） | 数据是有一个个的键值对：键 值  键 值                         |
| 数据是存在硬盘上，每次访问时，是将数据从硬盘读取到内存中     | 数据是存在内存中，在满足需要的时候，也可以将数据存在硬盘上（Redis的持久化） |



## 2. Redis

### 2.1 定义

* Redis是用C语言开发的一个开源的高性能**键值对**（key-value）数据库

### 2.2 支持的键值数据类型

* 字符串类型 String
* 散列类型 hash
* 列表类型 list
* 集合类型 set
* 有序集合类型  sortedset

### 2.3 备注

* Redis的服务占用端口号为**6379**
* Redis的键 最好不要超过1024个字节,这样不仅会消耗内存而且降低查找效率
* Redis的值 最大数据长度为512M

| 值的数据类型                 | ??                  | 对应java                           |
| ---------------------------- | ------------------- | ---------------------------------- |
| 字符串（String）             | 键----值            | Map<String,String>                 |
| 哈希（hash）                 | 大键---小键---值    | Map<String,Map<String,String>>     |
| 字符串列表（list）           | 键----值1，值2，值3 | Map<String,LinkedList< String>>    |
| 字符串集合（set）            | 键----值1，值2，值3 | Map<String,HashSet< String>>       |
| 有序字符串集合（sorted set） | 键----值1，值2，值3 | Map<String,LinkedHashSet< String>> |





## 3. 方法

### 3.1 字符串类型方法 -->重点

```java
// 1.存储键值对
set key value
> set name "zhangsan"
    
// 2.根据键找值
get key
> get name
> "zhangsan"

// 3.删除指定的key
del key
> del name

// 4.获取多个值
mget key1 key2 ...
> set name "zhangsan"
> set age 18
> set gender nam
> mget name age gender
	"zhangsan"
	"18"
	"nam"
```

### 3.2 哈希(hash) 方法

```java
// 1.添加数据
hset key ﬁeld value
> hset myhash username zhangsan
```







### 3.5 通用指令

```java

```



