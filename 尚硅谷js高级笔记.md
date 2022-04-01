# 基础总结深入

### 数据类型 

 #### 1. 数据类型的分类

     + 基本(值)类型：
       + String:   - 任意字符串
       + Number : - 任意的数字
       + boolean: - true/false
       + undefined : - undefined
       + null: -null
     + 对象(引用)类型：
       + object： - 任意对象
       + function：- 一种特别的对象(可以执行)里面包含能执行的
       + Array：- 一种特别的对象（数值下标，内部数据是有序的）
  #### 2. 如何判断一种数据的类型(3种方式)
       + typeof：
         + 可以判断：undefined、数值、字符串、布尔值
       + instanceof：  
         + 判断对象具体类型
       + ===：
         + 能判断的只有：undefined，null，因为这两个类型只有一个值

- 示例代码：
   1. 基本类型
````javascript
 // typeof 返回数据类型的字符串表达
 var a 
 console.log(a,typeof a) // undefined 'undefined'
 console.log(undefined === 'undefined') // false
 console.log(a === undefined, a=== 'undefined') // true  true
 
 a =4 
 console.log(typeof a === 'number') // true
 
 a = 'atguigu'
 console.log(typeof a === 'string')  // true
 
 a = true 
 console.log(typeof a === 'boolean') //true
 
 a= null 
 console.log(typeof a)  //  'object	'
 console.log(typeof a === 'null') //false
````
   2. 对象类型
      + 函数是一个特殊的对象   
   ````javascript
   var b1 = {
   b2:[1,'abc',console.log],
   b3:function(){
      console.log('b3')
      }
   }
   console.log(b1 instanceof Object, b1 instanceof Array) // true false
   console.log(b1.b2 instanceof Array, b1.b2 instanceof Object) // true  true
   console.log(b1.b3 instanceof Function, b1.b3 instanceof Object)
   // true  true
  // 判断函数还有一种方式
   console.log(typeof b1.b3, typeof b1.b3 === 'function') // 'function'  true
   ````

1. undefined与null的区别?
   * undefined代表定义未赋值
   * nulll定义并赋值了, 只是值为null
2. 什么时候给变量赋值为null呢?
   * 初始赋值, 表明将要赋值为对象
   * 结束前, 让对象成为垃圾对象(被垃圾回收器回收)
3. 严格区别变量类型与数据类型?
  * 数据的类型
    * 基本类型
    * 对象类型
  * 变量的类型(变量内存值的类型)
    * 基本类型: 保存就是基本类型的数据
    * 引用类型: 保存的是地址值

### 数据、变量、内存

#### 1. 什么是数据?
  * 存储在内存中代表特定信息的'东东', 本质上是0101...
  * 数据的特点: 可传递, 可运算
  * 一切皆数据
  * 内存中所有操作的目标: 数据
    * 算术运算
    * 逻辑运算
    * 赋值
    * 运行函数
#### 2. 什么是内存?
  * 内存条通电后产生的可储存数据的空间(临时的)
  * 内存产生和死亡: 内存条(电路版)==>通电==>产生内存空间==>存储数据==>处理数据==>断电==>内存空间和数据都消失
  * 一块小内存的2个数据
     * 内部存储的数据
     * 地址值
  * 内存分类
    * 栈: 全局变量/局部变量
    * 堆: 对象
#### 3. 什么是变量?
   * 可变化的量, 由变量名和变量值组成
   * 每个变量都对应的一块小内存, 变量名用来查找对应的内存, 变量值就是内存中保存的数据
#### 4. 内存,数据, 变量三者之间的关系
   * 内存用来存储数据的空间
   * 变量是内存的标识
      关于引用变量赋值问题
   * 2个引用变量指向同一个对象, 通过一个变量修改对象内部数据, 另一个变量看到的是修改之后的数据
   * 2个引用变量指向同一个对象, 让其中一个引用变量指向另一个对象, 另一引用变量依然指向前一个对象
      问题: 在js调用函数时传递变量参数时, 是值传递还是引用传递
   * 理解1: 都是值(基本/地址值)传递
   * 理解2: 可能是值传递, 也可能是引用传递(地址值)
      问题: JS引擎如何管理内存?
#### 1. 内存生命周期
   * 分配小内存空间, 得到它的使用权
   * 存储数据, 可以反复进行操作
   * 释放小内存空间
#### 2. 释放内存
   * 局部变量: 函数执行完自动释放
   * 对象: 成为垃圾对象==>垃圾回收器回收

### 对象
#### 1. 什么是对象?
   * 多个数据的封装体
   * 用来保存多个数据的容器
   * 一个对象代表现实中的一个事物
#### 2. 为什么要用对象?
   * 统一管理多个数据
#### 3. 对象的组成
   * 属性: 属性名(字符串)和属性值(任意)组成
   * 方法: 一种特别的属性(属性值是函数)
#### 4. 如何访问对象内部数据?
   * .属性名: 编码简单, 有时不能用
   * ['属性名']: 编码麻烦, 能通用

#### 问题: 什么时候必须使用['属性名']的方式?
  1. 属性名包含特殊字符: - 空格
  2. 属性名不确定