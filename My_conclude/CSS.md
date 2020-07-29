### CSS基础复习
**一、分析opacity：0、visibility：hidden、display：none**优劣和使用场景
* 结构：
   display：none 会让元素完全从渲染树中消失，渲染的时候不占据任何空间，不能点击；
   visibility：hidden 不会让元素从渲染树中消失，渲染元素继续占据空间，只是内容不可见，不能点击；
   opacity：0 不会让元素从渲染树消失，渲染元素继续占据空间，只是内容不可见，可以点击。
* 继承：
   display：none 是非继承属性，子孙节点消失由于元素从渲染树消失造成，通过修改子孙节点属性无法显示；
   visibility：hidden 是继承属性，子孙节点消失由于继承了hidden，通过设置visibility:visible;可以让子孙节点显示。
* 性能：
   display：none修改元素造成文档回流，读屏器不会读取 display：none元素内容，性能消耗较大。
   visibility：hidden修改元素只会造成元素的重绘，性能消耗较少读屏器读取visibility：hidden元素内容。
   opacity：0 修改元素造成重绘，性能消耗较少。
* 联系：他们都可以让元素不可见。

**二、清除浮动的方式有哪些？比较好的是哪一种？**
常见的一般为三种：clearfix，clear：both，overflow：hidden
比较好的是clearfix，后两者有局限性

**三、CSS Sprite是什么，有什么优缺点**
CSS Sprite是一种网页图片应用处理方式，就是吧网页中一些背景图整合到一张图片文件中，再利用CSS的“background-image”，“background-repeat”，“background-position”的组合进行背景定位。
其优点在于：
* 减少网页的http请求，提高性能，极大地提高页面加载速度，这也是CSS Sprite 最大的优点，也是其被广泛应用的主要原因；
* 增加图片信息重复度，提高压缩比，减少图片大小。
* 减少了命名困扰：只需对一张集合图片命名，不需要对每一个小元素进行命名提高制作效率。
* 更换风格方便：只需要在一张或少张图片上修改图片的颜色或样式，整个网页的风格就可以改变，维护起来更加方便。
缺点：
* 图片合成比较麻烦；
* 背景设置时，需要得到每一个背景单元的精确位置；
* 维护合成图片，最好只是往下加图片，而不要更改已有图片。
**四、介绍一下css的盒子模型？**
* 有两种，IE盒子模型、标准W3C盒子模型；IE的content部分中包含了border和padding；
* 盒模型：内容(content)、填充(padding)、边界(margin)、边框(border).
**五、列出display的值，说明作用。position的值，relative和absolute定位原点是？**
* display：
   * block 像块类型元素一样显示。
   * none 缺省值。像行内元素类型一样
   * inline-block 向行内元素一样显示，但其内容象块类型元素一样显示
   * list-item 象块类型元素一样显示，并添加样式列表标记。
* position：
   * absolute：生成绝对定位的元素，相对于static定位以外的第一个父元素进行定位。
   * fixed：固定定位，相对于了浏览器窗口进行定位
   * relative：生成相对定位的元素，相对于其正常位置进行定位
   * static 默认值。没有定位，元素出现在正常的流中。（忽略top，bottom，left，right，z-index）
   * inherit 规定从父元素继承属性的值。

**六、 容器包含若干浮动元素是如何清理浮动？？？**
   1. 容器元素闭合标签前添加额外元素并设置clear：both
   2. 父元素触发块级格式化上下文
   * 块级格式化上下文，它是一个独立的渲染区域，这个区域与外部毫不相干。
   * 触发条件：
      * 根元素（例如：html）
      * 元素浮动了（float不为none）
      * position为absolute或fixed
      * display为inline-block、table-sell、flex
      * overflow不为visible
   设置容器元素伪元素进行清理（推荐的清理浮动方法）

**七、display，position，float的关系**
   1. display为none，那么就不会生成元素对应的框，这种情况下，position和float都不起作用
   2. display非none，如果一个元素的position属性设置为absolute或者fixed，这种情况下，float被忽略，框的位置取决于属性 top、right、bottom、left以及box的容器
   3. display非none，并且position非absolute、fixed，如果float的值不为null，那么box是浮动的并且display的值为block
   4. display非none，并且position非absolute、fixed，float为none，不是根元素，那么就按照被指定的display的属性值来显示
   