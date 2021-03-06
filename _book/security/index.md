# 目录

<a href="#security-1">★★★ 如何防止XSS攻击</a>

<a href="#security-2">★★★ 如何防止CSRF攻击？</a>

<a href="#security-3">★★★ 如何接口加密？</a>

<a href="#security-4">★★★ 浏览器为什么要阻止跨域请求？如何解决跨域？每次跨域请求都需要到达服务端吗？</a>

<a href="#security-5">★★★ XSS和CSRF的原理以及防御措施</a>


# 安全面试真题

### <p id="security-1">★★★ 如何防止XSS攻击</p>

​	1，对输入和URL参数进行过滤(白名单和黑名单)

​		a，主要的思路就是将容易导致XSS攻击的边角字符替换成全角字符

​		b，对于每一个输入，在客户端和服务器端还要进行各种验证，验证是否合法字符，长度是否合法，格式是否正确

​		c，< 和 > 是脚本执行和各种html标签需要的，比如 \<script>，& 和 # 以及 % ，所以可以通过制定黑白名单规则来过滤符号

​		d，比如规定所有的输入只能是“大小写的26个英文字母和10个数字，还有-和_”，所有其他的输入都是非法的，会被抛弃掉。很显然			  如此严格的白名单是可以100%拦截所有的XSS攻击的。但是现实情况一般是不能进行如此严格的白名单过滤的

​	2，在输出数据之前对潜在的威胁的字符进行编码、转义是防御XSS攻击十分有效的措施。

​		a，作为body文本输出，作为html标签的属性输出：比如将< 转成&lt ；> 转成&gt等，

​		b，如果 `<script>`, `<style>`, `<img>` 等标签的 src 和 href 属性值为动态内容，那么要确保这些url没有执行恶意连接，

​				确保：href 和 src 的值必须以 `http://`开头，白名单方式；不能有10进制和16进制编码字符。

​	3，XSS 一般利用js脚步读取用户浏览器中的Cookie，而如果在服务器端对 Cookie 设置了HttpOnly 属性，那么js脚本就不能读取到			cookie，但是浏览器还是能够正常使用cookie。

### <p id="security-2">★★★ 如何防止CSRF攻击？</p>

概念：跨站请求伪造，比如用户登录了a.com ，浏览器保存了a.com的登录凭证(cookie)，然后用户被诱导，进入了b.com，然后b.com向a.com发送请求，浏览器会默认携带a.com的Cookie，然后a.com验证通过了，因为cookie是真的，所以b.com冒充用户执行了自己的操作。

​	1，同源检测

​		在HTTP协议中，每一个异步请求都会携带两个Header，用于标记来源域名：

```
	- Origin Header

	- Referer Header

这两个Header在浏览器发起请求时，大多数情况会自动带上，并且不能由前端自定义内容。 服务器可以通过解析这两个Header中的域名，确定请求的来源域。

当Origin和Referer头文件不存在时该怎么办？如果Origin和Referer都不存在，建议直接进行阻止。
```

​	2，CSRF Token

​		a，将CSRF Token输出到页面中，服务器需要给这个用户生成一个Token，该Token通过加密算法对数据进行加密，

​		b，页面提交的请求携带这个Token

​		c，当用户从客户端得到了Token，再次提交给服务器的时候，服务器需要判断Token的有效性，验证过程是先解密Token，对比加密			字符串以及时间戳，如果加密字符串一致且时间未过期，那么这个Token就是有效的。

​	3，分布式校验

​		a，由于使用Session存储，读取和验证CSRF Token会引起比较大的复杂度和性能问题，目前很多网站采用Encrypted Token Pattern				方式。这种方法的Token是一个计算出来的结果，而非随机生成的字符串。这样在校验时无需再去读取存储的Token，只用再次				计算一次即可。

​		b，这种Token的值通常是使用UserID、时间戳和随机数，通过加密的方法生成。这样既可以保证分布式服务的Token一致，又能保				证Token不容易被破解。

​	4，双重Cookie验证

​		a，另一种防御措施是使用双重提交Cookie。利用CSRF攻击不能获取到用户Cookie的特点，我们可以要求Ajax和表单请求携带一个				Cookie中的值。

[参考]: https://www.cnblogs.com/lr393993507/p/9834856.html



### <p id="security-3">★★★ 如何接口加密？</p>

1、接口调用方和接口提供方约定好统一的参数加密算法

2、接口调用方在调用时把加密后的_sign放在参数中去请求接口

3、接口提供方接到响应后，判断时间戳是不是在有效时间内（这个时间间隔根据你的安全范围可以是10分钟，5分钟，20秒等，过期失效，前提是需要保证接口提供方和调用方的服务器时间为准确的网络同步时间）

4、把参数中除了_sign以外的参数进行加密，然后把加密结果和传过来的_sign比较，相同则执行调用请求。

5、如果服务器和客户端的时间没有同步，可以返回错误的同时候在返回一个服务器的当前时间，客户端接收到该错误后再请求上一个接口，时间则传服务器刚刚返回的时间6、如果用户还没有登录时，还没有token之类的唯一标识时，可以和服务端定义一个固定的标识来使用就行。7、涉及到比较重要的信息，可以用AES对value进行加密，防止抓包拉取到上传的数据。8、追求安全可以考虑https的双向验证模式 + 参数的sign签名的规则双重验证达到安全的请求后台。

[参考]: https://blog.csdn.net/lxf2323881/article/details/78845822



### <p id="security-4">★★★ 浏览器为什么要阻止跨域请求？如何解决跨域？每次跨域请求都需要到达服务端吗？</p>

​	1，为什么要阻止跨域请求？ 因为安全！！

​	2，解决跨域

​		a，通过jsonp跨域：通过script标签引入一个js文件，这个js文件载入成功后会执行我们在url参数中指定的函数，并且会把我们需要											的json数据作为参数传入。所以jsonp是需要服务器端的页面进行相应的配合的。

​		b，使用跨域资源共享（CORS）来跨域：（CORS）跨域资源共享是一份浏览器技术的规范，提供了 Web 服务从不同域传来沙盒脚				本的方法，以避开浏览器的同源策略，确保安全的跨域数据传输

​		c，代理：跨域是针对浏览器的，可以通过服务器端来解决该问题

[更多请参考]: https://www.cnblogs.com/gitnull/p/9817405.html



### <p id="security-5">★★★ XSS和CSRF的原理以及防御措施</p>

原理：

​		XSS又叫CSS (Cross Site Script) ，跨站脚本攻击。它指的是恶意攻击者往Web页面里插入恶意html代码，当用户浏览该页之时，嵌		入其中Web里面的html代码会被执行，从而达到恶意攻击用户的特殊目的。



​		CSRF（Cross-site request forgery），中文名称：跨站请求伪造，也被称为：one click attack/session riding，缩写为:CSRF/XSRF。

![](https://upload-images.jianshu.io/upload_images/1637343-f98498e9419fb156.png?imageMogr2/auto-orient/strip|imageView2/2/w/1052/format/webp)



防御措施：

<a href="#security-1">防止xss攻击</a>

<a href='#security-2'>防止csrf攻击</a>

