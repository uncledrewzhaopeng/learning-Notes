#### JavaScript

##### 定义

```html
1 简单的定义： 一个前端的可以实现动态效果（丰富的动画以及各种效果） 和 数据交互（后端打交道） 编程语言

2 js 是一种基于对象 的事件驱动型的 客户端 脚本语言

		基于对象：而非面向对象， 具有面向对象的特点
	  事件驱动： 前端很多功能 是要靠用户来产生事件 由事件来触发js执行
		打开灯 （用户）按下灯开关按钮（事情）  ----》 灯亮了
    用户 鼠标移到（或者点击）标题上面去 （事情）====》 菜单出来啦 （下拉菜单）
	 客户端：（app端） 浏览器端web端  
	 脚本语言： 宿主环境 （脚本语言 想要执行起作用 必须有一个依赖的解释执行的环境） js---宿主环境（浏览器）--- nodeJs(这个平台也可以玩js)
		脚本语言 as (flash动画)---宿主环境flash
		
		解释型语言： 脚本语言一般都是解释型语言 特点： 一般代码按照特定顺序 边解释 边执行
		编译型语言： C ... 代码需要事先编译成 系统可执行的代码---一次性执行
	
```

##### js的当初设计目的

>  就是为了解决前端用户注册验证问题  提高用户体验



##### JavaScript现在的意义  

1. 页面特效(PC端的网页效果)

2. 移动端(移动web和app)  app的内容（html+css+js）微信公众号，小程序

3. 异步和服务器交互 （js—-ajax）比如：局部的无刷新请求 天气预报气温 局部商品/新闻

4. 服务端开发(nodejs)   全栈工程师(前端 + nodeJs)

5. Js框架或者插件开发 (Vue.js React.js   框架 插件 )  过年回家—抢火车票—-加速包（插件）—12306抢票插件（js —原理很简单）

   

##### js的历史

```
1 js诞生1995年
2 js的作者 布兰登艾奇
3 js的前期的名字 liveScript 为了营销便利 更名 JavaScript
```

##### js的组成

```
1 ECMAScript (规定了js的核心语法规范)  ---（欧洲计算机工业协会制定的一个脚本）
		我们的js语言 是 这个ECMA语言标准 基础之上的扩展  （ECMA 规范）----js的语言实现
2 DOM： 供js去操作网页页面
3 BOM:  让js去操作浏览器的
```

##### js的书写

```html
<!--1 内嵌式/内部 的js写法 页面当中 写一个script标签 当前学习阶段使用它-->
	<script>
			js代码
	</script> 可以写js
	
<!--2 行内的js脚本  不推荐  不利于后期代码维护和管理-->  
	<div onclick="alert('哈哈哈')">这是一个div</div>

<!-- 3 外部js脚本文件 后期项目当中经常使用-->
<script src="js文件的路径">
	这里不要写js代码
</script>

注意事项：
1 script不是单标签
2 在引入外部js的script标签中 不要写js代码了 会覆盖
3 script 可以在页面任何地方写  一般推荐在</body>的后面
4 一个页面中 可以有多个script标签

属性：
Jscript 微软搞了
language 这个属性已经废弃 
type 规定脚本语言类型 可写可不写 
* src: 需要引入外部文件的src
<script>
	
</script>	
```

##### js的三条输出语句

```
1. console.log(“内容”)	在控制台打印输出内容  后期代码调试用的比较多
2. document.write(“内容”)	在页面书写内容
3. alert(“内容”)	弹窗显示内容  测试 弹出框 用的较多
```

##### js的注释

```
html注释： <!-- html注释 -->
css 注释： /*   css注释  */
	1 单行注释   // 斜杠后面这行代码已经注释了 ctrl + /
	2 多行注释  ctrl+shift+/： 
	/*  
	alert("123");
	console.log("111");
	*/

注释：1  对于复杂的代码逻辑 进行注释解释说明
		 2  对于功能模块的 划分 界限简洁清晰
```

热身小练习：1下拉菜单 2 设置盒子隐藏和显示 — 作业

##### 变量

```javascript
变量： 在内存中 用来存储数据 的 标识符
变量的命名规则（必须遵守 相当于法律）：
	1 可以由 字母 数字 下划线 来构成  但是不能以数字开头
  	abc123  123ab  _aa   box_123
  2 不能使用关键字  和  保留字
  	（关键字 是 当成程序正在使用的字 比如 var 是程序中定义变量的关键字 if else  function for ）
    	保留字 （程序当前没有在使用 但是未来的新版本以后会使用到 程序暂时保留下来了 保留字 class）
      
  3 区分大小写： var A;   var a;
 命名规范：（道德约束）  
 			1 变量名 要有意义  box--->oBox  btn--->oBtn   o---object对象  
			2 驼峰式命名法；第一个单词首字母小写  从第二个单词之后 首字母大写
							
```

作业：设置盒子样式 （布局 +   单击按钮—-盒子.style.width/height/backgroundColor）

##### 变量的理解

````javascript
变量的声明：
1 变量声明未赋值 其值 为  undefined
2 变量可以连续声明 
var userName = "aaa", age=23, job="fe";

交换两个变量练习：
var a = 12;
var b = 15;

// 方式1 
var c = a;
a = b;
b = c;

// 方式2
var sum = a + b;
a = sum - a;
b = sum - b;

// 扩展：
[a,b] = [b,a] // es6中的解构赋值
````

##### 关于+号的作用：

```javascript
作用1: 用来做 数字之间 求和运算
alert(12+13)
作用2: 用来做 字符串之间的 拼接
alert("12" + "13")

var userName = "尼古拉斯赵四";
var age = 40;
var job = "actor";
var text = "大家好，我叫"+ userName +",今年"+ age +"岁了，我的工作是" + job;
alert(text);
```

##### 关于html属性操作 (加的)

```javascript
html的属性操作：
1 读取获取
 	元素.属性名
	oBtn.type  oImg.src ...
2 修改 设置
  元素.属性名
  oBtn.value = "设置的内容"
  oImg.src = "2.jpg"

js中除了 通过.可以读取和设置属性之外  还有一个 []也可以读取和设置属性
1 读取获取
 	元素["属性名"]
	oBtn["type"]  oImg["src"] ...
2 修改 设置
  元素.属性名
  oBtn["value"] = "设置的内容"
  oImg["src"] = "2.jpg"

区别 两者都可以用  .更简单  但是不能后面直接跟变量  
[]比.麻烦一点 但是 []可以放变量来代替
    
练习：文字放大缩小


注意： 我们可以获取 src属性的路径（获取的是绝对路径）
		   也可以获取 一个颜色  （颜色因为有很多种表示方式 浏览器不一样 情况可能不一样 ）
       
       在以后 不要拿 路径 和颜色 做判断 
```

```html
元素.innerHTML inner里面的 HTML (内容)===》 元素里面的内容

oBox.innerHTML 可以获取这个盒子div元素里面的内容
```

> 设置盒子的样式的作业 

##### 操作符

> 算数运算符，逻辑运算符，赋值运算符，比较运算符，运算符优先级

##### 算数运算符

```javascript
几类：  +   -  *  /  %
+：js有两个作用： 1 数字之间的求和 2 字符串之间的拼接

%： %3 （0 1 2 ） 任何一个数字 取余3 其结果只能是在 0  1 2 之间循环

一元运算符 ++ --  前置 后置
前置 （先自增1 或者 自减1 然后参与运算）
后置 （先参与运算  后 自增1 或者 自减1）
var num1 = 5;
++ num1;   //  -> num1 = num1 + 1;
var num2 = 6;
console.log(num1 + ++ num2);
//=====================
var num1 = 5; 
num1 ++; 
var num2 = 6
console.log(num1 + num2 ++);
// ========================
var a = 1; var b = ++a + ++a; console.log(b); 
var a = 1; var b = a++ + ++a; console.log(b); 
var a = 1; var b = a++ + a++; console.log(b); 
var a = 1; var b = ++a + a++; console.log(b); 
Var k = 1
alert( k++ + ++k + k++ + ++k)

```

##### 逻辑运算符

```javascript
三个  && 与  || 或 ！非 取反

&&运行顺序： 先看左边  如果左边本质上为真 则去右边看看 直接返回右边结果
 如果左边本质上为假  则 直接返回左边的结果

 
 || 运行顺序： 先看左边  如果左边为真 则 直接返回左边结果，如果左边为假则去右边 返回右边结果
var a = 3 && 0 || 2; 
var b = 3 || 0 && 2;
var c= 0 || 2 && 3; 
alert(a),alert(b),alert(c);
//=============
var a = 1+1 && 3; 
var b = 0 && 1+1; 
var c = 1 || 2 && 3-1; 
alert(a); 
alert(b); 
alert(c);
```

#####  比较运算符 & 赋值运算符

```javascript
// 比较运算符
>  >=  <  <=  ==  !=   === !==
 '55' == 55; //true 
'55' === 55; //false 值相等，类型不相等 
 55 === 55; //true

// 赋值运算符
= +=  -=  *= /=  %=
```

##### 运算符的优先级

```
优先级从高到底 
() 优先级最高 
一元运算符 ++ -- ! 
算数运算符 先* / % 后 + - 
关系运算符 > >= < <= 
相等运算符 == != === !== 
逻辑运算符 先&& 后|| 
赋值运算符

练习1：
 ((4 >= 6) || ('人' != '阿凡达')) && !(((12 * 2) == 144) && true) 
练习2：// 5.toString() ==> "5"
var num = 10; if (5 == num / 2 && (2 + 2 * num).toString() === '22') { 
console.log(true); 
}
```

#### 判断语句

```
程序 一般由上到下 依次执行  但是有时候 我们需要更改程序执行的特定顺序
分支语句： 判断 

if相关语句：
	if(条件表达式) {
		 如果条件表达式成立 则执行这里的代码
	}
	
	
	if(条件表达式) {
		如果条件成立 则执行这里的代码
	}else {
		否则不成立 则执行这里的代码
	}
	
	if(条件表达式1){
		条件1 成立 则执行这里的代码
	}else if(条件2) {
			条件2 如果成立 则执行这里的代码
	}else if(条件3) {
		条件3成立 则执行这里的代码
	}else {
		如果以上条件都不成立 则执行这里的代码
	}
```

##### 作业安排：

```
1 文字的放大缩小练习
2 属性名和属性值的设置盒子 练习
3 简单留言框
4 把操作符这一块的练习题 做一遍
5 把if语句练习 
		1、是否年满18岁(是否成年) 
		2、判断一个数是偶数还是奇数 
		3、判断一个年份是闰年还是平年
		
京东案例 头部区域 html+css静态页面--下周二 全部交
找个时间--讲解一下 开心网局部排版
```

##### 三元运算

> if..else 一种简化的写法
>
> 条件? 成立执行的语句:不成立的执行的语句;

```
判断年龄是否年满18岁 
if语句---> 三元运算 
判断奇偶数 if---> 三元运算
```

##### 判断选择的语句—switch

```javascript
switch(条件) {
	case 常量1：语句1； break;
	case 常量2: 语句2； break;
	.....
	default: 默认语句
}

// 注意点： 
1.break的作用： 停止终止后面代码执行 停止switch 不加的情况要注意
2 条件 和常量比较的时候 是 === 全等（类型和值都必须相等）
if(){} .... else if(){} ... else if() {} ..else{}

练习： 通关口令 if  switch
练习： 星期几  switch语句  （多分支语句）
```

##### 练习

```html
1 两个图片来回切换 --- 开关（简单逻辑）
2 多图片切换---  大仓库（数组）
```

#####  js获取元素第二种方式   加的  docment.getElementById()

```javascript
document/某个父级.getElementsByTagName(标签名);
获取的是一个html集合（像一个仓库一样 可以通过标号 去取里面的元素）
```





##### 作业安排：

```
1 三元运算  练习：1.年满18岁  2.比较两个值谁最大
2  switch  练习 1 通过口令 2 星期几
3  多个图片切换
4  while  do...while
		
		案例： ​ 
      1、打印100以内7的倍数 ​ 
      2、打印100以内的奇数
      3、打印100以内所有偶数的和
	打印正方形
	打印三角形
	打印 九九乘法表
	
	使用do-while循环：
	选择“你喜欢我吗？(y/n):"，
	如果输入为y则打印”我也是“，
	若输入为n,则继续询问 
```

##### continue和break

```javascript
// break: 停止整个循环 后续不会继续循环了
// continue 跳过这一次循环  继续后续循环（当然要满足条件才循环）

// 练习1 break  求1--100的和  但是遇到个位为3的数 则停止累加
var sum = 0;
for(var i = 1; i <= 100; i++) {
   if(i % 10 == 3) {
     break;
   }
   sum += i
}
// 练习2 break  求1--100的和  但是遇到个位为3的数 则跳过
var sum = 0;
for(var i = 1; i <= 100; i++) {
   if(i % 10 == 3) {
     continue;
   }
   sum += i;
}

注意点： continue 和 break 只能控制一层循环
```

```
for语法：
for(循环变量初始化;循环条件;循环变量更新) {
   循环体
}

练习1: li 隔行变色  document.getElementsByTagName("li"); 通过for 循环 判断奇偶 

练习2: js字符串拼接 元素.innerHTML  10个div    定位 left  top
		一行 放置 10个div  定位
		
		斜着放置 10div
		
		作业 (循环  字符串拼接 找规律)：
			放置100div  一行10个div  一共10排
			放置 v字形 div
性能问题： document.body.innerHTML +="<div>"	 性能非常差 （频繁的写入页面中元素  导致频繁渲染页面 效率低下）
解决方法： 设置一个变量 用变量来循环拼接一堆div（这是在内存中拼接的）  用这个变量 一次性写入到页面中  （相当于做了一次 页面渲染 速度非常快）


*******************加的********************
自定义属性：
		我们可以给标签 添加一个自己定义的属性
		<input type="button"  value="按钮" >
		在js中： inp.abc = '111'  (页面中不会显示 但是js可以用)
		aBtn[k].index = k;
		在function中  通过this.index找到对应的下标
		
选项卡案例---> 
   1 布局html + css样式
   2 思路：
   		 通过循环 给每一个按钮 添加 单击事件  单击之后 让对应的div显示
   		 这里遇到个问题： 单击事件的function里面 i有问题 （总是循环结束后的值）====》 解决方式是：自定义（属性）索引
```



***

#### js 中数据类型

>  js由三部分来构成  ECMAScript   DOM   BOM
>
> ECMAScript是js语法核心规范  var     if(){}else{}    

> 为了便于理解 数据 官方给出一些分类

```js
// 1 数字类型  number: 12  -9  0
// 2 字符串 string   凡是被"", '' 都是字符串  文字内容   oBtn.value "按钮"  div.innerHTML 获取也是字符串 

// 3 布尔类型 boolean： true 真  false 假

// 4 对象类型 object：	
				[]数组 ===》属于对象
        {}对象
// 5 null  空对象
        
// 6 undefined 未定义 （声明一个变量 没有赋值  其值为未定义undefined）
 
        
 // es6语法中 多了 symbol 数据类型 
 上面的这六种数据类型是 js---> ECMAScript 它规定的类型划分
 
 
 ecmascript--->es5(我们目前所学的这个版本) es6  ---es7  es8 
```

```
number 数字类型   string字符串类型  boolean布尔类型 称之为 简单数据类型 （值类型）

object 对象类型  称之为复杂数据类型 （引用类型）

null
undefined 这两种属于特殊类型
```

##### 关于数据类型之间的转换

```
1 转换数字类型方法
	Number()  parseInt()  parseFloat()
	
2 转换字符串类型方法
	toString()  String()
3 转换布尔类型方法
	Boolean()

以上转换方法 称之为 显式类型转换 （我们用户 在直接调用这些方法 进行转换  主动 明着 转）

隐式类型转换 （我们可能察觉不到 会自动帮我转 悄悄）

```

##### 作业安排：

```
作业 (循环  字符串拼接 找规律)：
			1 放置100div  一行10个div  一共10排  截图截图
			2 放置 v字形 div  截图效果
			3 隔行变色的li练习
			
			4 选项卡案例--边参考边理解
			
			
		  5 数据类型练习题：

			var arr = [ '100px', 'abc'-6, [], -98765, 34, -2, 0, '300', , function(){alert(1);}, null, document, [], true, '200px'-30,'23.45元', 5, Number('abc'), function(){ alert(3); }, 'xyz'-90 ]; 


					1、找到arr里所有的数字：-98765, 34, -2, 0, 5 
					2、找到可以转成数字的：'100px', -98765, 34, -2, 0, '300', '23.45元', 5 
					3、把转成数字以后，最大值判断出来：300 
					4、把 NaN 所在的位置找出来：1 14 17 19 
京东项目：
```



#### 函数

##### 函数的概念以及定义方式

```js
// 概念：
函数：把具有特定功能的独立代码块封装起来 形成一个实体（函数），起个名字（函数名）, 函数后期可以反复调用
作用：函数可以封装代码 实现代码复用 让程序变得简洁 高效
// 定义
两种
	1 函数的声明
  function 函数名() {
    
  }
2 函数表达式
var aa = function() {
  
}
```

##### 函数的调用

```js
函数有很多调用方式
1 直接调用  函数名()
2 事件调用  onclick = function(){} onmouseover = function(){}
```

##### 函数的分类

```js
分类方式1 ：
	系统内置函数  alert() parseInt() Number() // function alert() {}
  用户自定义函数 function abc() {}
分类方式2：
	有名函数
  匿名函数 ---匿名函数无法直接调用 可以通过匿名函数自调用来实现
  (function (a){
    alert(a);
  })(24);
函数的立即执行表达式
```

##### 函数的传参

```js
// 函数的参数；
function fun1(a,b,c) {  // a b c 形参：函数在定义的时候写的参数
  // 形参相当于局部的变量
}

fun1("你好", "哈哈", "呵呵"); 实参：函数在调用的时候 写的参数
参数 是 一一对应的 接收的
参数可以写多个 
如果实参 多于 形参 ： 多余的那个实际参数 没用了
如果形参 多于 实参  多余的形参 值 undefined
```

##### 作用域与预解析

```js
作用域： （当前变量/形参或者函数）起作用的区域：
全局作用域  全局函数 全局变量
局部作用域 （函数可以形成局部作用域）局部变量 局部函数

js语言；通过浏览器的js解释器去解释执行的
那么这个解释器有意思：
 第一步预解析：（找找当前作用域下有没有声明的变量（形参） 和 声明的函数）
 					如果同名冲突了 函数级别高于变量  级别一样高 后者覆盖前者
 第二步代码执行：按照顺序执行
 
alert(a);
var a = 1;
alert(a);
function a(){alert(2)}
alert(a)
var a = 3;
alert(a)
function a(){alert(4)}
alert(a)

```

> 作用域链：局部的变量和函数 在使用的时候 如果局部没有声明。它会沿着一个（隐形的链条 向上着 变量和函数）由里向外逐层着 本着就近原则 这样一个查找链条就是作用域链

![作用域链](作用域链.png)

#####  函数内部的三个小东西

> return  this  arguments

```js
return : 返回值
特点：
1 return可以返回任何数据类型
2 return 返回 返回值之后， 后面代码不执行 函数终止
3 return 默认返回undefined
```

```js
this: 这个 代词 当前函数被谁调用 我this就指向谁

1 函数如果直接调用  内部的this指向window对象
2 函数如果被事件调用 内部的this指向 触发该事件的前面的那个元素
```

```js
arguments: 在函数内部 自动存储 当前函数传入的实际参数 它是一个集合

应用场景： 适合参数个数不确定的情况
比如： 求任意个数最大值  
      求任意个数的和
```

> 练习1 ： 封装$函数 用来获取id
>
> 练习2: 计价器 函数传参 封装 ----（）
>
> 练习3: 选项卡 —-进阶—选项卡传参

```js
作业安排： 以上三个练习作业
把作用域预解析这几个题 再做一下
var  a  = 1;
function fn1(){
    alert(a);
    var a = 2;
}
fn1()
alert(a);
//===============
var  a  = 1;
function fn1(){
    alert(a);
    a = 2;
}
fn1()
alert(a);
//============
var  a  = 1;
function fn1(a){
    alert(a);
    a = 2;
}
fn1()
alert(a);
// =================
var  a  = 1;
function fn1(a){
    alert(a);
    a = 2;
}
fn1(a)
alert(a);

```

```
计价器 进阶后面 
数据类型练习题
```

#### 上午回顾

```
递归函数：
定义： 函数调用自身的编程技巧
讲故事===》无限递归---> 需要给一个条件（让某一刻停止递归）否则 会 内存栈溢出
function tellStory() {
	console.log('ddddd...')
	tellStory();
}

递归函数 求阶乘
function jc(n) {
	if(n == 1){
		return 1;
	}
	return n * jc(n-1)
}
var result = jc(12);


```

##### 递归斐波那契数列

```
有个人想知道，一年之内一对兔子能繁殖多少对？于是就筑了一道围墙把一对兔子关在里面。已知一对兔子每个月可以生一对小兔子，而一对兔子从出生后第3个月起每月生一对小兔子。假如一年内没有发生死亡现象，那么，一对兔子一年内（12个月）能繁殖成多少对？
斐波那契数列 1  1  2  3   5   8  13  21  34  55   递归函数 

function Feibo(n) {
	if(n <= 2) {
		 return 1;
	}
	return Feibo(n-1) + Feibo(n-2)
}
var result = Feibo(12)

```

##### 数组

```
数组：存储多条数据  数据类型  大仓库 
[[1,2],["hello","hehe"]]
定义： 1 数组的简单声明方式  / 字面量声明方式
		var arr1 = []
		   2 数组的标准声明方式 /构造函数声明方式
		var arr2 = new Array(4,6,8)==> [4,6,8]
		new Array(6)  ==> [,,,,,] undefined
特性：
  1 长度 length  数组的长度 可读可写  
  2 数组 可以通过下标 去找里面的数据 下标都是从0开始的
  
 
 练习：训练 通过循环 去 遍历数组 --解决问题
 
 数组 方法：
 	 1 四个小宝贝方法
 	 	push()  pop()  unshift()  shift()
 	 2 splice() 删除方法 （删除 添加 修改）
 	 3 slice() 截取数组
```

##### 冒泡排序 (理解大概的原理  手写基本的冒泡排序)

```js
for(var i = 0; i < arr.length - 1; i++) {   // 外层循环控制的比较的轮数
		// var onOff = "假设这一轮拍好了"; 这个开关小逻辑 是为了优化轮数的
		var onOff = true;
    //    这个 arr.length-1-i 是为了优化次数的
		for(var k = 0; k < arr.length-1-i; k++) {  // 1轮   4次  2轮 3次  3轮 2次  4轮 1次
			// 俩俩相邻比较 
			// 如果前一个数 大于 后一个数
			if(arr[k] > arr[k+1]) {
				// 交换位置
				// 设置一个临时变量 用来存 第一个数据
				var temp = arr[k];
				arr[k] = arr[k+1];
				arr[k+1] = temp;
				// onOff = "你的假设是错误 这次没排好呢"
				onOff = false;
			}
		} // 内层循环  控制的每轮比较的次数
		if(onOff == true) {
			// 已经排好了 没必要继续循环了
			break;
		}
}
```

##### 数组 的方法

```python
# 1 push():
定义： 从数组的末尾添加一个或中多个元素
参数： 一个或者 多个元素
返回值：改变后的数组的长度 
愿数组是否发生改变：愿数组改变了

# 2 pop()：
定义： 从数组的末尾删除1个元素
参数： 无
返回值：删除后的那个元素 
原数组是否发生改变：愿数组改变了

# 3 unshift()：
定义： 从数组的开始位置添加1个或者多个元素
参数： 一个或者多个元素
返回值：改变后的数组的长度
原数组是否发生改变：原数组改变了

# 4 shift()：
定义： 从数组的开始位置删除1个元素
参数： 无
返回值：删除后的那个元素
原数组是否发生改变：原数组改变了

//============================
# 5. splice()：
定义：删除方法 （删除 修改 添加）
参数： 
	1 开始删除元素的位置
	2 删除元素的个数    默认删除到最后
	3 需要添加的元素

返回值：删除后的元素 组成的新的数组
原数组是否发生改变：原数组改变了

# 6. slice()：
定义：截取方法
参数： 
	1 开始截取位置  默认为0
	2 结束截取的位置 默认到最后 （不包含结束位置）

返回值：截取后的元素 组成的新数组
原数组是否发生改变：原数组不会发生改变

# 7 concat():
定义： 用来连接数组或者其他元素 合并数组/元素
参数： 数组 或者是 元素
返回值：连接后的新数组 
原数组是否发生改变： 原数组不会发生改变

# 8 indexOf:
定义： 查找数组中的元素 的位置
参数： 
		1 需要找的元素 
		2 开始查找的位置  默认从0的位置开始找
返回值：返回下标位置 
		如果找到了 则返回对应的下标
    如果没找到 则返回-1
原数组是否发生改变： 原数组不会发生改变
# 9 lastIndexOf: 
定义： 从后往前查找数组中的元素 的位置
参数： 
		1 需要找的元素 
		2 开始查找的位置  默认从0的位置开始找
返回值：返回下标位置 
		如果找到了 则返回对应的下标
    如果没找到 则返回-1
原数组是否发生改变： 原数组不会发生改变


# 10.reverse() 
定义：翻转数组
参数：无
返回值 翻转后的数组
愿数组是否发生改变：原数组会发生改变

# 11 sort()
定义： 排序方法 默认排序方式 字符串编码规则
参数 ：
	sort(function (a,b){ return a -b }) 数字 从小到大排序
  sort(function (a,b){ return b-a }) 数字 从小到大排序
  扩展：随机打乱数组
  sort(function(){return Math.random() - 0.5}); 
  
返回值 排序后的数组
原数组是否发生改变：原数组会发生改变

#  12 join方法：
定义： 可以将 数组 转换为字符串 通过一个连接符
参数： 连接符
返回值：字符串
原数组：不会发生改变

```

##### 字符串方法

```js
// 1 charAt(): 在字符串中 通过下标 找对应的字符

// 2 charCodeAt() ： 在字符串中 通过下标 找对应字符的字符编码

// 3 String.fromCharCode():根据字符编码 返回对应的字符

练习： 加密 解密练习

// indexOf()

// lastIndexOf()

// substring()

// slice()

// toUpperCase()
// toLowerCase()

// split()

数学对象
日期对象
倒计时

循环 while do..while  for 两层嵌套 乘法表 函数 break continue

函数封装 包一个壳 计价器  最贵单价
	概念 定义 调用  传参  作用域与预解析  全局变量/局部变量  作用域链 
  return   this   arguments
```

##### 小题

```
1  生成13位条形码(6K)
Ean-13码规则：第十三位数字是前十二位数字经过计算得到的校验码。
例如：690123456789
第十三位计算其校验码的过程为：
@前十二位的奇数位和6+0+2+4+6+8=26
@前十二位的偶数位和9+1+3+5+7+9=34
@将奇数和与偶数和的三倍相加26+34*3=128
@取结果的个位数：128的个位数为8
@用10减去这个个位数10-8=2
所以校验码为2（注：如果取结果的个位数为0，那么校验码不是（10-0=10），而是0）
实现方法ean13（）计算验证码，输入12位条码，返回带验证码的条码。
例如：输入：692223361219输出：6922233612192

function ean13(num){
 
}
ean13(692223361219);
2  递归 阶乘练习
3  冒泡排序写两遍
4   复习今天学习的方法 数组方法/字符串方法

5 昨天的知识点（函数） 循环
	计价器
	扩展：

Math对象
倒计时
计价器
剩余作业
```

####  字符串的方法

```
str.indexOf():在字符串中，找对应的字符的下标 从前往后找
参数1:需要找的字符  参数2：开始查找的位置
lastIndexOf：从后往前找  
参数1:需要找的字符  参数2：开始查找的位置

返回值：如果找到 返回对应的下标  找不到 则返回-1
```

```js
// 截取方法
substring(): 截取字符串  
参数1: 开始截取的位置  参数2 结束截取的位置（不包含结束位置）
返回值 截取后的字符串
slice()
截取字符串  
参数1: 开始截取的位置  参数2 结束截取的位置（不包含结束位置）
返回值 截取后的字符串

区别： 1 substring 支持颠倒顺序 slice不支持
      2 substring 不支持负数 会当0来处理  slice支持负数
```

> 判断邮箱类型

```js
大小写转换方法
str.toUpperCase()
str.toLowerCase()
```

```js
split 将字符串 通过分割符 转换为数组
参数 分割符 "-" "a"
返回值是数组
```

> “abcdfg" ==> "gfedcba"



##### 日期和时间对象

```js
// 1 获取日期时间对象  
var mydate = new Date(); //mydate 日期时间对象
var year = mydate.getFullYear();
var month = mydate.getMonth() + 1; 
var date = mydate.getDate();
var week = mydate.getDay();
var hour = mydate.getHours();
var min = mydate.getMinutes();
var sec = mydate.getSeconds();
var ms = mydate.getMilliseconds();

获取日期时间 页面中显示
==》 图片时间 （图片img  for循环  获取日期时间 字符串拼接  补零函数）
```

##### Math数学对象

```js
// Math js内置的一个对象 它有很多方法 提供给我们使用 提高开发效率
Math.PI  数学常量
Math.round() 四舍五入
Math.floor() 向下取整
Math.ceil() 向上取整
Math.pow(x,y) 求x的y次方
Math.abs() 取绝对值
Math.max() 求最大值
Math.min() 求最小值
Math.sin() Math.cos() Math.tan() 三角函数 ...
Math.sqrt() 开平方 
Math.random() 随机数

公式： x--y 随机整数  Math.round(Math.random()*(y-x)) + x;

```

#####  验证码

```js
// 求四位随机数字 （可以重复）
//  方法1
var str = "";	
	// 产生 0--9 之间随机整数
for(var i = 0; i < 4; i++) {
  str += Math.round(Math.random()*9)
}	
// 方法2 
var num = Math.round(Math.random()*9999)
var result = zero(num); // 0--9999随机整数 45 7 3994  0004  0067 0238

// 方法3
var arr = [1,2,3,4,5,6,7,8,9,0];
var str = "";
//这是 第三种方法  可以数组重复的
	for(var i = 0; i < 4; i++) {
		arr.sort(function () {
		return Math.random() - 0.5;
		})

		str += arr[0];
	}
// str 是最后结果

// 不重复
arr.sort(function () {
	return Math.random() - 0.5;
})
// 截取数组中的前四位  通过join 方法  使用 空字符串连接 转成字符串
var result = arr.slice(0,4).join("")
//=======================
Math.random().toString().substring(2,6)   //  0.42341216389 

扩展一下：四位数字随机 不重复（递归函数也可以去做）

留的题：
    字母 + 数字  随机四位 验证码 （可以重复）
```

##### 作业（今晚+ 自习）

```js
1 判断邮箱类型练习
2 图片时间
3 倒计时练习
4 字母 + 数字  随机四位 验证码 （可以重复）
5 计价器补充完成
6 综合小案例
7 展开收缩案例
8 字符串今天方法复习一下
```



##### js对象

```js
// js对象定义：
// 1 {}
	var obj1 = {
    // 键名:键值   键名唯一
    age:24,
    name:"尼古拉斯赵四",
    job:"舞者"
  }
// 2 new Object
  var obj2 = new Object(); // obj是一个对象
  // js对象.键= 你给设置的键值
  obj2.name = "克里斯蒂安刘能";
  obj2.age = 45;
  obj2.job = "二人转演员"
```

> 注意：
>
> 1. j s对象中 键名唯一  
>
> 2.  里面键值对是无序的
>
> 3. 读取键值：对象名称.键名 ==> 键值 
>
> 4. 设置键值  对象名.键名= 键值
>
> 5. []可以代替点 对象名["键名"] 
>
>    obj2.name = "克里斯蒂安刘能";
>
>    obj2["name"] = "克里斯蒂安刘能";



##### 上午回顾

> 1 展开收缩案例 2 验证码案例（字母+数字 可以重复的）

##### js对象

```
js 一种数据类型
定义：
1 简单声明方式 字面量声明方式  {}
2 标准声明方式 构造函数声明方式  new Object()  

内部 键值对 进行内容存储
键名唯一
var obj1 = {
key:value
name:"张三",
age : 24
}

var obj2 = new Object()
obj2.name = "李四";
obj2["age"] = 26

我们可以通过这个方式 去描述表示一个对象 
程序 对象： 属性和方法去描述对象的特征和行为


批量创建对象  封装函数---工厂函数
function createStudent(name,age){
	  var stu = {};
	  stu.name = name;
	  stu.age = age;
	  stu.studying = function(){
	  
	  };
	  stu.playing = function() {
	  
	  }
	  return stu
}

只有对象  才可以 挂载 属性和方法

优雅：构造函数(专门用来创建/构造 一个对象)

function CreateStudent(){
	 this.name = "李四";
	 this.age = 44;
	 this.studying = function(){
	 	   console.log("正在学习..")
	 }
}
var stu1 = new CreateStudent()
console.log(stu1.name)
```

##### json

```
json:javascript object notation js对象标记法  数据格式
严格意义上： 键名用双引号引起来
json:一个轻量级的前后端数据交互格式 （重量级 data.xml  data.json）
前端 ： js对象  --json （json字符串 --> js对象）

{
"a":3,
"b":"hehe"
}
```

##### js对象的遍历方式

```
for ... in 循环语句 遍历我们的对象
for(var k in 对象){
		k:对象中的每一个键名
		对象[k] : 对象中的每一个键值
}
对象：无序属性（方法）的集合
数组属于特殊的对象：因为它的键名是下标（有序的 0  1 2 ...）
数组：for循环   for in去循环
普通对象 ：只能用for in循环  无法用for循环
```



```js
js介绍
ECMAScript
DOM:
BOM
js 变量
js 操作符
js 判断语句
js 循环 
js 函数 
js 数据类型 类型转换
js 数组 
js 字符串 10
js 日期时间对象/Math对象
js js对象 /  构造函数--面向对象基础
js DOM操作  document.getElementById()  练习
document.getElementsByTagName();//集合
js 操作 html属性
js 自定义属性---> 选项卡案例

DOM: 文档树模型 节点  节点类型
childNodes children
firstChild  firstElementChild
======
function first(ele) {  // 标准浏览器  IE6 7 8
	 	 var firstEle = ele.firstElementChild || ele.firstChild;
	 	 // 父级元素中没有元素节点  此时 谷歌 走后面 直接获取的空白文本 
	 	 // 父级元素中如果没有任何节点 此时 firstEle 空  
	 	 if(firstEle && firstEle.nodeType == 1) {
	 	 	return firstEle;
	 	 }else {
	 	 	return null;
	 	 }
	 }
------
lastChild  lastElementChild
previousSibling  previousElementSibling
nextSiblings    nextElementSibling


```

##### 值类型与引用类型

![值类型与引用类型](值类型与引用类型.png)



##### 获取元素的$函数

```js
function $(selector，parent) {
  parent = parent || document;
  if(selector.charAt(0) === "#") {
    return document.getElementById(selector.slice(1))
  }else {
    return parent.getElementsByTagName(selector);
  }
}
```

##### 获取样式的兼容性函数

```
function getStyle(ele,attr) {
   if(ele.currentStyle) {
       return ele.currentStyle[attr]
   }else {
   		 return getComputedStyle[attr]
   }
}
```

#####  作业：

```
1 利用构造函数去创建对象 --- 小狗对象 特征 行为  3个小狗

2 理解一下 值类型与引用类型 --课堂对应的练习 看图

3 封装一个$函数

4 封装获取样式的函数 getStyle

5 封装first(), last()   prev()/next() 测试一下
```

##### DOM

> dom:document  object model 文档对象模型

```
document 看成一个对象， 在这个大的文档对象下 有很多内容（文本 标签 注释 属性 。。。）这些内容都可以看成文档中的一个个的节点，节点时有类型，节点之间时有关系，我们可以从整体把这个一样节点构成的结构 称之为
DOM树结构，通过研究里面的节点和节点之间关系，了解一些DOM操作方法，能够更加高效的开发

<ul>
		<li></li>
		<li></li>
		<li></li>
		<li></li>
	</ul>
	
	父子关系，兄弟关系...
	
	# aa元素中的直接孩子们 
	aa.childNodes 兼容性问题 （标准浏览器下 包含所有的子节点 元素 文本 空白文本  注释..）  IE 6 7 8 只能识别元素 
	aa.children： 没有兼容性问题 在所有浏览器下 都只获取元素节点 （推荐）
	
	
	firstChild 第一个子节点：
  		标准浏览器下：第一子节点（空白 元素 注释。。）
  		IE 6 7 8 : 只识别元素节点
	firstElementChild：
			标准浏览器下： 只获取元素节点
			IE 6 7 8 不识别
			
	封装一个函数 实现各个浏览器的兼容
	
	function first(ele) {
		  var firstEle = ele.firstElementChild || ele.firstChild;
		  // 只有一个空白文本节点 nodeType ==1
		  // firstEle 不能为空 假的
		  if(firstEle && firstEle.nodeType == 1){
		  	return fisrtEle;
		  }else {
		  	return null;
		  }
      
		  
	}
	var result = first(ul);
	if(result) {
		 继续后续操作
	}
```

##### DOM：

js如何操作文档中的元素/文本/属性 

```
DOM:概念
DOM 节点  以及 节点类型

childNodes children

firstChild  firstElementChild
lastChild  lastElementChild

previousSibling  previousElementSibling
nextSibling   nextElementSibling

parentNode 父节点 没有兼容性问题

封装了四个 小方法 （处理了兼容性 节点方法）

封装获取类名的方法 getClassName   ===>  $函数

三个属性方法
getAttribute()
setAttribute()
removeAttribute()

封装 逻辑思维 / 函数封装传参
```

1658261070@qq.com

```
创建DOM元素
createElement(标签名)  创建一个节点   
createTextNode(文本内容)
appendChild(节点)  追加一个节点

插入元素
insertBefore(节点, 原有节点)  在已有元素前插入
```



```
DOM元素创建 插入  删除 练习  留言
1、留言---> 倒序留言---> 单击删除留言


2  选项卡案例
// 获取：getAttribute(名称)
// 设置：setAttribute(名称, 值)
// 删除：removeAttribute(名称)

3 封装一个$个函数 (加入 getClassName) --->myTool.js

4 创建表格案例

扩展：祝愿墙
```



#### DOM

***

#####  DOM

```
documnet  object model 文档对象模型
document 文档
object 把我们的文档看成一个对象  文档下 有很多 内容 （这些内容 注释 文本 标签（元素）统称为节点）
抽象成 dom树状结构   

节点和节点之间就有关系  父子关系  兄弟关系  祖先级 关系 ...
通过这些关系 来快速的操作页面中的元素（dom元素）提高我们开发效率
```

##### 节点类型

```
元素节点  nodeType  1
属性节点            2
文本节点            3
注释节点            8
文档节点document    9
文本类型声明<!docType html> 10
```

##### 子节点们

```
childNodes:获取某个元素下的 直接子节点 （不包含孙级节点）    
		在标准浏览器下（谷歌火狐safari..IE9）：可以识别空白文本节点 注释  元素类型节点  （不太好）
		IE6 7 8: 只识别元素
children：获取某个元素下的 直接子节点 （不包含孙级节点）  不是w3c官方标准属性 但是 却被各大浏览器厂商识别 没有兼容性问题  （推荐使用）
		在标准浏览器下   IE6 7 8   都识别为 元素节点
```

##### 第一个孩子 /最后一个孩子

```js
firstChild: 获取第一个子节点    
		在标准浏览器下（谷歌火狐safari..IE9）：可以识别空白文本节点 注释  元素类型节点  （不太好）
		IE6 7 8: 只识别元素
firstElementChild：这个是针对标准浏览器下：只识别第一个元素类型的子节点 但是IE6 7 8不识别

封装了一个兼容性函数
function first(ele) {
		var firstEle = ele.fisrtElementChild || ele.firstChild;
		// 处理两个特殊情况 1 只有空白文本  2 没有任何节点 null
		if(firstEle && firstEle.nodeType == 1) {
				return firstEle;
		}else {
				return false;
		}
}
if( first(ul) ) {
		first(ul).style.backgroundColor = 'red';
}

last:获取最后一个子节点 
		在标准浏览器下（谷歌火狐safari..IE9）：可以识别空白文本节点 注释  元素类型节点  （不太好）
		IE6 7 8: 只识别元素
lastElementChild：这个是针对标准浏览器下：只识别第一个元素类型的子节点 但是IE6 7 8不识别

封装了一个兼容性函数
function last(ele) {
		var lastEle = ele.lastElementChild || ele.lastChild;
		// 处理两个特殊情况 1 只有空白文本  2 没有任何节点 null
		if(lastEle && lastEle.nodeType == 1) {
				return lastEle;
		}else {
				return false;
		}
}
if( last(ul) ) {
		last(ul).style.backgroundColor = 'red';
}
```

##### 前一个兄弟节点/后一个兄弟节点

```
previousSibling: 获取前一个兄弟节点
		标准浏览器下：可以识别 文本节点  注释  元素节点 （有可能获取错 不太好）
		IE6 7 8  只识别元素节点

previousElementSibling：获取前一个兄弟节点 标准浏览器中的属性 
	IE 6 7 8 不识别
// 用来获取前一个兄弟节点的函数 （处理了兼容性）
function  prev(ele){
		var prevEle = ele.previousElementSibling || ele.previousSibling
		if(prevEle && prevEle.nodeType == 1) {
			return prevEle;
		}else {
			return null
		}
}

if( prev(li) ) {
    prev(li).style.backgroundColor = 'green'
}




nextSibling:获取后一个兄弟节点
		标准浏览器下：可以识别 文本节点  注释  元素节点 （有可能获取错 不太好）
		IE6 7 8  只识别元素节点

nextElementSibling：获取前一个兄弟节点 标准浏览器中的属性 
	IE 6 7 8 不识别
// 用来获取前一个兄弟节点的函数 （处理了兼容性）
function  next(ele){
		var nextEle = ele.nextElementSibling || ele.nextSibling
		if(nextEle && nextEle.nodeType == 1) {
			return nextEle;
		}else {
			return null
		}
}

if( next(li) ) {
    next(li).style.backgroundColor = 'green'
}
```

##### 父节点

```
parentNode 某个元素父节点 没有兼容性问题
练习： 点击a链接 移除 当前的li
```

##### DOM中属性操作方法

```
DOM:提供的三个方法 去获取/设置属性
获取：getAttribute(名称)
设置：setAttribute(名称, 值)
删除：removeAttribute(名称)

js中前面学过的简单的获取/设置属性方式   . / []    推荐
```

##### DOM创建/插入/替换/删除/克隆节点操作

```js
js学过  

添加元素方式1： innerHTML 
div.innerHTML = "<div>文字</div>"  
优点：适合大量的字符串拼接  可以不覆盖原内容
缺点：频繁写入页面中 性能较差
			有个解决方法（用变量先拼接 后续再一次性赋给 innerHTML）
添加页面中元素的方式2：
document.write()
写法 简单  缺点：容易覆盖原内容（事件调用中）不能放入某个元素中内容

第三种创建元素方式：
var oDiv = createElement('div') 创建一个元素节点

A.appendChild(B) 把B节点放入A的里面的最后    练习：留言框

A.insertBefore(B,C)  在A中 把B放在C的前面  练习： 倒序留言框
```

```js
A.removeChild(B) 在A中把 B子节点给删除
		B.remove()  把B本身直接删除
    
A.replaceChild(B,C)在A中  用B去替换C节点

A.cloneNode()  把A复制一份 参数可以加个true 是深度克隆（会把里面的子孩子全部复制过来）
```

##### 封装了获取className函数

> document.getElementsByClassName() IE 6 7 8不支持这个方法
>
> 于是我们封装一个函数（处理兼容性问题） 锻炼我们的逻辑思维

```js
function getClassName(yourClass) {
	// 获取所有的标签元素
	var allEles = document.getElementsByTagName('*');
  // 建立一个数组 用来存 带有aa类的所有标签元素
  var arrEles = [];
  // 循环所有的标签
  for(var i = 0; i< allEles.length; i++) {
    // 每一个标签身上的类 字符串 通过空格分割 转换为数组
    var arrClassName = allEles[i].className.split(" ");  //字符串  ""   "cc aa box"  "aa"  "abc"
    // ["aa","cc","box"] [""] ["abc"] ["aa"]
    // 循环数组中的每一个类
    for(var j = 0; j<arrClassName.length; j++) {
      // 看看有没有我要找的类
       if(arrClassName[j] == yourClass) {
            arrEles.push(allEles[i]);
            // 当前标签没必要往后看了
         		break;
         }
    }
  }
  return arrEles;
}

getClassName('aa')
```



##### BOM

> browser object  model 浏览器对象模型
>
> 提供了一些j s如何操作浏览器的一些属性和方法

```
window顶级对象  
	document 文档对象
	navigator
	location
	history
	screen
	...
	
for(var k in window) {
查看它身上的属性和方法   每个浏览器略有差异
}

var newWindow = open(参数1：url地址, 参数2:打开方式)
这个方法 会返回 新窗口的window对象

close() 关闭窗口

window.navigator.userAgent 用户代理信息：浏览器的详细信息
判断是什么浏览器或者其他程序 访问网站  系统信息（可能不准确）
window系统： cmd---> systeminfo  BIOS：basic input output system

封装一个函数 判断浏览器是什么
```

```
window.location 地址栏操作

window.location.href 完整的url地址
location.hostname: 主机名
protocol：协议 
port：端口 80 443 
pathname 路径
search  用来获取?后面 参数信息
hash   #后面的内容
reload() 重新载入页面 可以加个true 强制刷新

练习:获取查询字符串search 转成 js对象的函数
```

```
history: 历史记录
	back() 往回后退一个记录
	forward() 往前前进一个记录
	go() 指定数量  go(2) go(-1)

小练习	
	
screen 屏幕对象
   screen.height/width
```

```
window下面的三个事件
load加载事件 当浏览器程序全部加载完毕的时候 会触发该事件
window.onload = functon(){}
resize事件 当窗口调整大小的时候 会触发该事件
window.onresize = function(){}
scoll滚动事件 当滚动条滚动的时候触发该事件
window.onscroll = function() {}
```



##### 作业安排

```
1 盒子/网页背景图片自动切换 写
2 选项卡自动切换  写
3 网页广告弹框  写
     4 把今天课件过一遍
5 上移下移案例 写
6 一堆尺寸记一下     13.dom尺寸.html
     7 把MyTool.js 看一遍 
8 navigator 浏览器判断小函数 写
9 location queryString函数看一下  写
```

##### 匀速运动函数

```js
第一步：先实现 一个盒子 向右运动
        var current = parseInt(getStyle(oBox, 'left'));
        // 开启一个循环定时器 
        timer = setInterval(function() {
            // 每次 速率10
            current += 13;
            if (current >= 800) {
                current = 800;
            }
            // 赋值给left 产生效果
            oBox.style.left = current + 'px';
            // 当这个物体 到达目标了 则清除定时器
            if (current == 800) {
                clearInterval(timer);
            }
        }, 30);
```

```js
第二步：向左走 实现以后 合并成一个函数
    function move(rate, target) {
        // 获取当初的left位置
        var current = parseInt(getStyle(oBox, 'left'));
        //清除一下页面中原有的定时器
        clearInterval(timer); // null
        // 开启一个循环定时器 
        timer = setInterval(function() {
            current += rate;
            if (current >= target && rate > 0) {
                current = target;
            }
            if (current <= target && rate < 0) {
                current = target;
            }
            // 赋值给left 产生效果
            oBox.style.left = current + 'px';
            if (current == target) {
                clearInterval(timer);
            }
        }, 30);

    }
```

```js
第三步 : 上下走==方向  内部判断合并 速率正负值的考虑  谁运动物体
function move(ele,rate, target,dir) {
        // 获取当初的left位置
        var current = parseInt(getStyle(ele, dir));
  			rate = current < target? rate: -rate;
        //清除一下页面中原有的定时器
        clearInterval(timer); // null
        // 开启一个循环定时器 
        timer = setInterval(function() {
            current += rate;
            if (current >= target && rate > 0 || current <= target && rate < 0) {
                current = target;
            }
            // 赋值给left 产生效果
            ele.style[dir]= current + 'px';
            if (current == target) {
                clearInterval(timer);
            }
        }, 30);

    }
```

```js
第四步 尝试把函数放到外部文件中  考虑 var timer = null 问题 
思路：不写变量 把定时器 存到 当前运动物体的自定义属性timer身上 相当于给当前运动对象的属性身上挂载定时器
回调问题：加入一个回调函数 传入到函数内部 实现后续的运动操作 callback
function move(ele,rate, target,dir,callback) {
        // 获取当初的left位置
        var current = parseInt(getStyle(ele, dir));
  			rate = current < target? rate: -rate;
        //清除一下页面中原有的定时器
        clearInterval(ele.timer); // null
        // 开启一个循环定时器 
        ele.timer = setInterval(function() {
            current += rate;
            if (current >= target && rate > 0 || current <= target && rate < 0) {
                current = target;
            }
            // 赋值给left 产生效果
            ele.style[dir]= current + 'px';
            if (current == target) {
                clearInterval(ele.timer);
              // 这里说明当前物体运动完啦
              if(typeof callback == 'function'){
                  callback()
                } 
             
            }
        }, 30);

}
//软件开发原则：对修改关闭 对扩展开放
```

##### 作业：运动函数 和轮播图

扩展作业 ： 上下滑动图  / 下落苹果/小方块   （运动函数）

祝愿墙  

抖动函数， ----综合小案例--小游戏

```
1 静态布局 html +css
  给一个主体的大盒子div作为白色窗口  里面的表情用div（背景是qq表情）
  
  
```

##### 事件

***

##### 焦点事件

```
网页页面中 一些可以参与用户交互的元素 可以获取焦点
比如： a标签  input表单标签  input按钮  textarea 文本域...
页面中我们的鼠标 同一时刻 只有一个焦点

让一个可以参与用户交互的元素获取焦点的方式 有三种
1 鼠标直接点击
2 键盘的Tab  
3 js获取焦点
	
关于焦点的两个方法：
	A.focus() 让A 获取焦点 
	A.blur() 让A失去焦点
 练习：百度框自动获取焦点
 
 关于焦点的两个事件
 // 当A获取焦点的时候 触发一个事件处理函数
 A.onfocus = function(){}
 // 当A 失去焦点的时候 触发一个事件处理函数
 A.onblur = function(){}
 
 练习：输入框提示文字
```

##### event事件对象

> 当一个事件发生的时候  js会把关于当前发生的这个事件的详细信息 存储在某个地方 ---- 事件对象（飞机黑匣子）

```
在哪儿获取：浏览器不一样获取方式不一样
第一种方式： 直接从全局window对象下 找event属性 window.event
第二种方式： 默认从事件处理函数的第一个参数传入 
谷歌浏览器：两种方式都可以
火狐： 旧版 （支持第二种）更新后的火狐 都支持
IE 浏览器 9以及以上 都支持
IE678 只支持第一种

为了考虑不同的浏览器的情况 ----兼容性处理
A.onclick = function(e){
	e = e || event;
	e:已经处理好了
}
```

##### 盒子跟着鼠标走

```
从事件对象当中 获取鼠标坐标
然后 让盒子的位置left top 跟着变化（在mousemove）
```

##### 下拉菜单

```
事件冒泡：
	当一个事件发生的时候 会从该元素起步 逐渐向上传递 传递给父级们 直到 window 顶层对象为止
 这样一个事件传递过程 事件冒泡   事件冒泡当事件发生时 就会默认执行 （每一个父级元素都会收到冒泡事件）
 
 阻止事件冒泡：
 在需要阻止向上冒泡的事件处理函数中 通过事件对象获取cancelBubble (默认为false)
 e.cancelBubble = true;
```

> **事件冒泡本身是一种机制 没有好坏之分，如果不需要冒泡 可以阻止，有时候我们也可以利用这种冒泡机制来实现一些效果**

##### 事件委托（代理）---原理（利用事件冒泡机制）

```
删除留言案例：
		给父级ul 添加单击事件  在里面通过事件对象寻找事件源 然后去删除每一条留言
		
	事件委托应用场景：内部子元素会动态变化，适合将子元素身上的事件委托给父级元素代理执行 （性能更好一些）	
```

##### 事件绑定方式

```js
传统绑定方式
onclick = function(){} onmouseover =function(){}
缺点： 同一个元素 同一个事件 绑定不同的事件处理函数 后者会覆盖前者

新的绑定方式
标准浏览器下支持的
addEventListener  添加事件侦听器 
元素.addEventListener(事件名称, 事件处理函数，是否捕获)
    // 参数1: 事件名称  
    // 参数2: 事件处理函数
    // 参数3: 是否捕获 
    
attachEvent() 这个方法是IE浏览器都支持
    // 元素.attachEvent('on'+事件名称,事件处理函数)
    // 参数1: 'on'+事件名称
    // 参数2: 事件处理函数
    
 封装一个兼容性函数
 function bind(obj,evName,evFn) {
 		if(obj.addEventListener){
      obj.addEventListener(evName,evFn);
    }else if(obj.attachEvent){
             obj.attachEvent("on"+evName,evFn)
    }else {
      	obj['on'+evName] = evFn;
    }
 }
```

##### 作业

```
练习：输入框提示文字
下拉菜单 阻止事件冒泡
删除留言案例 --利用事件冒泡--事件委托
事件绑定函数的封装 与 解绑函数的封装 （了解初步掌握 ）
div斜着走
提交留言
```



***

##### 表单事件

```
onchange事件： 当元素的值发生的时候 会触发该事件（必须焦点离开的时候的触发，必须是值发生变化才会触发）
	比如：下拉选择菜单 去选择某个项  立马会触发该事件

oninput：输入事件：随着你的输入 一直持续触发： 搜索关键词/查询内容
<input type="text"  />
```

##### 默认事件

> 当触发某个事件的时候，浏览器会自动完成某种行为
>
> 比如：a链接  滚动条按空格 默认会滚动一屏  图片拖拽默认会打开图片  右击--菜单 ...

**练习：自定义右键菜单**

> oncontextmenu    return false 普通的写法：e.preventDefault()

##### 拖拽

> 任务：div拖拽/图片拖拽   扩展（完整的多图片拖拽/碰撞检测交换位置）

```js
// 1 div拖拽
// 三个事件 + 原理
oBox.onmousedown = function(e) {
        // 做一个事件对象兼容性处理
        e = e || event;
        // 求出相对位置 = 当前鼠标x坐标  - 当前盒子的左侧偏移量
        var disX = e.clientX - oBox.offsetLeft;
        var disY = e.clientY - oBox.offsetTop;
				
				 // e.preventDefault();
        // 2.2 鼠标移动
        document.onmousemove = function(e) {
                e = e || event;
                // 盒子应该随着鼠标走
                // 盒子的left = 当前的鼠标的x坐标 - x固定距离 
                // 盒子的top = 当前的鼠标的y坐标 - y固定距离 
                oBox.style.left = e.clientX - disX + 'px';
                oBox.style.top = e.clientY - disY + 'px';
            }
            // 2.3 鼠标抬起 取消移动
        document.onmouseup = function() {
            document.onmousemove = null;
        }
    }
```

```
//2 图片 拖拽 加入一个 e.preventDefault() 阻止默认行为（在鼠标按下）
```

```
//3 封装一个函数 包一下 传一个obj 
// 循环中 调用函数 实现 多个div/多个图片 拖拽
```

```
//4 扩展： 封装碰撞检测函数
// 5 测试 在onmousemove 找两个图片 检测是否正确
// 6 循环页面上的每一个图片 然后让当前的拖拽物体 去和别的每一个图片去碰撞检测一下 用数组去存一下
// 7 在数组中 循环每一个图片 找当前和我拖拽物体的距离（斜边）求出最短值
拿到最短距离的碰撞图片
// 8 抬起鼠标 要进行判断 是否有碰撞上的最短距离图片newObj
  如果有 交换位置  如果没有 则自己回到原位置
  其中加了过渡属性 让交换位置产生时间过渡
  
 注意细节：在按下的一些初始化设置  transition重置 z-index重置
```

##### 闭包

```
闭包: 在一个函数内部 定义一个函数,内部这个函数可以引用外部函数的变量或者参数 , 使 该变量或者参数能够常驻内存,避免被垃圾回收机制所回收, 那么当前的内部函数(以及外部引用的变量或者参数)的整体 可以称之为闭包环境	
```

```
作用: 	
1 将函数和变量 私有化 代码功能开发 模块化  避免被全局污染,			 
2 可以解决建立索引的问题

银行取款练习
选项卡的闭包实现
```

##### 面试题

```js
var name1 = 'hehe';				
var obj = {			
	name1 : 'the object',			
	getNameFunc: function(){								
		console.log(this);				
		var that = this;				
		return function(){										
			return that.name1;				
		}							
	}					
}		
console.log( obj.getNameFunc()() );
```

