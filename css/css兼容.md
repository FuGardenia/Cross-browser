#css兼容.md
##css兼容问题原因<br/>

###浏览器内核不同
> > >
	Mozilla Firefox ( Gecko )
	Internet Explorer ( Trident )
	Opera ( Presto )
	Safari ( WebKit )
	Google Chrome ( WebKit )
	国内浏览器（腾讯TT、世界之窗、360浏览器、遨游浏览器 都是给IE或者chrome加了个外壳）

###DOCTYPE解析不同

> ###CSS规则
> > ####1、默认样式不同
> > > 
	html
	body
	form
	margin
	padding
	行高

> > ####2、块级元素和行级元素

> > ####3、盒子模型

> > ####4、透明/遮罩

> > ####5、不同的元素
> > >
	（1）IE不认min-height,min-width
	（2）curser:hand;只有IE认，用curser:pointer;
	（3）属性选择器
	（4） ime-mode设置输入法chrome不可用

5、float
float闭合:
6、position

万恶的IE

单选复选框前面与文字不对齐

&nbsp; 显示的大小不一致

!important（顺序）
1、只有IE6不识别，用来做IE6方面兼容比较好。
2、用来覆盖样式。