#XDATA-HTML编码规范
---
## 1.概述

    1. 编写目的  
        为前端开发人员的HTML代码编写提供参考依据和统一标准
    2. 统一编程风格的意义  
        - 增加开发过程代码的强壮性、可读性、易维护性
        - 减少有经验和无经验开发人员编程所需的脑力工作
        - 为系统的良好维护打下好的基础
        - 在项目范围内统一代码风格
        - 通过人为以及自动的方式对最终软件应用质量标准
        - 使新的开发人员快速适应项目氛围
        - 支持项目资源的复用，允许开发人员从一个项目区域（或子项目团队）移动到另一个，而不需要重新适应新的子项目团队的氛围
        - 一个优秀而且职业化的开发团队所必需的素质
    3. 预期的读者和阅读建议  
        本文档适用于前端开发人员在进行HTML代码编写时进行参考  
---
## 2.文件规范

    1. html、css、js、images、fonts等文件目录组织如下所示

![文件目录组织][HTML-image1]

    2. 文件命名原则  
        所有字母小写，单词之间使用破折号（-）相连，压缩后的文件在原文件名（除扩展名）后添加.min，例如bootstrap-theme.css文件在压缩后变为bootstrap-theme.min.css
    3. 常用目录名  
        data（数据库）、images（图片）、install（安装）、templets（模版）、include（包含）、admin（后台）、rss（订阅）、media（媒体）、config（配置）、script（脚本）、language（语言）、style（样式）
---
## 3.代码风格

### 3.1-缩进与换行

    - 使用4个空格或一个TAB作为一个缩进层级
    - 模版代码的缩进优先保证HTML代码的缩进规则
### 3.2-命名规则

    - class的命名必须单词全字母小写，单词间以-分隔，且必须代表相应的模块或部件的内容或功能，不得以HTML内置样式进行命名，命名应该具有明确的语义，同时避免创建无样式信息的 class
    - id作为JavaScript Hook，其命名必须保持在页面中的唯一性，命名应该具有明确的语义
### 3.3-标签

#### 3.3.1-标签出现顺序

    标签出现的顺序如下所示
    ①<!DOCTYPE html>
    ②<html>  
        ③<head>  
            ④<meta http-equiv="Content-Type" content="text/html; chartset=UTF-8"> 
            ⑤<title>页面标题</title>  
        ③</head>  
        ⑥<body>  
        ⑥</body>  
    ②</html>  
#### 3.3.2-标签书写规范

    该部分只对标签书写进行规范说明，标签的具体说明详见*具体标签说明*
    - HTML中的标签必须使用小写字母
    - 标签的闭合要符合HTML5的规定，自闭合（self-closing tag）标签无需闭合，例如：img、input、br等;可选的闭合标签（closing tag）需闭合，例如<li></li>、<body></body>等
    - 标签必须合理嵌套*（详见标签嵌套规则）*
    - 标签的使用必须遵循标签的语义，例如：p：段落；h1、h2、h3、h4、h5、h6：层级标题；strong、em：强调；b：样式加粗；i：样式倾斜；ins：插入；del：删除；abbr：缩写；code：代码标识；cite：引述来源作品的标题；q：引用；blockquote：一段或长篇引用；ul：无序列表；lo：有序列表；dl、dt、dd：定义列表。语义化的HTML结构，有助于机器理解，另一方面多人协作时，能迅速了解开发者意图
    - 在CSS可以实现相同需求的情况下尽量不要使用表格进行布局
    - 应尽量减少标签的数量，通过迭代和重构可以达到该要求
#### 3.3.3-标签嵌套规则

    <a>不允许嵌套<div>这种约束属于语义嵌套约束，与之区别的约束还有严格嵌套约束，例如：<a>不允许嵌套<a>。严格嵌套约束在所有的浏览器下都不被允许，而语义嵌套约束，浏览器大多会容错处理，生成的文档树可能相互不太一样
    1. 语义嵌套约束
    - <li>用于<ul>或<ol>下
    - <dd>、<dt>用于<dl>下
    - <thead>、<tbody>、<tfoot>、<tr>、<td>用于<table>下
    2. 严格嵌套约束
    - inline-level元素，仅可以包含文本或其他inline-level元素
    - <a>里不可以嵌套交互式元素<a>、<button>、<select>等
    - <p>里不可以嵌套块级元素<div>、<h1>-<h6>、<p>、<ul>、<ol>、<li>、<dl>、<dt>、<dd>、<form>等
    3. 基本的标签嵌套规则
    - <body>可以直接包含块状元素、<ins>、<del>、<script>，不可以直接包含行内元素
    - <ins>和<del>可以包含块状元素或行内元素，其他任何行内元素都不允许包含块状元素
    - <p>、<h1>-<h6>可以直接包含行内元素和文本信息，但不允许包含块状元素
    - <dl>元素只允许包含<dt>和<dd>，同时<dt>不能包含块状元素，只允许包含行内元素，对于<dd>可以包含任何元素
    - <form>元素不能够直接包含<input>元素，因为<input>元素属于行内元素，<form>元素仅仅能够包含块状元素
    - <table>元素只能够包含<caption>、<colgroup>、<col>、<thead>、<tbody>、<tfoot>，不能够直接包含<tr>或其他任何元素
### 3.4-属性

    - 属性出现的顺序：id、class、name、data-xxx、src、for、type、href、title、alt、aria-xxx、role，以此保证属性的易读性
    - 属性必须使用小写字母，其属性值必须用双引号包围
    - 布尔类型的建议不添加属性值（disabled、checked、selected等属性不用设置值），自定义属性建议以×××-为前缀，推荐使用data-为前缀
    - 不要在HTML标签中嵌入使用CSS样式，这是一种很山寨的做法，同时不便于样式的管理
    - 为所有元素定义样式（class属性）
### 3.5-页面头部

#### 3.5.1-DOCTYPE

    DOCTYPE即文档声明，若是没有写文档声明，则会出现怪异解析。为每个HTML页面的第一行添加声明，这样能够确保在每个浏览器中拥有一致的表现
    - 使用DOCTYPE来启用标准模式，建议使用大写的DOCTYPE
#### 3.5.2-语言编码

    - 有助于提高页面的可访问性，必须设置正确的lang属性，例如：<html lang="zh-CN">
    - 页面必须指定字符编码的meta，且必须是head的第一个直接子元素，，例如<meta charset="UTF-8">*（详见具体标签说明中的<meta>标签）*
#### 3.5.3-CSS和JavaScript引入

    - 引入CSS时必须指明rel="stylesheet"，在引入CSS和JavaScript时必须指明type属性，例如：<link rel="stylesheet" href="code-guide.css"> <script type="text/javascript" src="code-guide.js"></script>
    - CSS文件外链至<head></head>之间，这样可以加快网页加载速度，因为这样可以使网页逐步渲染
    - JavaScript代码必须放在页面末尾或采用异步加载，因为当加载一个脚本时，页面会暂停加载，直到脚本完全载入，因此会浪费用户很多时间
#### 3.5.4-Head内容

    - <title>标签必须设置为<head>的直接子元素，并紧随charset声明之后*（详见具体标签说明中的title标签）*
    - 所有页面必须注明title名称
    - <head>标签里放置的内容不会在页面中显示，页面中显示的内容是放在<body>里面的，<head>部分除了放置<meta>、<title>标签，还有链接到CSS的link标签
### 3.6-图片

    - 为所有的图片加上alt属性这样可以让禁用图片或者使用特殊设备的用户无障碍了解你的网页信息，并且对图像搜索引擎友好。如只起装饰作用而没有任何意义的图片可设置alt属性值为空
    - 所有图形均要标注width及height属性（防止图片变形）
    - 禁止<img>的src取值为空，延迟加载的图片也要增加默认的src属性值
### 3.7-表单

#### 3.7.1-控件标题

    - 文本标题的控件必须使用<label>标签将其与其标题相关联，例如：<label><input type="checkbox" name="confirm" value="on">我已确认上述条款</label>或<label>用户：</label><input type="text" name="user" id="user">
#### 3.7.2-按钮

    - 使用<button>元素时必须指明type属性值
#### 3.7.3-可访问性

    - 当使用JavaScript进行表单提交时，应使原生提交功能正常工作
    - 根据内容类型指定输入框的type属性，例如：<input type="date">
### 3.8-多媒体

    - 使用<audio>以及<video>标签来播放音频、视频时，应当注意格式。音频格式：MP3、WAV、Ogg，MP4、WebM、Ogg
### 3.9-注释

    - 针对页面或模块的CSS、JavaScript代码必须进行详细的注释
    - 给区块代码及重要功能（比如循环）加上注释，方面后台添加功能
    - 模块注释：<!-- 文章列表模块 -->
    - 区块注释，例如：
        <!--
        @name: ......
        @description: ......
        @author: ......
        -->
---
## 4.具体标签说明

### 4.1-概述

    本章中所列出的标签均为前端开发中常用的标签控件，每个标签具体的属性可以参考：[W3School-HTML](http://www.w3school.com.cn/tags/html_ref_byfunc.asp)
### 4.2-注释标签

    HTML使用<!--...-->作为注释标签，用来在源文档中插入注释。注释不会在浏览器中显示
### 4.3-DOCTYPE标签

    <!DOCTYPE>声明位于文档中的最前面的位置，处于<html>标签之前，<!DOCTYPE>声明不是一个HTML标签；它是用来告知Web浏览器页面使用了哪种HTML版本
### 4.4-html标签

    <html>标签告知浏览器这是一个HTML文档,该标签是HTML文档中最外层的元素，是所有其他HTML元素（除了<!DOCTYPE>标签）的容器
### 4.5-head标签

    <head>标签是所有头部元素的容器，<head>标签必须包含文档的标题（title），可以包含脚本、样式、meta信息以及其他更多的信息，如下所示
    - <title>，在头部中，这个标签是必须的
    - <style>
    - <base>
    - <link>
    - <meta>
    - <script>
    - <noscript>
### 4.6-meta标签

    <meta>标签：提供的是有关页面的元信息（meta-information）,里面的charset="utf-8"表示字符编码，因为不同国家的语言不同，其转义的方式不同，所以为了不会出现乱码的情况，必须加上一个字符编码，而"utf-8"又被称为万国码
    <meta>标签的属性有两种：
    - name和content：name属性用于描述网页，它以“名称/值”来表现，而name具体的内容则由content属性来表示，其中，name一般使用较多的是keywords（关键字）、description（简短的描述），便于爬虫查找和分类，如下图所示  

![name和content属性][HTML-image2]

    - http-equiv与content属性，目前较多是使用它们进行页面的刷新与跳转，如下图所示  

![http-equiv和content属性][HTML-image3]

### 4.7-title标签

    <title>标签：用来表示网页是用来干什么的，<title>标签的内容会在浏览器的标题栏中进行显示
    注意：<meta>标签一定是在<title>标签的前面，原因是：网页的读取顺序是从上到下，要先进行字符编码的设置，不然<title>里面的内容就有可能出现乱码
    <title>标签定义浏览器工具栏中的标题，提供页面被添加到收藏夹时的标题，显示在搜索引擎结果中的页面标题
### 4.8-link标签

    <link>标签定义文档与外部资源的关系，<link>标签最常见的用途是链接样式表
    注意：<link>元素是空元素，它仅包含属性；此元素只能存在于<head>部分，不过它可出现任何次数
### 4.9-style标签

    <style>标签定义HTML文档的样式信息。在<style>标签中，用户可以规定在浏览器中如何呈现HTML文档
    每个HTML文档能包含多个<style>标签
### 4.10-script标签

    <script>标签用于定义客户端脚本，比如JavaScript。<script>标签既可包含脚本语句，也可以通过"src"属性指向外部脚本文件。JavaScript通常用于图像操作、表单验证以及动态内容更改
    如果使用"src"属性，则<script>标签必须是空的
    有多种执行外部脚本的方法，如下所示
    - 如果async="async"：脚本相对于页面的其余部分异步地执行（当页面继续进行解析时，脚本将被执行）
    - 如果不使用async且defer="defer"：脚本将在页面完成解析时执行
    - 如果既不使用async也不使用defer：在浏览器继续解析页面之前，立即读取并执行脚本
### 4.11-body标签

    <body>标签定义文档的主体，包含文档的所有内容（比如文本、超链接、图像、表格和列表等等）
### 4.12-h1-h6标签

    用来定义HTML标题，<h1>定义重要等级最高的标题。<h6>定义重要等级最低的标题
    如果是博客，应把<h1>标签留给文章标题
### 4.13-p标签

    用于定义段落，<p>标签会自动在其前后创建一些空白。浏览器会自动添加这些空间，用户也可以在样式表中规定
### 4.14-form标签

    <form>标签用于创建供用户输入的HTML表单，该标签可以包含一个或多个如下的表单元素：<input>、<textarea>、<button>、<select>、<option>、<optgroup>、<fieldset>、<label>
### 4.15-input标签

    <input>标签规定了用户可以在其中输入数据的输入字段，该标签在<form>标签中使用，用来声明允许用户输入数据的input控件，输入字段可通过多种方式改变，取决于 type 属性
### 4.16-textarea标签

    <textarea>标签定义一个多行的文本输入控件，文本区域中可容纳无限数量的文本，其中的文本的默认字体是等宽字体（通常是Courier）。可以通过cols和rows属性来规定textarea的尺寸大小，不过更好的办法是使用CSS的height和width属性
### 4.17-button标签

    <button>标签定义一个按钮，该标签内部，用户可以放置内容，比如文本或图像。这是该标签与使用<input>标签创建的按钮之间的不同之处
    提示：应始终为button标签规定type属性，不同的浏览器<button>标签的type属性使用不同的默认值
### 4.18-select标签

    <select>标签用来创建下拉列表，<select>标签中的<option>标签定义了列表中的可用选项
### 4.19-label标签

    <label>标签为<input>标签定义标注（标记），<label>标签不会向用户呈现任何特殊效果。不过，它为鼠标用户改进了可用性。如果用户在<label>标签内点击文本，就会触发此控件。就是说，当用户选择该标签时，浏览器就会自动将焦点转到和标签相关的表单控件上
    <label>标签的for属性应当与相关元素的id属性相同
### 4.20-img标签

    <img>标签定义HTML页面中的图像，有两个必需的属性：src和alt
    从技术上讲，图像并不会插入HTML页面中，而是链接到HTML页面上。<img>标签的作用是为被引用的图像创建占位符
    提示：通过在<a>标签中嵌套<img>标签，给图像添加到另一个文档的链接
### 4.21-canvas标签

    <canvas>标签通过脚本（通常是JavaScript）来绘制图形（比如图表和其他图像），<canvas>标签只是图形容器，用户必须使用脚本来绘制图形
### 4.22-a标签

    <a>标签定义超链接，用于从一个页面链接到另一个页面。<a>标签最重要的属性是href属性，它指定链接的目标
    在所有浏览器中，链接的默认外观如下：
    - 未被访问的链接带有下划线而且是蓝色的
    - 已被访问的链接带有下划线而且是紫色的
    - 活动链接带有下划线而且是红色的
### 4.23-ul标签

    <ul>标签定义无序列表，<ul>标签与<li>标签一起使用，创建无序列表
### 4.24-ol标签

    <ol>标签定义了一个有序列表，列表排序以数字来显示。<ul>标签与<li>标签一起使用，定义列表选项
### 4.25-li标签

    <li>标签定义列表项目，<li>标签可用在有序列表（<ol>）、无序列表（<ul>）和菜单列表（<menu>）中
### 4.26-div标签

    <div>标签定义HTML文档中的一个分隔区块或者一个区域部分，<div>标签常用于组合块级元素，以便通过CSS来对这些元素进行格式化
    默认情况下，浏览器通常会在<div>标签前后放置一个换行符。然而，用户可以通过使用CSS改变这种情况
### 4.27-span标签

    <span>标签用于对文档中的行内元素进行组合。<span>标签没有固定的格式表现。当对它应用样式时，它才会产生视觉上的变化。如果不对<span>应用样式，那么<span>元素中的文本与其他文本不会任何视觉上的差异
    <span>标签提供了一种将文本的一部分或者文档的一部分独立出来的方式
### 4.28-table标签

    若设计的界面可以用HTML+CSS实现，则尽量不要使用<table>标签，若一定要使用<table>标签，则在此对其进行相应的说明
    <table>标签定义HTML表格，一个HTML表格包括<table>标签，一个或多个<tr>、<th>以及<td>标签
    <tr>标签定义表格行，<th>标签定义表头，<td>标签定义表格单元。更复杂的HTML表格也可能包括<caption>、<col>、<colgroup>、<thead>、<tfoot>以及<tbody>标签
#### 4.28.1-table标签使用规范

    1. 尽量不使用百分比进行宽高控制
    2. table尽量横切，便于加快下载速度
    3. table位置说明，这里所说的table位置是指表格位于页面左、中、右，一般不指上、中、下。table居左：<table align=left>，由于缺省值是居左，所以这里的align=left可以不写；table居中：<table align=center>，不要写成<center>表格</center>；table居右：<table align=right>
    4. table缩进，应尽量避免表格嵌套过多的情况发生，对于不可避免的表格嵌套，应以以下方法写，每级table以一个TAB缩进，属于本级table下的<tr>、<td>应对齐本级<table>标签
    5. 定义表格宽、高，一般简单的定义表格的宽高，就在<table>、<tr>或<td>里面定义width和height属性值就可以了，有一些技巧，如下所示
    - 同列表格的宽：同列表格如果宽度一样，只写第一行定义的宽度，其他的允许不写
    - 同行表格的高：同行表格如果高一样，则把height属性写入<tr>中，<td>内部需要做单独定义，另外其他同行相同的定义，如背景颜色等，均可写入<tr>
---
## 5.其他规范

    - _开发中随时进行标准验证_
    - _压缩前端代码_
    - 书写链接时，建议在URL地址后面加上“/”，例如：href="http://.../.../"
    - 不属于标签部分的特殊符号都用编码表示，出现在内容中的特殊符号都需要用编码形式表现出来，例如："<"用&lt表示，">"用&gt表示，"&"用&amp表示，"用&quot表示，尽量用&nbsp;表示空格
    - body中必须标明background-color属性，无背景色时赋值#fff
    - 对16进制数的标识一定要加"#"
    - 禁止在字符串尾部加空格方式控制屏幕位置
    - 字体字号需要规范使用，突出主次层级
---
## 6.补充说明

### 6.1-IE兼容说明

    - 优先使用最新版本的IE和Chrome内容
    - 使用代码<meta http-equiv="X-UA-Compatible" content="IE=edge, chrome=1">
    - 如果CSS样式表基本定型，那么可以为IE单独建立一个样式表，然后仅对IE生效，例如：<!--[if it IE 7]><link rel="stylesheet" type="text/css" media="screen" href="path/to/ie.css/"/><![end if]-->
### 6.2-SEO优化

    SEO：是由英文Search Engine Optimization缩写而来，中文译为“搜索引擎优化”。SEO是指通过站内优化比如网站结构调整、网站内容建设、网站代码优化等以及站外优化，比如网站站外推广、网站品牌建设等，使网站满足搜索引擎收录排名需求，在搜索引擎中提高关键词排名
    <head>  
        <meta charset="utf-8">
        <!-- 兼容IE -->
        <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">  
        <!-- SEO优化 -->  
        <title>Style Guide</title>  
        <meta name="keywords" content="your keywords">  
        <meta name="description" content="your description">  
        <meta name="author" content="author,email address">  
    </head>  
### 6.3-viewport（移动端）

    - viewport：一般指的是浏览器窗口内容区的大小，不包含工具条、选项卡等内容
    - width：浏览器宽度，输出设备中的页面可见区域宽度
    - device-width：设备分辨率宽度，输出设备的屏幕可见宽度
    - initial-scale：初始缩放比例
    - maximum-scale：最大缩放比例
    - 例如，为移动端设备优化，设置可见区域的宽度和初始缩放比例：<meta name="viewport" content="width=device-width, initial-scale=1.0">
### 6.4-IOS图标（移动端）

    - apple-touch-icon：图片自动处理成圆角和高光等效果
    - apple-touch-icon-precomposed：禁止系统自动添加效果，直接显示设计原图
    - 例子如下所示  
    <!-- iPhone 和 iTouch，默认 57x57 像素，必须有 -->
    <link rel="apple-touch-icon-precomposed" href="/apple-touch-icon-57x57-precomposed.png">
    <!-- iPad，72x72 像素，可以没有，但推荐有 -->
    <link rel="apple-touch-icon-precomposed"     href="/apple-touch-icon-72x72-precomposed.png" sizes="72x72">
    <!-- Retina iPhone 和 Retina iTouch，114x114 像素，可以没有，但推荐有 -->  
    <link rel="apple-touch-icon-precomposed" href="/apple-touch-icon-114x114-precomposed.png" sizes="114x114">
    <!-- Retina iPad，144x144 像素，可以没有，但推荐有 -->
    <link rel="apple-touch-icon-precomposed" href="/apple-touch-icon-144x144-precomposed.png" sizes="144x144">
---
*本规范文档将不断修改更新，请各位批评指正*

[HTML-image1]:https://github.com/DIST-XDATA/Code-Conventions/blob/master/image/HTML-image1.png
[HTML-image2]:
[HTML-image3]:
