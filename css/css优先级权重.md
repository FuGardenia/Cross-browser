css优先级权重.md
===
#多类选择（IE7之前不能正确识别）
空格：多个类同时选择<br/>
链接一起：同时包含该类<br/>

#CSS 选择器类型
##!important强制样式 (优先级：最高)(优先级权重：1000)

##ID 选择器 (优先级权重：100)

##类选择器 (优先级权重：10)
##属性选择器 (优先级权重：10)
###简单属性选择（ a[title] {color:red;}）
###多个属性进行选择（a[href][title] {color:red;}）
###特定属性值的元素（a[href="http://www.w3school.com.cn/about_us.asp"] {color: red;}）
###多个属性-值选择器链接在一起来选择一个文档。（a[href="http://www.w3school.com.cn/"][title="W3School"] {color: red;}）

	子串匹配属性选择器
	它是 CSS2 完成之后发布的
	类型
	描述
	[abc^="def"]
	选择 abc 属性值以 "def" 开头的所有元素
	[abc$="def"]
	选择 abc 属性值以 "def" 结尾的所有元素
	[abc*="def"]
	选择 abc 属性值中包含子串 "def" 的所有元素
	a[href*="w3school.com.cn"] {color: red;}

##伪类 (优先级权重：10)

	W3C："W3C" 列指示出该属性在哪个 CSS 版本中定义（CSS1 还是 CSS2）。
	属性
	描述
	CSS
	:active
	向被激活的元素添加样式。
	1
	:focus
	向拥有键盘输入焦点的元素添加样式。
	2
	:hover
	当鼠标悬浮在元素上方时，向元素添加样式。
	1
	:link
	向未被访问的链接添加样式。
	1
	:visited
	向已被访问的链接添加样式。
	1
	:first-child
	向元素的第一个子元素添加样式。
	2
	:lang
	向带有指定 lang 属性的元素添加样式。
	2
	伪类的语法：
	selector : pseudo-class {property: value}
	如：a:link {color: #FF0000}     

##伪元素 (优先级权重：1)
 
	属性
	描述
	CSS
	:first-letter
	向文本的第一个字母添加特殊样式。
	1
	:first-line
	向文本的首行添加特殊样式。
	1
	:before
	在元素之前添加内容。
	2
	:after
	在元素之后添加内容。
	2
	伪元素的语法：
	selector:pseudo-element {property:value;}
	如：p:first-line
	  {color:#ff0000;
	  font-variant:small-caps;}

##元素/类型选择器 (优先级权重：1)

	择器通常将是某个 HTML 元素，比如 p、h1、em、a，甚至可以是 html 本身：
	html {color:black;}
	h1 {color:blue;}
	h2 {color:silver;}
	通配符选择器 (优先级权重：0)
	例如，下面的规则可以使文档中的每个元素都为红色：
	* {color:red;}
	Ø  CSS 选择器组合关系
	CSS 分组
	例如，如果您想把很多元素显示为灰色，可以使用类似如下的规则：
	body, h2, p, table, th, td, pre, strong, em {color:gray;}
	后代选择器
	举例来说，如果您希望只对 h1 元素中的 em 元素应用样式，可以这样写：
	h1 em {color:red;}
	子元素选择器
	如果您不希望选择任意的后代元素，而是希望缩小范围，只选择某个元素的子元素，请使用子元素选择器（Child selector）。
	例如，如果您希望选择只作为 h1 元素子元素的 strong 元素，可以这样写：
	h1 > strong {color:red;}
	这个规则会把第一个 h1 下面的 strong 元素变为红色，但是第二个 strong 不受影响：
	This is very important.
	This is really very important.
	结合后代选择器和子选择器
	请看下面这个选择器：
	table.company td > p
	上面的选择器会选择作为 td 元素子元素的所有 p 元素，这个 td 元素本身从 table 元素继承，该 table 元素有一个包含 company 的 class 属性。
	相邻兄弟选择器
	如果需要选择紧接在另一个元素后的元素，而且二者有相同的父元素，可以使用相邻兄弟选择器（Adjacent sibling selector）。
	例如，如果要增加紧接在 h1 元素后出现的段落的上边距，可以这样写：
	h1 + p {margin-top:50px;}
	这个选择器读作：“选择紧接在 h1 元素后出现的段落，h1 和 p 元素拥有共同的父元素”。
