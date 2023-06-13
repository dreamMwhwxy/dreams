---
title: JavaScript--用户端脚本
date: 2023-06-13 15:17:21
tags:
cover: https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/202306132305049.jpg
---
  



# [ 全套知识点| MDN (mozilla.org)](https://developer.mozilla.org/en-US/docs/Learn)



# JavaScript  

### JavaScript的三大组成部分是：

1、ECMAscript；2、文档对象模型DOM；3、浏览器对象模型BOM。其中，ECMAscript是javascript的核心，描述了语言的基本语法和数据类型。

- ECMAScript：JavaScript的核心，描述了语言的基本语法(var、for、if、array等)和数据类型(数字、字符串、布尔、函数、对象(obj、[]、{}、null)、未定义)，ECMAScript是一套标准，定义了一种语言（比如JS）是什么样子。

- 2、文档对象模型（DOM）：DOM（文档对象模型）是 HTML 和 XML 的应用程序接口（API）。DOM 将把整个页面规划成由节点层级构成的文档。HTML 或 XML 页面的每个部分都是一个节点的衍生物

- 3、浏览器对象模型（BOM）

  对浏览器窗口进行访问和操作。例如弹出新的浏览器窗口，移动、改变和关闭浏览器窗口，提供详细的网络浏览器信息（navigator object），详细的页面信息（location object），详细的用户屏幕分辨率的信息（screen object），对cookies的支持等等。

# JavaScript输入输出语句

- prompt（info）浏览器弹出输入框用户可以输入
- alert（msg）浏览器弹出警示框
- console.log(msg)浏览器控制台打印输出信息、

# JavaScript 变量

### 变量的本质

变量是程序在内存申请一块用来存储数据的空间。它们可以包含几乎任何东西 - 而不仅仅是字符串和数字。变量还可以包含复杂的数据，甚至整个函数来做惊人的事情。

### 申明变量

有两种  **ver** 和  **let** JavaScript  中变量是大小写敏感的    myName 和myname 是两个不同的变量。在声明变量时最好使用 **“小骆驼大小写”** 。变量的重赋值，最后一次赋值为最终结果。

### 动态键入

JavaScript是一种“动态类型语言”，这意味着，与其他一些语言不同，您不需要指定变量将包含的数据类型（数字，字符串，数组等）。

例如，**如果您声明一个变量并为其提供一个用引号括起来的值，则浏览器会将该变量视为字符串：**

```js
let myString = 'Hello';
```

即使括在引号中的值只是数字，它仍然是一个字符串 - 而不是一个数字 - 所以要小心：

> ```js
> let myNumber = '500'; // oops, this is still a string
> typeof myNumber;
> myNumber = 500; // much better — now this is a number
> typeof myNumber;
> ```
>

### JavaScript 中的常量 const （有疑问）

除了变量之外，您还可以声明常量。这些类似于变量，除了：

- 在声明它们时必须初始化它们
- 初始化后，您无法为它们分配新值。

# JavaScript 数据类型

### 数据类型二大类



1. 简单数据类型（Number  String   Boolean   Undefined  Null）

   ![image-20220907163327555](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/image-20220907163327555.png)

   - NaN 是非数字类型

   判断是否为非数字用  **isNaN（）** 并返回一值 如果是数字返回的是 **false** 如果不是数字返回 **true**

   - 字符串转义字符![image-20220907174425727](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/image-20220907174425727.png)

   - 字符串长度

     ```js
    var zifuLength = ('我要中 彩票！')
     alert (zifuLength.length);   //7
     ```
   
     

2. 复杂数据类型（ object）

### 数据类型的转换

##### JavaScript 变量可以转换为新变量或其他数据类型：

- 通过使用 JavaScript 函数
- 通过 JavaScript 自身自动转换

1. 将数字转换为字符串：

   全局方法 **String()** 可以将数字转换为字符串。

   Number 方法 **toString()** 也是有同样的效果。

2. 将日期转换为字符串

   全局方法 String() 可以将日期对象转换为字符串。

   ```js
   String(new Date())      // 返回 Thu Jul 17 2014 15:38:19 GMT+0200 (W. Europe Daylight Time)
   ```

##### 将字符串转换为数字

- 全局方法 **Number()** 可以将字符串转换为数字。

- 字符串包含数字(如 "3.14") 转换为数字 (如 3.14).

- 空字符串转换为 0。

- 其他的字符串会转换为 NaN (不是个数字)。

```js
Number("3.14")    // 返回 3.14
Number(" ")       // 返回 0
Number("")        // 返回 0
Number("99 88")   // 返回 NaN
```

![image-20220911144159475](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/image-20220911144159475.png)**前两种重要**

##### 装换成布尔型

![image-20220913140929700](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/image-20220913140929700.png)



# JavaScriot 运算符

#### 算术运算符

![image-20220918174602118](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/image-20220918174602118.png)

 前自增与后自增 单独使用效果 一样。但是前自递增与后自增使用方法不一样。

**后自增：先放回原值，后自加一。  前自增：先自加一，后返回值。**

#### 比较运算符

![image-20220918183638900](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/image-20220918183638900.png)

注意 运算符 == （会把字符串转换成数据型）



#### 逻辑运算符![image-20220918184426696](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/image-20220918184426696.png)

**逻辑中断（短路运算）的原理**：当有多个表达式（值）时，左边表达式的值可以确定时，就不再继续运算右边表达式的值。 

※`0`、`" " （空字符串）`、`' '（空字符串）`、`null（空值）`、`undefined（未定义）`、`NaN（非数值）`都表示为`false`，除这些之外的为true。



#### 逻辑与的逻辑中断

 javascript依次获取每一个操作数，将它们转换为布尔变量，如果是false，则直接返回这个操作数的值（注意，`返回的是转换前的原值`，不一定是布尔类型），中断后面操作数的处理；否则继续处理下一个操作数。如果直到最后一个操作数仍然对应布尔变量true，则返回最后这个操作数的值。

语法：

```js
逻辑与&&，当两边全为true时，结果才为true
把&&想象成是两个true，它缺false所以应该返回个false

		 true true
表达式1		&& 		表达式2

从左往右数，哪个表达式是false就返回谁的原值，并且中断停止不再继续。
如果全都是true就返回最后一个表达式2的原值。

```

例题：

```js
<script type="text/javascript">
	document.write(123 && 456); 				 //返回值为456
	document.write(0 && 456); 					 //返回值为0
	document.write(0 && 1 + 2 && 456 * 56789);   //返回值为0
	document.write(" " && 1 + 2 && 456 * 56789); //返回值为空白（空的字符串）
</script>

```

#### 逻辑或的逻辑中断

  javascript依次获取每一个操作数，将它们转换为布尔变量，如果是false，则直接返回这个操作数的值（注意，返回的是转换前的原值，不一定是布尔类型），中断后面操作数的处理；否则继续处理下一个操作数。如果直到最后一个操作数仍然对应布尔变量false，则返回最后这个操作数的值。

语法：

```js
逻辑或||，当两边全为false时，结果才为false
把||想象成是两个false，它缺true所以应该返回个true

		false false
表达式1 		||		表达式2

从左往右数，哪个表达式是true就返回谁的原值，并且中断停止不再继续。
如果全都是false就返回最后一个表达式2的原值。

```

例题：

```js
<script type="text/javascript">
	document.write(123 || 456); 			 	// 返回值为123
	document.write(123 || 456 || 456 + 123); 	// 返回值为123
	document.write(0 || 456 || 456 + 123);  	 //返回值为456
</script>

```

#### 赋值运算符

![image-20220918201400942](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/image-20220918201400942.png)

#### 运算符优先级

![image-20220919092733179](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/image-20220919092733179.png)

# JavaScript 流程控制语句

### 流程控制（if 、switch）

- **if 语句** - 只有当指定条件为 true 时，使用该语句来执行代码
- **if...else 语句** - 当条件为 true 时执行代码，当条件为 false 时执行其他代码
- **if...else if....else 语句**- 使用该语句来选择多个代码块之一来执行
- **switch 语句** - 使用该语句来选择多个代码块之一来执行

三元表达式 是简化的 if 语句。表达式格式为：      num > 8  ? (是真返回这个值)  : （是假返回这个值）；--------有返回值

switch 语句中的条件值  n  与 case 中的值是**全等的关系**。

```js
switch(n)
{
    case 1:
        执行代码块 1
        break;
    case 2:
        执行代码块 2
        break;
    default:
        与 case 1 和 case 2 不同时执行的代码
}
```

### 循环语句（for 、while）

- **for** - 循环代码块一定的次数
- **for/in** - 循环遍历对象的属性
- **while** - 当指定的条件为 true 时循环指定的代码块
- **do/while** - 同样当指定的条件为 true 时循环指定的代码块

```js
// for
for(初始化变量;条件表达式;操作表达式){
	//循环体
}
//循环体中初始变量只执行一次。
```

```js
//   for/in
<script>
function myFunction(){
	var x;
	var txt="";
	var person={fname:"Bill",lname:"Gates",age:56}; 
	for (x in person){
		txt=txt + person[x];
	}
	document.getElementById("demo").innerHTML=txt;
}
</script>
```

```js
//witch
while (条件)
{
    需要执行的代码
    //注意需要终止循环的条件。                与 for循环相比 while 循环能实现更复杂的循环条件
}
```



```js
// do while
//1:循环语法结构
do{
    //循环体
}
while(条件表达式)
//2：do while 和 while不同于 do while 先执行一次循环体 ，在判条件表达式，如果为真继续执行，如果为假这跳出循环。-----至少执行一次。
```

### JavaScript break 和 continue 语句

**continue** 语句  中断当前  的循环中的迭代，然后继续循环下一个迭代。

**break** 语句可用于跳出循环。

**break** 语句跳出循环后，会继续执行该循环之后的代码

# JavaScript 数组

数组的作用：把一组数据的变量名存放在一个变量里（数组）。

数组创建：

```js
// 1、利用 new 创建新数组。
	var arr = new Array[];
// 2、利用数组字面量创建数组。
	var arr1 = [];
**********注意事项：不能直接对数组名赋值否则数组内容回丢失。*********
```

### 判断是否为 数组

```js
// 方法一
var arr = [];
var odj = {};
console.log(arr instanceof Array);   //  输出 true
console.log(odj instanceof Array);   //  输出 false
// 用内置函数    Array.isArray();

```



   当检测 Array 实例时，Array.isArray 优于 instanceof，因为 Array.isArray 能检测 iframes



# JavaScript 函数

### 函数的定义



函数的声明：

```js
function functionName(parameters) {
  执行的代码
  return 返回的值 ;  // 注意 return 后面的代码不会被执行！！
}
// 不调用不执行。
```

### return 注意事项：

- return 后面的代码不会被执行！！
- 只返回一个值，如果有多个值会返回最后一个值。（如果想返回多个值 可以利用数组）。
- 函数如果有 return 则返回 return 后的值，如果没有 return 则返回 undefined 。
- ***函数可以调用另外一个函数！！！***

### 函数的参数（形参与实参）

在 js 中形参的个数可以不等于实参的个数。当实参个数大于形参 会去到形参的个数。当实参的个数小于 形参的个数 另一个形参就是没有数字的变量（undefined）。   而在 java 中 形参的个数与实参的个数不匹配时会报错。建议形参个数与实参个数相等。

![image-20220922153120001](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/image-20220922153120001.png)

### arguments 对象

JavaScript 函数有个内置的对象 arguments 对象。

argument 对象包含了函数调用的参数数组。

通过这种方式你可以很方便的找到最大的一个参数的值：

### 函数的二种命名方式

```js
// 1：利用函数关键字自定义函数（命名函数）
function fn(){

}
fn();
// 2: 函数表达式（匿名函数）
var fun = function(){

}
注意： (1)- fun 是变量名 不是函数名。
	  (2)  函数表达式也可以进行传递参数
	  (3)  函数表达式和申明变量差不多，只不过变量里面存的是值 而函数表达式里面存的是函数

```

### JavaScript 作用域

JavaScript 变量生命周期在它声明时初始化。

局部变量在函数执行完毕后销毁。

全局变量在页面关闭后销毁。



函数参数只在函数内起作用，是局部变量。

***！！！！当变量没有声明只有赋值当全局变量看（ 即使是在函数内部 ）！！！！***



### JavaScript 预解析

> ```js
> 
> 1.问 
> console.log(num);  // 报错
> 2.问
> console.log(num); // nudefined
> var num = 10 ;
> 3.问
> fun();            	// 11
> function fun () {
> 	console.log(11);
> }
> 4.问
> fn();           // 报错！！
> var fn = function(){
> 	console.log(22);
> }
> fn();         // 输出 22
> ----------------------------------------------------------------------
> // 1.我们js引擎运行js分为两步:预解析 代码执行
> // (1). 预解析js引擎会把js里面所有的var  还有function  提升到当前作用域的最前面
> // (2). 代码执行按照代码书写的顺序  从上往下执行
> // 2.预解析分为变量预解析 (变量提升) 和函数预解析 (函数提升)
> //(1)变量提升   就是把所有的变量声明提升到当前的作用域最前面    不提升赋值操作
> //(2)函数提升   就是把所有的函数声明提升到当前作用域的最前面     不调用函数
> ```

```js
//    经典案例   
		 f1();
        console.log(c);
        console.log(b);
        console.log(a);
        function f1() {
            var a = b = c = 9; 
            console.log(a);
            console.log(b);
            console.log(c);
        }   // 输出结果  9 9 9 9 9 报错
```

# JavaScript 对象

JavaScript 中的所有事物都是对象：字符串、数值、数组、函数...

此外，JavaScript 允许自定义对象。     对象只是一种特殊的数据。对象拥有**属性**和**方法**。

### 创建对象的方法

- 使用 Object 定义并创建对象的实例。（new Object）
- 使用函数来定义对象，然后创建新的对象实例。（构造函数）
- 利用对象字面量创建对象

#### 1.利用对象字面量创建对象

​	

```js
// 1.利用对象字面量创建对象
        var obj = {
            uname:'张三',
            uage:18,
            sex:'男',
            sayHi:function() {
                console.log('Hi!')
            }
        }
        // (1)里面的属性或者方法我们采用键值对的方法  键 属性名： 值 属性值
        // (2)多个属性或者方法用逗号隔开
        // (3)方法冒号后面跟的是匿名函数  
// 2.对象的使用
        // (1) 调用属性时 我们采用 对象民.属性名
        console.log(obj.uname);
        // (2)调用属性 还有另一种方法
        console.log(obj['uage']);
        // (3)调用方法   对象名.方法名();   不要忘记小括号！！
        obj.sayHi();
```

#### 2.利用 new object() 创建对象

```js
 var mingren = new Object(); // 创建一个空的对象 
        mingren.name = '鸣人';
        mingren.age = 18;
        mingren.eax = '男';
        mingren.ability_m = function() {
            console.log('我鸣人会影分身！！！')
        }
        console.log(mingren.name);
        mingren.ability_m();
        // 注意我们用 = 号赋值的方法  添加对象的属性和方法------结束用 分号结束
```

#### 3.利用构造函数创建对象

```js
// 构造函数 必需按着这种格式。
        function Star (name,age,eax ) {
            this.name = name;
            this.age = age;
            this.eax = eax;
            this.Sing = function (params) {
                console.log (params);
            }
        }
        var ldh = new Star ('刘德华', 43 ,'男');   // 调用函数放回的是一个对象
        console.log (ldh.name);
        console.log (ldh['age']);
        ldh.Sing('冰雨');
        var zxy = new Star ('张学友', 54 , '男');
        console.log (zxy.name + '' + zxy.eax);
         
        // 1.构造函数的名字首字母要大写 （ Star ）
        // 2.构造函数不需要返回值 return 就可以返回结果。
        // 3.调用构造函数时 必需使用 new 
        // 4.只要 new star（） 就创建了一个  ldh 对象 {}
        // 5. 构造函数时候 属性和方法前面都要加 this  指向对象
```

![image-20220924212822160](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/image-20220924212822160.png)

### new 关键字的执行过程

1. 在内存中新建一个空的对象
2. 让 this 指向新对象
3. 执行构造函数里面的代码，给这个新对象赋值属性和方法
4. 返回这个新对象（所以构造函数里面不需要  return）



### for in 遍历对象

```
for(var key in 对象名){
	console.log(key);    // 输出的是 对象的属性名
	console.log(对象名[key]);      //输出的是 对象的属性。
}
```

# JavaScript 内置对象

对象分为三中：

1. 自定义对象
2. 内置对象-----就是 JS 语言自带的对象，这些对象供开发者使用，并提供了常用或基本的必要功能（属性和方法）
3. 浏览器对象 ---- 是 JS 独有的

#### Math

**`Math.PI`** 表示一个圆的周长与直径的比例，约为 3.14159：

**`Math.abs(x)`** 函数返回指定数字 “x“ 的绝对值。

**`Math.floor()`** 返回小于或等于一个给定数字的最大整数。   向下取整。	

**`Math.ceil()`** 函数返回大于或等于一个给定数字的最小整数。 向上取整。

**`Math.round()`** 函数返回一个数字四舍五入后最接近的整数。

**`Math.random()`** 函数返回一个浮点数， 伪随机数在范围从**0 到**小于**1**，也就是说，从 0（包括 0）往上，但是不包括 1（排除 1），然后您可以缩放到所需的范围。实现将初始种子选择到随机数生成算法;它不能被用户选择或重置。返回一个随机浮点数。**Math.floor(Math.random() * (max - min)) + min;** //不含最大值，含最小值

#### Date

new Date();     //如果没有参数返回系统当前的时间
new Date(value);
new Date(dateString);

Date()是构造函数必需 使用new 来调用函数

**getMonth()**  -----返回一个 0 到 11 的整数值： 0 代表一月份，1 代表二月份， 2 代表三月份，依次类推。（想得到正确的需要 + 1）

![image-20220927133058230](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/image-20220927133058230.png)

#### 毫秒数

**`getTime()`** 方法返回一个时间的格林威治时间数值。（总的毫秒数——1970.1.1---现在）

你可以使用这个方法把一个日期时间赋值给另一个[`Date`] 对象。这个方法的功能和 **valueOf(）**方法一样

**+new Date()**也是总的毫秒数。

最简单的一种方法 直接打印       **Date.now()**  H5新增加的一种方法   有兼容性问题

#### 倒计时 

```js
 function countDown(tame){
            var nowTame = +new Date();     // 当前时间总的毫秒数
            var inPutTime = +new Date(tame);  // 用户输入时间的总毫秒数
            var times = (inPutTime-nowTame) / 1000;  // times 是剩余总的秒数
            var d = parseInt(times / 60 / 60 / 24); // 天
            d = d < 10 ? '0' + d : d ;
            var h = parseInt(times / 60 / 60 % 24); // 小时
            h = h < 10 ? '0' + h : h ;
            var m = parseInt(times / 60 %60); // 分
            m = m < 10 ? '0' + m : m;
            var s = parseInt(times % 60); // 秒
            s = s < 10 ? '0' + s : s ;
            return '倒计时：' + d + '天 ' + h + '时 ' + m + '分 ' + s + '秒';
        }
        // var date = new Date();
        // console.log(date);
        console.log(countDown('2022-10-1 0:0:0'));
```

#### Array()

```JS
// 1.字面量创建数组
        var array_1 = [1,2,3,4,5]
    // 2.利用 new  Array();创建
        // var array = new Array();    没有参数时 创建空数组
       // var array = new Array(4);      只有一个参数时  是数组的长度 是长度为4 的空数组
        var array = new Array(2,3);      // 二个以上是数组。
        console.log(array);
```

JavaScript 的 **`Array`** 对象是用于构造数组的全局对象，数组是类似于列表的高阶对象。

#### Array.isArray()  

H5 新增的方法。

判断是否为数组    如果是数组则返回 true  否则为 false 。

当检测 Array 实例时，Array.isArray 优于 instanceof，因为 Array.isArray 能检测 iframes 。

#### 添加、删除数组元素

四个重点方法：

![image-20220928092504215](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/image-20220928092504215.png)

```js
********************添加数组元素push(),unshift()****************
    
// (1) push() 在数组末尾 添加一个或者多个数组元素
        var arr = [1,2,3];
        //arr.push('我是新加进来的', 5);
        console.log(arr.push('我是新加进来的', 5));   //  arr.push()  返回值是新数组长度-----------  5
        console.log(arr);                              //原数组发生变化 ----------   [1,2,3,'我是新加进来的', 5];
    // (2)unshift() 在数组前面 添加一个或多个数组元素
        console.log(arr.unshift('我是头部'));   //  arr.unshift()  返回值是新数组长度 -------------- 6
        console.log(arr);                     //原数组发生变化--------------['我是头部',1,2,3,'我是新加进来的', 5]
```

```js
*******************添加数组元素pop(),shift()************
// 2、删除数组元素
        // (1) pop() 删除数组最后一个数组元素
       // arr.pop();       // 括号内不需要添加元素  且一次只能删除一个
        console.log(arr.pop());   // 返回值是 删除的最后数组元素    ---------5
        console.log(arr);        // 数组也发生变化

         // (2) shift() 删除数组第一个数组元素
       // arr.shift();       // 括号内不需要添加元素  且一次只能删除一个
       console.log(arr.shift());   // 返回值是 删除的第一个数组元素    ---------我是头部
        console.log(arr);        // 数组也发生变化------------------
```

#### **翻转数组   Array.reverse();**   改变数组并 返回数组。

#### **排序 Array.sort();   改变数组并 返回数组。**   **注意！！**排序回出错：

列如

```js
const array1 = [1, 30, 4, 21, 100000];
array1.sort();
console.log(array1);    // expected output: Array [1, 100000, 21, 30, 4]

// 解决方法 加上 
// function compareNumbers(a, b) {
  // return a - b;}
const array1 = [1, 30, 4, 21, 100000];
array1.sort(function compareNumbers(a, b) {
   return a - b;   // 升序排列   return b - a； // 降序排列
});
console.log(array1);    


```

#### 查找元素序列 Array.indexOf();

Array.indexOf(“需要查找的数据” ， [查找的位置可以没有]);      只会查找第一个数据的位置

首个被找到的元素在数组中的索引位置; 若没有找到则返回 **-1**。

#### 数组转化为字符串  join();

toString()   和  join( 分隔符 )   可以添加任意的分隔符。

#### **`concat()`** 

方法用于合并两个或多个数组。此方法不会更改现有数组，而是返回一个新数组。不影响原数组！

#### **`splice()`** 

方法通过删除或替换现有元素或者原地添加新的元素来修改数组，并以数组形式返回被修改的内容。此方法会改变原数组。

```js
const months = ['Jan', 'March', 'April', 'June'];
months.splice(1, 0, 'Feb');
// Inserts at index 1
console.log(months);
// Expected output: Array ["Jan", "Feb", "March", "April", "June"]

months.splice(4, 1, 'May');
// Replaces 1 element at index 4
console.log(months);
// Expected output: Array ["Jan", "Feb", "March", "April", "May"]
```

*******

指定修改的开始位置（从 0 计数）。如果超出了数组的长度，则从数组末尾开始添加内容；如果是负值，则表示从数组末位开始的第几位（从 -1 计数，这意味着 -n 是倒数第 n 个元素并且等价于 `array.length-n`）；如果负数的绝对值大于数组的长度，则表示开始位置为第 0 位。

`deleteCount` 可选

整数，表示要移除的数组元素的个数。如果 `deleteCount` 大于 `start` 之后的元素的总数，则从 `start` 后面的元素都将被删除（含第 `start` 位）。如果 `deleteCount` 被省略了，或者它的值大于等于`array.length - start`(也就是说，如果它大于或者等于`start`之后的所有元素的数量)，那么`start`之后数组的所有元素都会被删除。如果 `deleteCount` 是 0 或者负数，则不移除元素。这种情况下，至少应添加一个新元素。

`item1, item2, ...` 可选

要添加进数组的元素，从`start` 位置开始。如果不指定，则 `splice()` 将只删除数组元素。

***********

#### 基本包装类型

基本数据类型没有属性和方法，对象才有属性和方法，js 可以直接将 基本数据类型包装为复杂数据类型。（string，boolean，Number）

#### 大小写转换

- `toUpperCase()` 转换大写
- `toLowerCase()` 转换小写

# 字符串对象

### 字符串的不可变性

![image-20221009135448572](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/image-20221009135448572.png)

### 根据位置返回字符串

![image-20221009142005744](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/image-20221009142005744.png)

### 截取字符串

**substr( '截取的初始位置' ,' 截取的长度')**   同样可以使用在数组中。在以后 substr 可能被舍弃。 建议使用 **substring()** 截取长度不添加默认截取到字符串最后。`slice()`截取字符串

>  区别

1. 当第一个参数为大于等于0的数时，第二个数为0时，slice返回值为空；substring返回值是从第0个字符到第一个参数值结束的字符串；

2. 当两个参数都大于零时，两个函数返回值一致；

3. 只要第一个参数小于零，第二参数不管为何值，slice返回值都为空；第二个参数为负数时，subtring返回值为空，第二个参数为正是返回值为从零开始到stop结束的字符串；

4. 当第一个参数大于等于零，第二参数小于零，slice返回值为第一个参数到从尾部数第二个参数之间的字符串；subtring返回值为从零开始到stop结束的字符串；
   

### 替换字符串

**replace( '将要替换的字符' , '替换为的字符' )**  -------------------------- 他只会替换第一个字符

### 将字符串转换为数组 

**split('字符串的分隔符')**         







# DOM

什么是DOM：文档对象模型是w3c组织推荐的处理可扩展标记语言（html 和 xml）的标准编程接口。通过这些接口可以改变网页的结构、样式和内容。

### DOM树：

![image-20221009172817849](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/image-20221009172817849.png)

- 文档：一个页面就是一个文档，DOM中使用documen表示
- 元素：页面中所以的标签都是元素，DOM中使用element表示
- 节点：网页中所以的内容都是节点（标签、属性、文本、注释 换行等），DOM中使用note表示

**DOM中吧以上内容看做      对象**        存在  =获取元素

#### `getElementById()`

[`getElementById()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Document/getElementById)返回一个匹配特定 [ID](https://developer.mozilla.org/zh-CN/docs/Web/API/Element/id)的元素。由于元素的 ID 在大部分情况下要求是独一无二的，这个方法自然而然地成为了一个高效查找特定元素的方法。

```js
语法：
var element = document.getElementById(id);
```

- **`element`**是一个 [Element](https://developer.mozilla.org/zh-CN/docs/Web/API/Element) 对象。如果当前文档中拥有特定 ID 的元素不存在则返回 null.
- **`id`**是大小写敏感的字符串，代表了所要查找的元素的唯一 ID.

#### **`getElementsByTagName()`**

返回的是一个伪数组，如果没有这个标签 则是空的伪数组。

指定的元素的子树会被搜索，不包括元素自己。返回的列表是动态的，这意味着它会随着 DOM 树的变化自动更新自身。

#### querySelector()

返回与指定的选择器组匹配的元素的后代的**第一个元****素**。

#### querySelectorAll()

返回选择器所有的元素对象集合。          切记里面要加上 选择器符号   #id   .less

#### body 和 html 标签的获取

body          document.body;

html            document.documentElement;

### 事件基本三要素

事件原、事件类型（如何触发程序，比如点击onclick、鼠标经过、滑轮）、事件处理程序（通过函数赋值完成）。

### 常见的鼠标事件

![image-20221010161145570](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/image-20221010161145570.png)

### 操作元素

innerText    改变元素内部的文字内容。（不识别 html 标签）----只读时会去除 html 标签

innerHtml        是识别  html 标签

![image-20221010170921296](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/image-20221010170921296.png)

元素的属性  也可以修改   

#### 操作元素属性

**案例**

```js
 <button type="button">按钮</button>
    <input type="text" value="请输入内容">
    <script>
        // 获取元素
        var bu = document.querySelector('button');
        var inp = document.querySelector('input');
		// 注册事件 处理程序
        bu.onclick = function(){
            inp.value = '被点击了！'
          //  bu.disabled = true;   // 禁用按钮！
            this.disabled = true;    //  this 指向的函数的调用者 
        }
    </script>
```

#### 操作样式属性

案例

```js
<head>
	<style>
        div{
            background-color: blueviolet;
            width: 100px;
            height: 100px;
        }
    </style>
</head>
<body>
    <div></div>
    <script>
        // 获取元素
        var div = document.querySelector('div');
		// 注册事件 处理程序
        div.onclick = function(){
            this.style.backgroundColor = 'cyan';
            this.style.width = '200px'
        }
    </script>
                   ******************************************************************************
            document.style        行内样式操作
            document.className   类名式操作
            
            
    ** 注意 **
                js 里面的样式采用驼峰命名法  如 fontSize ， backgroundColor
                JS 修改 style操作 产生的是行内样式，css权重比较高。
```

#####  document.style  和 document.className  注意事项

 **`document.style  `**   如果样式少 或者功能简单下使用     

**``document.className``**  适合于较多的 或者更复杂的的情况。用className 修改元素属性  会直**接覆盖掉**原先有的类名  如果想要即保留原先的类名 又想添加新的类名  用多类名选择器即可。例如

```js
 this.className = 'frist change';  // 中间用  空隔开。 frist 和 change 对应的是二个类名
```

#### 操作元素总结

![image-20221012210338017](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/image-20221012210338017.png)

#### 属性的获取

**获取属性：**

element.属性  获取属性值

element.getAttribute（‘属性’）

**区别：**

element.属性-----------获取内置属性（元素自带的属性）

element.getAttribute（‘属性’）------------只要获取自定义属性（标准）我们程序员自己设定的属性

#### 设置属性值：

element.属性   = '值' 

element.setAttribute（‘属性’ ，'值‘）

**区别：**

element.属性   = '值'   ---------设置内置属性值

element.setAttribute（‘属性’ ，'值‘）-----------注意设置自定义属性（标准）。同时也可以设置内置属性值

#### 删除属性：

element.removeAttribute('属性')

### 自定义属性

设置自定义属性值     element.setAttribute（‘属性’ ，'值‘）

获取自定义属性值    element.getAttribute('属性')  

**给自定义属性取名时 H5 规定自定义属性  date-开头作为属性名并赋值**

H5 新增的 获取 自定义属性的方法。    dateset 是 以date开头的自定义属性的集合。  **`element.dateset.index`**  或者是 **`element.dataset['index']`** 

```js
<div data-list-name='one'> </div>
var listname = div.dataset.listName;        

自定义名字 是 data-list-name  获取属性值 div.dataset.listName;        

```

## 节点

#### 节点概述

![image-20221019183606200](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/image-20221019183606200.png)

#### 节点层级

根据DOM树可以吧节点划分为 不同的层级关系，常见的是 **父子兄层级关系**

##### ***父亲节点***

**`node.parentNode`**  返回最近的父亲节点。如果没有父亲节点则返回空值（null）。

##### **子节点**

**`node.childNodes`** 获得的是所有的子节点  包括元素节点与 文本节点等  （数组）

**`node.children`**   直接获取子类元素 （伪数组）

##### 获取第一个字元素和最后 一个 子元素

**`node.fristChild`**       **`node.lastChild`**  获取的是子类的第一个（最后一个）节点    其中包括文本节点 和 元素节点。

**`node.fristElementChild`**      **`node.lastElementChild`**       直接获取 子类 的第一个（最后一个） 元素节点。

但在 实际开发中 考虑兼容性问题，采用    **`node.children[0]`** 获取 第一个元素 

<font color='red'>**`node.children[node.children.length -1]`**</font> 。  获取最后一个 子节点元素。

##### 兄弟节点

**`node.nextSibling`**  得到的是下一个兄弟节点 包括文本节点 和元素节点  

- [x] **`node.nextElementSibling`**  得到下一个兄弟元素节点。      没有则返回空（null）``

- [x] ``**`node.previousElementSibling`** `得到上一个兄弟元素节点`     没有则返回空（null）

<font color = 'blue' size = '5'>这两个方法只有在IE9 上才兼容</font>

```js
解决兼容性问题
function getNextElementSibling (element){
    var el = element;
    while(el = el.nestSibling){
        if(el.nodeType == 1){
           return el;
           }
    }
    return null;
}
```

#### 添加节点元素

##### 1、创建节点元素

**`document.createElement('将要创建的子节点')`**

##### 2、添加子节点

**`node.aqqendChild('将要添加的子节点')；`**           ----- 在末尾添加 

**`node.insertBefore('将要添加的子元素' ，添加的位置);

```js
var li = document.createElement('li');   // 创建
var ul = document.querySelector('ul');   // 获取父元素
ul.appendChild(li);                       //添加元素   在末尾
ul.insertBefore(li,ul.children[0])        // 在开头添加 元素
```

#### 删除节点元素

**`node.removechild(child)`**  删除节点元素   返回的是删除的节点

#### 复制节点

**`node.cloneNode()`**    复制节点  相当于创建了一个节点    任然需要指定添加到那个位置

<font color= 'red'>注意:</font> cloneNode()  如果括号里面为空或者 为false   是浅拷贝   只拷贝标签  不拷贝里面的子元素---- 如果为  true  则是深拷贝

### 节点创建效率

![image-20221023154441086](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/202210231544485.png)



# 高级事件

### 1、注册事件（绑定事件）

#### 1.1 注册事件

![image-20221023164101447](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/202210231641541.png)

#### 1.2 事件监听

**`eventTarget.addEventListener(type,listener,[useCapture])`**    兼容性问题，h5新增的。

**eventTarget.addEventListener()**  方法将指定的监听器注册到 eventTarget（目标对象上），当该对象触发指定事件时，就会执行事件处理函数。

- <font color='red'>type:</font>  事件类型字符串 比如 **click** **mouseover** 注意的是这里 不需要添加 on。    添加   ‘  ’。
- <font color='red'>listener：</font> 事件处理函数 ，事件发生时 会调用该监听函数
- <font color='red'>useCapt：</font> 可选参数 是一个布尔值 默认 false 。

<font color = 'blue' size = 4> **`eventTarget.addEventListener(type,listener,[useCapture])`**    可以给事件添加多个事件监听器</font>



#### 1.3 attachEvent 事件监听方式 （只适用于 ie 9 以前的版本）

![image-20221023180429554](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/202210231804623.png)

不推荐使用这种方 法



<font color= 'rgb(27,234,223)' size = 6 >解决兼容性问题解决</font>  

```js
function addEventListener(element,eventName,fn){
	// 判断当前浏览器是否支持 addEventListener方法
	if (element.addEventListener){
	element.addEventListener(eventName,fn);// 第三个参数 默认是false
    }else if (element.attachEvent){
	element.attachEvent('on'+ eventName,fn);
    } else{
	// 相当于 element.onclick=fn;
	element['on’+ eventName]=fn;
    }
```

### 2、删除事件（解绑事件）

```js
 var div = document.querySelectorAll('div');
        // 传统生成点击 加 删除
        div[0].onclick = function(){
            alert('22');
            div[0].onclick = null;
        }
        // 监听事件  删除
        div[1].addEventListener('click',fn);
        function  fn(){
            alert('44');
            div[1].removeEventListener('click',fn);
        }
```

**`element.removeEventListener('将要删除的事件'‘ 事件处理函数’)`**       <font color='red'> 事件处理函数需要放在注册事件外addEventListener('click',fn);      并且在里面调用函数不需要加小括号</font >



### <font color = 'red'>3.DOM 事件流</font>

事件流描的是从页面中接受事件的顺序，事件发生时会在元素之间以特定的顺序传播，这个传播过程就是<font color = 'red' >DOM事件流</font>

比如我们给 div 注册一个点击事件  ：

DOM流经历了三个阶段：

1. 捕获
2. 当前目标阶段                                         
3. 冒泡阶段

![image-20221024113734843](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/202210241137921.png)



- 事件冒泡：IE最早提出，事件开始时由具体的元素接受，然后逐级向上传播到DOM最顶层节点的过程
- 事件捕获：网景最早提出，由DOM最顶层节点开始，然后逐级向下传播到最具体元素接受的过程。

![image-20221024114926960](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/202210241149041.png)

**onblur**  **onfocus**    **onmouseenter**   **onmouseleave**  是没有 冒泡阶段的

### 4.1 事件对象 

**`element.removeEventListener('将要删除的事件',function(event){})`**  其中的 **event**  就是事件对象  

事件对象只有有了事件才会存在，并且是系统自动创建的，不需要我们传递参数。而且 我们 可以给事件对象取名  在实际开发中 经常使用   e  来代替  event   。但是在 ie 678 中不兼容 。不能使用 H5 新增的注册事件     使用老板本的兼容问题。

event  是一个包含一系列事件的集合，比如 鼠标点击的坐标，键盘录入的键位等等

```js
        var div = document.querySelector('div');
        div.onclick = function(event){
            // 兼容写法
            event = event || window.event;
            console.log(event);
        }
```

#### 4.2 事件对象属性

![image-20221024153454082](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/202210241535201.png)

**e.target 的常用的属性**

event.target.nodeName 　　//获取事件触发元素标签名（li，p，div，img，button…）

event.target.id　　　　　　//获取事件触发元素id

event.target.className　　//获取事件触发元素classname

event.target.innerHTML　 //获取事件触发元素的内容（li）

**e.target ** 和  **this **的区别

```js
    <div>123</div>
    <ul>
        <li>123</li>
        <li>456</li>
        <li>789</li>
    </ul>
    <script>
        // e.target  返回的触发事件的对象   而  this 返回的是 事件绑定对象（元素）
        var div = document.querySelector('div');
        div.addEventListener('click',function(e){
            console.log(e.target);   // <div>123</div>
            console.log(this);   // <div>123</div>
        })

        var ul = document.querySelector('ul');
        ul.addEventListener('click',function(e){
            console.log(e.target);     // 返回的是点击ul 其中的 li 
            console.log(this);      // <ul>
        });
    </script>
```

**阻止默认事件发生** 

```js
        var a = document.querySelector('a');
        a.addEventListener('click',function(e){
            e.preventDefault();    // dom 标准写法
        })
```

### 5.事件委托

原理：

<font color= 'red'>不是每个子节点上单独设置监听器，而是在子节点的父节点设置监听器，然后利用冒泡原理影响每一个子节点</font>  只访问一次DOM 提高了 程序效率。

> 演示：

```
<ul id="ul1">
             <li>111</li>
             <li>222</li>
             <li>333</li>
             <li>444</li>
   </ul>
        
<script type="text/javascript">
             window.onload = function(){
                 var oUl = document.getElementById('ul1');
                 oUl.onmouseover = function(ev){
                     var ev = ev || window.event;
                     var oLi = ev.srcElement || ev.target;
                     if(oLi.nodeName.toLowerCase() == 'li'){
                         oLi.style.background = 'red';
                     }                    
                 }
                 oUl.onmouseout = function(ev){
                     var ev = ev || window.event;
                     var oLi = ev.srcElement || ev.target;
                    if(oLi.nodeName.toLowerCase() == 'li'){
                         oLi.style.background = '';
                     }                
                }
             }
         </script>
```



# 常见 鼠标键盘事件

### 1、鼠标事件

![image-20221010161145570](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/image-20221010161145570.png)

#### 1.1禁用鼠标右键菜单

**contextmenu** 主要控制应该何时显示上下文菜单，主要用于程序员取消默认的上下文菜单。

```js
document.addEventListener('contextmenu', function (e) {
            e.preventDefault();
        }); 
```

#### 1.2、禁止鼠标选中（**selectstart **开始选中 ）

```js
 document.addEventListener('selectstart', function (e) {
            e.preventDefault();
        });
```

#### 1.3、鼠标事件对象

**event** 对象代表事件的状态，跟事件相关的一系列信息集合。限阶段我们主要使用的鼠标事件对象，**MouseEvent** 和键盘事件对象

**keyboardEvent**

![image-20221025175035752](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/202210251750726.png)

### 2、键盘事件

![image-20221025195229767](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/202210251952837.png)

------

<img src="https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/202210261106226.png" alt="image-20221026110645151"  />

------

**keyCode**  可以获取用户按下的键位   返回的是ASCII 表的值。

**keydown** 和 **keyup**  不区分大小写   **keypress** 可以区分大小写 。  但是**keypress** 不识别功能键，实际开发中还是使用前二者比较多。



------



# BOM 浏览器对象模型

## BOM 概述

BOM 提供了独立于内容而与浏览器窗口交互的对象，其核心的对象是 window 。

BOM 是由一系列相关的对象构成，并且每个对象都提供了很多方法和属性。

![image-20221102143015083](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/202211021430173.png)

![image-20221102143358173](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/202211021433259.png)

<font color='red'>window 是浏览器的顶级对象，</font> 它具有双重角色

1. 它是 js 访问浏览器的一个接口。
2. 它是一个全局变量，定义在全局作用域中的变量、函数都会变成 window 的属性和方法。

在调用的时候可以省略 window 如全面学到的对话框都属于 window 对象方法。

<font color='red' size='5'>注意：window 下的特殊属性，window.name。（在给其他变量起名时尽量避免取名 name。）</font> 

## window 对象的常见事件

### 2.1窗口加载事件

 **`window .onload`** 或者 **`window.addEventListener('load',function(){})`**

`window .onload` 是窗口（页面）加载事件，当文档内容全部加载完毕才会触发该事件（包括图形 文件 css 等），才会调用的处理函数。

<font color='red' size = '5'>注意：</font>

1. 有了 **`window .onload`** 就可以吧 js 代码写到任意的位置，因为onload 在页面加载完成后才会被执行。
2.  **`window .onload`** 在传统方法只能写一个 ，如果有多个会以最后一个 **`window .onload`** 为准。
3. 如果使用 **`window.addEventlinstener`** 就不会有限制。

如果需要加载的页面图片过多，使用 **window.onload** 图片为加载完成时是无法进行页面交互的。这时候就要用到新的事件 **`winaow.addEventLinsener('DOMContentLoaded')`**   **DOMContentLoaded** 在 DOM 加载完毕时就会执行。   ------ie9 以上支持！

### 2.2 调整窗口大小事件

**`window.onresize = function(){}`**  和  **`window.addEventLinstener('resize',function(){})`**  是调整窗口大小加载事件，当触发时就会调用的处理函数。

<font color='red' size = '5'>注意：</font> 

1. 当页面像素大小发生变化时，就会触发这个事件
2. 我们经常用这个事件完成响应式布局， 用 **window.innerHeight**  获取页面的高度

## 定时器

### 3.2 window.**setTimeout** 定时器

**`window.setTimeout(调用函数，[延迟多少毫秒])`** 用于设置一个定时器，该定时器在到期后会被调用

<font color= 'red'>注意：</font>

1. window 可以省略.

2. 这个调用函数 可以**直接写函数** ，**或者写函数名调用** 或者采用字符串 **‘ 函数名() ’** 三种方式，第三种不建议使用

3. 延迟的毫秒数默认为 0  ，如果设置 必需是毫秒数

4. 因为一个页面内有很多定时器，可以给定时器赋值一个标志符。

   #### 3.2.1 window.setInterval()定时器

   **`window.setInterval()`** 定时器和 **setTimout()** 定时器几乎一样。 <font color= 'blue'>唯一不同的是 </font>**`window.setInterval()`** 在延迟毫秒数反复执行回调函数   而      **setTimout()**  只执行一次就结束了。

### 3.3 清除定时器 window.clearTimout('定时器的标识符')

**window.clearTimout('定时器的标识符')** 

**`window.clearInterval('定时器的标识符触发触发')`**

<font color= 'red'>注意：</font>

1. window 同样可以省略。
2. 里面的参数就是定时器的标识符。

# this 指向问题



1.   全局作用域或普通函数中的 this 指向全局对象 window （定时器里面的的 this 也指向 window）

   ```js
   console.log(this) // window
   
   function fn (){
       console.log(this)//window
   }
   fn();
   
   setTimeout(function(){console.log(this)},1000) // window
   ```

   

2. 方法调用中 谁调用指向谁。

   ```js
   var o = {
       typles:ture,
       typle:function(){
           console.log(this);
       }
   }
   0.type();  // 指向的是调用者
   ***********
       var bt = document.querySelector('button');
   bt.onclick = function(){
       console.log(this)// this 指向的是bt这个按钮
   }
   ```

   

3. 构造函数中的 this 指向构造函数的实例化。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         

```js
function Function (){
	console.log(this);    // this 指向的是 fun 实例对象
}
var fn = new Function();
```

解决 this 指向的问题 可以使用  apply  和 call  或者 使用 箭头函数。  具体常考 JavaScript 忍者秘籍。

# JS 执行机制

##### 同步和异步的执行机制

***同步任务***：

同步任务都在主线上执行，形成一个**执行栈**。

而异步任务都放在 任务队列中（消息队列）。

***异步任务：***

JS 的异步是通过回调函数实现的。一般而言异步任务主要分为一下三中类型：

1、普通事件，如 click，resize，

2、加载事件，如load，error。

3、定时器，包括setInterval ，setTimeout等

```js
console.log(1);
setTimeout(function(){
    console.log(2);
},0)
console.log(3);
**************************************
    输出的结果是 132
因为定时器是异步任务，在同步任务的 执行栈 执行完毕  才会去执行 任务队列中的 定时器。
```

![image-20221104102909401](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/202211041029579.png)

# location 对象

window 对象给我们提供了 location 属性 用于获取或设置窗口的 URL ，并且可以用于解析 URL ,因为这个属性返回的是一个对象，所以我们将 location 属性称为 location对象。

# URL 

![image-20221105141340306](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/202211051413458.png)

# location 对象的属性

![image-20221105141805524](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/202211051418604.png)

# location 对象的方法

![image-20221105152740319](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/202211051527400.png)

# navigator 对象

![image-20221105154022149](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/202211051540239.png)

# history 对象

![image-20221105154412234](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/202211051544308.png)



将 https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/ 替换为

D:%5CWED%5C%E7%9F%A5%E8%AF%86%E7%82%B9%5CJS%E7%AC%94%E8%AE%B0%5C%E5%9B%BE%E7%89%87%5C



![202211092048486](D:%5CWED%5C%E7%9F%A5%E8%AF%86%E7%82%B9%5CJS%E7%AC%94%E8%AE%B0%5C%E5%9B%BE%E7%89%87%5C202211092048486.png)