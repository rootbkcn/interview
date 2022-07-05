# 目录

<a href="#html-1">★★★ 什么是 `bundle`, 什么是 `chunk`，什么是`module`？</a>

<a href="#html-2">★★★ hash chunkhash contenthash三者区别</a>

<a href="#html-3">★★★ 你知道什么是脚手架吗？</a>

<a href="#html-4">★★★ 你们公司有自己的脚手架工具么，他是怎么工作的？</a>

<a href="#html-5">★★★ webpack的核心思想是什么</a>

<a href="#html-6">★★★ Loader和Plugin的区别</a>

<a href="#html-7">★★★ 有哪些常见的Loader和Plugin，简单聊一聊各自的作用</a>

<a href="#html-8">★★★ 说一下 Webpack 的热更新原理</a>

<a href="#html-9">★★★ 如何优化 Webpack 的构建速度</a>

<a href="#html-10">★★★ 自己写过Loader和Plugin么</a>

<a href="#html-11">★★★ 代码分割的本质是什么？有什么意义呢？</a>

<a href="#html-12">★★★ 说下 tree-shaking 的原理</a>

<a href="#html-13">★★★ babel原理</a>

<a href="#html-14">★★★ linux部署和windows sever服务器区别？</a>

<a href="#html-15">★★★ 你们公司项目发布流程是什么样的？</a>

<a href="#html-16">★★★ 前端资源发布路径怎么实现非覆盖式发布（平滑升级）？</a>

<a href="#html-17">★★★ SSR项目是如何发布的</a>

<a href="#html-18">★★★ 你有发布过自己的npm包吗？流程是怎样的？</a>

<a href="#html-19">★★★ 介绍下 npm 模块安装机制，为什么输入 pm install 就可以自动安装对应的模块？</a>

<a href="#html-20">★★★ 你会搭建私有的npm仓库吗？怎么搭建？</a>

<a href="#html-21">★★★ Webpack 为什么慢，如何进行优化</a>

<a href="#html-23">★★★ jenkins 上线流程</a>
前后端，运维都可以在上面任意配置，工程化管理。前端可视化打包，甚至一键工程上线，甚至可以把前端的功能打包成测试包给测试人员测试，甚至给非开发人员进行操作。

<a href="#html-24">★★★ webpack 中 loader 和 plugins 的区别</a>

<a href="#html-25">★★★ 什么是长缓存，在webpack中如何做到长缓存优化？</a>

<a href="#html-26">★★★ 使用git上传的时候，会出现那些冲突，怎么解决这些冲突？</a>

<a href="#html-27">★★★ 什么是组件？什么是模块化？有什么区别？</a>

<a href="#html-28">★★★ 你们公司有自己的脚手架工具么，他是怎么工作的？</a>




# 前端工程化面试真题

<p id="html-1">★★★ 什么是 `bundle`, 什么是 `chunk`，什么是`module`？</p>

##### 什么是module

module是我们经常所说的模块，不管是esModule(import/export或export default)、CommonJs(require/module.exports)、AMD(依赖前置require(['Ma','Mb'],(a,b)=>_/define({key:value}))都属于module

##### 什么是chunks
chunks是webpack依据module间的引用关系通过代码分割生成的不同chunk文件，同时wenpack也可对chunk文件做些一些操作（如加chunkname）
##### 什么是bundle

bundle是webpack最终经过编译输出output的文件集合，他可以包含多个经过加载和编译后的chunk文件，由于bundle是经过加载和编译的最终源文件，所以直接可以在浏览器运
<p id="html-2">★★★ hash chunkhash contenthash三者区别</p>
在了解这三者的区别之前首先需要清楚一个概念，构建项目为何需要缓存，因为webpack实现热更新后，每次更新都会将我们的业务代码和第三方库的代码同时打包更新，降低构建效率，所以需要使用webpack的optimization.splitChunks分离第三方库和业务代码，公共模块直接缓存就不要每次更新都消耗资源

#####  hash 
是跟整个项目构建有关，只要项目的文件内容发生变化，整个项目构建的hash值都会更改，并且全部文件都共用相同的hash值,所以一旦修改任何一个文件，整个项目的文件缓存都将失效
#####  chunkhash
为避免整个项目的文件因为hash不断变化而导致缓存失效，需要chunkhash，chunkhash根据模块之间引入关系生成不同的chunk文件的同时生成对应的hash值，而不再是所有文件共用同一个hash值
如果需要对chunkhash做进一步优化就需要使用上述所说的optimization.splitChunks或者dllPlugin，可以将公共库以及业务代码抽离而直接缓存公共库，只要公共库只要不发生版本迭代，那么公共库的chunkhash就一直不会变。
##### contenthash
contenthash又是在chunkhash的进一步优化，webpack在根据模块引入关系生成对应的chunk文件，模块可能引入index.css以及index.js,那么当index.js变化而index.css没有变化，则项目更新时inedx.css也会被迫重新加载，导致资源损耗

+ 优化方法：
我们可以使用extract-text-webpackplugin(webpack4)里的contenthash值，保证引入css文件所在的模块只要css文件内容不变，就不会重复构建css
+ 配置方法
```js
var extractTextPlugin = require('extract-text-webpack-plugin')
  plugins:[
   new extractTextPlugin('../css/bundle.[name].[contenthash].css')
 ]
```
补充：webpack5已经使用mini-css-extract-plugin代替extractTextPlugin，感兴趣的了解一下
<p id="html-3">★★★ 你知道什么是脚手架吗？</p>

##### 脚手架的概念和作用：
就是拥有完整的开发环境，帮助我们快速的生成一套既定的项目架构、文件、配置。使用者只需要专注自己的业务代码即可，不需要使用者单独配置
##### 脚手架的构成：
常见的脚手架的开发环境主要分为三种模式：生产模式，开发模式，测试模式。以及需要配置完整的路由系统(vue-router,react-router-dom)，和状态管理系统(vuex,redux)才能保证开发环境的完整性
##### 常见的脚手架：
Vue-cli,Creat-React-app,umi-app


<p id="html-4">★★★ 你们公司有自己的脚手架工具么，他是怎么工作的？</p>
我们公司有自己的脚手架工具

<p id="html-5">★★★ webpack的核心思想是什么</p>

##### 万物皆模块：
在webpacck的世界中，其他任何资源都可以当做模块的方式引入
##### 代码分割：
webapp 的优化关键在于代码体积，当应用体积增大，实现代码的按需加载是刚需，这也是 webpack 出现的根本原因
##### 可定制化：
任何一个工具都不可能解决所有问题，提供解决方案才是最可行的，webpack基于可定制化的理念构建，通过插件系统，配置文件，可实现大型项目的定制需求
<p id="html-6">★★★ Loader和Plugin的区别</p>

###### loader是一个转换器

+ 1、用于对模块源码文件的预编译和转换，loader描述了webpack如何处理非javascript模块。
+ 2、没有loader，构建的打包过程无法顺利完成
+ 3、loader作用在打包前
+ 4、将A文件转换为B文件，操作的是文件，比如将A.scss转换为A.css，是单纯的文件转换过程

###### Plugin是插件扩展器

+ 1、plugin构建过程更完整的补充和优化，如使用new UglifyJsPlugin(),new CssMinimizerPlugin()压缩js和css
+ 2、没有plugin，文件的打包过程可以完成
+ 3、plugin作用于整个打包过程，
+ 4、针对webpack的打包过程，他不直接操作文件，而是基于事件机制工作，会监听webpack打包过程的事件钩子，执行任务，通过事件钩子拦截webpack的执行。

<p id="html-7">★★★ 有哪些常见的Loader和Plugin，简单聊一聊各自的作用</p>

#### 常用Loader
+ babel-loader使得webpack可以通过babel转译js代码
+ css-loader转译css文件，会对@import和url()进行处理，就像js解析import/require一样,
+ style-loadder把css-loader转译后的结果插入输出的脚本中显示样式效果
+ sass-loader/less-loader都是用来预编译和转换.sass/.less文件
+ file-loader将一个文件中的加载文件、图片import/require()解析为url,并且将文件发送到输出文件夹，并返回文件的publicURL，
+ url-loader是file-loader功能的扩展和封装，options选项中可以设置对引用图片大小的限制，如果大于等于限制，默认使用file-loader并传递所有参数，如果小于，则默认使用base64编码并返回输出，
```js
  // 示例
      use: [
          {
            loader: 'url-loader',//等价写法use:'url-loader'?limit=1024
            options: {
              limit: 8192,
            }
          },
      ]
```
#### 常用Plugin
+ DllPlugin:作用和optimization.splitChunk的作用相似，都是用某种方法拆分bundles,可以大幅度提升构建速度
+ SplitChunksPlugin：分离公共的第三方模块以及业务代码
+ extract-text-webpackplugin: extract-text-webpackplugin(webpack4)里的contenthash值，保证引入css文件所在的模块只要css文件内容不变，就不会重复构建css
+ MiniCssExtractPlugin：抽离css文件，删除和压缩css代码，本插件是extract-text-webpackplugin插件的webpack5的升级用法，可以实现contenthash
+ HtmlWebpackPlugin：
```
1、为html文件动态引入外部资源给script、link添加compile(编译)后的hash，防止引用缓文件问题
2、可以生成创建html入口文件，比如单页面可以生成一个html文件入口，多页面生成多个html
```
+ UglifyjsWebpackPlugin：删除和压缩js文件
+ EslintWebpackPlugin:作用类似eslint-loader(eslint-loader已被弃用)，审查代码是否符合编码规范和统一，审查代码是否存在语法错误
+ CssMinimizerWebpackPlugin:这个插件使用 cssnano 优化和压缩 CSS。
<p id="html-8">★★★ 说一下 Webpack 的热更新原理吧</p>

 首先热更新所更新的内容是基于hash值发生改变的文件

 更新的原理方法是webpack-dev-server启动本地服务，源码在webpack-dev-server的package.json中的bin命令，可以找到命令的入口文件bin/webpack-dev-server.js。注：源码附在最后
  
这段代码主要完成了
+ 一、webpack启动后，完成webpack所有编译工作，以及监听本地文件变化
+ 二、使用express框架启动本地服务让浏览器可以请求本地的静态资源。
+ 三、本地服务启动后，再启动websocket服务，通过websocket，可以建立本地服务和浏览器的双向通信，这样就可以实现本地文件变化，立马告知浏览器可以更新了

```js
// node_modules/webpack-dev-server/bin/webpack-dev-server.js
// 生成webpack编译主引擎 compiler
let compiler = webpack(config);
// 启动本地服务
let server = new Server(compiler, options, log);
server.listen(options.port, options.host, (err) => {
    if (err) {throw err};
});
// node_modules/webpack-dev-server/lib/Server.js
class Server {
    constructor() {
        this.setupApp();
        this.createServer();
    }
    
    setupApp() {
        // 依赖了express
    	this.app = new express();
    }
    
    createServer() {
        this.listeningApp = http.createServer(this.app);
    }
    listen(port, hostname, fn) {
        return this.listeningApp.listen(port, hostname, (err) => {
            // 启动express服务后，启动websocket服务
            this.createSocketServer();
        }
    }                                   
}
```
<p id="html-9">★★★ 如何优化 Webpack 的构建速度</p>

##### 不要让loader做太多事情，以babel-loader为例

最常见的优化方式是，用include或exclude来帮助我们避免不必要的转译,除此之外，如果我们开启缓存转译结果缓存至文件系统，则至少可以提升两倍工作效率
```js
use:{
  exclude:/(node_module|bower_components)/,
  loader:'babel-loader?cacheDirectory=true'
  }
```
##### 不要放过第三方库，以node_modules为代表，庞大又不可或缺。推荐使用DllPlugin
用DllPlugin处理文件，要分两步走：
+ 基于dll专属的配置文件，打包dll库
```js
const path = require('path')
const webpack = require('webpack')

module.exports = {
    entry: {
      // 依赖的库数组
      vendor: [
        'prop-types',
        'babel-polyfill',
        'react',
        'react-dom',
        'react-router-dom',
      ]
    },
    output: {
      path: path.join(__dirname, 'dist'),
      filename: '[name].js',
      library: '[name]_[hash]',
    },
    plugins: [
      new webpack.DllPlugin({
        // DllPlugin的name属性需要和libary保持一致
        name: '[name]_[hash]',
        path: path.join(__dirname, 'dist', '[name]-manifest.json'),
        // context需要和webpack.config.js保持一致
        context: __dirname,
      }),
    ],
}
// 编写完成之后，运行这个配置文件，我们的 dist 文件夹里会出现这样两个文件：
```
+ 基于 webpack.config.js 文件，打包业务代码
```js
const path = require('path');
const webpack = require('webpack')
module.exports = {
  mode: 'production',
  // 编译入口
  entry: {
    main: './src/index.js'
  },
  // 目标文件
  output: {
    path: path.join(__dirname, 'dist/'),
    filename: '[name].js'
  },
  // dll相关配置
  plugins: [
    new webpack.DllReferencePlugin({
      context: __dirname,
      // manifest就是我们第一步中打包出来的json文件
      manifest: require('./dist/vendor-manifest.json'),
    })
  ]
}

```
其中SplitChunksPlugin也可以将公共模块和业务代码抽离成chunks，热更新时就不需要再更新公共模块的内容了，区别在于他每次构建时都会重新构建一次vender，而DllPlugin一次生成vender，终生使用，效率更高)
##### 删除和压缩优化
粗粒度删除压缩：tree-shaking可以实现删除项目中未被引用的代码
原理：
```js
//test.js
export const a =1;
export const b = 2;
// main.js
import {a} from './test.js'
```
对于以上情况，test文件中的变量b如果没有在项目中使用的话，就不会被打包到文件中
使用：
在webpack4中，开启生产环境就会自动开启这个优化功能，也可以手动的引入ModuleConcatenationPlugin的支持
细粒度删除压缩： UglifyjsWebpackPlugin和MiniCssExtractPlugin：删除和压缩js文件和css文件
##### 将loader由单进程转为多进程构建
 Happypack--将loader由单进程转为多进程,进程是程序运行的数据集合，是系统资源分配基本单位，一般情况下单核cpu只有一个单进程，多核cpu在node的cpu利用率不足的情况下才会由单进程转为多进程。而Happypack帮我们做了这个事儿。多核并发，最大限度使用多核cpu的作用。大大提升效
##### 可视化工具的使用，找出导致文件体积过大的原因
推荐使用webpack-bundule-analyzer,配置方法和普通的 plugin 无异，它会以矩形树图的形式将包内各个模块的大小和依赖关系呈现出来

<p id="html-10">★★★ 自己写过Loader和Plugin么</p>

##### 自定义Plugin
Webpack通过Plugin机制让其更加灵活，以适应各种应用场景。在Webpack运行的生命周期中会广播出许多事件，Plugin可以监听这些事件，在合适的时机通过Webpack提供API改变输出结果

最简单的Plugin的代码
```js
class BasicPlugin{
  // 在构造函数获取用户传给该插件的配置
  constructor(options){
    
  }
  // Webpack 会调用 BasicPlugin 实例的 apply 方法给插件实例传入 compiler 对象
  apply(compiler){
    compiler.plugin('compilation',function(compilation){

    })
  }
}
// 导出plugin
module.export = BasicPlugin;
// plugin的使用
const BasicPlugin= require('./BasicPlugin.js')
```
+ 插件的执行过程
+ 执行 new BasicPlugin(options) 初始化一个 BasicPlugin 获得其实例。
+ 初始化 compiler 对象后，再调用 basicPlugin.apply(compiler) 给插件实例传入 compiler 对象
+ 获取到 compiler 对象后，就可以通过 compiler.plugin(事件名称, 回调函数) 监听到 Webpack 广播出来的事件，并且可以通过compiler去操作webpack
#### Compiler 和 Compilation
在开发 Plugin 时最常用的两个对象就是 Compiler 和 Compilation，它们是 Plugin 和 Webpack 之间的桥梁。 Compiler 和 Compilation 的含义如下：
+ Compiler 对象包含了 Webpack 环境所有的的配置信息，包含 options，loaders，plugins 这些信息，这个对象在 Webpack 启动时候被实例化，它是全局唯一的，可以简单地把它理解为 Webpack 实例；
+ Compilation 对象包含了当前的模块资源、编译生成资源、变化的文件等。当 Webpack 以开发模式运行时，每当检测到一个文件变化，一次新的 Compilation 将被创建。Compilation 对象也提供了很多事件回调供插件做扩展。通过 Compilation 也能读取到 Compiler 对象。
compiler事件钩子:
![](.\compiler.png)
compilation事件钩子
![](.\compilation.png)
#### 事件流
Webpack 的事件流机制应用了观察者模式，和 Node.js 中的 EventEmitter 非常相似。Compiler 和 Compilation 都继承自 Tapable，可以直接在 Compiler 和 Compilation 对象上广播和监听事件，方法如下：
```js
/**
* 广播出事件
* event-name 为事件名称，注意不要和现有的事件重名
* params 为附带的参数
*/
compiler.apply('event-name',params);

/**
* 监听名称为 event-name 的事件，当 event-name 事件发生时，函数就会被执行。
* 同时函数中的 params 参数为广播事件时附带的参数。
*/
compiler.plugin('event-name',function(params) {

});
// 同理，compilation.apply 和 compilation.plugin 使用方法和上面一致。
```
#### 监听文件变化
Webpack 会从配置的入口模块出发，依次找出所有的依赖模块，当入口模块或者其依赖的模块发生变化时， 就会触发一次新的 Compilation
在开发插件时经常需要知道是哪个文件发生变化导致了新的 Compilation，为此可以使用如下代码：
```js
// 当依赖的文件发生变化时会触发 watch-run 事件
compiler.plugin('watch-run', (watching, callback) => {
    // 获取发生变化的文件列表
    const changedFiles = watching.compiler.watchFileSystem.watcher.mtimes;
    // changedFiles 格式为键值对，键为发生变化的文件路径。
    if (changedFiles[filePath] !== undefined) {
      // filePath 对应的文件发生了变化
    }
    callback();
});

```
##### 自定义loader
一个用于替换的loader。替换原来JS代码中的name。
webpack.config.js
```js
const path = require('path');
// 先看看怎么用
module.exports = {
    //...
    module: {
        rules: [
            { 
                test: /\.js$/, 
                use: [{ 
                    // 本地引用loader
                    loader: path.resolve('./replace-loader'),
                    options: {
                        // 通过配置传入words来替换NAME为wei
                        words: 'wei'
                    }
                }]
            }
        ]
    }
};

```
replace-loader.js
```js
// loader-utils是专门用于自定义loader时的一些工具函数
const { getOptions } = require('loader-utils');

module.exports = function(source) {//参数是我们的需解析文件的内容
    const options = getOptions(this); //拿到配置信息的方法

    return source.replace(/NAME/g,options.words);//必须要有返回
}
```
原文链接：https://blog.csdn.net/qq_36228442/article/details/100037165
<p id="html-11">★★★ 代码分割的本质是什么？有什么意义呢？</p>
+ 代码分割的本质：
是能够把代码分离到不同的bundle中，避免出现大体积的代码包，然后可以按需加载或并行加载这些文件
+ 代码分离的意义：
代码分离可以获取更小的bundle，以及控制资源加载优先级，合理使用可以极大的减少加载时间

+ 代码分割的实现方式有三种：
```
入口起点：使用entry手动分离代码(不建议)
```
防止重复加载：使用optimization.splitChunks配置选项，可以将第三方公共模块和业务代码直接分离
```
动态引入：使用import()方法来分离代码，原理是当 Webpack 解析到该语法时，会自动进行代码分割，分割出不同的chunks
```
> 语法：使用的时候再去下载对应的文件，返回一个Promise，当Promise成功后再去执行回调,(动态引入的另一种方式是require.ensure())
```js
import("./math").then(math => {
  console.log(math.add(16, 26));
});
```
```js
//所有可能匹配此模式的文件都会自动进行代码拆分。
const loadFile = file => import （` ./ $ { file } ` ） 
```
import动态语法实现异步加载的代码演示，
```js
function getComponent(){
   return import(./loadash).then(_=>{
      const element = document.createElement('div');

      element.innerHTML = _.join(['Hello', 'webpack'], ' ');
      return element;
   })
}
getComponent().then(component=>{
 document.body.appendChild(component);
})
```
<p id="html-12">★★★ 说下 tree-shaking 的原理</p>

作用：tree-shaking可以实现删除项目中未被引用的代码
原理：
```js
//test.js
export const a =1;
export const b = 2;
// main.js
import {a} from './test.js'
```
对于以上情况，test文件中的变量b如果没有在项目中使用的话，就不会被打包到文件中
使用：
在webpack4中，开启生产环境就会自动开启这个优化功能，也可以手动的引入ModuleConcatenationPlugin的支持

<p id="html-13">★★★ babel原理</p>

babel需要将高级语法转换，那么babel也势必需要进行编译，babel的执行过程就是一个编译转换的工程，过程如下

       编译器(parse)            转换过程(transform)           生成器(generator)
源代码——————————————抽象语法树AST——————————————————修改后的AST——————————————————转换后的代码

由此我们可以看到babel的核心原理就是parse、transform和generator三个部分

#### parse
在babel中编译器的插件是@babel/parse,其作用就是将源码转变为AST,使用前需要npm i @babel/parser
```js
const babelParser = require('@babel/parser');
const code = "const name='jcq'";
const ast = babelParser.parse(code);
————————————————————————输出结果————————————————————————
Node {
    type: 'File',
    start: 0,
    end: 12,
    loc:
    SourceLocation {
      start: Position { line: 1, column: 0 },
      end: Position { line: 1, column: 12 } },
  errors: [],
   program:
    Node {
      type: 'Program',
      start: 0,
     end: 12,
      loc: SourceLocation { start: [Position], end: [Position] },
     sourceType: 'script',
    interpreter: null,
      body: [ [Node] ],
     directives: [] },
   comments: [] 
   }
  //这就是ast结构树，可以使用ast.program.body[0]，可以在declarations(声明)找到关键字和我们源码中的const
  
```
#### transform
babel官网中并没有称为transfrom转换器的结构。babel是一个工具链，需要有插件才会成功编译，不然只会将原来的代码转换成AST结构，再将AST经过generator转成原来的代码，比如@babel/plugin-transform-react-jsx是将react中的jsx转换成react.createElement()。在转换过程中有两个重要的插件
##### @babel/types
它的作用是创建、修改、删除、查找ast节点
##### @babel/traverse
这个插件的作用是对ast进行遍历parse
经过以上两个插件的转换最终就可以直接交付给浏览器引擎编译执行
#### generator
这个过程使用的插件是@babel/generator，其作用就是transform后的ast重新生成浏览器可以运行的js代码
#### 进阶简化
以上过程繁琐却又不可或缺，所以我们常见的@babel/core整合了所有插件，只需要使用transfrom就可以完成整个步骤，上源码
```js
//此过程直接有babel/core内置的transform完成了整个过程虚拟dom生成React.createElememt(div)的过程
var babel = require("@babel/core");
var code = "<div class='c'>jyy</div>";  // 代码
babel.transform(code,{plugins: ["@babel/plugin-transform-react-jsx"],},function(err, result){
    console.log(result.code);
    // React.createElement("div", {
    //   class: "c"
    // }, "jyy");
});
```
<p id="html-14">★★★ linux部署和windows sever服务器区别？</p>
+ 性价比：Linux服务器性价比更高，Linux作为资源管理器和操作系统来说，是开源的，免费的，而正版windows的操作系统是收费的。
+ 性能方面：相同配置的Linux服务器的性能比windows服务器好一些，Linux服务器占用的资源少一点
+ 稳定性方面：Window系统用户量大，因而攻击者多一些，所以暴露了更多的系统安全漏洞。Linux是多用户多进程系统，意味着Linux能够一次性处理大量正在进行的进程，比windows处理的多
+ 安全性方面：Linux系统开源软件的开发方式有助于暴露错误，集众人智慧解决问题，补丁更新更快。这是windows不具备的，Windows的另一个不利因素是其许多应用程序依靠远程过程调用，这就迫使Windows的防火墙没有Linux那样严格。而Linux远程过程调用是限制使用的。

<p id="html-15">★★★ 你们公司项目发布流程是什么样的？</p>

#### 需求阶段
产品部门提出需求项目，出需求文档，产品原型，产品目标
需求评审(产品，开发，测试，至少一名架构师参与)
审评通过后，上传需求文档，产品原型到conflunce，后续开发&测试依据conflunce

#### 设计阶段
+ 设计评审
+ 详细设计文档
+ 类图.时序图.结构架构图，复杂核心设计详细说明文档
#### 开发阶段
+ Coding&CodeReview
+ 自测
+ 由负责产品的同事主持参与

#### 功能预演(根据项目具体情况可拆分预演，主要防止开发对需求理解不一致)
+ 由负责产品的同事主持参与
#### 测试阶段(测试准入&输入：系统可run，可测；Code Review完成;相应文档齐全；功能预演完成)
+ 测试计划
+ 测试用例编写Review
+ 准备测试环境
+ 部署应用&准备测试数据
+ 冒烟测试(研发和测试扯皮)
+ 测试完成，更新jira状态为待上线；邮件发布测试报告；测试完成。邮件发送至项目组所有成员(项目经理，产品，开发，测试)

#### 发布阶段

+ 和产品同事确认发布范围，先小范围提供测试版本，测试通过没问题才可上线
+ 上线完成后，需立即由自己发送或Leader代发全员邮件，准确告知上线更新内容、更新地址、下载方法等内容
+ 临时取消上线；上线过程，中途终止；重大bug紧急修复；以上三种情况，需CTO批准并告知直属Leader

<p id="html-16">★★★ 前端资源发布路径怎么实现非覆盖式发布（平滑升级）？</p>


<p id="html-17">★★★ SSR项目是如何发布的</p>


<p id="html-18">★★★ 你有发布过自己的npm包吗？流程是怎样的？</p>
1.首先将自己的脚手架发布到githuhb仓库
然后在新建一个脚手架文件夹jcq-cli，并执行
```
2.npm init -y 生成package.json
```
3.安装我们需要的模块commander,download-git-repo.
```
npm i commander download-git-repo
```

4.在项目根目录创建index.js文件，写入相应的处理逻辑
```js
#! /usr/bin/env node

const program = require('commander');
const download = require('download-git-repo');
//version 版本号
//name 新项目名称
program.version('1.0.0', '-v, --version')
    .command('init <templateName> <projectName>')
    .action((templateName, projectName) => {
        if (templateName === "vue") {
            console.log('clone template ...');
            download('github:junkaicool/jkc-cli-vue-src', projectName, function (err) {
                console.log(err ? 'Error' : 'Success')
            })
        } else if(templateName === "react") {
            console.log('clone template ...');
            download('github:junkaicool/jkc-cli-react-src', projectName, function (err) {
                console.log(err ? 'Error' : 'Success')
            })
        } else {
          console.error('A template name that does not exist')
        }
    });
program.parse(process.argv);
// #! /usr/bin/env node是执行这个文件时使用node方式执行
// program.version是解析别人输入jkc-cli -v时输出的内容: 1.0.0
// command解析输入jkc-cli init vue my-vue-project，init后面两个参数，一个模板名，一个项目名
// action是根据上面的两个参数做相应的逻辑处理，判断模板名，去相应的git仓库下载代码。download的第一个参数下载地址不是填我们git的网址，按照我的格式填就行，第二个参数是生成的项目名，第三个参数是错误的回调执行函数。
```
5.在package.json文件中加入，这一步是我们在命令行jkc-cli的时候执行的文件。
```js
....
 "bin": {
        "jcq-cli": "index.js"
  },
....

```
登陆npm 注意一定要切回官方npm才能成功(因为你的账号是在官网注册登陆的)
```
npm login --registry http://registry.npmjs.org
```
登陆成功显示
```
Logged in as ranbaojia on http://registry.npmjs.org/.
```
然后发布 也要在官方网站发布,发布的时候一定要确保你的包名不存在,并且发布前一定要确保邮箱验证npm才可以
```
npm publish 
```
然后直接可以下载你在npm发布的包了，你定要区分清楚现在是处于镜像下载环境还是官方下载环境
```
npm i -g jcq-cli
```
如果下载失败，最好执行一下以下代码
```
npm config set registry http://registry.npmjs.org
```
生成你的脚手架
```
jcq-cli init vue my-first-npmpackage
```

<p id="html-19">★★★ 介绍下 npm 模块安装机制，为什么输入 npm install 就可以自动安装对应的模块？</p>

##### npm安装机制
+ 发出npm install命令
+ 查询node_modules目录中是否已经存在指定模块，若存在，不再安装
+ 若不存在，npm向registry查询模块压缩包的网址，下载压缩包，并解压压缩包到当前项目的node_modules目录

##### npm install实现原理
输入npm install后，会经历以下几个阶段
+ 执行自身的preinstall，当前npm工程如果定义了perennial钩子此时会被执行
+ 确定首层依赖模块，也就是dependencies 和 devDependencies属性中直接指定的模板
+ 获取模块，主要分为确定模块版本信息，如版本是^1.1.0，然后获取模块实体，先从本地根据版本查是否有缓存，没有则从仓库下载
+ 模块扁平化，从npm3开始默认从node_modules查找是否有重复模块，有则直接丢弃。
+ 最后则开始安装模块，更新版本描述文件，直到npm install完成。

<p id="html-20">★★★ 你会搭建私有的npm仓库吗？怎么搭建？</p>

业界主流的私有npm仓库搭建的主流方案有如下四种方法：
1、直接购买，缺点：公司可能不会提供经费，二npm在国内访问很慢，就是花钱也买不到好的体验。
2、使用git+ssh这种方式直接引用到GitHub项目地址,缺点：不能更新即npm update
3、使用Sinopia,建议
4、使用cnpmjs.org，建议
##### Sinopia方案  
安装：
```
npm install -g sinopia
```
启动
```
sinopia
warn  --- config file - /home/map/.config/sinopia/config.yaml warn  --- http address - http://localhost:4873/
```
此时访问localhost:4873,可获取html文件并且服务端响应正常，表示安装成功

<p id="html-21">★★★ Webpack 为什么慢，如何进行优化</p>
webpack为了进行资源的压缩和合并，在打包过程中会引入很多大型的第三方库，以babel、babel-loader为例，使得打包构建以及输出的过程都变得缓慢。具体的构建优化见<a href="#html-9">★★★ 如何优化 Webpack 的构建速度</a>

<p id="html-23">★★★ jenkins 上线流程</p>
  关于jekins上线流程，有一篇详细文章介绍
<a href='https://www.cnblogs.com/kevingrace/p/6022447.html' ></a>

<p id="html-24">★★★ webpack 中 loader 和 plugins 的区别</p>

###### loader是一个转换器

+ 1、用于对模块源码文件的预编译和转换，，loader描述了webpack如何处理非javascript模块。
+ 2、没有loader，构建的打包过程无法顺利完成
+ 3、loader作用在打包前
+ 4、将A文件转换为B文件，操作的是文件，比如将A.scss转换为A.css，是单纯的文件转换过程
###### Plugin是插件扩展器

+ 1、plugin构建过程更完整的补充和优化，如使用new UglifyJsPlugin(),new CssMinimizerPlugin()压缩js和css
+ 2、没有plugin，文件的打包过程可以完成
+ 3、plugin作用于整个打包周期
+ 4、针对webpack的打包过程，他不直接操作文件，而是基于事件机制工作，会监听webpack打包过程的事件钩子，执行任务，通过事件钩子拦截webpack的执行。

<p id="html-25">★★★ 什么是长缓存，在webpack中如何做到长缓存优化？</p>

+ 浏览器在用户访问页面的时候，都会对静态资源进行存储，但是每次代码更新或者升级的时候，我们都需要浏览器去重新加载代码，最方便的方法就是以文件名的方式引入，只下载新的代码块，不加载旧的没有变化的代码块，这就是长缓存，
+ 在webpack4中使用SplitChunkPlugin把第三方库和业务代码分离，由于第三方库的chunkHash未改变，所以只会对改变的业务代码的模块进行更新。而第三方库的代码块因为长缓存而不更新。
<p id="html-26">★★★ 使用git上传的时候，会出现那些冲突，怎么解决这些冲突？</p>

##### 逻辑冲突
git自动处理(合并/应用补丁)成功，但是逻辑上是有问题的
##### 内容冲突
##### 树冲突
<p id="html-27">★★★ 什么是组件？什么是模块化？有什么区别？</p>

##### 组件化
就是基础库或者基础组件，意思是把代码重复的部分提炼出一个个组件供给功能使用
##### 模块化
就是业务框架或者业务模块，也可以理解为框架，意思是把功能进行划分，将同一类型的代码整合在一起，所以模块的功能相对复杂，都属于同一个业务。
##### 区别：
使用：组件的使用能在不同项目(模块)重复应用的代码，而模块按照项目功能需求划分成不同类型的业务框架
目的：组件是复用，解耦，模块是为了隔离、封装
依赖：组件之间低依赖，比较独立，模块之间的依赖可通过路由进行耦合
架构定位：组件位于架构底层，被其它层所依赖，模块位于架构业务层
<p id="html-28">★★★ 你们公司有自己的脚手架工具么，他是怎么工作的？</p>
有自己的脚手架工具

<p id="html-29">★★★ Confluence和Wiki的关系</p>

#### Wiki介绍
Wiki是一种在网络上开放且可供多人协同创作的超文本系统，由美国人沃德·坎宁安于1995年首先开发，这种超文本系统支持面向社群的协作式写作，同时也包括一组支持这种写作。沃德·坎宁安将wiki定义为“一种允许一群用户用简单的描述来创建和连接一组网页的社会计算系统”。 [1]  Wiki站点可以有多人（甚至任何访问者）维护，每个人都可以发表自己的意见，或者对共同的主题进行扩展与探讨


概念 Confluence是一个企业级的Wiki,可用于企业、部门、团队内部进行信息共享和协同编辑。
关键词：信息共享、协同编辑

以下几个基本概念需要了解一下：
#### 空间（Space）
空间是Confluence系统中的一个区域，用于存储wiki页面，并可实现对空间中的所有文档进行统一的权限管理。
通常，我们可以针对每个项目单独创建一个空间，然后将与该项目相关的文档信息放置到该空间中，并只对项目成员开设访问/编辑权限。
除了项目空间，每个成员都有一个个人空间。平时成员可以将工作总结或笔记等文档放置到自己的空间中；对于对团队有帮助的文档，就可以将文档移动至团队项目空间中。
可以理解为SVN或Git的一个库

DashboardDashboard是Confluence系统的主页，在Dashboard界面中包含了Confluence站点中的所有空间列表，以及最近更新内容的列表。

#### 页面（Page）
在Confluence系统中，页面是存储和共享信息的主要方式。页面可以互相链接、连接、组织和访问，并以树状结构进行组织，放置于空间之中。
页面遵循所见即所得的编辑方式，操作上简单易用。更强大的地方在于，页面支持大量的内容展现形式，除了富文本文档外，还包括图表、视频、附件（可预览）、流程图、公式等等；如果还不够，还可以通过海量的第三方插件进行扩展。
在页面中可以通过@其它成员，通知相关成员查看文档。文档保存成功后，被@的成员就会收到邮件，并可根据邮件中的链接访问到该文档，然后进行评论或者协同编辑。

#### 模板（template）
创建页面时除了采用空白文档，也可以选择模板。模板是在空白文档的基础上，根据特定需求添加了一些文档要素，可辅助用户更好更快地创建文档。
Confluence内置了大量的模板，可辅助用于项目工作的各个环节，包括产品需求、会议记录、决策记录、指导手册（How-to）、回顾记录、工作计划、任务报告等等。并且由于Confluence和JIRA是同一家公司的产品，在Confluence中可以和JIRA进行无缝衔接，实现对产品质量实现更好的展现。
如果对Confluence自带的模板不满意，还可以对模板进行调整，或者根据自己的需求创建其它类型的模板。

权限（Permission）在安全性方面，Confluence具有完善和精细的权限控制，可以很好地控制用户在Wiki中创建、编辑内容和添加注释。

权限控制分3个维度，分别是团队（Group），个人（Individual Users），匿名用户（Anonymous）。

使用团队级的权限控制时，需要在Confluence服务器中对公司员工进行分组，好处在于配置比较方便，只需要对整个团队进行统一的权限配置。

但在实际项目中，经常会存在同一个项目包含多个跨团队成员的情况，这个时候就不适合采用团队权限配置方式，只能采用逐个添加成员的方式，并对各个成员分别配置权限。

另外一种情况，就是对于未登录的用户，以及项目成员以外的用户，可以开设部分权限，例如只读（View）
掌握以下信息，就可以开始使用了


待解决问题
polyfills:提供api以方便兼容不同的浏览器
vendor：项目插件扩展
CommonsChunkPlugin 每次构建时都会重新构建一次 vendor？
原因就是因为CommonsChunkPlugin把polyfills和vendor进行了打包，polyfills和vendor中包含了mian所有需要的公共模块，
所以mian不再进行打包这些公共模块，只打包我们自己写的模块。