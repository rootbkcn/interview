# 目录

<a href="#node-1">★★★ 如何使用原生 Node.js 操做 cookie？</a>

<a href="#node-2">★★ 什么是 Node.js？我们在哪里使用它？</a>

<a href="#node-3">★★ 为什么要使用 Node.js？</a>

<a href="#node-4">★★★ Node.js 有哪些特点？</a>

<a href="#node-5">★★★ setImmediate 和 setTimeOut 区别在哪里?</a>

<a href="#node-6">★★★ 如何更新 Node.js 的版本?</a>

<a href="#node-7">★★ 为什么 Node.js 是单线程的？</a>

<a href="#node-8">★★ 什么是回调函数？</a>

<a href="#node-9">★★★ 什么叫做回调地狱？ 如何阻止回调地狱？</a>

<a href="#node-10">★★ Node.js 和 ajax 的区别是什么?</a>

<a href="#node-11">★★★ nextTick 和 setImmediate 的区别是什么？</a>

<a href="#node-12">★★ 请使用 Node.js 原生的 HTTP 模块创建一个 web Server。</a>

<a href="#node-13">★★★★ koa 中间件的实现原理</a>

<a href="#node-14">★★★ 请使用 Node.js 编写代码实现遍历文件夹并输出所有的文件名</a>

<a href="#node-15">★★★★ 图片上传到服务器的过程</a>

<a href="#node-16">★★★ token 存储在 localStorage 里，当过期时过期的 token 怎么处理？</a>

<a href="#node-17">★★★★★ koa 和 express 的区别</a>

<a href="#node-18">★★★ MySQL 和 MongoDB 的区别，他们都是怎么查询语句的，具体讲讲怎么查询的？</a>

<a href="#node-19">★★★★ 了解 eggjs 吗？</a>

<a href="#node-20">★★★ 什么是服务端渲染，服务端渲染的优点？</a>

<a href="#node-21">★★★ 如何在 Node.js 中操作 MongoDb 数据库</a>

<a href="#node-22">★★★ 谈谈 socket 的三种常见使用方式</a>

<a href="#node-23">★★★ 前后端数据交互的常见使用方式</a>

<a href="#node-24">★★★ Node.js 优缺点以及适用场景</a>

# Node.js 面试真题

### <p id="node-1">★★★ 如何使用原生 Node.js 操做 cookie？</p>

- 获取 cookie： req.headers.cookie
- 设置 cookie：
  res.writeHead(200, {
  'Set-Cookie': 'myCookie=test',
  'Content-Type': 'text/plain'
  })
  [参考链接](https://www.cnblogs.com/csygl/p/14525406.html)

### <p id="node-2">★★ 什么是 Node.js？我们在哪里使用它？</p>

- 是什么：Node.js 是一个基于 Chrome V8 引擎的 JavaScript 运行环境。是一个让 JavaScript 运行在服务器端的开发平台，它让 JavaScript 的触角伸到了服务器端。但与 PHP、JSP、.net 等相比，Node.js 跳过了 Apache、Naginx、Tomcat、IIS 等 HTTP 服务器，它不需要建设在任何服务器软件之上。
- 在哪里使用：Web 全栈开发、聊天室、Web 爬虫等 (?，不确定)

### <p id="node-3">★★ 为什么要使用 Node.js？</p>

- nodejs 会让我们的编程工作变得简单，它主要包含如下几点几个好处:

  1）. 执行快速
  2）. 永远不会阻滞。
  3）. 异步处理机制。
  4）. 避免并行所带来的问题。

### <p id="node-4">★★★ Node.js 有哪些特点？</p>

特点：单线程、事件驱动、非阻塞 I/O

### <p id="node-5">★★★ setImmediate 和 setTimeOut 区别在哪里?</p>

- setImmediate 和 setTimeOut 都是延迟加载。而当这两个定时器同时运行在主模块时，运行顺序是不一定的。setTimeOut 受进程性能的约束，有可能比 setImmediate 快，也有可能慢于 setImmediate。 而在 I/O 事件的回调中，setImmediate 方法的回调永远在 setTimeOut 的回调前执行。

### <p id="node-6">★★ 如何更新 Node.js 的版本?</p>

- npm install npm -g (在命令行中将 npm 在重新安装一遍，如需指定版本需要加上 @版本数字 )

### <p id="node-7">★★ 为什么 Node.js 是单线程的？</p>

- 回答一：怼：如果不幸遇到面试官问这个问题，你反问他 nodejs 为什么叫做 nodejs.
- 翻资料组织了一下，非官方，仅供参考：
  - 回答二：苟：您好，贵公司的面试题还挺有深度的，这让我越来越期待加入贵公司了。关于 ndoejs 是单线程的，刚好前段时间阅读过有关 node 的文章。node 的作者在设计之初选择语言时，评估过当时的流行语言，最终选择了存在多年在后端却一直没有市场的 js,正是 js 的不被关注，使得使用 js 没有额外阻力，而 js 在浏览器中有广泛的事件驱动方面的应用，正符合作者的喜好。于是 node 使用了 js 作为开发语言，node 的作者在开发时保持了 js 单线程的特点，所以 nodejs 是单线程的。
  - 这题太诡异，原谅我三句话说不清楚，手动狗头
  - [参考网址](https://www.kancloud.cn/simon_chang/srqcnodejs/199225)

### <p id="node-8">★★★ 什么是回调函数？</p>

- 回调函数是指用一个函数作为参数传入另一个函数，这个函数会在某个时机被调用。

### <p id="node-9">★★ 什么叫做回调地狱？ 如何阻止回调地狱？</p>

- 回调地狱：回调地狱是由嵌套的回调函数导致的。这样的机制会导致有些函数无法到达，并且很难维护。
- 阻止回调地狱
  1）Promise
  2）async/await
  3）Generator

### <p id="node-10">Node.js 和 ajax 的区别是什么?</p>

- Nodejs 和 ajax 都是通过 JavaScript 来表现的，但是他们的目的截然不同。
- Ajax 是设计用来动态的更新页面的某个区域，从而不需要更新整个页面。
- Nodejs 是用来开发客户服务器类型应用的。

### <p id="node-11">★★★ nextTick 和 setImmediate 的区别是什么？</p>

- nextTick 和 setImmediate 都是延迟加载。但是 nextTick 是放在当前队列的最后一个执行，setImmediate 是在下一个队列的队首执行

### <p id="node-12">★★ 请使用 Node.js 原生的 HTTP 模块创建一个 web Server。</p>

```js
/* 示例代码 */
const http = require('http')
const port = 3000

const server = http.createServer((req, res) => {
	res.statusCode = 200
	res.setHeader('Content-Type', 'text/plain')
	res.end('Hello World')
})

server.listen(port, () => {
	console.log(`Server is running on http://127.0.0.1:${port}/`)
})
```

### <p id="node-13">★★★★ koa 中间件的实现原理</p>

1. 每个中间件默认接受两个参数，第一个参数是 Context 对象，第二个参数是 next 函数。只要调用 next 函数，就可以把执行权转交给下一个中间件。
2. 如果中间件内部没有调用 next 函数，那么执行权就不会传递下去。
3. 多个中间件会形成一个栈结构，以“先进后出”的顺序执行。整个过程就像，先是入栈，然后出栈的操作。

### <p id="node-14">★★★ 请使用 Node.js 编写代码实现遍历文件夹并输出所有的文件名</p>

```js
const fs = require('fs')
const path = require('path')
const getAllFile = function (dir) {
	function traverse(dir) {
		fs.readdirSync(dir).forEach(file => {
			const pathname = path.join(dir, file)
			if (fs.statSync(pathname).isDirectory()) {
				traverse(pathname)
			} else {
				console.log(file)
			}
		})
	}
	traverse(dir)
}
```

### <p id="node-15">★★★★ 图片上传到服务器的过程</p>

- 前端业务
  - 根据后台接口发送请求，图片作为参数，需要带上一个 name 字段
- 后台业务

  - 后台接收图片可以使用 ndoe 的 fs、path 文件系统加上 multer 的 npm 包实现。主要思想是通过 multer 创建一个临时空间用来接收并存储前端发送过来的二进制图片数据。通过 fs 模块读取临时空间的数据，并使用 pipe 方法注入到 fs 模块创建 path 模块指向的服务器文件夹下

- 后台代码试例，express 环境

```js
var express = require('express')
var router = express.Router()
var fs = require('fs')
var path = require('path')
/* 用于处理非表单的文件数据流 */
var multer = require('multer')
// 配置数据流向的文件,绝对路径，相对于根目录
var upload = multer({ dest: 'upload/' })
// 创建一个接收为编码的二进制数据流的方法实例 接收 name 为 newimg 字段的上传文件，最大接收为 1
var cpUpload = upload.fields([{ name: 'newimg', maxCount: 1 }])

// 接口
router.post('/add', cpUpload, (req, res) => {
	// 前端发送请求后，服务器已经接受到了前端传递过来的图片数据，保存在 files 对象下
	// 加上 cpUpload，数据就会从这个方法所设置的地址流过来，生成一个本地临时空间，类似于虚拟 DOM
	// 获取这段数据
	var img = req.files.newimg[0]

	// fs 模块读取临时空间的数据
	var readStream = fs.createReadStream(img.path)
	// 设置图片存入的路径，并给文件名前面加上一个时间轴，防止命名重复
	var imgpath = `/cdn/${Date.now()}-${img.originalname}`
	// 创建一个写入图片数据的地址
	var writeStram = fs.createWriteStream(
		path.resolve(__dirname, `../public${imgpath}`)
	)
	// 设置一个 pipe 管道，将读取的数据解析并注入到写入地址
	readStream.pipe(writeStram)
	// 监听注入地址的 close 事件，表示注入完毕
	writeStram.on('close', () => {
		// 返回给前端一个图片地址
		res.json({ err: 0, msg: 'success', data: { img: imgpath } })
	})
})
module.exports = router
```

### <p id="node-16">★★★ token 存储在 localStorage 里，当过期时过期的 token 怎么处理？</p>

- 当前端进行页面跳转或者需要鉴权的操作时，会发送请求到后台，而 token 会跟随请求头一起发送，后台通过请求头接收到 token 时会进行判断，若是过期了，应该返回一个 401 的状态码给前端，前端接收到以后，应该重定向到登录页要求用户重新登陆。

### <p id="node-17">★★★★★ koa 和 express 的区别</p>

- 最大的区别在于语法，experss 的异步采用的是回调函数的形式，而 koa1 支持 generator + yeild，koa2 支持 await/async，无疑更加优雅。
- 中间件的区别，koa 采用洋葱模型，进行顺序执行，出去反向执行，支持 context 传递数据
  express 本身无洋葱模型，需要引入插件，不支持 context
  express 的中间件中执行异步函数，执行顺序不会按照洋葱模型，异步的执行结果有可能被放到最后，response 之前。
  这是由于，其中间件执行机制，递归回调中没有等待中间件中的异步函数执行完毕，就是没有 await 中间件异步函数
- 集成度区别
  express 内置了很多中间件，集成度高，使用省心，
  koa 轻量简洁，容易定制

### <p id="node-18">★★★ MySQL 和 MongoDB 的区别，他们都是怎么查询语句的，具体讲讲怎么查询的？</p>

- 区别

  - 数据库模型
    mysql 是关系型数据库，现在使用最多的数据存储技术
    mongodb 是非关系型数据库，并且是非关系型数据库中最像关系型的数据库
  - 存储方式
    mongodb-以类 JSON 的文档的格式存储
    mysql-不同引擎有不同的存储方式
  - 数据处理方式
    mongodb-基于内存，将热数据存放在物理内存中，从而达到高速读写
    mysql-不同引擎有自己的特点

- 查询语句
  - mongodb 的查询语句类似于 js 使用 api 的场景，通过 . 来调用，并传递参数来进行控制查询内容 如：查询 username 为张三，age 为 27 的数据
  ```js
  db.users.find({ username: '张三', age: 27 })
  ```
  - 而 mysql 则是标准的 sql 语句，同样查询代码如下：
  ```js
  select * from users where "username" = "张三" and age = 27
  ```

### <p id="node-19">★★★★ 了解 eggjs 吗？</p>

- 不了解
- eggjs 的特性
  提供基于 Egg 定制上层框架的能力
  高度可扩展的插件机制
  内置多进程管理
  基于 Koa 开发，性能优异
  框架稳定，测试覆盖率高
  渐进式开发

### <p id="node-20">★★★ 什么是服务端渲染，服务端渲染的优点？</p>

- 服务端渲染：页面渲染过程是在服务端完成，最终的 HTML 字符串，直接通过请求发送给客户端。
- 服务器端渲染的优势就是利于 SEO 优化，首屏加载快，因为客户端接收到的是完整的 HTML 页面。

### <p id="node-21">★★★ 如何在 Node.js 中操作 MongoDb 数据库</p>

- 引入 mongoose
- 使用 mongoose.connect()方法连接到 MongoDB 数据库
- 监听连接是否成功
- 然后通过 node，书写接口，对数据库进行增删改查

### <p id="node-22">★★★ 谈谈 socket 的三种常见使用方式</p>

- 第一种方式是 netSocket，主要使用的是 node 中的 net 模块。服务端通过 new net.createServer() 创建服务，使用 on('connection') 方法建立连接，在回调函数中即可获取到客户端发送的信息。客户端通过 new net.Socket() 创建 Socket，通过 connect 连接指定端口和域名后，即可调用 write 方法发送数据
- 第二种方式是 webSocket，服务端引入第三方插件 ws 创建 socket 服务，客户端使用 H5 新增 API new WebSocket 连接服务端，通过 send 方法发送数据，onmessage 方法接收数据
- 第三种方式是 socket.io，服务端引入 socket.io' 模块创建服务，客户端引入 socket.io.js' 文件，建立连接后，客户端和服务端都是通过 on 方法接收数据，都是使用 emit 方法发送数据。

### <p id="node-23">★★★ 前后端数据交互的常见使用方式</p>

- cookie：前端可以直接设置或获取 cookie，后端可以使用 req.set('set-cookie'， '')设置 cookie，在前端发送请求时通过 req 的 header 字段中获取 cookie
- 利用 AJAX，和 JQuery 中已经封装好的 $.ajax、$.post、$.getJSON 通过创建一个 XMLHttpRequest 对象，来进行前后端交互。
- 服务端渲染，浏览器请求到的内容可以通过后端加工一下，将数据直接渲染好，再返回给浏览器。

### <p id="node-24">★★★ Node.js 优缺点以及适用场景</p>

- 优点

  - Node.js 采用事件驱动、异步编程，为网络服务而设计。简单易学，可以很快上手做后端设计。
  - Node.js 非阻塞模式的 IO 处理给 Node.js 带来在相对低系统资源耗用下的高性能与出众的负载能力，非常适合用作依赖其它 IO 资源的中间层服务。
  - Node.js 轻量高效，可以认为是数据密集型分布式部署环境下的实时应用系统的完美解决方案。

- 缺点

  - 单线程，可靠性低，一旦这个进程崩掉，那么整个 web 服务就崩掉了。
  - 开源组件库质量参差不齐，更新快，向下不兼容
  - 不适合做企业级应用开发，特别是复杂业务逻辑的，代码不好维护，事务支持不是很好。

- 适用场景

  - 大量 Ajax 请求的应用，例如个性化应用，每个用户看到的页面都不一样，需要在页面加载的时候发起 Ajax 请求，NodeJS 能响应大量的并发请求。
  - 实时应用：如在线聊天，实时通知推送等等
  - 工具类应用：海量的工具，小到前端压缩部署，大到桌面图形界面应用程序

  - 总而言之，NodeJS 适合运用在高并发、I/O 密集、少量业务逻辑的场景。
