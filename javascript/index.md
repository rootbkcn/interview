# 目录

<a href="#js-1">★★ 介绍一下JS的内置类型有哪些？</a>

<a href="#js-2">★★★★ 介绍一下 typeof 区分类型的原理</a>

<a href="#js-3">★★★ 介绍一下类型转换</a>

<a href="#js-4">★★★★ 说说你对 JavaScript 的作用域的理解。什么是作用域链？</a>

<a href="#js-5">★★ 解释下 let 和 const 的块级作用域</a>

<a href="#js-6">★★★★ 说说你对执行上下文的理解 </a>

<a href="#js-7">★★★ 对闭包的看法，为什么要用闭包？说一下闭包的原理以及应用场景？闭包的 this 指向问题？</a>

<a href="#js-8">★★★ 简述闭包的问题以及优化 </a>

<a href="#js-9">★★★ 如何确定 this 指向？改变 this 指向的方式有哪些？</a>

<a href="#js-10">★★★ 介绍箭头函数的 this</a>

<a href="#js-11">★★★ 谈一下你对原型链的理解，画一个经典的原型链图示</a>

<a href="#js-12">★★★ ES5/ES6 的继承除写法以外还有什么区别？</a>

<a href="#js-13">★★★★ 你对事件循环有了解吗？说说看！</a>

<a href="#js-14">★★★★ 微任务和宏任务有什么区别？</a>

<a href="#js-15">★★★★★ 浏览器和 Node 事件循环的区别？</a>

<a href="#js-16">★★★ 异步解决方案有哪些？</a>

<a href="#js-17">★★★ async 和 await 、promise的区别 和 这两个的本质</a>

<a href="#js-18">★★★ 简述 aync await 的好处</a>

<a href="#js-19">★★★ 移动端点击事件 300ms 延迟如何去掉？原因是什么？</a>

<a href="#js-20">★★★ Cookie 有哪些属性？其中HttpOnly，Secure，Expire分别有什么作用？

<a href="#js-21">★★★ 用多种方法实现 JavaScript 继承。</a>

<a href="#js-21">★★★★ 如何实现函数的柯里化？比如 add(1)(2)(3)</a>

<a href="#js-22">★★★★ 什么是反柯里化</a>

<a href="#js-23">★★ 将 [1,2] 与 [3,[4]] 合并为 [1,2,3,[4]]</a>

<a href="#js-24">★★ Array.forEach() 与 Array.map() 的区别，Array.slice() 与 Array.splice() 的区别？</a>

<a href="#js-25">★★ 将 1234567 转换为 1,234,567</a>

<a href="#js-26">★★★ bind 的作用是什么？</a>

<a href="#js-27">★★ Promise.resolve(Promise.resolve(1)).then(console.log) 输出？</a>

<a href="#js-28">★★★ var let const的区别</a>

<a href="#js-29">★★★ document load 和 documen ready的区别</a>

<a href="#js-30">★★★ 如何自定义事件？</a>

<a href="#js-31">★★★ 如何用 setTImeout 来实现 setInterval？</a>

<a href="#js-32">★★★ 如何判断 user 对象里有没有 a 这个属性？如果把user对象中所有的属性都输出出来？`(var user = {'a': '19', 'b': '18', 'c': '16'})`</a>

<a href="#js-33">★★ 使用 setTimeout 模拟 setInterval 的功能做一个60秒的倒数计时</a>

<a href="#js-34">★★★ 实现一个函数 add()，运算结果可以满足如下预期结果</a>
```js
add(1)(2) //3
add(1,2,3)(10) //16
add(1)(2)(3,4)(5) //15
```

<a href="#js-35">★★★ 如何避免回调地狱？</a>

<a href="#js-36">★★ 写一个 function，清除字符串前后的空格。（兼容所有的浏览器）</a>

<a href="#js-37">★★ 使用正则表达式验证邮箱格式。</a>

<a href="#js-38">★★★ 简述同步和异步的区别</a>

<a href="#js-39">★★ JavaScript 中 callee 和 caller 的作用</a>

<a href="#js-40">★★ 统计字符串中字母个数或统计最多的字母数。</a>

<a href="#js-41">★★★ jQuery 的事件委托方法 on，live，delegate之间有区别？</a>

<a href="#js-42">★★★ 简述下 Promise 对象</a>

<a href="#js-43">★★★ 数组扁平化，不用 api</a>

<a href="#js-44">★★★ 用 JavaScript 实现观察者模式</a>

<a href="#js-45">★★ 简述一下面象对象的六法则</a>

<a href="#js-46">★★★ 谈谈垃圾回收机制方法以及内存管理</a>

<a href="#js-47">★★★ 开发过程中遇到内存泄漏的问题都有哪些？</a>

<a href="#js-48">★★★ 请编写获取当前窗口地址中查询参数name的值，当前窗口地址为：https://foo.com/?id=1&name=tom</a>

<a href="#js-49">★★★ 已知a，b两个构造函数，现在 let c = new a()，如何在c的存储地址不变的情况下，改变c的继承（c->a 转为 c->b）</a>

<a href="#js-50">★★★ 浏览器有哪些兼容问题，你封装过什么插件</a>

<a href="#js-51">★★★ 如何判断一个对象是否为数组，函数</a>

<a href="#js-52">★★★ 写一个函数，接受可变个数参数，且每个参数均为数字，返回参数的最大值。</a>

<a href="#js-53">★★★ 请写出 ES6 Array.isArray() </a>

<a href="#js-54">★★★ 实现一个函数 clone，可以对 JavaScript 中的5种主要数据类型进行值复制。</a>

<a href="#js-55">★★★ 假如A页面我定义了一个定时器，然后跳到B页面如果让A页面的定时器暂停</a>

<a href="#js-56">★★★ promise的实现原理，如果我现在向服务器发送一个请求，但是我后悔了，不想让服务器返回数据，去实现一个delay </a>

<a href="#js-57">★★★ CommonJS 和 RequireJS 的实现原理</a>

<a href="#js-58">★★★ 面向对象编程与面向过程编程的区别？</a>

<a href="#js-59">★★★ eval 是做什么的？性能怎么样？安全如何？</a>

<a href="#js-60">★★★★★ 函数节流、防抖。scroll resize 使用函数节流实现不要频繁触发事件的需求。</a>

<a href="#js-61">★★★ 数据类型（判断，==和===）堆栈、内存泄漏及垃圾回收机制</a>

<a href="#js-62">★★★★ 了解 ES6 的 Proxy 吗？</a>

<a href="#js-63">★★★★ 深拷贝是什么？项目哪里是用到了深拷贝？</a>

<a href="#js-64">★★★ swiper 插件从后台获取数据没问题，css 代码啥的也没问题，但是图片不动，应该怎么解决？</a>

<a href="#js-65">★★★★ ES6 中，数组监测怎么实现的（代理）</a>

<a href="#js-66">★★ jQuery 优点和缺点</a>

<a href="#js-67">★★★ ES6 class 关键字原理跟 function 什么区别？</a>

<a href="#js-68">★★★ iframe 跨域问题，页面之间怎么传值？</a>

<a href="#js-69">★★★ 简述 commonJS、AMD 和 CMD</a>

<a href="#js-70">★★★ require.js 源码看过吗？怎么做到异步加载的</a>

<a href="#js-71">★★ jQuery，$() 能传什么参数? html 代码怎么解析? 传 function 呢?</a>

<a href="#js-72">★★ AMD 怎么加载文件的?</a>

<a href="#js-73">★★ jQuery 怎么找到事件源元素</a>

<a href="#js-74">★★★★ 模板引擎原理</a>

<a href="#js-75">★★ map 和 foreach 的区别</a>

<a href="#js-76">★★★★ ES6 的新特性</a>

<a href="#js-77">★★ 2018/01/01 转换成 2018年/1月/1日</a>

<a href="#js-78">★★★ 0.1+0.2 等不等于 0.3？自己封装一个让他们相等的方法</a>

<a href="#js-79">★★★ 跨域是什么？有哪些解决跨域的方法和方案？</a>

<a href="#js-80">★★★ 什么是函数式编程？什么的声明式编程？</a>

<a href="#js-81">★★★ super() 是否必须执行？不执行怎么让它不报错？</a>

<a href="#js-82">★★★ eventloop 渲染在哪一步？</a>

<a href="#js-83">★★★★ 图片懒加载怎么实现？</a>

<a href="#js-84">★★ for-in 循环会遍历出原型上的属性吗？怎么避免遍历到原型上的属性</a>

<a href="#js-85">★★★ 简述call、apply、bind，call 和 apply哪个性能更好？</a>

<a href="#js-86">★★ ES6 箭头函数和普通函数有什么差异？</a>

<a href="#js-87">★★★ Promise 避免回调地狱的语法糖--实现链式调用的核心点是什么？</a>

<a href="#js-88">★★★ 进程线程区别是什么？</a>

<a href="#js-89">★★★ 禁止事件冒泡，禁止默认事件</a>

<a href="#js-90">★★ import export commonJS 对比区别</a>

<a href="#js-91">★★ 为什么 JavaScript 是单线程</a>

<a href="#js-92">★★★ 使用箭头函数应该注意什么？</a>

<a href="#js-93">★★★ 你知道 ES6 中的 Generator 和 yiled 吗？在实际开发中使用过吗？</a>

<a href="#js-94">★★★ Cookie、storage 的区别？什么时候使用？</a>

<a href="#js-95">★★★ map、fillter、reduce 各自有什么作用？</a>

<a href="#js-96">★★ JS的基本数据类型判断有什么方法？</a>

<a href="#js-97">★★★ 构造函数、实例对象、原型对象三者的关系是什么？</a>

<a href="#js-98">★★★★★ JS中的常见设计模式以及应用场景？</a>

<a href="#js-99">★★ 介绍下事件代理，主要解决什么问题</a>

<a href="#js-100">★★★★  异步的解决方案有哪些？</a>

<a href="#js-101">★★ new 的原理是什么？通过 new 的方式创建对象和通过字面量创建有什么区别？</a>

<a href="#js-102">★★ 数组去重的方法</a>

<a href="#js-103">★★★★ 常见内存泄漏</a>

<a href="#js-104">★★★ promise 常见方法和 all 和 race的应用场景 </a>

<a href="#js-105">★★★ 介绍一下 ES6 中 Set, Map的区别？</a>

<a href="#js-106">★★ 并行和并发的区别是什么？</a>

<a href="#js-107">★★★ 为什么操作 dom 慢？</a>

<a href="#js-108">★★★★ 插入几万个 dom ，如何实现页面不卡顿？</a>

<a href="#js-109">★★★ js中的常用事件绑定方法</a>

<a href="#js-110">★ 简述 src 和 href 的区别？</a>

<a href="#js-111">★★★★ 你知道什么是原型吗？我们为什么要用原型呢？或者说原型为我们提供了什么？</a>

<a href="#js-112">★★★ 你了解原型链吗 你能说说 prototype 与 __proto__ 的区别吗？</a>

<a href="#js-113">★★★ ts 和 js 的区别</a>

<a href="#js-114">★★★ 简述原生 js 发 ajax 的步骤</a>

<a href="#js-115">★★ 是否所有函数都有 prototype 一说？</a>

<a href="#js-116">★★ 为什么 await 在 forEach 中不生效？如何解决？</a>

<a href="#js-117">★ a 标签中，如何禁用 href 跳转页面或定位链接？</a>

<a href="#js-118">★★ 请描述一下 cookies，sessionStorage 和 localStorage 的区别？</a>

<a href="#js-119">★★★ instanceof的原理是什么？</a>







# JavaScript面试真题


### <p id="js-1"> 1. ★★ 介绍一下JS的内置类型有哪些？

```JS
1. 空类型:null
2. 未定义:undefined
3. 布尔:boolean
4. 数字:number
5. 字符串:string
6. 符号:symbol(ES6新增)
7. 对象:object
除了对象之外,其他为基本类型.
```

### <p id="js-2"> 2. ★★★★ 介绍一下 typeof 区分类型的原理

```JS
typeof原理： 不同的对象在底层都表示为二进制，在Javascript中二进制前（低）三位存储其类型信息。

000: 对象
010: 浮点数
100:字符串
110: 布尔
1: 整数
/*----------------------------------------------*/
typeof null 为"object", 原因是因为 不同的对象在底层都表示为二进制，在Javascript中二进制前（低）三位都为0的话会被判断为Object类型，null的二进制表示全为0，自然前三位也是0，所以执行typeof时会返回"object"
```

### <p id="js-3"> 3. ★★★ 介绍一下类型转换

```JS
/*-------------------显式转换---------------------*/
1. toString()  	// 转化为字符串，不可以转null和underfined
2. Number() 	// 转换为数字，字符串中有一个不是数值的字符，返回NaN
3. parseInt()	// 转换为数字，第一个字符不是数字或者符号就返回NaN
4. String() 	// 转换为字符串， 
5. Boolean() 	// 转换为布尔值
/*-------------------隐式转换(+-)---------------------*/
当 JavaScript 尝试操作一个 "错误" 的数据类型时，会自动转换为 "正确" 的数据类型
1. num  +  ""  -> String
2. num + bool -> num
// 当加号运算符时，String和其他类型时，其他类型都会转为 String；其他情况，都转化为Number类型

3. string - num -> num
// 其他运算符时， 基本类型都转换为 Number，String类型的带有字符的比如： 
4. 'a1' - num -> NaN
// 与undefined 一样。

/*-------------------隐式转换(逻辑表达式)---------------------*/

1. 对象和布尔值比较
对象和布尔值进行比较时，对象先转换为字符串，然后再转换为数字，布尔值直接转换为数字
[] == true;  //false  []转换为字符串'',然后转换为数字0,true转换为数字1，所以为false
2. 对象和字符串比较
对象和字符串进行比较时，对象转换为字符串，然后两者进行比较。
[1,2,3] == '1,2,3' // true  [1,2,3]转化为'1,2,3'，然后和'1,2,3'， so结果为true;
3. 对象和数字比较
对象和数字进行比较时，对象先转换为字符串，然后转换为数字，再和数字进行比较。
[1] == 1;  // true  `对象先转换为字符串再转换为数字，二者再比较 [1] => '1' => 1 所以结果为true
4. 字符串和数字比较
字符串和数字进行比较时，字符串转换成数字，二者再比较。
'1' == 1 // true
5. 字符串和布尔值比较
字符串和布尔值进行比较时，二者全部转换成数值再比较。
'1' == true; // true 
6. 布尔值和数字比较
布尔值和数字进行比较时，布尔转换为数字，二者比较。
true == 1 // true
```

### <p id="js-4"> 4. ★★★★ 说说你对 JavaScript 的作用域的理解。什么是作用域链？

```JS
在 JavaScript 中有两种作用域类型：

1. 局部作用域:只能在函数内部访问它们
2. 全局作用域:网页的所有脚本和函数都能够访问它
JavaScript 拥有函数作用域：每个函数创建一个新的作用域。

作用域决定了这些变量的可访问性（可见性）。

函数内部定义的变量从函数外部是不可访问的（不可见的）。

作用域链：
当查找变量的时候，会先从当前上下文的变量对象中查找，
如果没有找到，就会从父级(词法层面上的父级)执行上下文的变量对象中查找，一直找到全局上下文的变量对象，也就是全局对象。
这样由多个执行上下文的变量对象构成的链表就叫做作用域链

```

### <p id="js-5"> 5. ★★ 解释下 let 和 const 的块级作用域

```JS
/*------------let-----------*/
1. let声明的仅在块级作用域内有效，
2. let不会发生变量提升的现象，所以一定要在定义后使用，否则报错。
3. 暂时性死区：只要块级作用域内存在let命令，它所声明的变量就绑定这个区域，不再受外部影响。
4. 不允许重复声明，let不允许在相同作用域内，重复声明同一个变量：
/*-----------const----------*/
1. 声明一个只读的常量。一旦声明，常量的值就不能改变。
2. 一旦声明，就要立即初始化，否则也报错。
3. const命令声明的常量也不提升，同样存在暂时性死区，只能在声明的位置后使用。
4. 也不可以重复声明。

```

### <p id="js-6"> 6. ★★★★ 说说你对执行上下文的理解

```JS
执行上下文有且只有三类，全局执行上下文，函数上下文，与eval上下文(eval一般不会使用)
1. 全局执行上下文：
   全局执行上下文只有一个，也就是我们熟知的window对象，我们能在全局作用域中通过this直接访问到它
2. 函数执行上下文
   函数执行上下文可存在无数个，每当一个函数被调用时都会创建一个函数上下文；
   需要注意的是，同一个函数被多次调用，都会创建一个新的上下文。

3. 执行上下文栈(下文简称执行栈)也叫调用栈，
执行栈用于存储代码执行期间创建的所有上下文，具有LIFO（Last In First Out后进先出，也就是先进后出）的特性。

JS代码首次运行，都会先创建一个全局执行上下文并压入到执行栈中，之后每当有函数被调用，都会创建一个新的函数执行上下文并压入栈内；由于执行栈LIFO的特性，所以可以理解为，JS代码执行完毕前在执行栈底部永远有个全局执行上下文。
```

### <p id="js-7"> 7. ★★★ 对闭包的看法，为什么要用闭包？说一下闭包的原理以及应用场景？闭包的 this 指向问题？

```JS
闭包的作用：
1. 在外部访问函数内部的变量
2. 让函数内的局部变量可以一直保存下去
3. 模块化私有属性和公共属性

闭包的原理：
全局变量生存周期是永久，局部变量生存周期随着函数的调用介绍而销毁。
闭包就是 在函数中定义且成为该函数内部返回的函数的自由变量 的变量，该变量不会随着外部函数调用结束而销毁。 
（注：不光是变量，函数内声明的函数也可以形成闭包）
当函数可以记住并访问所在的词法作用域，即使函数是在当前词法作用域之外执行，这时就产生了闭包。

闭包的应用场景：
// 1. 返回值 最常见的一种形式

    var fun_1 = function () {
      var name = "limo";
      return function () {      
        return name;
      }
    }
    var fun_1 = function () {
      var name = "limo";
      return name;
    }
    var fu_1 = fun_1();
    console.log("fu_1():" + fu_1());

// 2. 函数赋值 一种变形的形式是将内部函数赋值给一个外部变量

    var f2;
    var fun_2 = function () {
      var name = "limop"
      var a = function () {
        return name;
      }
      f2 = a;
    }
    f2();
    console.log(f2);

// 3. 函数参数 通过函数参数引用内部函数产生闭包

    var fn_3 = function (f3) {
      console.log(f3);
    }
    
    function fun_3() {
      var name = "limo";
      var a = function () {
        return name;
      }
      fn_3(a)
    }
    fun_3();

// 4. IIFE(自执行函数)

    var fn_4 = function (f4) {
      console.log(f4);
    };
    (function fun_4() {
      var name = "limo";
      var a = function () {
        return name;
      }
      fn_3(a)
    })();

// 5. 循环赋值

    function foo(){
      var arr = [];
      for(var i = 0; i < 10; i++){
        arr[i] = (function(n){
          return function(){
            return n;
          }
        })(i)
      }
      return arr;
    }
    var bar = foo();
    console.log(bar[3]());

// 6. getter和setter

    // getter和setter函数来将要操作的变量保存在函数内部，防止暴露在外部
    var getValue, setValue;
    (function () {
      var num = 0
      getValue = function () {
        return num
      }
      setValue = function (v) {
        if (typeof v === 'number') {
          num = v
        }
      }
    })();
    console.log(getValue());    //0
    setValue(10);
    console.log(getValue())     //10

// 7.迭代器（计数器）

    var add = function(){
      var num = 0;
      return function(){
        return ++num;
      }
    }();
    console.log(add());
    console.log(add());
    
    function setUp(arr){
      var i = 0;
      return function(){
        return arr[i++];
      }
    }
    var next = setUp(['Steve','Alex','LingYi']);
    console.log(next());
    console.log(next());
    console.log(next());

// 8.触发事件

    window.onload = function (){
      var btn = document.querySelector('.btn')
      btn.onclick = function (){//事件相当于在全局触发
        btn.style.color = 'red'//保持对上层作用域的引用 btn
        console.log('abc')
        // this
      }
    }

闭包的this指向问题：

var myNumber = {
  value: 1,
  add: function(i){
    var helper = function(i){
        console.log(this);
          this.value += i;
    }
    helper(i);
  }
}
myNumber.add(1);
1.this指向window对象（因为匿名函数的执行具有全局性，所以其this对象指向window）；
2.不能实现value加1（每个函数在被调用时都会自动取得两个特殊变量，this和arguments，内部函数在搜索这两个对象时，只会搜索到其活动对象为止，所以不能实现访问外部函数的this对象）；
3.修改代码实现正确功能

第一种解决方法：

var myNumber={
    value:1,
    add:function(i){
        var that=this;//定义变量that用于保存上层函数的this对象
        var helper=function(i){
             console.log(that);
        that.value+=i;
    }
    helper(i);
    }
}
myNumber.add(1);

第二种解决方法：

var myNumber={
    value:1,
    add:function(i){
        var helper=function(i){
            this.value+=i;
        }
        helper.apply(this,[i]);//使用apply改变helper的this对象指向，使其指向myNumber对象
    }
}
myNumber.add(1);
第三种解决方法

var myNumber={
    value:1,
    add:function(i){
        var helper=function(i){
            this.value+=i;
        }.bind(this,i);//使用bind绑定，和apply相似，只是它返回的是对函数的引用，不会立即执行
        helper(i);
    }
}
myNumber.add(1);
```



### <p id="js-8"> 8. ★★★ 简述闭包的问题以及优化

```JS
闭包的缺点：占用内层空间 大量使用闭包会造成 栈溢出

由于闭包会一直占用内存空间，直到页面销毁，我们可以主动将已使用的闭包销毁：
将闭包函数赋值为null 可以销毁闭包
```

### <p id="js-9"> 9. ★★★ 如何确定 this 指向？改变 this 指向的方式有哪些？

```JS
 this 指向：
1. 全局上下文（函数外）
无论是否为严格模式，均指向全局对象。注意:严格模式下全局对象为undifined
2. 函数上下文（函数内）
默认的，指向函数的调用对象，且是最直接的调用对象：
简单调用，指向全局对象注意:严格模式下全局对象为undifined，某些浏览器未实现此标准也可能会是window

改变this指向的方式：
1. 第一种： new关键字改变this指向

//构造函数版this
function Fn(){
    this.user = "李某";
}
var a = new Fn();
console.log(a.user); //李某
/*----------------------------------------*/
2. 第二种： call()
// 把b添加到第一个参数的环境中，简单来说，this就会指向那个对象
var a = {
    user:"李某",
    fn:function(){
        console.log(this.user); //李某
    }
}
var b = a.fn;
b.call(a);  //若不用call，则b()执行后this指的是Window对象
/*----------------------------------------*/
3. 第三种：apply()
// apply方法和call方法有些相似，它也可以改变this的指向，也可以有多个参数，但是不同的是，第二个参数必须是一个数组
var a = {
    user:"李某",
    fn:function(){
        console.log(this.user); //李某
    }
}
var b = a.fn;
b.apply(a);
/*----------------------------------------*/
4. 第四种：bind()
// bind方法返回的是一个修改过后的函数,
// bind也可以有多个参数，并且参数可以执行的时候再次添加，但是要注意的是，参数是按照形参的顺序进行的。
var a = {
    user:"李某",
    fn:function(){
        console.log(this.user); //李某
    }
}
var b = a.fn;
var c = b.bind(a);
c();
```

### <p id="js-10"> 10. ★★★ 介绍箭头函数的 this

```JS
由于箭头函数不绑定this， 它会捕获其所在（即定义的位置）上下文的this值， 作为自己的this值
1. 所以 call() / apply() / bind() 方法对于箭头函数来说只是传入参数，对它的 this 毫无影响。
2. 考虑到 this 是词法层面上的，严格模式中与 this 相关的规则都将被忽略

作为方法的箭头函数this指向全局window对象，而普通函数则指向调用它的对象
```

### <p id="js-11"> 11. ★★★ 谈一下你对原型链的理解，画一个经典的原型链图示

```JS
原型链:
因为每个对象和原型都有原型，对象的原型指向原型对象，
而父的原型又指向父的父，这种原型层层连接起来的就构成了原型链。
```

![img](https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimage.mamicode.com%2Finfo%2F201809%2F20180917165312027007.png&refer=http%3A%2F%2Fimage.mamicode.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=jpeg?sec=1622810836&t=b6b151974ee8bbfb0e420a30caa148dd)

### <p id="js-12"> 12. ★★★ ES5/ES6 的继承除写法以外还有什么区别？

```JS
1. ES5 的继承实质上是先创建子类的实例对象，然后再将父类的方法添加 到 this 上(Parent.apply(this)).
2. ES6 的继承机制完全不同，实质上是先创建父类的实例对象 this(所以必 须先调用父类的super()方法)，然后再用子类的构造函数修改 this。
3. ES5 的继承时通过原型或构造函数机制来实现。
4. ES6 通过 class 关键字定义类，里面有构造方法，类之间通过 extends 关 键字实现继承。
5. 子类必须在 constructor 方法中调用 super 方法，否则新建实例报错。因 为子类没有自己的 this对象，而是继承了父类的 this 对象，然后对其进行加工。 如果不调用 super 方法，子类得不到 this 对象。
6. 注意 super 关键字指代父类的实例，即父类的 this 对象。 注意:在子类构造函数中，调用 super 后，才可使用 this关键字，否则报错
```

### <p id="js-13"> 13. ★★★★ 你对事件循环有了解吗？说说看

Event Loop(事件循环)中，每一次循环称为 tick, 每一次tick的任务如下：

- 执行栈选择最先进入队列的宏任务(通常是`script`整体代码)，如果有则执行
- 检查是否存在 Microtask，如果存在则不停的执行，直至清空 microtask 队列
- 更新render(每一次事件循环，浏览器都可能会去更新渲染)
- 重复以上步骤

宏任务 > 所有微任务 > 宏任务，如下图所示：

![img](https://segmentfault.com/img/remote/1460000015317438?w=587&h=528)

```JS
从上图我们可以看出：

1. 将所有任务看成两个队列：执行队列与事件队列。
2. 执行队列是同步的，事件队列是异步的，宏任务放入事件列表，微任务放入执行队列之后，事件队列之前。
3. 当执行完同步代码之后，就会执行位于执行列表之后的微任务，然后再执行事件列表中的宏任务
```

### <p id="js-14"> 14. ★★★★ 微任务和宏任务有什么区别？

|                    | 宏任务（macrotask）                                          | 微任务（microtask）                                          |
| ------------------ | ----------------------------- | -------------------------------- |
| 谁发起的           | 宿主（Node、浏览器）                                         | JS引擎                                                       |
| 具体事件           | 1. script (可以理解为外层同步代码) 2. setTimeout/setInterval 3. UI rendering/UI事件 4. postMessage，MessageChannel 5. setImmediate，I/O（Node.js） | 1. Promise 2. MutaionObserver 3. Object.observe（已废弃；`Proxy` 对象替代） 4. process.nextTick（Node.js） |
| 谁先运行           | 后运行                                                       | 先运行                                                       |
| 会触发新一轮Tick吗 | 会                                                           | 不会                                                         |

### <p id="js-15"> 15. ★★★★★ 浏览器和 Node 事件循环的区别？

浏览器中的事件循环：

![img](https://image.fundebug.com/2019-01-14-002.png)

Node中的事件循环：

Node 中的 Event Loop 和浏览器中的是完全不相同的东西。Node.js 采用 V8 作为 js 的解析引擎，而 I/O 处理方面使用了自己设计的 libuv，libuv 是一个基于事件驱动的跨平台抽象层，封装了不同操作系统一些底层特性，对外提供统一的 API，事件循环机制也是它里面的实现（下文会详细介绍）。

![img](https://image.fundebug.com/2019-01-14-004.png)

Node.js 的运行机制如下:

- V8 引擎解析 JavaScript 脚本。
- 解析后的代码，调用 Node API。
- libuv 库负责 Node API 的执行。它将不同的任务分配给不同的线程，形成一个 Event Loop（事件循环），以异步的方式将任务的执行结果返回给 V8 引擎。
- V8 引擎再将结果返回给用户。


### <p id="js-16"> 16. ★★★ 异步解决方案有哪些？

```JS
解决方案：
/*---------1.回调函数callback：----------*/
被作为实参传入另一函数，并在该外部函数内被调用，用以来完成某些任务的函数。如setTimeOut，ajax请求，readFile等。
例：

function greeting(name) {
  alert('Hello ' + name);
}

function processUserInput(callback) {
  var name = prompt('请输入你的名字。');
  callback(name);
}

processUserInput(greeting);
优点：
解决了异步的问题。

缺点：
回调地狱：多个回调函数嵌套的情况，使代码看起来很混乱，不易于维护。

/*---------2.事件发布订阅：---------*/
当一个任务执行完成后，会发布一个事件，当这个事件有一个或多个‘订阅者’的时候，会接收到这个事件的发布，执行相应的任务，这种模式叫发布订阅模式。如node的events,dom的事件绑定
例：

document.body.addEventListener('click',function(){
  alert('订阅了');
},false);
document.body.click(); 
优点：
时间对象上的解耦。

缺点：
消耗内存，过度使用会使代码难以维护和理解

/*---------3.Promise：---------*/
Promise是es6提出的异步编程的一种解决方案。
Promise 对象有三种状态：

pending: 初始状态，既不是成功，也不是失败状态。
fulfilled: 意味着操作成功完成。
rejected: 意味着操作失败。
promise的状态只能从pending变成fulfilled，和pending变成rejected，状态一旦改变，就不会再改变，且只有异步操作的结果才能改变promise的状态。
例：
let promise = new Promise(function (resolve, reject) {
    fs.readFile('./1.txt', 'utf8', function (err, data) {
        resolve(data)
    })
})

promise
    .then(function (data) {
        console.log(data)
    })
优点：
解决了回调地狱的问题，将异步操作以同步操作的流程表达出来。

缺点：
无法取消promise。如果不设置回调函数，Promise内部抛出的错误，不会反应到外部。当处于Pending状态时，无法得知目前进展到哪一个阶段（刚刚开始还是即将完成）。当执行多个Promise时，一堆then看起来也很不友好。

/*---------4.Generator：---------*/
Generator是es6提出的另一种异步编程解决方案，需要在函数名之前加一个*号，函数内部使用yield语句。Generaotr函数会返回一个遍历器，可以进行遍历操作执行每个中断点yield。
例：

function * count() {
  yield 1
  yield 2
  return 3
}
var c = count()
console.log(c.next()) // { value: 1, done: false }
console.log(c.next()) // { value: 2, done: false }
console.log(c.next()) // { value: 3, done: true }
console.log(c.next()) // { value: undefined, done: true }
优点：
没有了Promise的一堆then(),异步操作更像同步操作，代码更加清晰。

缺点：
不能自动执行异步操作，需要写多个next()方法，需要配合使用Thunk函数和Co模块才能做到自动执行。


/*---------5.async/await：---------*/
async是es2017引入的异步操作解决方案，可以理解为Generator的语法糖，async等同于Generator和co模块的封装，async 函数返回一个 Promise。
例：

async function read() {
 let readA = await readFile('data/a.txt')
 let readB = await readFile('data/b.txt')
 let readC = await readFile('data/c.txt')

 console.log(readA)
 console.log(readB)
 console.log(readC)
}

read()
优点：
内置执行器，比Generator操作更简单。async/await比*yield语义更清晰。返回值是Promise对象，可以用then指定下一步操作。代码更整洁。可以捕获同步和异步的错误。
```

### <p id="js-17"> 17. ★★★ async 和 await 、promise的区别 和 这两个的本质

```JS
/*---------Promise概念：---------*/
Promise 是异步编程的一种解决方案，比传统的解决方案——回调函数和事件——更合理和更强大，简单地说，Promise好比容器，里面存放着一些未来才会执行完毕（异步）的事件的结果，而这些结果一旦生成是无法改变的

/*---------async await概念：---------*/
async await也是异步编程的一种解决方案，他遵循的是Generator 函数的语法糖，他拥有内置执行器，不需要额外的调用直接会自动执行并输出结果，它返回的是一个Promise对象。

两者的区别：
Promise的出现解决了传统callback函数导致的“地域回调”问题，但它的语法导致了它向纵向发展行成了一个回调链，遇到复杂的业务场景，这样的语法显然也是不美观的。而async await代码看起来会简洁些，使得异步代码看起来像同步代码，await的本质是可以提供等同于”同步效果“的等待异步返回能力的语法糖，只有这一句代码执行完，才会执行下一句。

async await与Promise一样，是非阻塞的。

async await是基于Promise实现的，可以说是改良版的Promise，它不能用于普通的回调函数。
```

### <p id="js-18"> 18. ★★★ 简述 aync await 的好处

```JS
1. async/await最重要的好处是同步编程风格
2. async/await有本地浏览器支持。截至今天，所有主流浏览器 查看都完全支持异步功能。
3. async关键字。它声明 getBooksByAuthorWithAwait()函数返回值确保是一个 promise，以便调用者可以安全调用 getBooksByAuthorWithAwait().then(...)或 await getBooksByAuthorWithAwait()
```

### <p id="js-19"> 19. ★★★ 移动端点击事件 300ms 延迟如何去掉？原因是什么？

```JS
300毫秒原因：
当用户第一次点击屏幕后，需要判断用户是否要进行双击操作，于是手机会等待300毫秒，
解决方法：FastClick.js
FastClick 是 FT Labs 专门为解决移动端浏览器 300 毫秒点击延迟问题所开发的一个轻量级的库。FastClick的实现原理是在检测到touchend事件的时候，会通过DOM自定义事件立即出发模拟一个click事件，并把浏览器在300ms之后的click事件阻止掉。
```

### <p id="js-20"> 20. ★★★ Cookie 有哪些属性？其中HttpOnly，Secure，Expire分别有什么作用？

```JS
Cookie属性：
name　　字段为一个cookie的名称。
value　　字段为一个cookie的值。
domain　　字段为可以访问此cookie的域名。
path　　字段为可以访问此cookie的页面路径。 比如domain是abc.com,path是/test，那么只有/test路径下的页面可以读取此cookie。
expires/Max-Age 　　字段为此cookie超时时间。若设置其值为一个时间，那么当到达此时间后，此cookie失效。不设置的话默认值是Session，意思是cookie会和session一起失效。当浏览器关闭(不是浏览器标签页，而是整个浏览器) 后，此cookie失效。
Size　　字段 此cookie大小。
http　　字段  cookie的httponly属性。若此属性为true，则只有在http请求头中会带有此cookie的信息，而不能通过document.cookie来访问此cookie。
secure　　 字段 设置是否只能通过https来传递此条cookie

1 secure属性
当设置为true时，表示创建的 Cookie 会被以安全的形式向服务器传输，也就是只能在 HTTPS 连接中被浏览器传递到服务器端进行会话验证，如果是 HTTP 连接则不会传递该信息，所以不会被窃取到Cookie 的具体内容。
2 HttpOnly属性
如果在Cookie中设置了"HttpOnly"属性，那么通过程序(JS脚本、Applet等)将无法读取到Cookie信息，这样能有效的防止XSS攻击。
3 Expire属性
设置Cookie的失效时间：
```

### <p id="js-21"> 21. ★★★★ 如何实现函数的柯里化？比如 add(1)(2)(3)

```JS
/*-----解决方法1：-----*/
function add () {
  var args = Array.prototype.slice.call(arguments);

  var fn = function () {
    var sub_arg = Array.prototype.slice.call(arguments);
　　 // 把全部的参数聚集到参数的入口为一个参数： args.concat(sub_arg)
    return add.apply(null, args.concat(sub_arg));
  }

  fn.valueOf = function () {
  return args.reduce(function(a, b) {
      return a + b;
    })
  }

  return fn;
}
console.log(add(1,2)) // 3
console.log(add(1)(2)) // 3
console.log(add(1)(2)(3)) // 6
console.log(add(1,2,3)(4)) // 10

/*-----解决方法2：-----*/

function add () {
    var args = Array.prototype.slice.call(arguments);

    var fn = function () {
        // 把参数都放在一个相当于全局变量的 args 里面　
        args.push(...arguments)
        return fn;
    }

    fn.valueOf = function () {
        return args.reduce(function(a, b) {
            return a + b;
        })
    }

    return fn;
}
console.log(add(1,2)) // 3
console.log(add(1)(2)) // 3
console.log(add(1)(2)(3)) // 6
console.log(add(1,2,3)(4)) // 10
```

### <p id="js-22"> 22. ★★★★ 什么是反柯里化

```JS
在JavaScript中，当我们调用对象的某个方法时，其实不用去关心该对象原本是否被设计为拥有这个方法，这是动态类型语言的特点。可以通过反柯里化(uncurrying)函数实现，让一个对象去借用一个原本不属于他的方法。
```

### <p id="js-23"> 23. ★★ 将 [1,2] 与 [3,[4]] 合并为 [1,2,3,[4]]

```JS
JS数组合并方法:
let arr3 = [1,2].concat([3,[4]]);	//[1,2,3,[4]]
```

### <p id="js-24"> 24. ★★ Array.forEach() 与 Array.map() 的区别，Array.slice() 与 Array.splice() 的区别？

```JS
/*-----forEach-----*/
forEach不支持return,对原来的数组也没有影响。但是我们可以自己通过数组的索引来修改原来的数组

var ary = [12,23,24,42,1];
var res = ary.forEach(function (item,index,input) {
     input[index] = item*10;
})
console.log(res);//-->undefined;
console.log(ary);//-->会对原来的数组产生改变；
/*-----map-----*/
map支持return返回值，也不影响原数组，但是会返回一个新的数组

var ary = [12,23,24,42,1];
var res = ary.map(function (item,index,input) {
     return item*10;
})
console.log(res);//-->[120,230,240,420,10];
console.log(ary);//-->[12,23,24,42,1]；

array.slice(start,end)函数是取array数组中指定的一些元素：
根据数组下标start和end，两个参数为取值的开始和结束下标，取出的值不包括end位置的值，生成一个新数组作为返回值；
这里end可以为空，为空则取从start位置到数组结尾的元素，生成新数组。

array.splice(start,length,insert_one......)函数则是直接在原数组进行删除、添加、替换元素的操作：
start为数组删除元素的开始下标，
length为从start位置开始array删除元素的个数，
后面参数为删除之后array重新插入的数据内容，插入位置为删除位置，而非数组开头或末尾，
返回值为array删除的元素组成的数组。
显而易见，splice函数可以用来对数组元素进行替换。由splice操作后的数组array，数组中内容如果已经改变，就再也找不回array在splice之前的模样。
```

### <p id="js-25"> 25. ★★ 将 1234567 转换为 1,234,567

```JS
function fun(n){
    return String(n).replace(/(?!^)(?=(\d{3})+\.)/g, ",") 
}
```

### <p id="js-26"> 26. ★★★ bind 的作用是什么？

```JS
bind()方法主要就是将函数绑定到某个对象，
bind()会创建一个函数，函数体内的this对象的值会被绑定到传入bind()第一个参数的值
```

### <p id="js-27"> 27. ★★ Promise.resolve(Promise.resolve(1)).then(console.log) 输出？

```JS
// 答案：1
```

### <p id="js-28"> 28. ★★★ var let const的区别

```JS
1. var声明的变量会挂载在window上，而let和const声明的变量不会
2. var声明变量存在变量提升，let和const不存在变量提升
3. let和const声明形成块作用域
4. 同一作用域下let和const不能声明同名变量，而var可以
5. 使用let/const声明的变量在当前作用域存在暂存死区
6. const一旦声明必须赋值,不能使用null占位,声明后不能再修改,如果声明的是复合类型数据，可以修改其属性
```

### <p id="js-29"> 29. ★★★ document load 和 documen ready的区别

```JS
DOM文档解析：

解析html结构
加载脚本和样式文件
解析并执行脚本
构造html的DOM模型      //ready
加载图片等外部资源文件
页面加载完毕           //load

document load:
load是当页面所有资源全部加载完成后（包括DOM文档树，css文件，js文件，图片资源等），执行一个函数，load方法就是onload事件。

documen ready:
构造html的DOM模型加载完毕后触发
```

### <p id="js-30"> 30. ★★★ 如何自定义事件？

```JS
自定义事件
事件是与DOM交互的最常见的方式。通过实现自定义事件，可以让事件用于非DOM代码中。
思想：创建一个管理事件的对象，让其他对象监听那些事件。

基本模式：

function EventTarget(){
    this.handlers = {};
}

EventTarget.prototype = {
    constructor:EventTarget,
    addHandler:function(type,handler){
        if(typeof this.handlers[type] === "undefined"){
            this.handlers[type] = [];
        }
        this.handlers[type].push(handler);
    },
    fire:function(event){
        if(!event.target){
            event.target = this;
        }
        if(this.handlers[event.type] instanceof Array){
            const handlers = this.handlers[event.type];
            handlers.forEach((handler)=>{
                handler(event);
            })
        }
    },
    removeHandler:function(type,handler){
        if(this.handlers[type] instanceof Array){
            const handlers = this.handlers[type];
            for(var i = 0,len = handlers.length; i < len; i++){
                if(handlers[i] === handler){
                    break;
                }
            }
            handlers.splice(i,1);
        }
    }
}
```

### <p id="js-31"> 31. ★★★ 如何用 setTImeout 来实现 setInterval？

```JS
1.不去关心回调函数是否还在运行
在某些情况下，函数可能需要比间隔时间更长的时间去完成执行。比如说是用setInterval每隔5秒对远端服务器进行轮询，网络延迟，服务器无响应以及其他因素将会阻止请求按时按成。结果会导致返回一串无必要的排成队列请求。

2.忽视错误
因为某些原因，setInterval调用的代码中会出现一个错误，但是代码并不会中止执行而是继续执行错误的代码。

3.缺乏灵活性
除了前面提到的缺点之外，我非常希望setInterval方法能有一个表明执行次数的参数而不是无休止的执行下去。

function interval(func, w, t){
    var interv = function(){
        if(typeof t === "undefined" || t-- > 0){
            setTimeout(interv, w);
            try{
                func.call(null);
            }
            catch(e){
                t = 0;
                throw e.toString();
            }
        }
    };
    setTimeout(interv, w);
};

```

### <p id="js-32"> 32. ★★★ 如何判断 user 对象里有没有 a 这个属性？如果把user对象中所有的属性都输出出来？

`(var user = {'a': '19', 'b': '18', 'c':  '16'})`

```JS
如何判断 user 对象里有没有 a 这个属性？

js对象的Object.hasOwnProperty()方法
返回一个布尔值，判断对象是否包含特定的自身（非继承）属性。

let obj = new Object();
obj.a = "123";
console.log(obj.hasOwnProperty('a'))  // true
console.log(obj.hasOwnProperty('b'))  // false

把user对象中所有的属性都输出出来
for(item for user){
    console.log(item)
}
```

### <p id="js-33"> 33. ★★ 使用 setTimeout 模拟 setInterval 的功能做一个60秒的倒数计时

```JS
function setInter(s,fn){
  let timeOut = (s,fn)=>{
      setTimeout(()=>{
        fn();
        timeOut(s,fn);
      },s)
  }
  timeOut(s,fn);
}
 
//调用上面的方法
setInter(60000,()=>{console.log("hello world!")})
```

### <p id="js-34"> 34. ★★★ 实现一个函数 add()，运算结果可以满足如下预期结果

```JS
function add () {
  var args = Array.prototype.slice.call(arguments);

  var fn = function () {
    var sub_arg = Array.prototype.slice.call(arguments);
　　 // 把全部的参数聚集到参数的入口为一个参数： args.concat(sub_arg)
    return add.apply(null, args.concat(sub_arg));
  }

  fn.valueOf = function () {
  return args.reduce(function(a, b) {
      return a + b;
    })
  }

  return fn;
}
```

  ```JS
add(1,2,3)(10) //16
add(1)(2)(3,4)(5) //15
  ```

### <p id="js-35"> 35. ★★★ 如何避免回调地狱？

```JS
1. Promise 对象就是为了解决这个问题而提出的。它不是新的语法功能，而是一种新的写法，允许将回调函数的嵌套，改成链式调用。

promise只有两个状态resolve和reject，当它触发任何一个状态后，它会将当前的值缓存起来，并在有回调函数添加进来的时候尝试调用回调函数，如果这个时候还没有触发resolve或者reject，那么回调函数会被缓存，等待调用，如果已经有了状态(resolve或者reject)，则立刻调用回调函数。并且所有回调函数在执行后都立即被销毁。

2. ES6 co/yield方案
yield: Generator 函数是协程在 ES6 的实现，而yield是 Generator关键字， 异步操作需要暂停的地方，都用yield语句注明。
co: co 模块是著名程序员 TJ Holowaychuk 于 2013 年 6 月发布的一个小工具，用于 Generator 函数的自动执行。

3. ES7 async/await 方案
async/await是es7的新标准，并且在node7.0中已经得到支持。
它就是 Generator 函数的语法糖，async函数就是将 Generator 函数的星号（*）替换成async，将yield替换成await，仅此而已。可以理解官方对co和Generator 封装方案。
```

### <p id="js-36"> 36. ★★ 写一个 function，清除字符串前后的空格。（兼容所有的浏览器）

```JS
function trim(str) {
    if (str && typeof str === "string") {
        return str.replace(/(^\s*)|(\s*)$/g,""); //去除前后空白符
    }
}
```

### <p id="js-37"> 37. ★★ 使用正则表达式验证邮箱格式

```JS
function fChkMail(emailAddress){ 
    var reg = new RegExp("^[a-z0-9]+([._\\-]*[a-z0-9])*@([a-z0-9]+[-a-z0-9]*[a-z0-9]+.){1,63}[a-z0-9]+$"); 
    var bChk=reg.test(emailAddress); 
    return bChk; 
}
```

### <p id="js-38"> 38. ★★★ 简述同步和异步的区别

```JS
同步：
同步的思想是：所有的操作都做完，才返回给用户。这样用户在线等待的时间太长，给用户一种卡死了的感觉（就是系统迁移中，点击了迁移，界面就不动了，但是程序还在执行，卡死了的感觉）。这种情况下，用户不能关闭界面，如果关闭了，即迁移程序就中断了。

异步：
将用户请求放入消息队列，并反馈给用户，系统迁移程序已经启动，你可以关闭浏览器了。然后程序再慢慢地去写入数据库去。这就是异步。但是用户没有卡死的感觉，会告诉你，你的请求系统已经响应了。你可以关闭界面了。

同步和异步本身是相对的:
同步就相当于是 当客户端发送请求给服务端，在等待服务端响应的请求时，客户端不做其他的事情。当服务端做完了才返回到客户端。这样的话客户端需要一直等待。用户使用起来会有不友好。

异步就是，当客户端发送给服务端请求时，在等待服务端响应的时候，客户端可以做其他的事情，这样节约了时间，提高了效率。

存在就有其道理 异步虽然好 但是有些问题是要用同步用来解决，比如有些东西我们需要的是拿到返回的数据在进行操作的。这些是异步所无法解决的。
```

### <p id="js-39"> 39. ★★ JavaScript 中 callee 和 caller 的作用

```JS
1.callee
callee是对象的一个属性，该属性是一个指针，指向参数arguments对象的函数
作用：就是用来指向当前对象
返回正被执行的 Function 对象，也就是所指定的 Function 对象的正文. 
callee是arguments 的一个属性成员，它表示对函数对象本身的引用，这有利于匿名 
函数的递归或者保证函数的封装性

2.caller
caller是函数对象的一个属性，该属性保存着调用当前函数的函数的引用（指向当前函数的直接父函数）
返回一个对函数的引用，该函数调用了当前函数。
functionName.caller
functionName 对象是所执行函数的名称。
注意：
对于函数来说，caller 属性只有在函数执行时才有定义。 如果函数是由 Javascript 程序的顶层调用的，那么 caller 包含的就是 null 。
```

### <p id="js-40"> 40. ★★ 统计字符串中字母个数或统计最多的字母数

```JS
function count(str) {
  var obj = {}; // 统计对象
  var i = 0;
  var len = str.length;
  for (; i < len; i++){
    var curChar = str.charAt(i); 
    // 如果结果对象存在该字符的属性，则自增，否则置为1
    if (obj[curChar]) {
      obj[curChar]++;
    } else {
      obj[curChar] = 1;
    }
  }
  // 返回结果
  return obj;
}
var str = "javaScript";
console.log(count(str));
```

### <p id="js-41"> 41. ★★★ jQuery 的事件委托方法 on，live，delegate之间有区别？

```JS
live 把事件委托交给了document（根节点），document 向下去寻找符合条件的元素（）， 不用等待document加载结束也可以生效。

delegate可指定事件委托对象，相比于live性能更优，直接锁定指定选择器；

on事件委托对象选填，如果不填，即给对象自身注册事件，填了作用和delegate一致。
```

### <p id="js-42"> 42. ★★★ 简述下 Promise 对象

```JS
Promise是异步编程的一种解决方案，比传统的解决方案（回调函数和事件）更合理更强大。

所谓Promise，简单说就是一个容器，里面保存着某个未来才会结束的事件 (通常是一个异步操作)的结果。从语法上说，Promise是一个对象，从它可以获取异步操作的消息。

Promise对象有以下2个特点：
1.对象的状态不受外界影响。Promise对象代表一个异步操作，有三种状态：Pending(进行中)、Resolved(已完成)和Rejected(已失败)。只有异步操作的结果，可以决定当前是哪一种状态，任何其他操作都无法改变这个状态。这也是Promise这个名字的由来，它的英语意思就是“承诺”，表示其他手段无法改变。
2.一旦状态改变，就不会再变，任何时候都可以得到这个结果。Promise对象的状态改变，只有两种可能：从Pending变为Resolved；从Pending变为Rejected。只要这两种情况发生，状态就凝固了，不会再变了，会一直保持这个结果。就算改变已经发生了，你再对Promise对象田静回调函数，也会立即得到这个结果。这与事件(Event)完全不同，事件的特点是，如果你错过了它，再去监听，是得不到结果的。

有了Promise对象，就可以把异步操作以同步操作的流程表达出来，避免了层层嵌套的回调函数。此外，Promise对象提供了统一的接口，使得控制异步操作更加容易。
```

### <p id="js-43"> 43. ★★★ 数组扁平化，不用 api

```JS
function myFlat(arr){
    let res = [];
    for(let i=0; i<arr.length; i++){   
        if(arr[i] instanceof Array){
            res = res.concat(myFlat(arr[i]));
        }else {
            res.push(arr[i]);
        }
    }
    return res;
}
 
let arr = [1,[2,3,[4,5]]];
console.log(myFlat(arr))
```

### <p id="js-44"> 44. ★★★ 用 JavaScript 实现观察者模式

```JS
function BusinessOne(name){
	this.name = name;
	//订阅者的集合
	this.subscribers = new Array();
}
//订阅者的发送消息的方法(推模式)
BusinessOne.prototype.delive = function(news){
	var self = this;
	//给每一个订阅者发送消息
	this.subscribers.forEach(
		function(fn){
			//调用接受者处理信息的函数
			fn(news,self);
		}
	)
}
//扩展公共订阅的函数,和取消订阅的函数
Function.prototype.subscribe = function(publisher){
	var that = this;
	//some 访问数组度i型并且以参数的形式传回回调函数中
	//只要至少有一次返回是true那么some就是true
	var alreadyExists = publisher.subscribers.some(
		function(el){
			//处理不能重复订阅的功能
			if(el == that){
				return;
			}
		}
	);
	//没用订阅你就可以订阅
	if(!alreadyExists){
		publisher.subscribers.push(that);
	}
	return this;
}
//取消
Function.prototype.unsubscribe = function(publisher){
	var that = this;
	publisher.subscribers = publisher.subscribers.filter(
		function(el){
			if(el !== that){
				return el;
			}
		}
	);
	return this;
};
```

### <p id="js-45"> 45. ★★ 简述一下面象对象的六法则

```JS
1. 单一职责原则：一个类只做它该做的事情
2. 开闭原则：软件实体应当对扩展开放，对修改关闭
3. 依赖倒转原则：面向接口编程
4. 接口隔离原则：接口要小而专，绝不能大而全
5. 合成聚合复用原则：优先使用聚合或合成关系复用代码
6. 迪米特法则：迪米特法则又叫最少知识原则，一个对象应当对其他对象有尽可能少的了解(低耦合)
```

### <p id="js-46"> 46. ★★★ 谈谈垃圾回收机制方法以及内存管理

```JS
垃圾回收方式
① 标记清除
工作原理：是当变量进入环境时，将这个变量标记为“进入环境”。当变量离开环境时，则将其标记为“离开环境”。标记“离开环境”的就回收内存。
② 引用计数
工作原理：跟踪记录每个值被引用的次数。一旦没有引用，内存就直接释放了。

内存管理
什么时候触发垃圾回收？
垃圾回收器周期性运行，如果分配的内存非常多，那么回收工作也会很艰巨，确定垃圾回收时间间隔就变成了一个值得思考的问题。
1、合理的GC方案：(1)、遍历所有可访问的对象; (2)、回收已不可访问的对象。
2、GC缺陷：		(1)、停止响应其他操作；
3、GC优化策略：  (1)、分代回收（Generation GC）;(2)、增量GC
```

### <p id="js-47"> 47. ★★★ 开发过程中遇到内存泄漏的问题都有哪些？

```JS
1. 当页面中元素被移除或替换时，若元素绑定的事件仍没被移除，在IE中不会作出恰当处理，此时要先手工移除事件，不然会存在内存泄露。
2. 由于是函数内定义函数，并且内部函数--事件回调的引用外暴了，形成了闭包。闭包可以维持函数内局部变量，使其得不到释放。
```

### <p id="js-48"> 48. ★★★ 请编写获取当前窗口地址中查询参数name的值，当前窗口地址为：<https://foo.com/?id=1&name=tom>

```JS
function GetQueryString(name){
    var reg = new RegExp("(^|&)"+ name +"=([^&]*)(&|$)");
    var r = window.location.search.substr(1).match(reg);
    if(r!=null)
        return unescape(r[2]); 
    return null;
}
```

### <p id="js-49"> 49. ★★★ 已知a，b两个构造函数，现在 let c = new a()，如何在c的存储地址不变的情况下，改变c的继承（c->a 转为 c->b）

```JS
1. 改变原型链：通过改变C的prototype为b,实现内存地址不动，改变继承
```

### <p id="js-50"> 50. ★★★ 浏览器有哪些兼容问题，你封装过什么插件

```JS
//1.滚动条到顶端的距离（滚动高度）
var scrollTop = document.documentElement.scrollTop || document.body.scrollTop;
 
//2.滚动条到左端的距离
var scrollLeft = document.documentElement.scrollLeft || document.body.scrollLeft;
 
//3. IE9以下byClassName
function byClassName(obj,className){
    //判断是否支持byClassName
    if(obj.getElementsByClassName){
        //支持
        return obj.getElementsByClassName(className);
    }else{
        //不支持
        var eles = obj.getElementsByTagName('*'); //获取所有的标签
        var arr = []; //空数组，准备放置找到的对象
        //遍历所有的标签
        for(var i = 0,len = eles.length;i < len;i ++){
            //找出与我指定class名相同的对象
            if(eles[i].className === className){
                arr.push(eles[i]); //存入数组
            }
        }
        return arr; //返回
    }
}

//4. 获取非行内样式兼容    IE:currentStyle  标准：getComputedStyle
function getStyle(obj,attr){
    return window.getComputedStyle ? getComputedStyle(obj,true)[attr] : obj.currentStyle[attr];
}
//div.style.width =  '';设置样式
//obj['属性']： 对象是变量时，必须用对象['属性']获取。

//5. 获取事件对象的兼容
evt = evt || window.event

//6. 获取鼠标编码值的兼容
function getButton(evt){
    var e = evt || window.event;
    if(evt){
        return e.button;
    }else if(window.event){
        switch(e.button){
            case 1 : return 0;
            case 4 : return 1;
            case 2 : return 2;
        }
    }
}

//7. 获取键盘按键编码值的兼容
var key = evt.keyCode || evt.charCode || evt.which;

//8. 阻止事件冒泡的兼容
e.stopPropagation ? e.stopPropagation() : e.cancelBubble = true;

//9. 阻止超链接的默认行为的兼容
evt.preventDefault ? evt.preventDefault() : evt.returnValue = false;

//10. 添加事件监听器的兼容
function addEventListener(obj,event,fn,boo){
    if(obj.addEventListener){
        obj.addEventListener(event,fn,boo);
    }else if(obj.attachEvent){
        obj.attachEvent('on' + event,fn);
    }
}

//11. 移除事件监听器的兼容
function removeEventListener(obj,event,fn,boo){
    if(obj.removeEventListener){
        obj.removeEventListener(event,fn,boo);
    }else if(obj.detachEvent){
        obj.detachEvent('on' + event,fn);
    }
}

//12. 获取事件源的兼容
var target = event.target || event.srcElement;
```

### <p id="js-51"> 51. ★★★ 如何判断一个对象是否为数组，函数

```JS
方法一： instanceof:
var arr=[];
console.log(arr instanceof Array) //返回true

方法二： constructor:
console.log(arr.constructor == Array); //返回true

方法三： Array.isArray()
console.log(Array.isArray(arr)); //返回true
```

### <p id="js-52"> 52. ★★★ 写一个函数，接受可变个数参数，且每个参数均为数字，返回参数的最大值

```JS
function myMax(){
    return Math.max(arguments)
}
```

### <p id="js-53"> 53. ★★★ 请写出 ES6 Array.isArray()

```JS
if (!Array.isArray){
  Array.isArray = function(arg){
    return Object.prototype.toString.call(arg) === '[object Array]';
  };
}
```

### <p id="js-54"> 54. ★★★ 实现一个函数 clone，可以对 JavaScript 中的5种主要数据类型进行值复制

```JS
// 方法一：
Object.prototype.clone = function() {
    var o = this.constructor === Array ? [] : {};
    for (var e in this) {
        o[e] = typeof this[e] === "object" ? this[e].clone() : this[e];
    }
    return o;
};

//方法二：
/**
     * 克隆一个对象
     * @param Obj
     * @returns
     */
function clone(Obj) {
    var buf;
    if (Obj instanceof Array) {
        buf = []; //创建一个空的数组
        var i = Obj.length;
        while (i--) {
            buf[i] = clone(Obj[i]);
        }
        return buf;
    } else if (Obj instanceof Object) {
        buf = {}; //创建一个空对象
        for (var k in Obj) {
            //为这个对象添加新的属性
            buf[k] = clone(Obj[k]);
        }
        return buf;
    } else {
        //普通变量直接赋值
        return Obj;
    }
}
```

### <p id="js-55"> 55. ★★★ 假如A页面我定义了一个定时器，然后跳到B页面如果让A页面的定时器暂停

```JS
方法1：在beforeDestroy()等生命周期结束阶段内清除定时器：
beforeDestroy() {
    clearInterval(this.timer);
    this.timer = null;
}

方法2：通过$once这个事件侦听器器在定义完定时器之后的位置来清除定时器。

const timer = setInterval(() =>{
    // 某些定时器操作
}, 500);
// 通过$once来监听定时器，在beforeDestroy钩子可以被清除。
this.$once('hook:beforeDestroy', () => {
    clearInterval(timer);
})
```

### <p id="js-56"> 56. ★★★ promise的实现原理，如果我现在向服务器发送一个请求，但是我后悔了，不想让服务器返回数据，去实现一个delay

```JS
取消结束Promise的方法？
1. 返回一个pending状态的Promise，原Promise链会终止
Promise.resolve().then(() => {
    console.log('ok1')
    return new Promise(()=>{})  // 返回“pending”状态的Promise对象
}).then(() => {
    // 后续的函数不会被调用
    console.log('ok2')
}).catch(err => {
    console.log('err->', err)
})

2. Promise.race竞速方法

let p1 = new Promise((resolve, reject) => {
    resolve('ok1')
})
 
let p2 = new Promise((resolve, reject) => {
    setTimeout(() => {resolve('ok2')}, 10)
})
 
Promise.race([p2, p1]).then((result) => {
    console.log(result) //ok1
}).catch((error) => {
    console.log(error)
})

3. 当Promise链中抛出错误时，错误信息沿着链路向后传递，直至捕获
Promise.resolve().then(() => {
    console.log('ok1')
    throw 'throw error1'
}).then(() => {
    console.log('ok2')
}, err => {     
    // 捕获错误
    console.log('err->', err)
}).then(() => {   
    // 该函数将被调用
    console.log('ok3')
    throw 'throw error3'
}).then(() => {
    // 错误捕获前的函数不会被调用
    console.log('ok4')
}).catch(err => {
    console.log('err->', err)

Axios如何取消请求？
第一种通过CancelToken.source工厂方法创建cancel token

var CancelToken = axios.CancelToken;
var source = CancelToken.source();

axios.get('/user/12345', {
  cancelToken: source.token
}).catch(function(thrown) {
  if (axios.isCancel(thrown)) {
    console.log('Request canceled', thrown.message);
  } else {
    // 处理错误
  }
});

// 取消请求（message 参数是可选的）
source.cancel('Operation canceled by the user.');
第二种通过传递executor函数到CancelToken的构造函数来创建cancel token

var CancelToken = axios.CancelToken;
var cancel;

axios.get('/user/12345', {
  cancelToken: new CancelToken(function executor(c) {
    // executor 函数接收一个 cancel 函数作为参数
    cancel = c;
  })
});

// 取消请求
cancel();
```

### <p id="js-57"> 57. ★★★ CommonJS 和 RequireJS 的实现原理

```JS
commonjs是通过module.exports导出模块,用require引入一个模块，原理：闭包

requirejs是通过define定义导出模块，用require引入模块。
define('name',[],function(){
    return 'requirejs'
})
define('say',['name'].function(name){
    return "my name is" + name
})
require(['say'],function(text){
    console.log(text)
})

```

### <p id="js-58"> 58. ★★★ 面向对象编程与面向过程编程的区别？

```JS
面向过程的程序设计把计算机程序视为一系列的命令集合，即一组函数的顺序执行。为了简化程序设计，面向过程把函数继续切分为子函数，即把大块函数通过切割成小块函数来降低系统的复杂度。

而面向对象的程序设计把计算机程序视为一组对象的集合，而每个对象都可以接收其他对象发过来的消息，并处理这些消息，计算机程序的执行就是一系列消息在各个对象之间传递。
```

### <p id="js-59"> 59. ★★★ eval 是做什么的？性能怎么样？安全如何？

```JS
它的功能是把对应的字符串解析成js代码并运行，

应该避免使用eval,因为不安全，非常耗性能（2次，一次解析成js语句，一次执行）

注意：在项目里写js代码的时候，禁止使用的，因为有安全因素。
```

### <p id="js-60"> 60. ★★★★★ 函数节流、防抖。scroll resize 使用函数节流实现不要频繁触发事件的需求

```JS
// 答案：
防抖：
//scroll方法中的do somthing至少间隔500毫秒执行一次
    window.addEventListener('scroll',function(){
        var timer;//使用闭包，缓存变量
        return function(){
            if(timer) clearTimeout(timer);
            timer = setTimeout(function(){
                console.log('do somthing')
            },500)
        }
    }());//此处()作用 - 立即调用return后面函数，形成闭包
节流：
//scroll方法中当间隔时间大于2s，do somthing执行一次
    window.addEventListener('scroll',function(){
        var timer ;//使用闭包，缓存变量
        var startTime = new Date();
        return function(){
            var curTime = new Date();
            if(curTime - startTime >= 2000){
                timer = setTimeout(function(){
                    console.log('do somthing')
                },500);
                startTime = curTime;
            }

        }
    }());//此处()作用 - 立即调用return后面函数，形成闭包
```

### <p id="js-61"> 61. ★★★ 数据类型（判断，==和===）堆栈、内存泄漏及垃圾回收机制

```JS
// 答案：
1，== 判断值是否相等； === 判断值和数据类型是否严格相等
2，Javascript堆栈和垃圾回收机制
堆栈溢出
​ 当储存的数据导到某一限制时就会造成堆栈溢出

内存泄漏
​ 当不断向堆中存储数据，而不进行清理，这就是内存泄漏

垃圾回收机制（清除孤儿机制）
​ 语言当中一般分两种，一种是自动清理，一种是手动清理（GC），js中只有自动清理

​ 垃圾回收机制就是将引用对中的地址的对象设置为null，并且将所有引用该地址的对象都设置为null，并且移除事件侦听

​ 不会即时清除,垃圾回收车会根据内存的情况在适当的时候进行清除堆中的对象 内存到达一定程度了才会进行回收
```

### <p id="js-62"> 62. ★★★★ 了解 ES6 的 Proxy 吗？

```JS
// 答案：
Proxy，代理，是ES6新增的功能，可以理解为代理器（即由它代理某些操作）。
Proxy 对象用于定义或修改某些操作的自定义行为，可以在外界对目标对象进行访问前，对外界的访问进行改写。

new Proxy()表示生成一个 Proxy 实例
	-target：目标对象
	-handler：一个对象，其属性是当执行一个操作时定义代理的行为的函数。
注意：要实现拦截操作，必须是对 Proxy 实例进行操作，而不是针对目标对象 target 进行操作。
```

### <p id="js-63"> 63. ★★★★ 深拷贝是什么？项目哪里是用到了深拷贝？

```JS
// 答案：
1，在拷贝构造函数中假如只完成了数据成员本身的赋值则称为“浅拷贝”；编译器提供的默认拷贝构造函数就已经可以完成这个任务。
而假如要复制的数据除了属性值本身以外，还要复制附加在数据属性值上的额外内容，那就要自己来写拷贝构造函数了，来完成所谓的“深拷贝”。

举个例子：

若在构造函数中new了一个新的空间存放数据，并且用指针记录了首地址；若是浅拷贝，则在拷贝构造函数中指针值将复制给另一个数据成员，这样就会有两个指针指向同一个空间；这样的话在析构函数里将会对指针所指向的空间进行释放，由于两个指针指向的是同一个空间，在释放第一个指针指向的空间时不会出现什么问题，而释放第二个指针指向的空间时就会因为空间已经被解析过而导致解析的空间不存在的情况，就会造成程序无法终止。

而解决上面这种情况的办法就是使用“深拷贝”，深拷贝是在拷贝构造函数里再new一个新的空间。将数据复制在新空间里，并将拷贝的指针记录这个新空间的首地址，这样在析构函数里就不会有问题了。
2，在某些引用类型值不更新的情况下用深拷贝
```

### <p id="js-64"> 64. ★★★ swiper 插件从后台获取数据没问题，css 代码啥的也没问题，但是图片不动，应该怎么解决？

```JS
// 答案：
主要原因：
swiper提前初始化了，而这个时候，数据还没有完全出来。
解决方法
从swiper 入手，在swiper中写 observer:true/observeParents:true
 let myswiper = new Swiper(".swiper-container" , {
     autoplay: true,
     loop: true,
     // observer 修改swiper子元素时自动初始化swiper
     observer:true,
     // observeParents 包括当前父元素的swiper发生变更时也会初始化swiper
     observeParents:true,
 })
 从 Vue 入手，vue中专门提供了提供了一个方法nextTick() 用于解决dom的先后执行问题。
 mounted(){
     this.$nextTick(function(){
         // ...操作
         let myswiper = new Swiper(".swiper-container" , {
             autoplay: true,
             loop: true
         })
     })  
 }
```

### <p id="js-65"> 65. ★★★★ ES6 中，数组监测怎么实现的（代理）

```JS
// 通过ES6的关键字extends实现继承完成Array原型方法的重写
class NewArray extends Array {
  constructor(...args) {
    // 调用父类Array的constructor()
    super(...args)
  }
  push (...args) {
    console.log('监听到数组的变化啦！');

    // 调用父类原型push方法
    return super.push(...args)
  }
  // ...
}

let list3 = [1, 2];

let arr = new NewArray(...list3);
console.log(arr)
// (2) [1, 2]

arr.push(3);
// 监听到数组的变化啦！
console.log(arr)
// (3) [1, 2, 3]
```

### <p id="js-66"> 66. ★★ jQuery 优点和缺点

```JS
// 答案：
优点
1.出色的浏览器兼容性
2、出色的DOM操作的封装，使他具备强大的选择器，可以进行快速的DOM元素操作
3、可靠的事件处理机制、jq在处理事件绑定的时候是相当的可靠
4、完善的ajax（对ajax的封装非常好，不需要考虑复杂的浏览器的兼容和XMLhttprequest对象的创建和使用）
5、支持链式操作（什么是链式操作？通过‘.’来操作）和隐士迭代
6、减少服务器的压力和带宽并且加快了加载速度（为什么这么说？原因就是：当你打开网页之前打开了其他的网页，并且该网页也用了cdn的方式来
加载相同版本的jq文件，那么，浏览器就不会加载第二次，为啥舍近求远呢，和生活中的道理一样一样的！）
7、支持丰富的插件，当然你也可以自定义插件，再加上jq的文档也很丰富，对于程序员来说，是一件非常美好的事情
缺点
1.不能向后兼容。
每一个新版本不能兼容早期的版本。举例来说，有些新版本不再支持某些selector，新版jQuery却没有保留对它们的支持，而只是简单的将其移除。这可能会影响到开发者已经编写好的代码或插件。
2.插件兼容性。
与上一点类似，当新版jQuery推出后，如果开发者想升级的话，要看插件作者是否支持。通常情况下，在最新版jQuery版本下，现有插件可能无法正常使用。开发者使用的插件越多，这种情况发生的几率也越高。我有一次为了升级到jQuery 1.3，不得不自己动手修改了一个第三方插件。
3.多个插件冲突。
在同一页面上使用多个插件时，很容易碰到冲突现象，尤其是这些插件依赖相同事件或selector时最为明显。这虽然不是jQuery自身的问题，但却又确实是一个难于调试和解决的问题。
4.jQuery的稳定性。
jQuery没有让浏览器崩溃，这里指的是其版本发布策略。jQuery 1.3版发布后仅过数天，就发布了一个漏洞修正版1.3.1。他们还移除了对某些功能的支持，可能会影响许多代码的正常运行。我希望类似修改不要再出现。
5.对动画和特效的支持差。
在大型框架中，jQuery核心代码库对动画和特效的支持相对较差。但是实际上这不是一个问题。目前在这方面有一个单独的jQuery UI项目和众多插件来弥补此点。
```

### <p id="js-67"> 67. ★★★ ES6 class 关键字原理跟 function 什么区别？

```JS
// 答案：
function 可以用call apply bind 的方式 来改变他的执行上下文   
但是class 却不可以   class 虽然本质上也是一个函数  但是 其内（babel）部做了一层代理 来禁止了这种行为

关于构造器constructor
	在function定义的构造函数中，其prototype.constructor属性指向构造器自身
	在class定义的类中，constructor其实也相当于定义在prototype属性上
    
重复定义
	function会覆盖之前定义的方法
	class会报错
    
原型或者类中方法的枚举
    class中定义的方法不可用Object.keys(Point.prototype)枚举到
    function构造器原型方法可被Object.keys(Point.prototype)枚举到，除过constructor
    所有原型方法属性都可用Object.getOwnPropertyNames(Point.prototype)访问到
    

```

### <p id="js-68"> 68. ★★★ iframe 跨域问题，页面之间怎么传值？

```JS
// 答案：
一般有两个解决方案，一个是建立一个代理页面，通过代理页面传值，

另一个方法是通过H5的postMessage方法传值，今天用的是第二种。

首先，在父页面A中建立一个iframe，其中src要写好子页面B的地址，然后在A页面中写如下方法：

        var iframe = document.getElementById("onemap");
        var msg = {loginName:'arcgis',loginPassword:'Esri1234'};
        var childDomain = "https://geoplat.training.com";
        
        iframe.contentWindow.postMessage(msg,childDomain);

记住，childDomain与A的iframe的src地址不一样，childDomain是域，而src是域中的一个页面

msg是传输的信息，可以是字符串，也可以是对象。

上面的方法一定要写在一个函数中，并通过点击事件调用，如果希望iframe开始为空，点击后在设置src，

可以在设置src之后，通过setTimeout设置一定时间后在传输信息。

在子页面B中，通过对window添加事件获取传输过来的信息：

            window.addEventListener("message",function(obj){
               
                var name = obj.data.loginName;
                var password = obj.data.loginPassword;
                login.iframeChildLogin(name,password);
            },false);
这样就完成了从不同域的父页面向子页面传值的过程
```

### <p id="js-69"> 69. ★★★ 简述 commonJS、AMD 和 CMD

```JS
// 答案：
CommonJS导出模块的方法是exports，导入模块的是require，具体规范如下

1）如果一个JS文件中存在exports或require，该JS文件是一个模块

2）模块内的所有代码均为隐藏代码，包括全局变量、全局函数，这些全局的内容均不应该对全局变量造成任何污染

3）如果一个模块需要暴露一些API提供给外部使用，需要通过exports导出，exports是一个空的对象，你可以为该对象添加任何需要导出的内容

4）如果一个模块需要导入其他模块，通过require实现，require是一个函数，传入模块的路径即可返回该模块导出的整个内容

【注】CommonJS只是一个规范，相当于告诉你按什么标准制造汽车，但是具体怎么制造还是得看生产商。因此，有了规范以后，nodejs就去实现模块化了

AMD
AMD 是 RequireJS 在推广过程中对模块定义的规范化产出。
AMD 推崇依赖前置。

CMD
CMD 是 SeaJS 在推广过程中对模块定义的规范化产出。
CMD 推崇依赖就近
```

### <p id="js-70"> 70. ★★★ require.js 源码看过吗？怎么做到异步加载的

```JS
/**
  * Creates the node for the load command. Only used in browser envs.
  */
req.createNode = function (config, moduleName, url) {
    var node = config.xhtml ?
        document.createElementNS('http://www.w3.org/1999/xhtml', 'html:script') :
    document.createElement('script');
    node.type = config.scriptType || 'text/javascript';
    node.charset = 'utf-8';
    node.async = true;
    return node;
};

　　requirejs 导入模块的方式实际就是创建脚本标签，一切的模块都需要经过这个方法创建。requirejs 使用 onload 事件来处理回调函数：
```

### <p id="js-71"> 71. ★★ jQuery，$() 能传什么参数? html 代码怎么解析? 传 function 呢?

```JS
这个函数接收一个包含 CSS 选择器的字符串，然后用这个字符串去匹配一组元素。
jQuery 的核心功能都是通过这个函数实现的。 
jQuery中的一切都基于这个函数，或者说都是在以某种方式使用这个函数。这个函数最基本的用法就是向它传递一个表达式（通常由 CSS 选择器组成），然后根据这个表达式来查找所有匹配的元素。
默认情况下, 如果没有指定context参数，$()将在当前的 HTML document中查找 DOM 元素；如果指定了 context 参数，如一个 DOM 元素集或 jQuery 对象，那就会在这个 context 中查找。在jQuery 1.3.2以后，其返回的元素顺序等同于在context中出现的先后顺序。
```

### <p id="js-72"> 72. ★★ AMD 怎么加载文件的?

```JS
AMD 即Asynchronous Module Definition，中文名是异步模块定义的意思。它是一个在浏览器端模块化开发的规范
由于不是JavaScript原生支持，使用AMD规范进行页面开发需要用到对应的库函数，也就是大名鼎鼎RequireJS，实际上AMD 是 RequireJS 在推广过程中对模块定义的规范化的产出
requireJS主要解决两个问题
多个js文件可能有依赖关系，被依赖的文件需要早于依赖它的文件加载到浏览器
js加载的时候浏览器会停止页面渲染，加载文件越多，页面失去响应时间越长
看一个使用requireJS的例子
// 定义模块 myModule.js

define(['dependency'], function(){
    var name = 'Byron';
    function printName(){
        console.log(name);
    }

    return {
        printName: printName
    };
});

// 加载模块
require(['myModule'], function (my){
　 my.printName();
});
语法
requireJS定义了一个函数 define，它是全局变量，用来定义模块

define(id?, dependencies?, factory);
id：可选参数，用来定义模块的标识，如果没有提供该参数，脚本文件名（去掉拓展名）
dependencies：是一个当前模块依赖的模块名称数组
factory：工厂方法，模块初始化要执行的函数或对象。如果为函数，它应该只被执行一次。如果是对象，此对象应该为模块的输出值
在页面上使用require函数加载模块

require([dependencies], function(){});
require()函数接受两个参数

第一个参数是一个数组，表示所依赖的模块
第二个参数是一个回调函数，当前面指定的模块都加载成功后，它将被调用。加载的模块会以参数形式传入该函数，从而在回调函数内部就可以使用这些模块
require()函数在加载依赖的函数的时候是异步加载的，这样浏览器不会失去响应，它指定的回调函数，只有前面的模块都加载成功后，才会运行，解决了依赖性的问题。
```

### <p id="js-73"> 73. ★★ jQuery 怎么找到事件源元素

```JS
$(".btn").click(function(e){
    // e 就是事件对象
    e.target; // 事件的目标 dom
    e.currentTarget; // 事件处理程序正在处理事件的那个元素
    e.srcElement; // 事件的目标 ie
});
```

### <p id="js-74"> 74. ★★★★ 模板引擎原理

```JS
模板引擎是通过字符串拼接得到的

let template = 'hello <% name %>!'
let template = 'hello ' + name + '!'

字符串是通过new Function执行的

let name = 'world'
let template = `
  let str = 'hello ' +  name  + '!'
  return str
`
let fn = new Function('name', template)
console.log(fn(name)) // hello world!

将模板转换为字符串并通过函数执行返回
let template = 'hello <% name %>!'
let name = 'world'
function compile (template) {
  let html = template.replace(/<%([\s\S]+?)%>/g, (match, code) => {
    return `' + ${code} + '`
  })
  html = `let str = '${html}'; return str`
  return new Function('name', html)
}
let str = compile(template)
console.log(str(name)) // hello world!

函数只能接收一个name变量作为参数，功能太单一了，一般会通过对象来传参，with来减少变量访问。

with功能
let params = {
  name: '张三',
  age: 18
}
let str = ''
with (params) {
  str = `用户${name}的年龄是${age}岁`
}
console.log(str) // 用户张三的年龄是18岁

实现简单的模板引擎
let template = 'hello <% name %>!'
let name = 'world'
function compile (template) {
  let html = template.replace(/<%([\s\S]+?)%>/g, (match, code) => {
    return `' + ${code.trim()} + '`
  })
  html = `'${html}'`
  html = `let str = ''; with (params) { str = ${html}; } return str`
  return new Function('params', html)
}
let str = compile(template)
console.log(str({ name })) // hello world!
```

### <p id="js-75"> 75. ★★ map 和 foreach 的区别

```JS
forEach()方法不会返回执行结果，而是undefined。也就是说，forEach()会修改原来的数组。
map()方法会得到一个新的数组并返回。
```

### <p id="js-76"> 76. ★★★★ ES6 的新特性

```JS
1. const与let
2. 模板字符串
3. 解构赋值
4. 对象简写法
5. for...of循环
6. 展开运算符
7. 剩余参数(可变参数)
8. ES6箭头函数
9. 参数默认值
10.类和继承
11.模块化规范
```

### <p id="js-77"> 77. ★★ 2018/01/01 转换成 2018年/1月/1日

```JS
function fun(str){
    var date = new Date(str)
    return date.getFullYear()+'年/'+date.getMonth()+'月/'+date.getDate()+'日'
}
```

### <p id="js-78"> 78. ★★★ 0.1+0.2 等不等于 0.3？自己封装一个让他们相等的方法

```JS

在正常的数学逻辑思维中，0.1+0.2=0.3这个逻辑是正确的，但是在JavaScript中0.1+0.2！==0.3，这是为什么呢？这个问题也会偶尔被用来当做面试题来考查面试者对JavaScript的数值的理解程度。
 
　　在JavaScript中的二进制的浮点数0.1和0.2并不是十分精确，在他们相加的结果并非正好等于0.3，而是一个比较接近的数字 0.30000000000000004 ，所以条件判断结果为false。
  
方法1：设置一个误差范围值，通常称为”机器精度“，而对于Javascript来说，这个值通常是2^-52,而在ES6中，已经为我们提供了这样一个属性：Number.EPSILON，而这个值正等于2^-52。这个值非常非常小，在底层计算机已经帮我们运算好，并且无限接近0，但不等于0,。这个时候我们只要判断(0.1+0.2)-0.3小于Number.EPSILON，在这个误差的范围内就可以判定0.1+0.2===0.3为true。

function numbersequal(a,b){ 
    return Math.abs(a-b)<Number.EPSILON;
} 

方法2：转为整数运算
```

### <p id="js-79"> 79. ★★★ 跨域是什么？有哪些解决跨域的方法和方案？

```JS
什么是跨域?

所谓的同源是指，域名、协议、端口均为相同。
所谓的跨域，不同的域名、协议、端口皆为不同域

一个域与另一个域名、协议或者端口不同的域的之间访问都叫跨域

解决跨域的方法和方案：
1：通过服务端代理请求。如PHP，服务端语言php是没有跨域限制的，让服务器去别的网站获取内容然后返回给页面。

2：第二种：jsonp跨域
    1. jsonp跨域就是利用script标签的跨域能力请求资源
    2. jsonp与ajax没有半毛钱关系！！
    3. 浏览器的同源策略限制了js的跨域能力，但没有限制link img iframe script 的跨域行为
    实现方式：
    1. 利用js创建一个script标签，把json的url赋给script的scr属性，
    2. 把这个script插入到页面里，让浏览器去跨域获取资源
	3. JS先声明好回调函数，插入页面后会代为执行该函数，并且传入json对象为其参数。
    注意：
    1. jsonp只针对get请求
    2. script标签加载回来的资源会被当成js在全局执行

3：CORS 跨域资源共享(xhr2)
    CORS是一个W3C标准，全称是"跨域资源共享"（Cross-origin resource sharing）
    它允许浏览器向跨源服务器，发出XMLHttpRequest请求，从而克服了AJAX只能同源使用的限制
    整个CORS通信过程，都是浏览器自动完成，不需要用户参与
    对于开发者来说，CORS通信与同源的AJAX通信没有差别，代码完全一样
    实现CORS通信的关键是服务器，只要服务器实现了CORS接口，就可以跨源通信

4：nginx代理跨域
	通过nginx服务器转发跨域请求，达到跨域的目的
```

### <p id="js-80"> 80. ★★★ 什么是函数式编程？什么的声明式编程？

```JS
函数式编程：
函数式编程和声明式编程是有所关联的，因为他们思想是一致的：即只关注做什么而不是怎么做。但函数式编程不仅仅局限于声明式编程。
函数式编程最重要的特点是“函数第一位”，即函数可以出现在任何地方，比如你可以把函数作为参数传递给另一个函数，不仅如此你还可以将函数作为返回值。

声明式编程：
声明式编程是以数据结构的形式来表达程序执行的逻辑。它的主要思想是告诉计算机应该做什么，但不指定具体要怎么做。
SQL 语句就是最明显的一种声明式编程的例子，例如：
SELECT * FROM collection WHERE num > 5
除了 SQL，网页编程中用到的 HTML 和 CSS 也都属于声明式编程。
特点：
1：是它不需要创建变量用来存储数据。
2：不包含循环控制的代码如 for， while。
```

### <p id="js-81"> 81. ★★★ super() 是否必须执行？不执行怎么让它不报错？

```JS
非必须，
在 JavaScript 中，super 指的是父类的构造函数
如果想在构造函数中使用this，你必须首先调用super。 先让父类做完自己的事
不执行无法使用this，
	不报错的方法：
    	1：不使用this
        2：手动修正this
```

### <p id="js-82"> 82. ★★★ eventloop 渲染在哪一步？

```JS
任务队列
所有的任务可以分为同步任务和异步任务，同步任务，顾名思义，就是立即执行的任务，同步任务一般会直接进入到主线程中执行；而异步任务，就是异步执行的任务，比如ajax网络请求，setTimeout 定时函数等都属于异步任务，异步任务会通过任务队列( Event Queue )的机制来进行协调。

同步和异步任务分别进入不同的执行环境，同步的进入主线程，即主执行栈，异步的进入 Event Queue 。主线程内的任务执行完毕为空，会去 Event Queue 读取对应的任务，推入主线程执行。 上述过程的不断重复就是我们说的 Event Loop (事件循环)。

在事件循环中，每进行一次循环操作称为tick，通过阅读规范可知，每一次 tick 的任务处理模型是比较复杂的，其关键的步骤可以总结如下：

在此次 tick 中选择最先进入队列的任务( oldest task )，如果有则执行(一次)
检查是否存在 Microtasks ，如果存在则不停地执行，直至清空Microtask Queue
更新 render
主线程重复执行上述步骤
那么，什么是 microtasks ?规范中规定，task分为两大类, 分别是 Macro Task （宏任务）和 Micro Task（微任务）, 并且每个宏任务结束后, 都要清空所有的微任务,这里的 Macro Task也是我们常说的 task 。

(macro)task 主要包含：script( 整体代码)、setTimeout、setInterval、I/O、UI 交互事件、setImmediate(Node.js 环境)

microtask主要包含：Promise、MutaionObserver、process.nextTick(Node.js 环境)

整体 script 作为第一个宏任务进入主线程，遇到 console.log，输出 script start
遇到 setTimeout，其回调函数被分发到宏任务 Event Queue 中
遇到 Promise，其 then函数被分到到微任务 Event Queue 中,记为 then1，之后又遇到了 then 函数，将其分到微任务 Event Queue 中，记为 then2
遇到 console.log，输出 script end
至此，Event Queue 中存在三个任务，如下表：

宏任务	微任务
setTimeout	then1
-	then2
执行微任务，首先执行then1，输出 promise1, 然后执行 then2，输出 promise2，这样就清空了所有微任务
此时，所有的mircotask执行完毕，本轮事件循环结束，UI 开始 render，当 UI render 完毕，开始下一轮事件循环.
执行 setTimeout 任务，输出 setTimeout, 至此，输出的顺序是：script start, script end, promise1, promise2, setTimeout

UI渲染
根据HTML Standard，一轮事件循环执行结束之后，下轮事件循环执行之前开始进行 UI render。即：macro-task任务执行完毕，接着执行完所有的micro-task任务后，此时本轮循环结束，开始执行UI render。UI render完毕之后接着下一轮循环。
```

### <p id="js-83"> 83. ★★★★ 图片懒加载怎么实现？

```JS
原理：随着滚轮滚动，底部的图片会被不断地加载，从而显示在页面上，按需加载，当页面需要显示图片的时候才进行加载，否则不加载

1. 页面加载完成时记录每个img标签的src值的字符串，
2. 用鼠标滚轮判断图片是否出现在屏幕，如果是，则把记录的src值赋值给src属性
3. 然后让image的src来发起请求，获取对应的图片放置到DOM树的这个位置上，从而实现图片的页面渲染！
于是就可以知道，当进入页面的时候，其实我们已经把所有的图片的这个地址信息拿到了，图片懒加载的作用就是让这个图片的src按需发起请求，获取图片。
```

### <p id="js-84"> 84. ★★ for-in 循环会遍历出原型上的属性吗？怎么避免遍历到原型上的属性

```JS
使用 for in 循环遍历对象的属性时，原型链上的所有属性都将被访问

只遍历对象自身的属性，而不遍历继承于原型链上的属性，需要使用hasOwnProperty 方法过滤一下。
Object.prototype.say="cgl";
    var person ={
        age: 18
    };
    for (var key in person) {
        if(person.hasOwnProperty(key)){
            console.log(key, eval("person."+key));
        }
    } 
```

### <p id="js-85"> 85. ★★★ 简述call、apply、bind，call 和 apply哪个性能更好？

```JS
1、call()
call() 方法调用一个函数, 其具有一个指定的 this值和分别地提供的参数(参数的列表)。 第一个参数：在 fun 函数运行时指定的 this 值;如果指定了 null 或者 undefined 则内部 this 指向 window，后面的参数：指定的参数列表

var fn = function(arg1, arg2) {   
};
fn.call(this, arg1, arg2);

var  numbers = [5, 458 , 120 , -215 ]; 
var maxInNumbers = Math.max.call(Math,5, 458 , 120 , -215); //获取数组中的最大值458

2、apply()
apply()方法调用一个函数, 其具有一个指定的 this 值，以及作为一个数组（或类似数组的对象）提供的参数。apply() 与 call() 非常相似，不同之处在于提供参数的方式。apply() 使用参数数组而不是一组参数列表。

var fn = function(arg1, arg2) {   
};
fn.apply(this, [arg1, arg2])

var  numbers = [5, 458 , 120 , -215 ]; 
//umber 本身没有 max 方法，但是 Math 有，我们就可以借助 call 或者 apply 使用其方法。
var maxInNumbers = Math.max.apply(Math, numbers),   //获取数组中的最大值458
    
3、bind()
bind() 函数会创建一个新函数（称为绑定函数），新函数与被调函数（绑定函数的目标函数）具有相同的函数体（在 ECMAScript 5 规范中内置的call属性）。
当目标函数被调用时 this 值绑定到 bind() 的第一个参数，该参数不能被重写。绑定函数被调用时，bind() 也接受预设的参数提供给原函数。
一个绑定函数也能使用new操作符创建对象：这种行为就像把原函数当成构造器。提供的 this 值被忽略，同时调用时的参数被提供给模拟函数。

/* ------call 和 apply哪个性能更好？------ */
call的性能要比apply好一些，尤其是传递给函数的参数超过3个时所以后期开发的时候，可以使用call多一些
（传参数3个以内的话，call和apply性能差不多，超过3个以上call更好一些）
```

### <p id="js-86"> 86. ★★ ES6 箭头函数和普通函数有什么差异？

```JS
1. 相比普通函数更简洁的语法
2. 没有this,捕获其所在上下文的 this 值，作为自己的 this 值
3. 不能使用new,箭头函数作为匿名函数,是不能作为构造函数的,不能使用new
4. 不绑定arguments，用rest参数...解决
	let test3=(...a)=>{console.log(a[1])} //22
5. 使用call()和apply()调用:由于 this 已经在词法层面完成了绑定，通过 call() 或 apply() 方法调用一个函数时，只是传入了参数而已，对 this 并没有什么影响：
6. 箭头函数没有原型属性
7. 不能简单返回对象字面量
	let fun5 = ()=>({ foo: x })   //如果x => { foo: x }  //则语法出错
8. 箭头函数不能当做Generator函数,不能使用yield关键字
9. 箭头函数不能换行
	let a = ()
          =>1; //SyntaxError: Unexpected token =>
```

### <p id="js-87"> 87. ★★★ Promise 避免回调地狱的语法糖--实现链式调用的核心点是什么？

```JS
解决回调地狱的终极方法 async/await ES7的语法，可以通过 async/await让代码看起来像同步的
async异步 await等待
await 等待 就是当后面跟的是promise对象，就让他停止 ，先让里面的异步事情做完，在把结果返回给前面的新变量，在继续向后执行
他只生效当前作用域内部，也就是async函数内部。

实现链式调用的核心点:
在 then 中新创建的 Promise，它的状态变为 fulfilled 的节点是在上一个 Promise的回调执行完毕的时候。也就是说当一个 Promise 的状态被 fulfilled 之后，会执行其回调函数，而回调函数返回的结果会被当作 value，返回给下一个 Promise(也就是then 中产生的 Promise)，同时下一个 Promise的状态也会被改变(执行 resolve 或 reject)，然后再去执行其回调,以此类推下去…
```

### <p id="js-88"> 88. ★★★ 进程线程区别是什么？

```JS
什么是进程？什么是线程？
进程是系统中正在运行的一个程序，程序一旦运行就是进程。

进程可以看成程序执行的一个实例。进程是系统资源分配的独立实体，每个进程都拥有独立的地址空间。一个进程无法访问另一个进程的变量和数据结构，如果想让一个进程访问另一个进程的资源，需要使用进程间通信，比如管道，文件，套接字等。

一个进程可以拥有多个线程，每个线程使用其所属进程的栈空间。线程与进程的一个主要区别是，统一进程内的一个主要区别是，同一进程内的多个线程会共享部分状态，多个线程可以读写同一块内存（一个进程无法直接访问另一进程的内存）。同时，每个线程还拥有自己的寄存器和栈，其他线程可以读写这些栈内存。

线程是进程的一个实体，是进程的一条执行路径。

线程是进程的一个特定执行路径。当一个线程修改了进程的资源，它的兄弟线程可以立即看到这种变化。

进程和线程的区别体现在以下几个方面：
1.地址空间和其他资源（如打开文件）：进程间相互独立，同一进程的各线程间共享。某进程内的线程在其他进程内不可见。

2.通信：进程间通信IPC（管道，信号量，共享内存，消息队列），线程间可以直接独写进程数据段（如全局变量）来进程通信——需要进程同步和互斥手段的辅助，以保证数据的一致性。

3.调度和切换：线程上下文切换比进程上下文切换快得多。

4.在多线程OS中，进程不是一个可执行的实体。
```

### <p id="js-89"> 89. ★★★ 禁止事件冒泡，禁止默认事件

```JS
/*-----禁止事件冒泡:-----*/
function stopBubble(e) {
//如果提供了事件对象，则这是一个非IE浏览器
if ( e && e.stopPropagation )
    //因此它支持W3C的stopPropagation()方法
    e.stopPropagation();
else
    //否则，我们需要使用IE的方式来取消事件冒泡
    window.event.cancelBubble = true;
}

/*-----阻止浏览器的默认行为-----*/
function stopDefault( e ) {
    //阻止默认浏览器动作(W3C)
    if ( e && e.preventDefault )
        e.preventDefault();
    //IE中阻止函数器默认动作的方式
    else
        window.event.returnValue = false;
    return false;
}
```

### <p id="js-90"> 90. ★★ import export commonJS 对比区别

```JS
ES6和commonJS的一些区别

从语法的角度上看，ES6模块化的import 和 export 是一个内置的标识，而commonJS的module.exports 和 require 分别是js对象和方法。其ES6模块化和commonJS的实现方式不同。

1.ES6是在编译的时候导入文件，而commonJS是编译完成后，在通过require方法导入，并读取文件导出的文件，并返回一个module.exports对象

2.在ES6模块的内部this是问undefined，而commonJS的this为一个空对象

3.ES6模块输出的是一个引用，而commonJS模块输出的是一个值的引用
```

### <p id="js-91"> 91. ★★ 为什么 JavaScript 是单线程

```JS
js作为主要运行在浏览器的脚本语言，js主要用途之一是操作DOM。

举一个栗子，如果js同时有两个线程，同时对同一个dom进行操作，这时浏览器应该听哪个线程的，如何判断优先级？

为了避免这种问题，js必须是一门单线程语言
```

### <p id="js-92"> 92. ★★★ 使用箭头函数应该注意什么？

```JS
1. 不要在对象里面定义函数，对象里面的行数应该用传统的函数方法
2. 不要在对原型对象上定义函数，在对象原型上定义函数也是遵循着一样的规则
3. 不要用箭头定义构造函数
4. 不要用箭头定义事件回调函数
```

### <p id="js-93"> 93. ★★★ 你知道 ES6 中的 Generator 和 yiled 吗？在实际开发中使用过吗？

```JS
Generator 函数是 ES6 提供的一种异步编程解决方案
执行 Generator 函数会返回一个遍历器对象，可以依次遍历 Generator 函数内部的每一个状态
形式上，Generator函数是一个普通函数，但是有两个特征：
1. function关键字与函数名之间有一个星号
2. 函数体内部使用yield表达式，定义不同的内部状态

/*-----利用Generator函数，在对象上实现Iterator接口-----*/

function* iterEntries(obj) {
  let keys = Object.keys(obj);
  for (let i=0; i < keys.length; i++) {
    let key = keys[i];
    yield [key, obj[key]];
  }
}
 
let myObj = { foo: 3, bar: 7 };
 
for (let [key, value] of iterEntries(myObj)) {
  console.log(key, value);
}
```

### <p id="js-94"> 94. ★★★ Cookie、storage 的区别？什么时候使用？

```JS
区别：
1. cookie数据始终在同源的http请求中携带（即使不需要），即cookie在浏览器和服务器间来回传递。localStorage不会自动把数据发给服务器，仅在本地保存。

2. cookie数据还有路径（path）的概念，可以限制cookie只属于某个路径下。

3. 存储大小限制也不同，cookie数据不能超过4k，同时因为每次http请求都会携带cookie，所以cookie只适合保存很小的数据，如会话标识。localStorage 虽然也有存储大小的限制，但比cookie大得多，可以达到5M或更大。

4. 数据有效期不同，
    localStorage：始终有效，窗口或浏览器关闭也一直保存，因此用作持久数据；
    cookie只在设置的cookie过期时间之前一直有效，即使窗口或浏览器关闭。

5. WebStorage 支持事件通知机制，可以将数据更新的通知发送给监听者。

6. WebStorage 的 api 接口使用更方便。

使用场景：
localStorage可以用来统计页面访问次数。
cookie一般存储用户名密码相关信息，一般使用escape转义编码后存储。
```

### <p id="js-95"> 95. ★★★ map、fillter、reduce 各自有什么作用？

```JS
1：map 作用是生成一个新数组，遍历原数组，将每个元素拿出来做一些变换然后放入到新的数组中。
另外 map 的回调函数接受三个参数，分别是当前索引元素，索引，原数组

2：filter 的作用也是生成一个新数组，在遍历数组的时候将返回值为 true 的元素放入新数组，我们可以利用这个函数删除一些不需要的元素
和 map 一样，filter 的回调函数也接受三个参数，用处也相同。

3：reduce 可以将数组中的元素通过回调函数最终转换为一个值。
它接受两个参数，分别是回调函数和初始值，接下来我们来分解上述代码中 reduce 的过程
首先初始值为 0，该值会在执行第一次回调函数时作为第一个参数传入
回调函数接受四个参数，分别为累计值、当前元素、当前索引、原数组，后三者想必大家都可以明白作用，这里着重分析第一个参数
```

### <p id="js-96"> 96. ★★ JS的基本数据类型判断有什么方法？

```JS
1.typeof：
	typeof'';// string 有效
    typeof 1;// number 有效
    typeof Symbol();// symbol 有效
    typeof true;//boolean 有效
    typeof undefined;//undefined 有效
    typeof null;//object 无效
    typeof [] ;//object 无效
    typeof new Function();// function 有效
    typeof new Date();//object 无效
    typeof new RegExp();//object 无效
2.instanceof
    instanceof 是用来判断 A 是否为 B 的实例，表达式为：A instanceof B，如果 A 是 B 的实例，则返回 true,否则返回 false。 	   在这里需要特别注意的是：instanceof 检测的是原型
3.constructor
当一个函数 F被定义时，JS引擎会为F添加 prototype 原型，然后再在 prototype上添加一个 constructor 属性
4.toString
toString() 是 Object 的原型方法，调用该方法，默认返回当前对象的 [[Class]] 。这是一个内部属性，其格式为 [object Xxx] ，其中 Xxx 就是对象的类型。

对于 Object 对象，直接调用 toString()  就能返回 [object Object] 。而对于其他对象，则需要通过 call / apply 来调用才能返回正确的类型信息。
    Object.prototype.toString.call('') ;  // [object String]
    Object.prototype.toString.call(1) ;   // [object Number]
    Object.prototype.toString.call(true) ;// [object Boolean]
    Object.prototype.toString.call(Symbol());//[object Symbol]
    Object.prototype.toString.call(undefined) ;// [object Undefined]
    Object.prototype.toString.call(null) ;// [object Null]
    Object.prototype.toString.call(newFunction()) ;// [object Function]
    Object.prototype.toString.call(newDate()) ;// [object Date]
    Object.prototype.toString.call([]) ;// [object Array]
    Object.prototype.toString.call(newRegExp()) ;// [object RegExp]
    Object.prototype.toString.call(newError()) ;// [object Error]
    Object.prototype.toString.call(document) ;// [object HTMLDocument]
    Object.prototype.toString.call(window) ;//[object global] window 是全局对象 global 的引用
```

### <p id="js-97"> 97. ★★★ 构造函数、实例对象、原型对象三者的关系是什么？

![img](https://img-blog.csdn.net/20180914155910928?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM5MjQ3ODM1/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

### <p id="js-98"> 98. ★★★★★ JS中的常见设计模式以及应用场景？

```JS
1、单例模式
单例模式就是一个实例在整个网页的生命周期里只创建一次，后续再调用实例创建函数的时候，返回的仍是之前创建的实例。在实际开发中应用十分广泛，例如页面中的登录框，显示消息的提示窗
2、策略模式
策略模式是指将策略（算法）封装起来，策略的目的是将算法和使用分离开。
3、代理模式
代理模式很好理解，我们不能直接使用目标函数，而是通过调用代理函数来实现对目标函数的使用。
4、发布订阅模式
发布订阅模式在实际应用中非常常见，例如，我们在微信App上关注了某个公众号，当该公众号有新文章发布时，就会通知我们。
发布订阅模式定义了一种一对多的依赖关系，当“一”发生变化，通知多个依赖。
5、命令模式
所谓命令模式就是将下要执行的业务逻辑封装到一个函数或类中，不需要具体谁来执行该命令的
```

### <p id="js-99"> 99. ★★ 介绍下事件代理，主要解决什么问题

```JS
1. 绑定事件太多，浏览器占用内存变大，严重影响性能
2. Ajax出现，局部刷新盛行，每次加载完，都要重新绑定事件
3. 部分浏览器移除元素时，绑定的事件没有被及时移除，导致内存泄漏，严重影响性能
4. Ajax中重复绑定，导致代码耦合性过大，影响后期维护
```

### <p id="js-100"> 100. ★★★★  异步的解决方案有哪些？

```JS
1.回调函数callback
2.事件发布订阅
3.Promise
4.Generator
5.async/await
```

### <p id="js-101"> 101. ★★ new 的原理是什么？通过 new 的方式创建对象和通过字面量创建有什么区别？

```JS
new操作符的作用如下：
1.创建一个空对象
2.由this变量引用该对象
3.该对象继承该函数的原型
4.把属性和方法加入到this引用的对象中
5.新创建的对象由this引用，最后隐式地返回this。

区别:
字面量创建不会调用 Object构造函数, 简洁且性能更好;
```

### <p id="js-102"> 102. ★★ 数组去重的方法

```JS
/*
方法一：

双层循环，外层循环元素，内层循环时比较值

如果有相同的值则跳过，不相同则push进数组
*/
Array.prototype.distinct = function(){
 var arr = this,
  result = [],
  i,
  j,
  len = arr.length;
 for(i = 0; i < len; i++){
  for(j = i + 1; j < len; j++){
   if(arr[i] === arr[j]){
    j = ++i;
   }
  }
  result.push(arr[i]);
 }
 return result;
}
var arra = [1,2,3,4,4,1,1,2,1,1,1];
arra.distinct();    //返回[3,4,2,1]


/*
方法二：利用splice直接在原数组进行操作

双层循环，外层循环元素，内层循环时比较值

值相同时，则删去这个值

注意点:删除元素之后，需要将数组的长度也减1.
*/
Array.prototype.distinct = function (){
 var arr = this,
  i,
  j,
  len = arr.length;
 for(i = 0; i < len; i++){
  for(j = i + 1; j < len; j++){
   if(arr[i] == arr[j]){
    arr.splice(j,1);
    len--;
    j--;
   }
  }
 }
 return arr;
};
var a = [1,2,3,4,5,6,5,3,2,4,56,4,1,2,1,1,1,1,1,1,];
var b = a.distinct();
console.log(b.toString()); //1,2,3,4,5,6,56


/*
优点：简单易懂

缺点：占用内存高，速度慢

方法三：利用对象的属性不能相同的特点进行去重
*/
Array.prototype.distinct = function (){
 var arr = this,
  i,
  obj = {},
  result = [],
  len = arr.length;
 for(i = 0; i< arr.length; i++){
  if(!obj[arr[i]]){ //如果能查找到，证明数组元素重复了
   obj[arr[i]] = 1;
   result.push(arr[i]);
  }
 }
 return result;
};
var a = [1,2,3,4,5,6,5,3,2,4,56,4,1,2,1,1,1,1,1,1,];
var b = a.distinct();
console.log(b.toString()); //1,2,3,4,5,6,56


/*
方法四：数组递归去重

运用递归的思想

先排序，然后从最后开始比较，遇到相同，则删除
*/
Array.prototype.distinct = function (){
 var arr = this,
  len = arr.length;
 arr.sort(function(a,b){  //对数组进行排序才能方便比较
  return a - b;
 })
 function loop(index){
  if(index >= 1){
   if(arr[index] === arr[index-1]){
    arr.splice(index,1);
   }
   loop(index - 1); //递归loop函数进行去重
  }
 }
 loop(len-1);
 return arr;
};
var a = [1,2,3,4,5,6,5,3,2,4,56,4,1,2,1,1,1,1,1,1,56,45,56];
var b = a.distinct();
console.log(b.toString());  //1,2,3,4,5,6,45,56


//方法五：利用indexOf以及forEach
Array.prototype.distinct = function (){
 var arr = this,
  result = [],
  len = arr.length;
 arr.forEach(function(v, i ,arr){  //这里利用map，filter方法也可以实现
  var bool = arr.indexOf(v,i+1);  //从传入参数的下一个索引值开始寻找是否存在重复
  if(bool === -1){
   result.push(v);
  }
 })
 return result;
};
var a = [1,1,1,1,1,1,1,1,1,2,2,2,2,2,2,3,3,3,3,3,3,3,2,3,3,2,2,1,23,1,23,2,3,2,3,2,3];
var b = a.distinct();
console.log(b.toString()); //1,23,2,3
方法六：利用ES6的set

Set数据结构，它类似于数组，其成员的值都是唯一的。

利用Array.from将Set结构转换成数组

function dedupe(array){
 return Array.from(new Set(array));
}
dedupe([1,1,2,3]) //[1,2,3]
拓展运算符(...)内部使用for...of循环

1
2
3
let arr = [1,2,3,3];
let resultarr = [...new Set(arr)]; 
console.log(resultarr); //[1,2,3]
```

### <p id="js-103"> 103. ★★★★ 常见内存泄漏

```JS
1、静态集合类，如HashMap、LinkedList等等。如果这些容器为静态的，那么它们的生命周期与程序一致，则容器中的对象在程序结束之前将不能被释放，从而造成内存泄漏。简单而言，长生命周期的对象持有短生命周期对象的引用，尽管短生命周期的对象不再使用，但是因为长生命周期对象持有它的引用而导致不能被回收。

2、各种连接，如数据库连接、网络连接和IO连接等。在对数据库进行操作的过程中，首先需要建立与数据库的连接，当不再使用时，需要调用close方法来释放与数据库的连接。只有连接被关闭后，垃圾回收器才会回收对应的对象。否则，如果在访问数据库的过程中，对Connection、Statement或ResultSet不显性地关闭，将会造成大量的对象无法被回收，从而引起内存泄漏。

3、变量不合理的作用域。一般而言，一个变量的定义的作用范围大于其使用范围，很有可能会造成内存泄漏。另一方面，如果没有及时地把对象设置为null，很有可能导致内存泄漏的发生。

4、内部类持有外部类，如果一个外部类的实例对象的方法返回了一个内部类的实例对象，这个内部类对象被长期引用了，即使那个外部类实例对象不再被使用，但由于内部类持有外部类的实例对象，这个外部类对象将不会被垃圾回收，这也会造成内存泄露。

5、改变哈希值，当一个对象被存储进HashSet集合中以后，就不能修改这个对象中的那些参与计算哈希值的字段了，否则，对象修改后的哈希值与最初存储进HashSet集合中时的哈希值就不同了，在这种情况下，即使在contains方法使用该对象的当前引用作为的参数去HashSet集合中检索对象，也将返回找不到对象的结果，这也会导致无法从HashSet集合中单独删除当前对象，造成内存泄露
6、缓存泄漏
内存泄漏的另一个常见来源是缓存，一旦你把对象引用放入到缓存中，他就很容易遗忘，对于这个问题，可以使用WeakHashMap代表缓存，此种Map的特点是，当除了自身有对key的引用外，此key没有其他引用那么此map会自动丢弃此值
7、监听器和回调
内存泄漏第三个常见来源是监听器和其他回调，如果客户端在你实现的API中注册回调，却没有显示的取消，那么就会积聚。需要确保回调立即被当作垃圾回收的最佳方法是只保存他的若引用，例如将他们保存成为WeakHashMap中的键。
```

### <p id="js-104"> 104. ★★★ promise 常见方法和 all 和 race的应用场景

```JS
Promise.race（）：
race的用法：谁跑的快，以谁为准执行回调。

race的使用场景：比如我们可以用race给某个异步请求设置超时时间，并且在超时后执行相应的操作

Promise.all():
all的用法：谁跑的慢，以谁为准执行回调。

在前端的开发实践中，我们有时会遇到需要发送多个请求并根据请求顺序返回数据的需求
```

### <p id="js-105"> 105. ★★★ 介绍一下 ES6 中 Set, Map的区别？

```JS
Map
在JS中的默认对象的表示方式为{}，即一组键值对，但是键必须是字符串。
为了使用Number或者其他数据类型作为键，ES6规范引入了新的数据类型Map。
Map是一组键值对的结构，具有极快的查找速度。初始化Map需要一个二维数组，或者直接初始化一个空Map。
Map 对象是键值对集合，和 JSON 对象类似，但是 key 不仅可以是字符串还可以是其他各种类型的值包括对象都可以成为Map的键

Set
Set也是一组key的集合，与Map类似。但是区别是Set不存储value，并且它的key不能重复。
创建一个Set，需要提供一个Array作为输入，或者直接创建一个空Set：
重复元素会在Set中自动被过滤
Set 对象类似于数组，且成员的值都是唯一的
```

### <p id="js-106"> 106. ★★ 并行和并发的区别是什么？

```JS
并行意味着可以同时取得多个任务，并同时去执行所取得的这些任务。并行模式相当于将长长的一条队列，划分成了多条短队列，所以并行缩短了任务队列的长度

并发表示多个任务同时都要执行
```

### <p id="js-107"> 107. ★★★ 为什么操作 dom 慢？

```JS
DOM对象本身也是一个js对象，所以严格来说，并不是操作这个对象慢，而是说操作了这个对象后，需要经过跨流程通信和渲染线程触发的重新渲染，导致DOM操作慢
JS引擎和和渲染引擎的模块化设计，使得它们可以独立优化，运行速度更快，但是这种设计带来的后果就是DOM操作会越来越慢
```

### <p id="js-108"> 108. ★★★★ 插入几万个 dom ，如何实现页面不卡顿？

```JS
让创建插入节点的工作分批进行：
setTimeout(() => {
    // 插入十万条数据
    const total = 100000;
    // 一次插入 20 条，如果觉得性能不好就减少
    const once = 20;
    // 渲染数据总共需要几次
    const loopCount = total / once;
    let countOfRender = 0
    let ul = document.querySelector("ul");
    function add() {
        // 优化性能，插入不会造成回流
        const fragment = document.createDocumentFragment();
        for (let i = 0; i < once; i++) {
            const li = document.createElement("li");
            li.innerText = Math.floor(Math.random() * total);
            fragment.appendChild(li);
        }
        ul.appendChild(fragment);
        countOfRender += 1;
        loop();
    }
    function loop() {
        if (countOfRender < loopCount) {
            window.requestAnimationFrame(add);
        }
    }
    loop();
}, 0);
```

### <p id="js-109"> 109. ★★★ js中的常用事件绑定方法

```JS
1. 在DOM元素中直接绑定
2. 在JavaScript代码中绑定
3. 绑定事件监听函数
```

### <p id="js-110"> 110. ★ 简述 src 和 href 的区别？

```JS
src用于替换当前元素，href用于在当前文档和引用资源之间确立联系
```

### <p id="js-111"> 111. ★★★★ 你知道什么是原型吗？我们为什么要用原型呢？或者说原型为我们提供了什么？

```JS
什么是原型：
Javascript规定，每一个函数都有一个prototype对象属性，指向另一个对象（原型链上面的）。
prototype(对象属性)的所有属性和方法，都会被构造函数的实例继承。这意味着，我们可以把那些不变(公用)的属性和方法，直接定义在prototype对象属性上。

prototype就是调用构造函数所创建的那个实例对象的原型（proto）。

prototype可以让所有对象实例共享它所包含的属性和方法。也就是说，不必在构造函数中定义对象信息，而是可以直接将这些信息添加到原型中。

为什么要用原型：使用原型对象解决浪费内存
```

### <p id="js-112"> 112. ★★★ 你了解原型链吗 你能说说 prototype 与 __proto__ 的区别吗？

![img](https://pic1.zhimg.com/80/e83bca5f1d1e6bf359d1f75727968c11_1440w.jpg?source=1940ef5c)

```JS
1.对象有属性__proto__,指向该对象的构造函数的原型对象。
2.方法除了有属性__proto__,还有属性prototype，prototype指向该方法的原型对象。
```

### <p id="js-113"> 113. ★★★ ts 和 js 的区别

```JS
1.ts是静态类语言，可以做到声明即文档，js是动态类语言相对更灵活。
2.如用ts写一个button组件可以清晰的知道，ButtonProps如是否必传，可选，style是什么类型，disabled是什么类型，较js，ts更易于维护和拓展，可以做到代码即注释，避免一个月不见3，代码自己都忘记自己写了什么的尴尬，
4.ts对比js基础类型上，增加了 void/never/any/元组/枚举/以及一些高级类型
5.js没有重载概念，ts有可以重载
6.vscode/ide对ts有很友好的提示
7.ts更利于重构
```

### <p id="js-114"> 114. ★★★ 简述原生 js 发 ajax 的步骤

```JS
1.创建XMLHTTPRequest对象

2.使用open方法设置和服务器的交互信息

3.设置发送的数据，开始和服务器端交互

4.注册事件

5.更新界面
```

### <p id="js-115"> 115. ★★ 是否所有函数都有 prototype 一说？

```JS
1. 使用Function.prototype.bind创建的函数对象
function abc(){console.log('abc')}
var binded = abc.bind(null)
binded() //abc
console.log(binded.prototype) //undefined

2. 箭头函数也没有
var abc = ()=>{console.log('abc')}
abc() //abc
console.log(abc.prototype) //undefined
```

### <p id="js-116"> 116. ★★ 为什么 await 在 forEach 中不生效？如何解决？

```JS
lodash的forEach和[].forEach不支持await, forEach 只支持同步代码。

解决方法1：使用 for...of
解决方法2：使用 for循环
解决方法3：让orEach支持async await

forEach 在正常情况像下面这么写肯定是做不到同步的，程序不会等一个循环中的异步完成再进行下一个循环。原因很明显，在上面的模拟中，while 循环只是简单执行了 callback，所以尽管 callback 内使用了 await ，也只是影响到 callback 内部。

arr.myforeach(async v => {
    await fetch(v);
});
要支持上面这种写法，只要稍微改一下就好

Array.prototype.myforeach = async function (fn, context = null) {
    let index = 0;
    let arr = this;
    if (typeof fn !== 'function') {
        throw new TypeError(fn + ' is not a function');
    }
    while (index < arr.length) {
        if (index in arr) {
            try {
                await fn.call(context, arr[index], index, arr);
            } catch (e) {
                console.log(e);
            }
        }
        index ++;
    }
};


```

### <p id="js-117"> 117. ★ a 标签中，如何禁用 href 跳转页面或定位链接？

```html
<a href="#" onclick="return false;">return false;</a>
<a href="http://www.baidu.com" onclick="ds(event)">baidu</a>
<script>
	function ds(e){
		e.preventDefault();
	}
</script>
```

### <p id="js-118"> 118. ★★ 请描述一下 cookies，sessionStorage 和 localStorage 的区别？

```JS
不同点：

1.存储大小
cookie数据大小不能超过4k。
sessionStorage和localStorage 虽然也有存储大小的限制，但比cookie大得多，可以达到5M或更大。
2.有效时间
localStorage    存储持久数据，浏览器关闭后数据不丢失除非主动删除数据；
sessionStorage  数据在当前浏览器窗口关闭后自动删除。
cookie          设置的cookie过期时间之前一直有效，即使窗口或浏览器关闭
3. 数据与服务器之间的交互方式
cookie的数据会自动的传递到服务器，服务器端也可以写cookie到客户端
sessionStorage和localStorage不会自动把数据发给服务器，仅在本地保存。
```

### <p id="js-119"> 119. ★★★ instanceof的原理是什么？

```JS
// instanceof 可以正确的判断对象的类型，是通过判断对象的原型链中是不是能找到类型的 prototype。

function fn(left, right) {
    let prototype = right.prototype;
    left = left.__proto__;
    while (true) {
        if (left === undefined || left === null) {
            return false;
        }
        if (left === prototype) {
            return true;
        }
        left = left.__proto__;
    }
}
```

### <p id="js-120"> 120. ★★★ 用多种方法实现 JavaScript 继承

```JS
1、原型链继承
核心： 将父类的实例作为子类的原型
特点：
    1. 非常纯粹的继承关系，实例是子类的实例，也是父类的实例
    2. 父类新增原型方法/原型属性，子类都能访问到
    3. 简单，易于实现
缺点：

    1. 要想为子类新增属性和方法，必须要在new Animal()这样的语句之后执行，不能放到构造器中
    2. 无法实现多继承
    3. 来自原型对象的所有属性被所有实例共享（来自原型对象的引用属性是所有实例共享的）（详细请看附录代码： 示例1）
    4. 创建子类实例时，无法向父类构造函数传参
推荐指数：★★（3、4两大致命缺陷）

2、构造继承
核心：使用父类的构造函数来增强子类实例，等于是复制父类的实例属性给子类（没用到原型）
特点：
    1. 解决了1中，子类实例共享父类引用属性的问题
    2. 创建子类实例时，可以向父类传递参数
    3. 可以实现多继承（call多个父类对象）
缺点：
    1. 实例并不是父类的实例，只是子类的实例
    2. 只能继承父类的实例属性和方法，不能继承原型属性/方法
    3. 无法实现函数复用，每个子类都有父类实例函数的副本，影响性能
推荐指数：★★（缺点3）

3、实例继承
核心：为父类实例添加新特性，作为子类实例返回
特点：
	1.不限制调用方式，不管是new 子类()还是子类(),返回的对象具有相同的效果
缺点：

    1. 实例是父类的实例，不是子类的实例
    2. 不支持多继承
推荐指数：★★

4、拷贝继承

特点：支持多继承
缺点：
    1. 效率较低，内存占用高（因为要拷贝父类的属性）
    2. 无法获取父类不可枚举的方法（不可枚举方法，不能使用for in 访问到）
推荐指数：★（缺点1）

5、组合继承
核心：通过调用父类构造，继承父类的属性并保留传参的优点，然后通过将父类实例作为子类原型，实现函数复用
特点：
    1. 弥补了方式2的缺陷，可以继承实例属性/方法，也可以继承原型属性/方法
    2. 既是子类的实例，也是父类的实例
    3. 不存在引用属性共享问题
    4. 可传参
    5. 函数可复用
缺点：
	1. 调用了两次父类构造函数，生成了两份实例（子类实例将子类原型上的那份屏蔽了）
    
推荐指数：★★★★（仅仅多消耗了一点内存）

6、寄生组合继承
核心：通过寄生方式，砍掉父类的实例属性，这样，在调用两次父类的构造的时候，就不会初始化两次实例方法/属性，避免的组合继承的缺点

特点：堪称完美
缺点：实现较为复杂
推荐指数：★★★★★
```
