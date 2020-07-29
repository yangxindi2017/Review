### HTML基础复习
**<font color=red size=4>
一、 link和@import的区别？
</font>**
 1. link属于XHTML标签，而@import是CSS提供的；
 2. 页面被加载的时，link会同时被加载，而@import引用的css会等页面被加载完在加载；
 3. import只在IE5以上才能识别，而link是XHTML标签，无兼容问题；
 4. link方式的样式的权重，高于@import的权重。

**<font color=red size=4>
二、 html5有哪些新特性、移除了哪些元素？如何处理html5新标签的浏览器兼容问题？如何区分HTML和HTML5
</font>**

1. HTML5 现在已经不是SGML的子集，主要是关于图像，位置，存储，多任务等功能的增加。
   1. 新增特性 绘画canvas，用于媒介回放的video和audio元素；
   2. 本地离线存储 localstorage长期存储数据，浏览器关闭后数据不丢失;sessionStorage的数据在浏览器关闭后自动删除；
   3. 语义化更好的内容元素，article、footer、header、nav、section，表单控件calendar，time，date，email，url，search
   4. 新的技术webworker、websocket、Geolocation
2. 移除的元素
   1. 纯表现的元素：basefont,big,center,font,s,strike,tt,u;
   2. 对可用性产生负面影响的元素：frame，frameset，noframes;
3. 兼容性问题
   1. IE8/IE7/IE6支持通过document,createElement方法产生的标签，
   可以利用这一特性让这些浏览器支持HTML5 新标签；
   2. 浏览器支持新标签后，还需要添加标签的默认样式；
   3.当然最好的方法是直接使用成熟的框架、使用最多的是<font color=red >html5shim框架</font>

**三、Doctype的作用？严格模式和混杂模式如何区分？他们有何意义？ 参考：[吴秋桐博客](https://www.cnblogs.com/wuqiutong/p/5986191.html)**
1. 作用？
   <!DOCTYPE>声明叫做文件类型定义（DTD），必须在文档的最前面，告诉浏览器以何种方式渲染页面，这里有两种模式，严格模式和混杂模式。
2. 严格模式和混杂模式如何区分？
   * 严格模式：又称标准模式，是指浏览器按照W3C标准解析代码。
   * 混杂模式：又称怪异模式或兼容模式，是指浏览器用自己的方式解析代码，向后兼容，模拟老式浏览器，防止浏览器无法兼容页面。
   * 如何区分：浏览器解析时到底是用严格模式还是混杂模式，与网页中DTD直接相关。
3. 他们有何意义？
   严格模式与混杂模式存在的意义与其来源密切相关，如果说只存在严格模式，那么许多旧网站必然受到影响，如果只存在混杂模式，那么会回到当时浏览器大战时的混乱，每个浏览器都有自己的解析模式。

**四、块级元素和行内元素有哪些，以及区别？**
块级元素多为结构性的，行内元素为描述性的
* 区别：
   * 块级元素：
   1. 独占一行
   2. 可以设置宽度、高度、外边距、内边距
   3. 宽度默认是父级的100%
   4. 里边可以放行内或块级元素
   **<font color=red>注意：文字类的元素（p标签、h1-h6标签）内不能使用块级元素</font>**
   * 行内元素
   1. 相邻行内元素都在一行上
   2. 不可以设置高度、宽度
   3. padding（top、bottom），margin（top、bottom）无效
   4. padding、marign(left/right)有效
   **行内元素的padding-top、padding-bottom从显示效果上是增加的，但其实设置的是无效果的，并不会对周围的元素产生任何影响。**
   5. line-height有效
   6. 宽度是他本身内容的宽度
   7. 只能放文本或者其他行内元素
   **<font color=red>注意：1. 链接里不能放链接 2. a便签里可以放块级元素，但是将a标签转换为块级模式最安全</font>**
   * 行内块元素
   1. 相邻行内块元素在一行上，但是他们之间会有空白间隙（元素之间的空格转换的）
   2. 可以设置高度、宽度、外边距、内边距、行高
   3. 宽度是它本身内容的宽度