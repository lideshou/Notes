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
=>1.get把请求的数据放在URL上，post把数据放在HTTP的包体内（requrest body）<br>
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
4.设置行高，该元素的行高和其父元素的高度保持一致
