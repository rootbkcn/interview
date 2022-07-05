# 目录

<a href="#weapp-1">★★ 简单描述下微信小程序的相关文件类型</a>

<a href="#weapp-2">★★★★ 简述微信小程序原理</a>

<a href="#weapp-3">★★★ 小程序的双向绑定和vue哪里不一样</a>

<a href="#weapp-4">★★ 小程序的 wxss 和 css 有哪些不一样的地方</a>

<a href="#weapp-5">★★★ 小程序页面间有哪些传递数据的方法</a>

<a href="#weapp-6">★★★ 小程序的生命周期函数</a>

<a href="#weapp-7">★★★ 怎么封装微信小程序的数据请求</a>

<a href="#weapp-8">★★★ 哪些方法可以用来提高微信小程序的应用速度</a>

<a href="#weapp-9">★★ 微信小程序的优劣势</a>

<a href="#weapp-10">★★★ 怎么解决小程序的异步请求问题</a>

<a href="#weapp-11">★★★ 小程序关联微信公众号如何确定用户的唯一性</a>

<a href="#weapp-12">★★★ 如何实现下拉刷新</a>

<a href="#weapp-13">★★ bindtap 和 catchtap 的区别是什么</a>

<a href="#weapp-14">★★★★ 简述微信支付的业务流程</a>

<a href="#weapp-15">★★★ 什么是小程序自定义组件样式隔离,他有哪几种隔离模式？</a>

<a href="#weapp-16">★★★ 在小程序中又哪些方法让图片宽高比例保持不变？</a>

<a href="#weapp-17">★★ 小程序组件传参(父子，子父)</a>

<a href="#weapp-18">★★ 小程序组件生命周期</a>

<a href="#weapp-19">★★ 小程序页面生命周期</a>

<a href="#weapp-20">★★ 小程序怎么样实现路由传参 </a> 

<a href="#weapp-21">★★★ 小程序中的路由跳转switchTab navigateTo redirectTo的区别</a>

<a href="#weapp-22">★★★ 小程序tabbar实现原理</a>

<a href="#weapp-23">★★★ 小程序性能为什么那么好，为什么能做到即用即走的效果</a>

<a href="#weapp-24">★★ 如何自定义小程序的navigationBar</a>

<a href="#weapp-25">★★ 说说小程序中wx:if和hidden的区别</a>


# 小程序面试真题

### <p id="weapp-1">★★ 简单描述下微信小程序的相关文件类型</p>

> 微信小程序项目结构主要有四个文件类型

- `WXML`（WeiXin Markup Language）是框架设计的一套标签语言，结合基础组件、事件系统，可以构建出页面的结构。内部主要是微信自己定义的一套组件
- `WXSS` (WeiXin Style Sheets)是一套样式语言，用于描述 `WXML` 的组件样式
- `js` 逻辑处理，网络请求
- `json` 小程序设置，如页面注册，页面标题及`tabBar`

> 主要文件

- `app.json` 必须要有这个文件，如果没有这个文件，项目无法运行，因为微信框架把这个作为配置文件入口，整个小程序的全局配置。包括页面注册，网络设置，以及小程序的 `window` 背景色，配置导航条样式，配置默认标题
- `app.js` 必须要有这个文件，没有也是会报错！但是这个文件创建一下就行 什么都不需要写以后我们可以在这个文件中监听并处理小程序的生命周期函数、声明全局变量
- `app.wxss` 可选



### <p id="weapp-2">★★★★ 简述微信小程序原理</p>

> 微信小程序采用 `JavaScript`、`WXML`、`WXSS` 三种技术进行开发,本质就是一个单页面应用，所有的页面渲染和事件处理，都在一个页面内进行，但又可以通过微信客户端调用原生的各种接口微信的架构，是数据驱动的架构模式，它的 `UI` 和数据是分离的，所有的页面更新，都需要通过对数据的更改来实现
> 小程序分为两个部分 `webview` 和 `appService` 。其中 `webview` 主要用来展现 `UI` ，`appService` 有来处理业务逻辑、数据及接口调用。它们在两个进程中运行，通过系统层 `JSBridge` 实现通信，实现 `UI` 的渲染、事件的处理


### <p id="weapp-3">★★★ 小程序的双向绑定和vue哪里不一样</p>

小程序直接 `this.data` 的属性是不可以同步到视图的，必须调用：
>微信小程序在初始化之后，再对原来的数据对象进行任何更改，都始终不会生效！只能手动调用setData接口明确指明同步哪些键/值至视图层才会触发更新
>vue则是对数据对象进行了监听，只要有更改就可以并且会立即触发视图层的更新
```js
this.setData({
    // 这里设置
})
```

>设置值
- 在vue中,只需要再表单元素上加上v-model,然后再绑定data中对应的一个值，当表单元素内容发生变化时，data中对应的值也会相应改变，这是vue非常nice的一点。
 ```js
 <div id="app">  
  <input v-model="reason" placeholder="填写理由" class='reason'/>  
  </div>  

  new Vue({  
    el: '#app',  
    data: {  
    reason:''  
    }  
  })
 ```
- 但是在小程序中，却没有这个功能。那怎么办呢？当表单内容发生变化时，会触发表单元素上绑定的方法，然后在该方法中，通过this.setData({key:value})来将表单上的值赋值给data中的对应值。下面是代码，可以感受一下:
```js
<input bindinput="bindReason" placeholder="填写理由" class='reason' value='{{reason}}' name="reason" />  
  Page({  
  data:{  
  reason:''  
  },  
  bindReason(e) {  
  this.setData({  
  reason: e.detail.value  
  })  
  }  
  })
```
- 当页面表单元素很多的时候，更改值就是一件体力活了。和小程序一比较，vue的v-model简直爽的不要不要的。
>取值

- vue中，通过this.reason取值

- 小程序中，通过this.data.reason取值

### <p id="weapp-4">★★ 小程序的 wxss 和 css 有哪些不一样的地方</p>

> `WXSS` 和 `CSS` 类似，不过在 `CSS` 的基础上做了一些补充和修改

- 尺寸单位 `rpx`

`rpx` 是响应式像素,可以根据屏幕宽度进行自适应。规定屏幕宽为 `750rpx`。如在 `iPhone6` 上，屏幕宽度为 `375px`，共有 `750` 个物理像素，则 `750rpx = 375px = 750` 物理像素

- 使用 `@import` 标识符来导入外联样式。`@import` 后跟需要导入的外联样式表的相对路径，用;表示语句结束

```css
/** index.wxss **/
@import './base.wxss';

.container{
    color: red;
}
```


### <p id="weapp-5">★★★ 小程序页面间有哪些传递数据的方法</p>

- 使用全局变量实现数据传递

在 `app.js` 文件中定义全局变量 `globalData`， 将需要存储的信息存放在里面

```js
// app.js

App({
     // 全局变量
  globalData: {
    userInfo: null
  }
})
```

使用的时候，直接使用 `getApp()` 拿到存储的信息

- 使用 `wx.navigateTo` 与 `wx.redirectTo` 的时候，可以将部分数据放在 `url` 里面，并在新页面 `onLoad` 的时候初始化

```js
//pageA.js

// Navigate
wx.navigateTo({
  url: '../pageD/pageD?name=raymond&gender=male',
})

// Redirect
wx.redirectTo({
  url: '../pageD/pageD?name=raymond&gender=male',
})


// pageB.js
...
Page({
  onLoad: function(option){//option里面可以拿到路由参数
    console.log(option.name + 'is' + option.gender)
    this.setData({
      option: option
    })
  }
})
```

需要注意的问题：

`wx.navigateTo` 和 `wx.redirectTo` 不允许跳转到 `tab` 所包含的页面

`onLoad` 只执行一次

- 使用本地缓存 `Storage` 相关



### <p id="weapp-6">★★★ 小程序的生命周期函数</p>

- `onLoad` 页面加载时触发。一个页面只会调用一次，可以在 `onLoad` 的参数中获取打开当前页面路径中的参数,建议在此调接口
- `onShow()` 页面显示/切入前台时触发，不建议在此调接口
- `onReady()` 页面初次渲染完成时触发。一个页面只会调用一次，代表页面已经准备妥当，可以和视图层进行交互
- `onHide()` 页面隐藏/切入后台时触发。 如 `navigateTo` 或底部 `tab` 切换到其他页面，小程序切入后台等
- `onUnload()` 页面卸载时触发。如 `redirectTo` 或 `navigateBack` 到其他页面时

详见 [生命周期回调函数](https://link.zhihu.com/?target=https%3A//developers.weixin.qq.com/miniprogram/dev/framework/app-service/page.html%23%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F%E5%9B%9E%E8%B0%83%E5%87%BD%E6%95%B0)


### <p id="weapp-7">★★★ 怎么封装微信小程序的数据请求</p>

参考 [这里](https://link.zhihu.com/?target=https%3A//segmentfault.com/a/1190000014789969)


### <p id="weapp-8">★★★ 哪些方法可以用来提高微信小程序的应用速度</p>

1、提高页面加载速度

2、用户行为预测

3、减少默认 `data` 的大小

4、组件化方案


### <p id="weapp-9">★★ 微信小程序的优劣势</p>

> 优势

- 即用即走，不用安装，省流量，省安装时间，不占用桌面
- 依托微信流量，天生推广传播优势
- 开发成本比 `App` 低

> 缺点

- 用户留存，即用即走是优势，也存在一些问题
- 入口相对传统 `App` 要深很多
- 限制较多,页面大小不能超过2M。不能打开超过10个层级的页面


### <p id="weapp-10">★★★ 怎么解决小程序的异步请求问题</p>

> 小程序支持大部分 `ES6` 语法

- 在返回成功的回调里面处理逻辑
- `Promise` 异步

### <p id="weapp-11">★★★ 小程序关联微信公众号如何确定用户的唯一性</p>

> 如果开发者拥有多个移动应用、网站应用、和公众帐号（包括小程序），可通过 `unionid` 来区分用户的唯一性，因为只要是同一个微信开放平台帐号下的移动应用、网站应用和公众帐号（包括小程序），用户的 `unionid` 是唯一的。换句话说，同一用户，对同一个微信开放平台下的不同应用，`unionid` 是相同的


### <p id="weapp-12">★★★ 如何实现下拉刷新</p>

- 首先在全局 `config` 中的 `window` 配置 `enablePullDownRefresh`
- 在 `Page` 中定义 `onPullDownRefresh` 钩子函数,到达下拉刷新条件后，该钩子函数执行，发起请求方法
- 请求返回后，调用 `wx.stopPullDownRefresh` 停止下拉刷新

参考 [这里](https://link.zhihu.com/?target=https%3A//juejin.im/post/5a781c756fb9a063606eb742)


### <p id="weapp-13">★★ bindtap 和 catchtap 的区别是什么</p>

相同点：首先他们都是作为点击事件函数，就是点击时触发。在这个作用上他们是一样的，可以不做区分

不同点：他们的不同点主要是bindtap是不会阻止冒泡事件的，catchtap是阻止冒泡的


### <p id="weapp-14">★★★★ 简述微信支付的业务流程</p>

- 步骤1：用户在商户APP中选择商品，提交订单，选择微信支付。

- 步骤2：商户后台收到用户支付单，调用微信支付统一下单接口。参见[统一下单API](https://pay.weixin.qq.com/wiki/doc/api/app/app.php?chapter=9_1)。

- 步骤3：统一下单接口返回正常的prepay_id，再按签名规范重新生成签名后，将数据传输给APP。参与签名的字段名为`appid`，`partnerid`，`prepayid`，`noncestr`，`timestamp`，`package`。注意：package的值格式为`Sign=WXPay`

- 步骤4：商户APP调起微信支付。`api`参见本章节[app端开发步骤说明](https://pay.weixin.qq.com/wiki/doc/api/app/app.php?chapter=8_5)

- 步骤5：商户后台接收支付通知。`api`参见[支付结果通知API](https://pay.weixin.qq.com/wiki/doc/api/app/app.php?chapter=9_7)

- 步骤6：商户后台查询支付结果。，`api`参见[查询订单API](https://pay.weixin.qq.com/wiki/doc/api/app/app.php?chapter=9_2)（查单实现可参考：[支付回调和查单实现指引](https://pay.weixin.qq.com/wiki/doc/api/app/app.php?chapter=23_9&index=1)）
详情参考[这里](https://pay.weixin.qq.com/wiki/doc/api/app/app.php?chapter=8_3) 


### <p id="weapp-15">★★★ 什么是小程序自定义组件样式隔离,他有哪几种隔离模式？</p>

* 默认情况下，自定义组件的样式只受到自定义组件 wxss 的影响。除非以下两种情况：
- app.wxss 或页面的 wxss 中使用了标签名选择器（或一些其他特殊选择器）来直接指定样式，这些选择器会影响到页面和全部组件。通常情况下这是不推荐的做法。
- 指定特殊的样式隔离选项 styleIsolation 。
- styleIsolation 选项从基础库版本 2.6.5 开始支持。它支持以下取值：

- isolated 表示启用样式隔离，在自定义组件内外，使用 class 指定的样式将不会相互影响（一般情况下的默认值）；
- apply-shared 表示页面 wxss 样式将影响到自定义组件，但自定义组件 wxss 中指定的样式不会影响页面；
- shared 表示页面 wxss 样式将影响到自定义组件，自定义组件 wxss 中指定的样式也会影响页面和其他设置了 apply-shared 或 shared 的自定义组件。（这个选项在插件中不可用。）
参考[这里](https://zhuanlan.zhihu.com/p/163190376) 


### <p id="weapp-16">★★★ 在小程序中又哪些方法让图片宽高比例保持不变？</p>

* 使用mode：widthFix
   > `widthFix`：宽度不变，高度自动变化，保持原图宽高比不变。
首先我们先设置image的mode为`widthFix`，然后给图片加一个固定`rpx`的宽度，比如：`730rpx`。
这样图片也可以自适应了。。因为小程序的`rpx`本身就是一个自适应显示的单位
* 使用mode属性为`aspectFit`,并给图片一个固定`rpx`宽高
```js
<image src="/images/1.png" class="img" mode="widthFix"></image>
```
* 使用`bindload`绑定函数动态自适应
  
> 详情参考[这里](http://www.qianduan8.com/1005.html) 


### <p id="weapp-17">★★ 小程序组件传参(父子，子父)</p>

* 父传子
   > 自定义属性，属性的值来自声明式变量
   > 子组件通过props接收
* 子传父
   > 自定义事件，父组件通过事件接收子组件传过来的值
   > 自定义封装组件的例子：

```javascript
 //父组件使用
 //接收子组件数据的事件
  ontogg(ele) {
    console.log('接收子组件发过来的数据',ele)
  }
 //自定义横向滚动条
 let { box, imgs, cates,toView ,flag,end} = this.state
          <ScroLLview
            flag={flag}
            toView={toView}
            cates={cates}
            box={box}
            onChange={(ele)=>this.ontogg(ele)}
          />
    
    
  //子组件
  export default props=>{
  //接收父组件传过来的属性和事件
  const {box,flag,toView,cates,onChange}=props
  const renderSCview=()=>{
    return(
      cates.map(ele => (
        //view要加id，和scroll-into-view相关联
        <View
          //传给父组件的事件，要传过去的数据放在onchange参数里面
          onClick={() => onChange(ele)}
          className={ele.cate === box ? 'mack on' : 'mack'}
          key={ele.id}
          id={'c'+ele.id}
        >
          {ele.cate_zh}
        </View>
      ))
    )
  }
  return (
    // 横向滚动条
    <View style={ {position:flag ? "fixed":"static"} } className="nav fix">
      <ScrollView 
        className="scroll-view_H"
        scrollX
        scrollIntoView={'c'+(toView-1)}
        >
        <View className="list">
          {renderSCview()}
        </View>
      </ScrollView>
    </View>
  )
}
```
- 还可以参考[这里](https://zhuanlan.zhihu.com/p/267714541)


### <p id="weapp-18">★★ 小程序组件生命周期</p>

* 组件的生命周期，指的是组件自身的一些函数，这些函数在特殊的时间点或遇到一些特殊的框架事件时被自动触发

  | 生命周期 | 参数         | 描述                                     | 最低版本 |
  | -------- | ------------ | ---------------------------------------- | -------- |
  | created  | 无           | 在组件实例刚刚被创建时执行               | 1.6.3    |
  | attached | 无           | 在组件实例进入页面节点树时执行           | 1.6.3    |
  | ready    | 无           | 在组件在视图层布局完成后执行             | 1.6.3    |
  | moved    | 无           | 在组件实例被移动到节点树另一个位置时执行 | 1.6.3    |
  | detached | 无           | 在组件实例被从页面节点树移除时执行       | 1.6.3    |
  | error    | Object Error | 每当组件方法抛出错误时执行               | 2.4.1    |

  

参考[这里](https://blog.csdn.net/weixin_41829477/article/details/104297088) 

### <p id="weapp-19">★★ 小程序页面生命周期</p>

[页面生命周期流程图]:https://pic1.zhimg.com/80/v2-130cfbacc7761d994630d6ab9ae6c238_720w.png
* 1、小程序注册完成后，加载页面，触发`onLoad`方法，一个页面只会调用一次。
* 2、页面载入后触发`onShow`方法，显示页面，每次打开页面都会调用一次。
* 3、首次显示页面，会触发`onReady`方法，渲染页面元素和样式，一个页面只会调用一次。
* 4、当小程序后台运行或跳转到其他页面时，触发`onHide`方法。
* 5、当小程序有后台进入到前台运行或重新进入页面时，触发`onShow`方法。
* 6、当使用重定向方法`wx.redirectTo(OBJECT)`或关闭当前页返回上一页`wx.navigateBack()`，触发`onUnload`

参考[这里](https://zhuanlan.zhihu.com/p/28872497) 


### <p id="weapp-20">★★ 小程序怎么样实现路由传参 </p> 

* `wx.navigateTo` （非 `tabBar` 的页面的路径，能返回来，只能有五层）
```js
  wx.navigateTo({
    url: '../placeIntroduce/placeIntroduce?placeId=2',//在路径后面拼接
    })
    另外一个页面通过onload(options)这个生命周期获取到placeId
```
* `wx.redirectTo` （非 `tabBar` 的页面的路径，不能返回来，不限层）
```js
 wx.redirectTo （非 tabBar 的页面的路径，不能返回来，不限层）
  wx.redirectTo ({
    url: '../placeIntroduce/placeIntroduce?placeId=2',//在路径后面拼接
```
参考[这里](https://blog.csdn.net/weixin_30276935/article/details/97401135) 


### <p id="weapp-21">★★★ 小程序中的路由跳转switchTab navigateTo redirectTo的区别</p>

- wx.navigateTo()：保留当前页面，跳转到应用内的某个页面。但是不能跳到 `tabbar` 页面
- wx.redirectTo()：关闭当前页面，跳转到应用内的某个页面。但是不允许跳转到 `tabbar` 页面
- wx.switchTab()：跳转到 `abBar` 页面，并关闭其他所有非 `tabBar` 页面
- wx.navigateBack()关闭当前页面，返回上一页面或多级页面。可通过 `getCurrentPages()` 获取当前的页面栈，决定需要返回几层
- wx.reLaunch()：关闭所有页面，打开到应用内的某个页面


### <p id="weapp-22">★★★ 小程序tabbar实现原理</p>

* 要实现tabbar的导航条其实很简单，我们要实现全局的tabbar只需要在app.json文件中定义即可，局部的就在局部的tabbar文件中实现。
> 来看看app.json代码：
```js
export default {
  pages: [
    'pages/index/index',
    "pages/search/search",
    'pages/news/news',
    'pages/attention/attention',
    'pages/collect/collect',
    'pages/comment/comment',
    'pages/my/my',
    "pages/detail/detail",
    "pages/chat/chat",
  ],
  window: {
    backgroundTextStyle: 'light',
    navigationBarBackgroundColor: '#fff',
    navigationBarTitleText: '小红书',
    navigationBarTextStyle: 'black',
    enablePullDownRefresh: true
  },
  tabBar: {
    "list": [
      {
        "pagePath": "pages/index/index",
        "text": "首页",
        "iconPath": "assets/tabbar/1.png",
        "selectedIconPath": "assets/tabbar/2.png"
      },
      {
        "pagePath": "pages/news/news",
        "text": "消息",
        "iconPath": "assets/tabbar/news1.png",
        "selectedIconPath": "assets/tabbar/news2.png"
      },
      {
        "pagePath": "pages/my/my",
        "text": "我的",
        "iconPath": "assets/tabbar/3.png",
        "selectedIconPath": "assets/tabbar/4.png"
      }
    ]
  },
  permission: {
    "scope.userLocation": {
      "desc": "为了更好的为你服务，请允许访问你的地址"
    }
  }
}
```
参考[这里](https://www.cnblogs.com/izhaofu/p/6278589.html) 


### <p id="weapp-23">★★★ 小程序性能为什么那么好，为什么能做到即用即走的效果</p>

* 因为是轻量级的，代码包体积限制在2M以内，如果超过2M还可以进行分包，提高性能优化
* 运行在微信端,很多功能只需要使用API来实现，就可以实现跟APP的一样的功能
* 因为他的双线程的模型的原因，让小程序可以快速的一下将数据渲染出来呈现在用户的面前
* 是基于卫星或者支付宝这样的宿主环境的，微信客户端提供双线程去执行wxml, wxss, js文件

参考[这里](https://blog.csdn.net/xfy196/article/details/108232592)


### <p id="weapp-24">★★ 如何自定义小程序的navigationBar</p>

* 思路
> 隐藏原生样式
> 获取胶囊按钮、状态栏相关数据以供后续计算
> 根据不同机型计算出该机型的导航栏高度，进行适配
> 编写新的导航栏
> 引用到页面

参考[这里](https://zhuanlan.zhihu.com/p/117244248)


### <p id="weapp-25">★★ 说说小程序中wx:if和hidden的区别</p>

> 相同点：

wx:if 与 hidden 都用来控制小程序元素的显示

> 不同点

wx:if：
* 1、条件为 true 时显示
* 2、当元素显示时渲染
* 3、元素变为不显示时销毁元素

hidden：
* 1、条件为 false 时显示
* 2、当元素显示时渲染
* 3、元素变为不显示时保留元素
* 4、相当于使用了dispaly

总结：
1、当元素频繁切换是否显示时使用 hidden ，因为 wx:if 会频繁地销毁渲染元素
2、当元素不频繁切换是否显示时使用 wx:if，因为 wx:if 会避免页面加载时渲染过多，导致页面加载缓慢