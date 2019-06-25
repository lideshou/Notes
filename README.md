# Notes
## text-indent:-9999px;
=>字体隐藏属性，通常为了传达更好的视觉效果，我们常用图片替代掉字体。但是为了更好地让搜索引擎检索到，所以隐藏字体。
## onclick="return false;"
=>组织a链接的默认打开一个新窗口的事件发生。
## v-on:click.prevent
=>为了阻止链接在被点击时跳转。
## margin&padding的值各为4，3，2，1个的时候的代表含义
=>margin为4个时，margin:上  右  下  左;（为顺时针方向）<br>
=>margin为3个时，margin:上   左=右   下;<br>
=>margin为2个时，margin:上=下   左=右;<br>
=>margin为1个时，margin:上=右=下=左;
## visibility:hidden与display:none的区别
=>visibility:hidden将元素隐藏，但在网页所占的空间位置依然存在。<br>
=>display:none将元素的显示设置为无，在网页不占用任何空间。
## display常用属性值
=>none:此元素不会被显示<br>
=>block:此元素将被显示为块级元素，元素前后带有换行符<br>
=>inline:默认。此元素会被显示为内联元素，元素前后没有换行符<br>
=>inline-block:行内块元素
## 实现以一块图片为背景图片透明一个div
透明的div需要加position:absolute;而透明div外层的div要加上position:relative; 才能让透明div相对于外层div去定位，设置透明区域background:rgba(0,0,0,0.6)。并且将图片上层的divz-index属性的值调高。
## z-index
=>可被用于将在一个元素放置于另一元素之后.默认的是z-index是0，z-index-1拥有更低的优先级。
## nodemon安装后但是无法使用
=>是因为全局安装的路径不对，可以将全局安装的路径（F:\nodejs\node_global）添加到系统变量中
## webpack四个核心概念
=>entry（入口）、output（输出）、loader（依赖加载）、plugin（插件）
## get和post方法的区别
=>1.get把请求的数据放在URL上，post把数据放在HTTP的包体内（request body）<br>
  2.get提交数据有大小限制，而post没有<br>
  3.get产生一个tcp数据包，post产生两个tcp数据包<br>
  4.最后，get效率比较高
## bcrypthash加密函数参数个数版本发生变化 参照如下
=>//密码hash加密
                bcrybtNodejs.genSalt(10, function(err, salt) {
                    bcrybtNodejs.hash(newUser.password, salt, null,function(err, hash){
                        //如果有错误则抛出异常
                        if(err)  throw err;

                        //没有错误的话将加密后的密码赋值给...
                        newUser.password=hash;

                        newUser.save()
                            .then(user=>res.json(user))
                            .catch(err=>console.log(err))
                    });
## 实现水平居中常用的几种方法
1.margin: 0 auto;<br>
2.text-align: center;<br>
3.父元素display: flex;flex-direction: column;子元素align-self: center;<br>
4.父元素display: table-cell;子元素margin-left取值剩余宽度的一半(或者父元素position: absolute;)<br>
## 实现垂直居中常用的几种方法
1.display: inline-block;vertical-align: middle;<br>
2.父元素display: flex;flex-direction: row;子元素align-self: center;<br>
3.父元素display: table;子元素display: table-cell;vertical-align: middle;<br>
4.设置行高，该元素的行高和其父元素的高度保持一致.
## 浏览器是怎么对HTML5的离线储存资源进行管理和加载的呢？
在线的情况下，浏览器发现html头部有manifest属性，它会请求manifest文件，如果是第一次访问app，那么浏览器就会根据manifest文件的内容下载相应的资源并且进行离线存储。如果已经访问过app并且资源已经离线存储了，那么浏览器就会使用离线的资源加载页面，然后浏览器会对比新的manifest文件与旧的manifest文件，如果文件没有发生改变，就不做任何操作，如果文件改变了，那么就会重新下载文件中的资源并进行离线存储。
离线的情况下，浏览器就直接使用离线存储的资源。
## 关于cookies，sessionStorage 和 localStorage 的区别
相同：都存储在客户端（浏览器）<br>
1.存储大小<br>
cookies数据大小不能超过4k<br>
localstorage和sessionstorage也有数据限制，但可以达到5m<br>
2.有效时间<br>
localstorage只有主动删除数据才会消失<br>
sessionstorage在窗口关闭的时候数据自动删除<br>
cookies可以设置数据的有效时期<br>
3.数据与服务器端的交互方式<br>
cookie会把数据传输到服务端，服务端也可以写cookies到客户端<br>
localstotage和sessionstorage不会把数据传输到服务端，只保存在本地
## 清除浮动的方式以及优缺点<br>
1.clear:both简单，浏览器兼容性好，但容易造成页面混乱<br>
2.overflow:hidden使用简单，但是超出的尺寸会被隐藏<br>
3.使用伪元素:after浏览器兼容性好，但是代码较为复杂
## 闭包是什么 有什么特性 对页面有什么影响？
闭包是指有权访问另一个函数作用域的变量的函数<br>
封闭性：外部无法访问闭包北部的数据<br>
持久性：函数被调用后，闭包结构依然存在。<br>
过多的使用闭包会导致内存溢出
## 在 javascript 中，用于阻止默认事件的默认操作的方法是
preventDefault()
## link和@import的区别
1.link是由HTML提供，@import是由CSS样式提供<br>
2.link不仅能引入样式，比如定义RSS，定义rel连接属性等<br>
3.link引入的样式会在页面加载的时候同时加载，而@import引入的则会在页面加载完后再加载<br>
4.兼容性有一定的差别<br>
5.dom可以控制link但是不能控制@import
## HTML5新特性有哪些 删除了哪些元素？又如何处理兼容性的问题呢？如何区分HTML5和HTML！
1.语义化<br>
2.本地存储<br>
3.设备兼容<br>
4.连接特性，能够帮助我们将数据推送到客户端<br>
5.网页多媒体特性<br>
6.三维、图形及特效特性<br>
7.性能与集成特性<br>
8.css3特性<br>
### 移除的元素
纯表现的元素：basefont，big，center，font,s，strike，tt，u<br>
对可用性产生负面影响的元素：frame，frameset，noframes<br>
1.使用html5shim框架<br>
2.IE8/IE7/IE6支持通过document.方法产生的标签,利用这一特性让这些浏览器支持HTML5新标签。
### 区分
用doctype来区分
## iframe的优缺点
### 优点
1.iframe能够原封不动的把嵌入的网页展现出来。<br>
2.可以增加代码的可重用.<br>
### 缺点
1.会增加服务器的请求<br>
2.代码复杂，无法被搜索引擎解读。<br>
3.不易管理
## $(document).ready和window.onload的区别
$(document).ready()在DOM树加载完之后所有元素加载完成之前就可以执行了<br>
window.onload()需要在所有元素渲染完成后再执行
## 闭包是什么，为什么要使用闭包？
一言以蔽之，闭包就是可以调用其他函数作用域变量的函数，闭包的使用可以使变量一直存在在内存中。
