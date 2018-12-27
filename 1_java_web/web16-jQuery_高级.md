jquery的遍历

1. 原始方式遍历

   1. ```javascript
      for(var i=0;i<元素数组.length;i++){
          元素数组[i];
      }
      ```

2. 全局方式遍历

   ```javascript
   $.each(jquery对象,function(index,element){}); 
   其中， index:就是元素在集合中的索引 element：就是集合中的每一个元素对象
   ```

   ​	

3. jquery3.0 新特性遍历

   ```javascript
   for(变量 of jquery对象){
       变量；
   }  
   其中， 变量:定义变量依次接受jquery数组中的每一个元素
   		jquery对象：要被遍历的jquery对象
   ```


