JavaScript兼容性.md
===
	非入侵式JavaScript的观点可以从很多角度进行解读，大体是针对以下几个观点：
		1．并不是每个人的浏览器都支持JavaScript。你需要让每个人都能看到你的全部内容，
		而且无须在浏览器中执行代码就能够使用你的应用。
		2．有些人会使用一些运行方式非常奇怪的浏览器。比如视觉受损的人会使用屏幕阅
		读器，一些手机用户无法使用含有JavaScript的站点。
		3．JavaScript在不同的平台上运行方式不同。IE是造成这一问题的罪魁祸首。我们需
		要根据不同的浏览器编写不同的事件处理代码。
		4．这些事件处理器都会引用全局命名空间中的函数。如果你想把其他类库集成进来，
		而这些类库又带有相同的函数名称，那么你就会头疼了。
		5．这些事件监听器都会绑定数据结构和行为。这让你的代码更加难以维护、扩展和理解。

观点1  已经不再正确，几乎所有的浏览器都支持JavaScript。<br/>
观点2  最新的屏幕阅读器已经赶上来了。*ARIA语义学标签*<br/>
观点3  
#1、解决 split在chrome上不能用,不能错误提示

onKeyDownCheck<br/>(/635)
chrome <br/>
obj   [object HTMLInputElement]<br/>
ctype  undifined<br/>

IE<br/>
obj   [object]<br/>
ctype  k_zinteger<br/>

将ctype 改为 alert(type),传回text，在HTML上定义type="password"  传回password<br/>

[参考地址](http://blog.csdn.net/xxtjp/article/details/6852496)<br/>
obj.getAttribute('ctype');<br/>

{解决完成}<br/>
---
需要修改的文件 <br/>
修改split兼容性<br/>
 obj.ctype  改为 obj.getAttribute('ctype')<br/>

#2、解决 输入字母的时候，输入法在中文时一直提示错误，在onKeyDown时间

用css控制输入法让其变为英文输入格式<br/>

[参考地址](http://www.lidaren.com/archives/1240)<br/>
[参考地址](http://www.xue51.com/tuwen/slf-1226.html)<br/>

	/*Chrome Safari*/
	-webkit-ime-mode: auto | active | inactive | disabled
	/*Mozilla Firefox*/
	-moz-ime-mode: auto | active | inactive | disabled
	/*Opera*/
	-o-ime-mode: auto | active | inactive | disabled
	/*Internet Explorer*/
	-ms-ime-mode: auto | active | inactive | disabled
	/*CSS3 Standard*/
	ime-mode: auto | active | inactive | disabled

	<html xmlns="http://www.w3.org/1999/xhtml" >
	<head>
	<meta charset="UTF-8">
	<title>标题页</title>
	</head>
	<body>
	默认：<input><br>
	中文：<input style="ime-mode:active"><br>
	英文：<input style="ime-mode:inactive" onkeyup="this.value=this.value.replace(/[\u4e00-\u9fa5]/g,'')"><br/>

	</body>
	</html>

【But】在Chrome 30.0.1599.69 以后已经失效了，
【So】目前只能结合js来手动进行控制

[参考地址](http://blog.csdn.net/okkk/article/details/5899056)

时间顺序

	onkeydown
	onkeyup
	onkeypree
	文本框赋值

所以输入的时候，onkeydown最先提示的value值为空null

	if(msg == 2 || msg ==3){
    	if(key >=65 && key <= 90){
    		checkLength();
    	} else {
    		setFlag(false);
    	}
    }

key值在中文下a-z为229,英文下为65<br/>
; '' . / ,都为229

[键值参考目录](http://www.360doc.com/content/10/1120/17/4372345_70965202.shtml)

	解决方法1，但是输入在./等，没有提示弹框错误，只有文本框错误。
		if(msg == 2 || msg ==3){
	    	if(key >=65 && key <= 90 || key == 229){
	    		checkLength();
	    	} else {
	    		setFlag(false);
	    	}
	    }

##待其他方法解决

