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

[【scroll兼容】](http://www.cnblogs.com/xwgli/p/3490466.html)<br/>
[【各种宽度高度解析】](http://www.360doc.com/content/11/1025/09/432969_158877433.shtml)<br/>

[【事件绑定】]()<br/>

	W3C addEventListener removeEventListener
	IE  attachEvent detachEvent
	
结合siblim-tools.js 和 事件绑定.pdf 学习。


