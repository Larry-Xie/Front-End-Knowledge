# 前端面试

## HTML

1. `Doctype`的作用是什么？
    > `<!DOCTYPE>`声明位于位于HTML文档中的第一行，处于 `<html>` 标签之前。告知浏览器的解析器用什么文档标准解析这个文档。DOCTYPE不存在或格式不正确会导致文档以兼容模式呈现。

2. 标准模式与兼容模式各有什么区别?
    >标准模式的排版 和JS运作模式都是以该浏览器支持的最高标准运行。在兼容模式中，页面以宽松的向后兼容的方式显示,模拟老式浏览器的行为以防止站点无法工作。

3. 行内元素有哪些？块级元素有哪些？ 空(void)元素有那些？
    > CSS规范规定，每个元素都有display属性，确定该元素的类型，每个元素都有默认的display值。  
    > 行内元素有：`a` `b` `span` `img` `input` `select` `strong`  
    > 块级元素有：`div` `ul` `ol` `li` `h1` `h2` `h3` `h4` `p`  
    > 空元素有：`<br>` `<hr>` `<img>` `<input>` `<link>` `<meta>`

4. 介绍一下你对浏览器内核的理解？
    > 主要分成两部分：渲染引擎(layout engineer或Rendering Engine)和JS引擎。  
    > 渲染引擎：负责取得网页的内容（HTML、XML、图像等等）、整理讯息（例如加入CSS等），以及计算网页的显示方式，然后会输出至显示器或打印机。浏览器的内核的不同对于网页的语法解释会有不同，所以渲染的效果也不相同。  
    > JS引擎：解析和执行javascript来实现网页的动态效果。

5. 常见的浏览器内核有哪些？
    > Trident内核：IE,MaxThon,TT,The World,360,搜狗浏览器等  
    > Gecko内核：Netscape6及以上版本，FF,MozillaSuite/SeaMonkey等  
    > Presto内核：Opera7及以上  
    > Webkit内核：Safari，Chrome等

6. `HTML5`有哪些新特性、移除了那些元素？
    > `HTML5` 现在已经不是 SGML 的子集，主要是关于图像，位置，存储，多任务等功能的增加：
        > * 绘画 canvas;
        > * 用于媒介回放的 video 和 audio 元素;
        > * 本地离线存储 localStorage 长期存储数据，浏览器关闭后数据不丢失;
        > * sessionStorage 的数据在浏览器关闭后自动删除;
        > * 语意化更好的内容元素，比如 article、footer、header、nav、section;
        > * 表单控件，calendar、date、time、email、url、search;
        > * 新的技术webworker, websocket, Geolocation;
    > 删除的元素：
        > * 纯表现的元素：basefont，big，center，font, s，strike，tt，u;
        > * 对可用性产生负面影响的元素：frame，frameset，noframes；

7. 简述一下你对HTML语义化的理解?
    > 用正确的标签做正确的事情。  
    > html语义化让页面的内容结构化，结构更清晰，便于对浏览器、搜索引擎解析;  
    > 即使在没有样式CSS情况下也以一种文档格式显示，并且是容易阅读的;  
    > 搜索引擎的爬虫也依赖于HTML标记来确定上下文和各个关键字的权重，利于SEO;  
    > 使阅读源代码的人对网站更容易将网站分块，便于阅读维护理解。

8. 请描述一下 cookies，sessionStorage 和 localStorage 的区别？
    > cookie是网站为了标示用户身份而储存在用户本地终端（Client Side）上的数据（通常经过加密）。cookie数据始终在同源的http请求中携带（即使不需要），记会在浏览器和服务器间来回传递。  
    > sessionStorage和localStorage不会自动把数据发给服务器，仅在本地保存。

    > 存储大小：
        > * cookie数据大小不能超过4k。
        > * sessionStorage和localStorage 虽然也有存储大小的限制，但比cookie大得多，可以达到5M或更大。

    > 有期时间：
        > * localStorage: 存储持久数据，浏览器关闭后数据不丢失除非主动删除数据；
        > * sessionStorage: 数据在当前浏览器窗口关闭后自动删除。
        > * cookie: 设置的cookie过期时间之前一直有效，即使窗口或浏览器关闭

9. `iframe`有哪些缺点？
    > `iframe`会阻塞主页面的Onload事件；  
    > 搜索引擎的检索程序无法解读这种页面，不利于SEO;  
    > iframe和主页面共享连接池，而浏览器对相同域的连接有限制，所以会影响页面的并行加载。  
    > 使用iframe之前需要考虑这两个缺点。如果需要使用iframe，最好是通过javascript动态给iframe添加src属性值，这样可以绕开以上两个问题。

10. `title`与`h1`的区别、`b`与`strong`的区别、`i`与`em`的区别？ 
    > `title`属性没有明确意义只表示是个标题，`H1`则表示层次明确的标题，对页面信息的抓取也有很大的影响；  
    > `strong`是标明重点内容，有语气加强的含义，使用阅读设备阅读网络时：`<strong>`会重读，而`<b>`是展示强调内容。  
    > `i`内容展示为斜体，`em`表示强调的文本；

11. `defer`和`async`的区别？
    > defer并行加载js文件，会按照页面上script标签的顺序执行   
    > async并行加载js文件，下载完成立即执行，不会按照页面上script标签的顺序执行

12. 从输入网址到页面呈现的过程？
    > 通过dns解析获取ip  
    > tcp链接  
    > 客户端发送http请求  
    > tcp传输报文  
    > 服务器处理请求返回http报文
    > 客户端解析渲染页面 （构建DOM树 –> 构建渲染树 –> 布局渲染树：计算盒模型位置和大小 –> 绘制渲染树）

13. 为什么通常推荐将 CSS `<link>` 放置在 `<head></head>` 之间，而将 JS `<script>` 放置在 `</body>` 之前？
    > html顺序加载，其中js会阻塞后续dom和资源的加载，css不会阻塞dom和资源的加载但是会阻塞js的加载。
