---
title: jQuery 基础
date: 2023-06-13 14:56:26
tags:
---
**[jQuery插件免费网站1](http://www.htmleaf.com/)**

**[jQuery插件网站2](https://www.jq22.com/)**

**[jQuery的官网](https://jquery.com/download/)**

**[jQuery API中文文档](https://jquery.cuishifeng.cn/index.html)**

# jQuery的基本使用（页面DOM加载完毕）

> ```js
>  // $('div').hide();
>         // 1. 等着页面DOM加载完毕再去执行js 代码
>         // $(document).ready(function() {
>         //     $('div').hide();
>         // })
>         // 2.  等着页面DOM加载完毕再去执行js 代码
>         $(function() 
>             $('div').hide();
> 
>         })
> ```



# jQuery对象

## jQuery对象和DOM对象

```js
//1:DOM 对象 用原生 js 获取的对象
     var myDom = document.querySelector('div');
     console.dir(myDom);
 //2:jQuery 获取的对象
     $('div');
     console.dir($('div'));
```

## DOM对象和jQuery对象相互转换

```js
<video src="mov.mp4" muted></video>
    <script>
        // 1. DOM对象转换为 jQuery对象
        // (1) 我们直接获取视频，得到就是jQuery对象
        // $('video');
        // (2) 我们已经使用原生js 获取过来 DOM对象
        var myvideo = document.querySelector('video');
        // $(myvideo).play();  jquery里面没有play 这个方法
        // 2.  jQuery对象转换为DOM对象
        // myvideo.play();
        $('video')[0].play()
        $('video').get(0).play()
    </script><video src="mov.mp4" muted></video>
    <script>
        // 1. DOM对象转换为 jQuery对象
        // (1) 我们直接获取视频，得到就是jQuery对象
        // $('video');
        // (2) 我们已经使用原生js 获取过来 DOM对象
        var myvideo = document.querySelector('video');
        // $(myvideo).play();  jquery里面没有play 这个方法
        // 2.  jQuery对象转换为DOM对象
        // myvideo.play();
        $('video')[0].play()
        $('video').get(0).play()
    </script>
```

![image-20230221135100891](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/202302211351999.png)

# jQuery常用的API

![image-20230221135655624](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/202302211356693.png)

![image-20230221135911620](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/202302211359671.png)

# jQuery选择器

## 1.3 隐式迭代（重要）

**遍历内部DOM元素（伪数组形式存储）的过程就叫做隐式迭代。**
**简单理解：给匹配到的所有元素进行循环遍历，执行相应的方法，而不用我们再进行循环，简化我们的操作，方便我们调用。**

## 1.4 筛选选择器

![image-20230221142754436](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/202302211427500.png)

## 1.5 筛选方法（重点）

![image-20230221145407446](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/202302211454532.png)

<font color="red" size="5">重点记住: parent()  children() find() siblings() eq()</font>   find（）子孙后代都可以查找出来

```js
$(".nav>li").mouseover(function() {
                // $(this) jQuery 当前元素  this不要加引号
                // show() 显示元素  hide() 隐藏元素
                $(this).children("ul").show();
            });
```

## 1.6 链式编程

![image-20230221173602717](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/202302211736757.png)

# jQuery 样式操作

## 2.1 操作 css 方法

![image-20230221180639624](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/202302211817125.png)

```js
        $(function() {
            console.log($("div").css("width"));
            // $("div").css("width", "300px");
            // $("div").css("width", 300);
            // $("div").css(height, "300px"); 属性名一定要加引号
            $("div").css({
                width: 400,
                height: 400,
                backgroundColor: "red"
                    // 如果是复合属性则必须采取驼峰命名法，如果值不是数字，则需要加引号
            })
        })
```

![image-20230221182456341](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/202302211824389.png)

## 2.2 修改样式操作类

```php+HTML
 <style>
        div {
            width: 150px;
            height: 150px;
            background-color: pink;
            margin: 100px auto;
            transition: all 0.5s;
        }
        
        .current {
            background-color: red;
            transform: rotate(360deg);
        }
    </style>
    <script src="jquery.min.js"></script>
</head>

<body>
    <div class="current"></div>
    <script>
        $(function() {
            // 1. 添加类 addClass()
            // $("div").click(function() {
            //     // $(this).addClass("current");
            // });
            // 2. 删除类 removeClass()
            // $("div").click(function() {
            //     $(this).removeClass("current");
            // });
            // 3. 切换类 toggleClass()
            $("div").click(function() {
                $(this).toggleClass("current");
            });
        })
    </script>
</body>

</html>
```

![image-20230221193024935](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/202302211930982.png)

## **2.3**  类操作与className区别

**原生 JS 中 className 会覆盖元素原先里面的类名。**

**jQuery 里面类操作只是对指定类进行操作，不影响原先的类名。** 

# **3.** **jQuery** 效果jQuery 效果

jQuery 给我们封装了很多动画效果，最为常见的如下：

![image-20230222132947896](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/202302221329000.png)

## **3.1**  **显示隐藏切换效果**

### **1.** **显示语法规范**

```jQuery
show([speed,[easing],[fn]])
```

### **1.2** 显示参数

（1）参数都可以省略， 无动画直接显示。

（2）speed：三种预定速度之一的字符串(“slow”,“normal”, or “fast”)或表示动画时长的毫秒数值(如：1000)。

（3）easing：(Optional) 用来指定切换效果，默认是“swing”，可用参数“linear”。

（4）fn: 回调函数，在动画完成时执行的函数，每个元素执行一次。

### **2.** **隐藏**语法规范

```
hide([speed,[easing],[fn]])
```

### **2.** 2**隐藏**参数

（1）参数都可以省略， 无动画直接显示。

（2）speed：三种预定速度之一的字符串(“slow”,“normal”, or “fast”)或表示动画时长的毫秒数值(如：1000)。

（3）easing：(Optional) 用来指定切换效果，默认是“swing”，可用参数“linear”。

（4）fn: 回调函数，在动画完成时执行的函数，每个元素执行一次。

### **3.** **切换语法**规范

```
toggle([speed,[easing],[fn]])
```

### **3.2** 切换参数

（1）参数都可以省略， 无动画直接显示。

（2）speed：三种预定速度之一的字符串(“slow”,“normal”, or “fast”)或表示动画时长的毫秒数值(如：1000)。

（3）easing：(Optional) 用来指定切换效果，默认是“swing”，可用参数“linear”。

（4）fn: 回调函数，在动画完成时执行的函数，每个元素执行一次。

 **建议：*平时一般不带参数*，直接显示隐藏即可。**

## **3.2**  **滑动效果**

**1、效果语法规范**

```
slideDown([speed,[easing],[fn]])//下滑
slideUp([speed,[easing],[fn]])//上滑
slideToggle([speed,[easing],[fn]])//切换

```

**（1）参数都可以省略。**

**（2）speed:三种预定速度之一的字符串(“slow”,“normal”, or “fast”)或表示动画时长的毫秒数值(如：1000)。**

**（3）easing:(Optional) 用来指定切换效果，默认是“swing”，可用参数“linear”。**

**（4）fn: 回调函数，在动画完成时执行的函数，每个元素执行一次。**

## **3.3**  事件切换

```
hover([over,]out)
```

**（1）over:鼠标移到元素上要触发的函数（相当于mouseenter）**

**（2）out:鼠标移出元素要触发的函数（相当于mouseleave）**

**（3）如果只写一个函数，则鼠标经过和离开都会触发它**

## **3.4**  动画队列及其停止排队方法

### **3.4.1** 动画或效果队列

动画或者效果一旦触发就会执行，如果多次触发，就造成多个动画或者效果排队执行。

### **3.4.2停止排队**

```
stop()
```

(1）stop() 方法用于停止动画或效果。

(2) 注意： stop() 写到动画或者效果的前面， 相当于停止结束上一次的动画。

## **3.5**  **淡入淡出效果**

### **1.** **效果语法规范**

```
fadeIn([speed,[easing],[fn]])//淡入
fadeOut([speed,[easing],[fn]])//淡出
fadeToggle([speed,[easing],[fn]])//切换

```

### **2.** 淡入淡出切换效果参数

（1）参数都可以省略。

（2）speed：三种预定速度之一的字符串(“slow”,“normal”, or “fast”)或表示动画时长的毫秒数值(如：1000)。

（3）easing：(Optional) 用来指定切换效果，默认是“swing”，可用参数“linear”。

（4）fn: 回调函数，在动画完成时执行的函数，每个元素执行一次。

## **3.5**  **淡入淡出效果（不透明度）**

```
fadeTo([[speed],opacity,[easing],[fn]])
```

（1）**opacity 透明度必须写，取值 0~1 之间**。

（2）**speed：三种预定速度之一的字符串(“slow”,“normal”, or “fast”)或表示动画时长的毫秒数值(如：1000)。必须写**

（3）easing：(Optional) 用来指定切换效果，默认是“swing”，可用参数“linear”。

（4）fn: 回调函数，在动画完成时执行的函数，每个元素执行一次。

## **3.6**  **自定义动画** **animate**

```
animate(params,[speed],[easing],[fn])
```

（1）**params: 想要更改的样式属性，以对象形式传递，必须写。 属性名可以不用带引号， 如果是复合属性则需要采取驼峰命名法 borderLeft。其余参数都可以省略。**

（2）speed：三种预定速度之一的字符串(“slow”,“normal”, or “fast”)或表示动画时长的毫秒数值(如：1000)。

（3）easing：(Optional) 用来指定切换效果，默认是“swing”，可用参数“linear”。

（4）fn: 回调函数，在动画完成时执行的函数，每个元素执行一次。

# **4. jQuery** 属性操作

## **4.1**  **设置或获取元素固有属性值** **prop()**

### **1.** **获取属性语法**

```
prop(''属性'')
```

### **2.** **设置属性语法**

```
prop(''属性'', ''属性值'')
```

## **4.2**  **设置或获取元素自定义属性值** **attr

用户自己给元素添加的属性，我们称为自定义属性。 比如给 div 添加 index =“1”。 

**1.** **获取属性语法**

```
attr(''属性'')      // 类似原生 getAttribute()
```

**2.** **设置属性语法**

```
attr(''属性'', ''属性值'')   // 类似原生 setAttribute()
```

## **4.3**  **数据缓存** **data()**

data() 方法可以在指定的元素上存取数据，并不会修改 DOM 元素结构。一旦页面刷新，之前存放的数据都将被移除。 

**1.** **附加数据语法**

```
data(''name'',''value'')   // 向被选元素附加数据   
```

**2.** **获取****数据****语法**

```
date(''name'')             //   向被选元素获取数据   
```

同时，还可以读取 HTML5 自定义属性 data-index ，得到的是数字型

# **5. jQuery** **内容文本值**

**1.** **普通元素内容** **html()****（ 相当于原生inner HTML****)**

```
html(''内容'')   // 设置元素的内容
html()             // 获取元素的内容
```

**2.** **普通元素文本内容** **text()  (****相当与原生** **innerText****)**

```
text(''文本内容'')   // 设置元素的文本内容
text()                     // 获取元素的文本内容
```

**3.** **表单的值** **val()****（ 相当于原生****value)**

```
val(''内容'')   // 设置表单的值
val()              // 获取表单的值
```

# **6.** **jQuery** **元素操作**

主要是<font color="red"> 遍历</font>、创建、添加、删除元素操作。

## **6.1** **遍历元素**

jQuery 隐式迭代是对同一类元素做了同样的操作。 如果想要给同一类元素做不同操作，就需要用到遍历。

**语法**1:

```jquery
$("div").each(function (index, domEle) { xxx; }）       
```

\1. each() 方法遍历匹配的每一个元素。主要用DOM处理。 each 每一个

\2. 里面的回调函数有2个参数： index 是每个元素的索引号;<font color="red"> demEle 是每个DOM元素对象，不是jquery对象</font>

<font color="red">\3. 所以要想使用jquery方法，需要给这个dom元素转换为jquery对象 $(domEle)</font>

**语法**2：

```
$.each(object，function (index, element) { xxx; }）       
```

\1. $.each()方法可用于遍历任何对象。主要用于数据处理，比如数组，对象

\2. 里面的函数有2个参数： index 是每个元素的索引号; element 遍历内容

## **6.2** **创建****元素**

**语法：**

```
$(''<li></li>'');    
```

动态的创建了一个 <li> 

## **6.3** **添加****元素**

**1.** **内部添加**

```
element.append(''内容'')  //把内容放入匹配元素内部最后面，类似原生 appendChild。
element.prepend(''内容'')  //把内容放入匹配元素内部最前面。
```

**2**.**外部添加**

```
element.after(''内容'')        //  把内容放入目标元素后面
element.before(''内容'')    //  把内容放入目标元素前面 
```

①内部添加元素，生成之后，它们是父子关系。

②外部添加元素，生成之后，他们是兄弟关系。

## **6.4** **删除**元素

```
element.remove()   //  删除匹配的元素（本身）
element.html('' '')   //  清空匹配的元素内容
element.empty()    //  删除匹配的元素集合中所有的子节点
```

①remove 删除元素本身。

②empt() 和 html('''') 作用等价，都可以删除元素里面的内容，只不过 html 还可以设置内容。

# **7. jQuery** **尺寸、位置操作**

## **7.1**  **jQuery 尺寸**

![image-20230223170649790](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/202302231706902.png)

- 以上参数为空，则是获取相应值，返回的是数字型。
- 如果参数为数字，则是修改相应值。
- 参数可以不必写单位。

## **7.2**  **jQuery 位置**

**位置主要有三个： offset()、position()、scrollTop()/scrollLeft()**

**1. offset****()** **设置或获取元素偏移**

①offset() 方法设置或返回被选元素相对于**文档**的偏移坐标，跟父级没有关系。

②该方法有2个属性 left、top 。offset().top 用于获取距离文档顶部的距离，offset().left 用于获取距离文档左侧的距离。

③可以设置元素的偏移：offset({ top: 10, left: 30 });

**2.** **position()** **获取元素偏移**

①position() 方法用于返回被选元素相对于**带有定位的父级**偏移坐标，如果父级都没有定位，则以文档为准。

②该方法有2个属性 left、top。position().top 用于获取距离定位父级顶部的距离，position().left 用于获取距离定位父级左侧的距离。

③该方法只能获取。

**3.** **scrollTop**()/scrollLeft()***设置***或获取元素被卷去的头部和左侧

①scrollTop() 方法设置或返回被选元素被卷去的头部。

②不跟参数是获取，参数为不带单位的数字则是设置被卷去的头部。

# **2-1**. jQuery **事件注册**

## **单个事件注册**

**语法：**

```
$(“div”).click(function(){  事件处理程序 })       
element.事件(function(){})       
```

其他事件和原生基本一致。

比如mouseover、mouseout、blur、focus、change、keydown、keyup、resize、scroll 等

## **2.1** **事件处理** **on()** **绑定事件**

**on() 方法在匹配元素上绑定一个或多个事件的事件处理函数**

```
element.on(events,[selector],fn)       
```

- \1. events:一个或多个用空格分隔的事件类型，如"click"或"keydown" 。
- \2. selector: 元素的子元素选择器 。
- \3. fn:回调函数 即绑定在元素身上的侦听函数。 

## **2.1** **事件处理** **on()** **绑定事件**

**on()** **方法优势**1：

可以绑定多个事件，多个处理事件处理程序。 	

```
 $(“div”).on({
  mouseover: function(){}, 
  mouseout: function(){},
  click: function(){}	
});       
```

如果事件处理程序相同 

```
 $(“div”).on(“mouseover mouseout”, function() {
   $(this).toggleClass(“current”);
  });       
```

**on()** **方法**优势2：

可以事件委派操作 。事件委派的定义就是，把原来加给子元素身上的事件绑定在父元素身上，就是把**事件委派**给父元素。

```
$('ul').on('click', 'li', function() {
    alert('hello world!');
});       
```

在此之前有bind(), live() delegate()等方法来处理事件绑定或者事件委派，最新版本的请用on替代他们。

**on()** **方法**优势**3**：    重点！！！

动态创建的元素，click() 没有办法绑定事件， on() 可以给动态生成的元素绑定事件 

```
 $(“div").on("click",”p”, function(){
     alert("俺可以给动态生成的元素绑定事件")
 });       
 $("div").append($("<p>我是动态创建的p</p>"));
```

## **2.2** **事件处理** **off()** **解绑事件**

off() 方法可以移除通过 on() 方法添加的事件处理程序。

```
$("p").off() // 解绑p元素所有事件处理程序

$("p").off( "click")  // 解绑p元素上面的点击事件 后面的 off 是侦听函数名

$("ul").off("click", "li");   // 解绑事件委托

```

如果有的事件只想触发一次， 可以使用 one() 来绑定事件。

## **2.3** **自动触发事件 trigger()** 

有些事件希望自动触发, 比如轮播图自动播放功能跟点击右侧按钮一致。可以利用定时器自动触发右侧按钮点击事件，不必鼠标点击触发。

```
element.click()  // 第一种简写形式

element.trigger("type") // 第二种自动触发模式

$("p").on("click", function () {
  alert("hi~");
}); 

$("p").trigger("click"); // 此时自动触发点击事件，不需要鼠标点击

```

```
element.triggerHandler(type)  // 第三种自动触发模式
//triggerHandler模式不会触发元素的默认行为，这是和前面两种的区别。
```

# **3**. jQuery**事件**对象

事件被触发，就会有事件对象的产生。

```
element.on(events,[selector],function(event) {})       
```

阻止默认行为：event.preventDefault()  或者 return false 

阻止冒泡： event.stopPropagation()   

# **jQuery** **其他方法**

## **1. jQuery** **对象拷贝**

如果想要把某个对象拷贝（合并） 给另外一个对象使用，此时可以使用 $.extend() 方法

**语法：**

```
$.extend([deep], target, object1, [objectN])    
```

- \1. deep: 如果设为true 为深拷贝， 默认为false 浅拷贝 
- \2. target: 要拷贝的目标对象
- \3. object1:待拷贝到第一个对象的对象。
- \4. objectN:待拷贝到第N个对象的对象。
- \5. 浅拷贝是把被拷贝的对象复杂数据类型中的地址拷贝给目标对象，修改目标对象会影响被拷贝对象。
- \6. 深拷贝，前面加true， 完全克隆(拷贝的对象,而不是地址)，修改目标对象不会影响被拷贝对象。

<font color="red">1:浅拷贝是把原来对象里面的复杂数据的地址复制给目标对象.2:深拷贝是把数据完全复制一份给目标对象，如果里面没有冲突的属性则会合并在一起。**********在浅拷贝中修改目标对象的复杂数据也会改变原先对象的数据。</font>

# **2. jQuery** **多库共存**

**问题概述：**

jQuery使用$作为标示符，随着jQuery的流行,其他 js 库也会用这$作为标识符， 这样一起使用会引起冲突。

**客观需求：**

需要一个解决方案，让jQuery 和其他的js库不存在冲突，可以同时存在，这就叫做多库共存。

**jQuery** 解决方案：

- \1. 把里面的 $ 符号 统一改为 jQuery。 比如 jQuery(''div'')
- \2.  jQuery 变量规定新的名称：$.noConflict()    var xx = $.noConflict();

# 案例todo 本地存储 

![image-20230226144354269](https://wh22wxy-1314518111.cos.ap-chongqing.myqcloud.com/202302261444417.png)