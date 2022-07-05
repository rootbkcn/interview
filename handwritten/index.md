# 目录

<a href="#hw-1">★★★ 手写代码：实现forEach map filter reduce</a>

<a href="#hw-2">★★★ 手写实现一个简易的 Vue Reactive</a>

<a href="#hw-3">★★★ 手写代码，监测数组变化，并返回数组长度</a>

<a href="#hw-4">★★★ 手写原生继承，并说出局限性？</a>

<a href="#hw-5">★★★★ 手写一个柯里化函数</a>

<a href="#hw-6">★★★ 手写一个反柯里化函数</a>

<a href="#hw-7">★★★★ 手写一个Promise</a>

<a href="#hw-8">★★★ 手写一个instanceOf</a>

<a href="#hw-11">★★★ 手写ajax</a>

<a href="#hw-12">★★★ 手写JSONP的原理和实现</a>

<a href="#hw-13">★★★★ 手写深拷贝</a>

<a href="#hw-14">★★★ 手写浅拷贝</a>

<a href="#hw-15">★★★★ 手写 bind</a>

<a href="#hw-16">★★★★ 手写 call</a>

<a href="#hw-17">★★★★ 手写 apply</a>

<a href="#hw-18">★★★ 手写模拟 object.create</a>

<a href="#hw-19">★★★ 手写模拟 Object.is</a>

<a href="#hw-20">★★★ 手写 new </a>

<a href="#hw-21">★★★ 手写对象扁平化</a>

<a href="#hw-22">★★★ 手写数组扁平化</a>

<a href="#hw-23">★★★ 手写数组去重 </a>

<a href="#hw-24">★★★ 手写模拟实现 async/await</a>

<a href="#hw-25">★★★★ 手写实现发布/订阅模式</a>

<a href="#hw-26">★★★★ 手写防抖</a>

<a href="#hw-27">★★★★ 手写节流</a>



# 手写代码面试真题

### <p id="hw-1">★★★ 手写代码：实现forEach map filter reduce</p>

```javascript
 // 1. ------_forEach--------
    // Array.prototype.forEach() 方法对数组的每个元素执行一次给定的函数。
    //  arr.forEach(callback(currentValue [, index [, array]])[, thisArg])
    Array.prototype._forEach = function (fn, thisArg) {
      if (typeof fn !== 'function') throw '参数必须为函数'
      if (!Array.isArray(this)) throw '只能对数组使用此方法'
      let arr = this
      for (let i = 0; i < arr.length; i++) {
        fn.call(thisArg, arr[i], i, arr)  //用call来改变fn里面this的指向
      }
    }
    //test
    // window.value = 0
    // let obj = { value: 1 }
    // let arr = ["_", "for", "each"]
    // arr._forEach(
    //   function (ele, index, arr) {
    //     console.log("ele, index, arr", ele, index, arr);
    //     console.log("this.vaule", this.value);
    //   }, obj)


    // 2. ------_map--------
    // Array.prototype.map() 方法创建一个新数组，其结果是该数组中的每个元素是调用一次提供的函数后的返回值。
    //  arr.map(callback(currentValue [, index [, array]])[, thisArg])
    Array.prototype._map = function (fn, thisArg) {
      if (typeof fn !== 'function') throw "参数必须是回调函数"
      if (!Array.isArray(this)) throw "只能为数组使用此方法"
      const arr = this      //将调用者(实例化的arr)赋值给arr
      const newArr = []
      for (let i = 0, len = arr.length; i < len; i++) {
        newArr.push(fn.call(thisArg, arr[i], i, arr))
        //将每次调用的回调函数fn的返回值push到新数组中
      }
      return newArr  //返回新数组
    }
    //test
    // window.value = 0
    // let obj = { value: 1 }
    // let arr = ["_", "for", "each"]
    // const newArr = arr._map(
    //   function (ele, index) {
    //     return ele + "你好" + index
    //   }, obj)
    // console.log(newArr);


    // 3. ------_filter--------
    // Array.prototype.map() 方法创建一个新数组, 其包含通过所提供函数实现的测试的所有元素。 
    //  arr.filter(callback(currentValue [, index [, array]])[, thisArg])
    Array.prototype._filter = function (fn, thisArg) {
      if (typeof fn !== 'function') throw "参数必须是回调函数"
      if (!Array.isArray(this)) throw "只能为数组使用此方法"

      const arr = this      //将调用者(实例化的arr)赋值给arr
      const newArr = []
      for (let i = 0, len = arr.length; i < len; i++) {
        if (fn.call(thisArg, arr[i], i, arr)) { //判断回调的返回值是否为true
          newArr.push(arr[i])
        }
      }
      return newArr  //返回新数组
    }
    //test
    // window.value = 0
    // let obj = { value: 1 }
    // let arr = ["_", "for", "each"]
    // const newArr = arr._filter(
    //   function (ele, index) {
    //     return ele == "for"
    //   }, obj)
    // console.log(newArr);

    //???????传入的数组这个参数的作用是???????


    // 4. ------_reduce--------
    // Array.prototype.map() 方法对数组中的每个元素执行一个由您提供的reducer函数(升序执行)，将其结果汇总为单个返回值。
    //  arr.reduce(callback(accumulator, currentValue[, index[, array]])[, initialValue])
    Array.prototype._reduce = function (_reducer, initialValue) {
      if (typeof _reducer !== 'function') throw "参数必须是回调函数"
      if (!Array.isArray(this)) throw "只能为数组使用此方法"
      if ((!this.length && !initialValue)) throw "请传入初始值或者给非空对象使用此方法"

      let arr = this    //将调用者(实例化的arr)赋值给arr
      let result = initialValue || arr[0]  //初始值
      for (let i = 0, len = arr.length; i < len; i++) {
        if (!initialValue && i == 0) continue // 如果提供了initialValue，则起始索引号为0，否则从索引1起始。
        result = _reducer(result, arr[i], i, this)
      }
      return result  //返回新数组
    }

    // //test
    // let arr = [1, 3, 4]
    // const Result = arr._reduce(function (accumulator, currentValue, index, array) {
    //   console.log(index);
    //   return accumulator + currentValue
    // }, 2)
    // console.log(Result);

```



### <p id="hw-2">★★★ 手写实现一个简易的 Vue Reactive</p>

```javascript
<body>
  <div id="app">
    hello
  </div>
  <script>
      
      
    // 模拟 Vue 中的 data 选项
    let data = {
      msg: 'hello'
    }

    // 模拟 Vue 的实例
    let vm = {}

    // 数据劫持：当访问或者设置 vm 中的成员的时候，做一些干预操作
    Object.defineProperty(vm, 'msg', {
      // 可枚举（可遍历）
      enumerable: true,
      // 可配置（可以使用 delete 删除，可以通过 defineProperty 重新定义）
      configurable: true,
      // 当获取值的时候执行
      get () {
        console.log('get: ', data.msg)
        return data.msg
      },
      // 当设置值的时候执行
      set (newValue) {
        console.log('set: ', newValue)
        if (newValue === data.msg) {
          return
        }
        data.msg = newValue
        // 数据更改，更新 DOM 的值
        document.querySelector('#app').textContent = data.msg
      }
    })

    // 测试
    vm.msg = 'Hello World'
    console.log(vm.msg)
  </script>
</body>

```



### <p id="hw-3">★★★ 手写代码，监测数组变化，并返回数组长度</p>

```javascript
//手写代码，监测数组变化，并返回数组长度
// 获取Array的原型，并创建一个新的对象指向这个原型
    // const arrayMethods = Object.create(Array.prototype)
    // 创建一个新的原型，这就是改造之后的数组原型
    const ArrayProto = []
    // 重新构建Array原型里面的虽有方法
    Object.getOwnPropertyNames(Array.prototype).forEach(method => {
      if (typeof Array.prototype[method] === "function") {
        ArrayProto[method] = function () {
          console.log("我已经监听到数组触发了" + method + "事件")
          let len = this.length
          let result = Array.prototype[method].apply(this, arguments)
          console.log(len, this.length);
          if (len !== this.length) return this.length
          return result
        }
      }
    })
    let list = [1, 2, 3]
    // 将数组的原型链指向新构造的原型
    list.__proto__ = ArrayProto
    // 执行push事件
    console.log(list.push(2), list.pop(2), list.slice(2), list.unshift(2));
```



### <p id="hw-4">★★★ 手写原生继承，并说出局限性？</p>

```javascript
//构造函数Parent和Child
function Parent() {
    this.animals = 'animals';
    this.show = function() {
        console.log(this.animals);
    }
}
Parent.prototype.pro = 'pro';
function Child() {
    this.dog = 'dog';
}

//prototype继承
// 这样直接将Parent.prototype赋给Child.prototype的继承方式不可取，因为在改变Child.prototype里的属性会同时改变Parent.prototype
Child.prototype = Parent.prototype; // 不能访问构造函数属性，只能访问原型

// Object.create(Parent.prototype)构造的对象是一个空对象且它的原型指向Parent.prototype，所以这里的Parent.prototype是空对象，链接到了Parent.prototype，并不会影响到Parent.prototype
Child.prototype = Object.create(Parent.prototype); // 不能访问构造函数属性，只能访问原型

// 这种继承方式是将实例化后的Parent对象赋给Child的prototype，既可以访问Parent构造函数里边的属性，也可以访问原型属性
Child.prototype = new Parent();

// 以上任一操作完成后这一步必须操作，是将Child的构造函数指向自身，否则在执行完继承之后，实例化的对象构造函数是Parent
Child.prototype.constructor = Child;


//call，apply构造函数继承
// 需要将Child改写如下，apply类似，但缺陷就是访问不到Parent.prototype的属性了
function Child() {
    Parent.call(this);
    this.dog = 'dog';
}
```



### <p id="hw-5">★★★★ 手写一个柯里化函数</p>

```javascript
//柯里化：固定部分参数，返回一个接受剩余参数的函数，也称为部分计算函数，目的是为了缩小适用范围，创建一个针对性更强的函数。核心思想是把多参数传入的函数拆成单参数（或部分）函数，内部再返回调用下一个单参数（或部分）函数，依次处理剩余的参数。
//好处： 入口单一，易于测试和复用  
//缺点：  函数嵌套多、占内存


function Curry(fn,...args){
    return (..._args)=>{
        return fn(...args,..._args))
    }
}


function V(l,w,h){
    return l*w*h
}

const hcy =Curry(V,10)
hcy(5,8)   //400
hcy(6,7)   //420
```



### <p id="hw-6">★★★ 手写一个反柯里化函数</p>

```javascript
//反柯里化，从字面讲，意义和用法跟函数柯里化相比正好相反，扩大适用范围，创建一个应用范围更广的函数。使本来只有特定对象才适用的方法，扩展到更多的对象。
Function.prototype.unCurrying = function() {
  const self = this
  return function(...rest) {
    return Function.prototype.call.apply(self, rest)
  }
}
```



### <p id="hw-7">★★★★ 手写一个Promise</p>

```javascript
class Promise{
  constructor(executor){
    this.state = 'pending';
    this.value = undefined;
    this.reason = undefined;
    this.onResolvedCallbacks = [];
    this.onRejectedCallbacks = [];
         
    try{  // 如果executor执行报错，直接执行reject
      executor(this.resolve, this.reject);
    } catch (err) {
      reject(err);
    }
  }
    
    //成功
    resolv(value){
      // state改变,resolve调用就会失败
      if (this.state === 'pending') {
        // resolve调用后，state转化为成功态
        this.state = 'fulfilled';
        // 储存成功的值
        this.value = value;
      }
    };
    //失败
    reject(reason) {
      // state改变,reject调用就会失败
      if (this.state === 'pending') {
        // reject调用后，state转化为失败态
        this.state = 'rejected';
        // 储存失败的原因
        this.reason = reason;
      }
    };
    
    //then方法
 	then(onFulfilled,onRejected) {
    // 声明返回的promise2
    let promise2 = new Promise((resolve, reject)=>{
      if (this.state === 'fulfilled') {
        let x = onFulfilled(this.value);
        // resolvePromise函数，处理自己return的promise和默认的promise2的关系
        resolvePromise(promise2, x, resolve, reject);
      };
      if (this.state === 'rejected') {
        let x = onRejected(this.reason);
        resolvePromise(promise2, x, resolve, reject);
      };
      if (this.state === 'pending') {
        this.onResolvedCallbacks.push(()=>{
          let x = onFulfilled(this.value);
          resolvePromise(promise2, x, resolve, reject);
        })
        this.onRejectedCallbacks.push(()=>{
          let x = onRejected(this.reason);
          resolvePromise(promise2, x, resolve, reject);
        })
      }
    });
    // 返回promise，完成链式
    return promise2;
  }
}


```



### <p id="hw-8">★★★ 手写一个instanceOf</p>

```javascript
function instanceOf(left,right){
    let proto = left.__proto__
    let prototype = right.prototype
    while(true){
        if(proto === null) return false
        if(proto === prototype) return true 
        proto = proto.__proto__;
    }
}
```



### <p id="hw-11">★★★ 手写ajax</p>

```javascript
//1.创建对象
let  xhq = new XMLHttpRequest()
//2.初始话http请求参数
xhq.open(methode, url, true)
//3.发送请求
xhq.send({
    username:'wzx'
})
//4.监听请求状态,执行对应的回调函数
xhq.onreadystatechange = function () {
    if ( xhq.readystate == 4 && xhq.status == 200 ) {
        // success 回调
        success(xhq.responseText)
    }  else if (xhq.readyState == 4 && xhq.status !== 200) {
        // error 回调
        error()
    }
}


//-----------完整实现-----------
function sendAjax(obj) {
    function splicStr(data) {// get方式传入时，将内容进行data内容进行拼接
        var str = ''
        for (var i in data) {
            str = i + '=' + data[i]
        }
        return str
    }
    
// 原生ajax实现 步骤分析
// 一、声明XMLHttpRequest, 为了兼容IE5、6需要使用ActiveXObject()
	let xhq = new XMLHttpRequest() // 创建对象
// 二、初始化HTTP请求参数， 只初始化并不会发送
    if (obj.method.toUpperCase() === 'GET') { // get方法
        xhq.open(obj.method, obj.url + '?' + splicStr(obj.data),  typeof obj.async === 'boolean'? obj.async : true) // 路径拼接
        xhq.send()// 三、发送此次请求
    }
    else if (obj.method.toUpperCase() === 'POST') { // post方法
        xhq.open(obj.method, obj.url, typeof obj.async === 'boolean'? obj.async : true)
        xhq.setRequestHeader("content-type","application/x-www-form-urlencoded") // 以表单提交
        xhq.send(obj.data)// 三、发送此次请求
    }
//四、监听发送
    xhq.onreadystatechange = function () {
        if ( xhq.readyState == 4 && xhq.status == 200 ) {
            // success 回调
            success(xhq.responseText)
        } else if (xhq.readyState == 4 && xhq.status !== 200) {
            // error 回调
            error()
        }
    }
}

sendAjax({
    url: 'your url',
    method: 'post',
    async: true,
    data: {
        username: 'xiong',
        pwd: '123'
    },
    success: function (data) {
        console.log(data)
    },
    error: function () {
        console.log('发生了错误')
    }
})
```



### <p id="hw-12">★★★ 手写JSONP的原理和实现</p>

```javascript
function jsonp(url,data,callback){
    var funcName = 'jsonp_'+Date.now()+Math.random().toString().substr(2, 5)
    //如果有其他参数需要拼接
    if(typeof data==='object'){
        var tmpArr = []
        for (let key in data){
            let value =data[key]
            tmpArr.push(key+'='+value)
        }
        data = tmpArr.join('&')
    }
    let script = document.createElement('script')
    script.src = url + '?' + data + '&callback= ' + funcName
    document.body.appendChild(script)
    window[funcName]= function (data){
        callback(data)
        //清除标签
        delete Window[funcName]
        document.body.removeChild(script)
    }
}


```



### <p id="hw-13">★★★★ 手写深拷贝</p>

```javascript
//乞丐版
function deepCopy(obj){
    return obj.JSON.Parse(JSON.Stringify(obj))
}

//面试够用版
function deepCopy(obj){
    if(typeof obj)
    if(typeof obj =='object'){//判断是否为复杂数据源类型
        var result = obj.constructor == Array?[]:{}  //数组还是对象
        for(let i in obj){
            result[i]= typeof obj[i] =='object'? deepCopy(obj[i]):obj[i]
        }
    }else{
        //简单数据类型 
        var result = obj;
    }
    return result
}


```



### <p id="hw-14">★★★ 手写浅拷贝</p>

```javascript
function clone(target) {
    if(target === null ) {
        return target
    }
	// 克隆 数组 和 对象
    let cloneTarget = Array.isArray(target) ? [] : {}
    for (const key in target) {
        if (target.hasOwnProperty(key)) {//判断是否是本身的属性
            cloneTarget[key] = target[key]
        }
    }
    return cloneTarget
}

```



### <p id="hw-15">★★★★ 手写 bind</p>

```javascript
Function.prototype.myBind = function(context) {
    if (typeof this !== 'function') {
        throw new TypeError('Error')
    }
    //返回一个绑定this的函数，这里我们需要保存this
    const _this = this
    const args = [...arguments].slice(1)
        //返回一个函数
    return function F() {
        //因为返回一个函数，我们可以new F()需要判断能当做构造函数吗
        if (this instanceof F) { //实例是F这个构造函数造出来的
            return new _this(...args, ...arguments)  
        }
        return _this.apply(context, args.concat(...arguments))
    }
}

```



### <p id="hw-16">★★★★ 手写 call</p>

```javascript
Function.prototype.myCall = function(context) {
    context=context||window //传入参数的话，就指定context为this指向，否则指定window
    context.fn = this
    const args = [...arguments].slice(1) //入参删除context
    const result = context.fn(...args)
    delete context.fn
    return result
}
```



### <p id="hw-17">★★★★ 手写 apply</p>

```javascript
Function.prototype.myApply = function(context) {
   context = context || window
   context.fn = this   //给传入的上下文对象添加一个fn方法，这个fn方法即为myApply调用者
   let result 
   if(arguments[1]){
       result = context.fn(...arguments[1])
   }else{
       result = context.fn()
   }
    delete context.fn
    return result
}

```



### <p id="hw-18">★★★ 手写模拟 object.create</p>

```
function _create (obj){
	function F(){}  //创建一个构造函数
	F.prototype = obj  //将构造函数的原型对象赋值
	return new F()
}
```



### <p id="hw-19">★★★ 手写模拟 Object.is</p>

```
function _is(x, y) {
    if (x === y) {
        //运行到1/x === 1/y的时候x和y都为0，但是1/+0 = +Infinity， 1/-0 = -Infinity, 是不一样的
        return x !== 0 || y !== 0 || 1 / x === 1 / y
    } else {
    	//NaN===NaN是false,这是不对的，我们在这里做一个拦截，x !== x，那么一定是 NaN, y 同理
    	//两个都是NaN的时候返回true
        return x !== x && y !== y
    }
}

console.log(is(+0, -0))
console.log(is(NaN, NaN))
```



### <p id="hw-20">★★★ 手写 new </p>

```javascript
//new的实现过程(实际上就是调用这个构造函数，同时将构造函数的prototype上的属性方法挂上去。)
//1. 新建一个对象
//2. 对象 继承 构造函数的 原型链
//3. 将构造函数的this指向这个对象
//4. 根据构造函数的返回值的返回结构
function myNew(fn){ 
    let obj = {} //定义空对象obj
    obj = Object.create(fn.prototype) //将传入的构造函数的prototype属性方法复制到obj里面
    let args = Array.prototype.slice.call(arguments,1)// 获取除去fn之外的参数
    //或者  [...arguments].slice(1)
    let result = fn.call(obj,...args)  // 调用传入的构造函数,矫正this为obj，并传入args
    return typeof result === 'object'||result instanceof Function? result : obj;
    //如果构造函数返回引用类型，直接返回，否则返回obj
}

class Foo{
    constructor(){
    this.name = 'ciel'
	this.arg = arguments[0]
    }
    callname(){
        console.log(this.name)
    }
}

// 测试
let test = myNew(Foo, 'hhh', '123', 'saf')
test.callName()
console.log(test.arg)


```



### <p id="hw-21">★★★ 手写对象扁平化</p>

```javascript
export function jsonFlatten(data) {
  var result = {}
  function recurse(cur, prop) {
    if (Object(cur) !== cur) {
      result[prop] = cur
    } else if (Array.isArray(cur)) {
      for (var i = 0, l = cur.length; i < l; i++) { recurse(cur[i], prop + '[' + i + ']') }
      if (l === 0) { result[prop] = [] }
    } else {
      var isEmpty = true
      for (var p in cur) {
        isEmpty = false
        recurse(cur[p], prop ? prop + '.' + p : p)
      }
      if (isEmpty && prop) { result[prop] = {} }
    }
  }
  recurse(data, '')
  return result
}

```



### <p id="hw-22">★★★ 手写数组扁平化</p>

```javascript
//第一种 正则表达式
function flatten(arr){
    let str = JSON.stringify(arr);
    return str.replace(/(\[\]))/g,'').split(',')
}
//第二种 递归
function flatten(arr, result = []) {
  if (!Array.isArray(arr)) {
    result.push(arr)
    return result
  }
  for (let value of arr) {
    flatten(value, result)
  }
  return result
}
//第三种 数组字符串方法
function flatten(arr) {
  return arr.toString().split(',').map(ele => parseInt(ele))
}

//第四种
function flatten(arr){
  while(arr.some(item => Array.isArray(item))){
    arr = [].concat(...arr);
  }
  return arr;
}

```



### <p id="hw-23">★★★ 手写数组去重 </p>

```javascript
//1.ES6的Set
  function unique(arr){
      ruturn Array.from(new Set(arr))   
  }
//2. 双层for循环
   function unique(arr) {
      let result = []
      for (let i = 0, len = arr.length; i < len; i++) { //第一层遍历
        let flag = false  //进行标记
        for (let k = i + 1, len = arr.length; k < len; k++) {
          if (arr[i] === arr[k]) {  //如果后面有重复的就跳过
            flag = true
            k = arr.length
          }
        }
        if (!flag) result.push(arr[i]) //没有重复的，添加到数组中
      }
      return result
    }
//3. 利用数组的indexOf方法 
    function unique(arr) {
      let result = []
      for (let i = 0, len = arr.length; i < len; i++) {
        if (result.indexOf(arr[i]) === -1) result.push(arr[i])
      }
      return result
    }
//4. 利用类似桶排序的方法
    function unique(arr) {
      let result = []   
      let bucket = [];  //创建一个桶
      for (let i = 0, len = arr.length; i < len; i++) {
        bucket[arr[i]] = 1   //将有些桶标记
      }
      for (key in bucket) { //取出有标记的桶的下标
        console.log(key);
        result.push(Number(key))
      }
      return result
    }
//5. 利用filter方法
  function unique(arr) {
      return arr.filter((ele, index) => (arr.indexOf(ele) === index)) //过滤
    }

//6. 利用map方法
    function unique(arr) {
      return arr.map((ele, index) => {
        if (arr.indexOf(ele) === index) return ele
      })
    }
//7.排序后进行数组
 function unique(arr) {
      arr.sort()
      let result = []
      arr.forEach((ele, index) => {
        if (ele !== arr[index + 1]) result.push(ele)
      })
      return result
    }
```



### <p id="hw-24">★★★ 手写模拟实现 async/await</p>

```javascript

```



### <p id="hw-25">★★★★ 手写实现发布/订阅模式</p>

```javascript
class Subject { //定义被观察者
  constructor() {
    this.observers = []
  }

  addObserver(observer) { //订阅
    this.observers.push(observer)
  }

  removerObserver(observer) {//取消订阅
    let index = this.observers.indexOf(observer)
    if (index !== -1) {
      this.observers.splice(index, 1)
    }

  }

  notify() {  //通知
    this.observers.forEach(observer => {
      observer.update()
    })
  }
}

class Observer { // 定义观察者
  update() {
    console.log('subject更新了');
  }
  subscribeTo(subject) {
    subject.addObserver(this)
  }
}

let subject = new Subject() //被观察者
let observer1 = new Observer()  //观察者
observer1.subscribeTo(subject) //观察者进行订阅
let observer2 = new Observer()  //观察者
observer2.subscribeTo(subject) //观察者进行订阅
subject.notify()

```



### <p id="hw-26">★★★★ 手写防抖</p>

```javascript
funtion debounce(fn,delay){
    let timer = null
    return ()=>{
        clearTimeout(timer)
        timer =  setTimeout(()=>(fn())
        ,delay)
    }
}

let a = debounce(()=>(console.log('防抖处理')),500)

function 点击事件（）{
    a()
}
```



### <p id="hw-27">★★★★ 手写节流</p>

```javascript
function throttle(fn, delay = 500) {
  let lastTime, time
  return function(){
   	let context = this;
    let args = [].slice.call(arguments);
    time = Date.now()
    if (!lastTime || time - lastTime > delay) {
      fn.apply(context)
      lastTime = time
    }
  }
}

function fn(){
    console.log('节流')
}

let a =  throttle(fn, 1000)

function 点击事件(){
    a()
}

```

