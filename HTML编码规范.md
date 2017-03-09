# XDATA-HTML编码规范

## 目录

- [1 概述](#1)    
    
- [2 文件规范](#2)    
    
- [3 代码风格](#3)    
    
  - [3.1 通用](#3.1)    
    
  - [3.2 缩进与换行](#3.2)    
    
  - [3.3 命名规则](#3.3)    
    
  - [3.4 标签](#3.4)    
    
    - [3.4.1 标签出现顺序](#3.4.1)      
    
    - [3.4.2 标签书写规范](#3.4.2)      
    
    - [3.4.3 标签嵌套规则](#3.4.3)      
      
      - [3.4.3.1 语义嵌套约束](#3.4.3.1)      
      
      - [3.4.3.2 严格嵌套约束](#3.4.3.2)      
      
      - [3.4.3.3 基本标签嵌套规则](#3.4.3.3)      
      
      - [3.4.3.4 其他嵌套规则](#3.4.3.4)      
    
  - [3.5 属性](#3.5)    
    
  - [3.6 页面头部](#3.6)    
    
    - [3.6.1 DOCTYPE](#3.6.1)    
    
    - [3.6.2 语言编码](#3.6.2)    
    
    - [3.6.3 CSS和JavaScript引入](#3.6.3)    
    
    - [3.6.4 Head内容](#3.6.4)    
    
  - [3.7 图片](#3.7)    
  
  - [3.8 表单](#3.8)    
    
    - [3.8.1 控件标题](#3.8.1)    
    
    - [3.8.2 按钮](#3.8.2)    
    
    - [3.8.3 可访问性](#3.8.3)    
    
    - [3.8.4 其他事项](#3.8.4)    
    
  - [3.9 多媒体](#3.9)    
    
- [4 具体标签说明](#4)    
    
  - [4.1 概述](#4.1)    
  
  - [4.2 注释标签](#4.2)    
  
  - [4.3 DOCTYPE标签](#4.3)    
  
  - [4.4 html标签](#4.4)    
  
  - [4.5 head标签](#4.5)    
  
  - [4.6 meta标签](#4.6)    
  
  - [4.7 title标签](#4.7)    
  
  - [4.8 link标签](#4.8)    
  
  - [4.9 style标签](#4.9)    
  
  - [4.10 script标签](#4.10)    
  
  - [4.11 body标签](#4.11)    
  
  - [4.12 h1-h6标签](#4.12)    
  
  - [4.13 p标签](#4.13)    
  
  - [4.14 form标签](#4.14)    
  
  - [4.15 input标签](#4.15)    
  
  - [4.16 textarea标签](#4.16)    
  
  - [4.17 button标签](#4.17)    
  
  - [4.18 select标签](#4.18)    
  
  - [4.19 label标签](#4.19)    
  
  - [4.20 img标签](#4.20)    
  
  - [4.21 canvas标签](#4.21)    
  
  - [4.22 a标签](#4.22)    
  
  - [4.23 ul标签](#4.23)    
  
  - [4.24 ol标签](#4.24)    
  
  - [4.25 li标签](#4.25)    
  
  - [4.26 div标签](#4.26)    
  
  - [4.27 span标签](#4.27)    
  
  - [4.28 table标签](#4.28)    
    
    - [4.28.1 table标签使用规范](#4.28.1)    
  
- [5 其他规范](#5)    
    
- [6 补充说明](#6)    
    
  - [6.1 IE兼容说明](#6.1)    
    
  - [6.2 SEO优化](#6.2)    
    
  - [6.3 viewport（移动端）](#6.3)    
    
  - [6.4 IOS图标（移动端）](#6.4)    
    
<h2 id="1">1 概述</h2>

一个优秀的程序员应该能够编写既能让电脑识别的代码又能让其他开发人员能够看懂并愿意去看的规范代码（规范代码就是结构清晰、可读性高、代码易于维护、不至于太过程化而杂乱无章），也就是书写可维护性的代码  

**基本概念**  

可维护代码需要遵循以下规则：  
- 可理解性：其他人可以接手代码并理解它的意图和一般途径而无须原开发人员的完整解释  
- 直观性：代码中的东西一看就能明白，不管其操作过程多么复杂  
- 可适应性：代码在重复使用时只要求更改传入的参数而不要求修改或重写代码以达到要求  
- 可扩展性：在代码架构上已考虑到未来允许对核心功能进行扩展  
- 可调试性：当有地方出错时，代码可以给予开发人员足够的信息来尽可能直接的确定问题所在，一种让代码变得可维护的简单途径就是形成一套JavaScript代码的书写约定  

**编写目的**  

为前端开发人员的JavaScript代码编写提供参考依据和统一标准  

**统一编程风格的意义**  

- 增加开发过程代码的强壮性、可读性、易维护性  
- 减少有经验和无经验开发人员编程所需的脑力工作  
- 为系统的良好维护打下好的基础  
- 在项目范围内统一代码风格  
- 通过人为以及自动的方式对最终软件应用质量标准  
- 使新的开发人员快速适应项目氛围  
- 支持项目资源的复用，允许开发人员从一个项目区域（或子项目团队）移动到另一个，而不需要重新适应新的子项目团队的氛围  
- 一个优秀而且职业化的开发团队所必需的素质  

**预期的读者和阅读建议**  

- 本文档适用于前端开发人员在进行JavaScript代码编写时进行参考      
- 本文中[强制]指必须遵循的规范      
- 本文中[建议]指一些好的书写规范和书写技巧，建议大家使用      

<h2 id="2">2 文件规范</h2>

**[建议]html、css、js、images、fonts等文件目录组织如下所示**  

![文件目录组织](https://github.com/DIST-XDATA/Code-Conventions/blob/master/images/HTML_image1.png)

**[强制]文件命名原则**  
所有字母小写，单词之间使用破折号（-）相连，压缩后的文件在原文件名（除扩展名）后添加.min，例如bootstrap-theme.css文件在压缩后变为bootstrap-theme.min.css  
**[建议]常用目录名**      
- data（数据库）
- images（图片）
- install（安装）
- templets（模版）
- include（包含）
- admin（后台）
- rss（订阅）
- media（媒体）
- config（配置）
- script（脚本）
- language（语言）
- style（样式）      

<h2 id="3">3 代码风格</h2>

<h3 id="3.1">3.1 通用</h3>

**[建议]每行不得超过120个字符，过长的代码不容易阅读与维护，但考虑到HTML的特殊性，不做硬性要求**      
**[强制]同一页面，应避免使用相同的name与id，一个区别的方法是，在id与name后面分别加上-id和-name**      
示例：      
```javascript
<input name = "foo-name">
<div id = "foo-id"></div>
```  
**[建议]标签的使用应尽量简洁，减少不必要的标签**      
反例：      
```javascript
<span class = "avatar">
	<img src = "image.png">
</span>
```  
正例：      
```javascript
<img class = "avatar" src = "image.png">
```  
**[强制]属性值必须用双引号包围，不允许使用单引号，不允许不使用引号**  
反例：      
```javascript
<script src = esl.js></script>
<script src = 'esl.js'></script>
```  
正例：      
```javascript
<script src = "esl.js"></script>
```  
**[建议]省略嵌入式资源协议头**  
- 省略图像、媒体文件、样式表和脚本等URL协议头部声明（http:，https），如果不是这两个声明的URL则不省略
- 省略协议声明，使URL成相对地址，防止内容混淆问题和导致小文件重复下载（这主要是指http和https交杂的场景中）    

反例：  
```javascript
<script src = "http://www.google.com/js/gweb/analytics/autotrack.js"></script>
```  
正例：  
```javascript
<script src = "//www.google.com/js/gweb/analytics/autotrack.js"></script>
```  
**[建议]在调用CSS和JavaScript时，可以将type属性省略不写。HTML5在引入CSS时，默认type值为text/css；在引入JavaScript时，默认type值为text/javascript**      
示例：      
```javascript
<link rel = "stylesheet" href = "base.css">
<script src = "base.js"></script>
```  
**[建议]在编写代码时尽量将功能界面模块化，使用模块化的思路安排界面布局，主要体现在**  
- 每个模块必须有一个模块名
- 每个模块的基本组成部分应该一致
- 模块的子节点类名需带上模块名（防止模块间嵌套时产生不必要的覆盖）
- 孙辈节点无需再带模块名    

示例：  
```javascript
<div class = "m-detail">
	<div class = "m-detail-hd">
		<h1 class = "title">模块标题</h1>
	</div>
  <div class = "m-detail-bd">
	  <p class = "info">详细内容</p>
  </div>
  <div class = "m-detail-ft">
	  <a href = "#" class = "more">更多</a>
  </div>
</div>
```  

<h3 id="3.2">3.2 缩进与换行</h3>

**[强制]使用4个空格或一个TAB作为一个缩进层级**  
反例：      
```javascript
<div>
<span>测试</span>
</div>
```  
正例：      
```javascript
<div>
  <span>测试</span>
</div>
```      
**[强制]模版代码的缩进优先保证HTML代码的缩进规则**      

<h3 id="3.3">3.3 命名规则</h3>

**[强制]class的命名必须单词全字母小写，单词间以-分隔，且必须代表相应的模块或部件的内容或功能，不得以HTML内置样式进行命名，命名应该具有明确的语义，同时避免创建无样式信息的class**      
反例：      
```javascript
<div class = "contentHead"></div>
```  
正例：      
```javascript
<div class = "content-head"></div>
```  
**[强制]id的命名必须单词全字母小写，单词间以-分隔，作为JavaScript Hook，其命名必须保持在页面中的唯一性，命名应该具有明确的语义**  
反例：  
```javascript
<!--有两个div的id相同且命名方式不规范-->
<div id = "contentHead"></div>
<div id = "contentHead"></div>
```  
正例：      
```javascript
<div id = "content-head"></div>
<div id = "content-body"></div>
```  

<h3 id="3.4">3.4 标签</h3>

<h4 id="3.4.1">3.4.1 标签出现顺序</h4>

**[强制]标签出现的顺序如下所示**      
示例：      
```javascript
①<!DOCTYPE html>
②<html>  
    ③<head>  
        ④<meta http-equiv = "Content-Type" content = "text/html; chartset = UTF-8"> 
        ⑤<title>页面标题</title>  
    ③</head>  
    ⑥<body>  
    ⑥</body>  
②</html>  
```  

<h4 id="3.4.2">3.4.2 标签书写规范</h4>

该部分只对标签书写进行规范说明，以下规则均为**[强制]**  
1. HTML中的标签必须使用小写字母  
2. 标签的闭合要符合HTML5的规定，自闭合（self-closing tag）标签无需闭合，例如：img、input、br等;可选的闭合标签（closing tag）需闭合，例如li标签、body标签等  
3. 标签必须合理嵌套  
4. 标签的使用必须遵循标签的语义，例如：p：段落；h1、h2、h3、h4、h5、h6：层级标题；strong、em：强调；b：样式加粗；i：样式倾斜；ins：插入；del：删除；abbr：缩写；code：代码标识；cite：引述来源作品的标题；q：引用；blockquote：一段或长篇引用；ul：无序列表；lo：有序列表；dl、dt、dd：定义列表。语义化的HTML结构，有助于机器理解，另一方面多人协作时，能迅速了解开发者意图  
5. 在CSS可以实现相同需求的情况下尽量不要使用表格进行布局  
6. 应尽量减少标签的数量，通过迭代和重构可以达到该要求  

<h4 id="3.4.3">3.4.3 标签嵌套规则</h4>

a标签不允许嵌套div标签这种约束属于语义嵌套约束，与之区别的约束还有严格嵌套约束，例如：a标签不允许嵌套a标签。严格嵌套约束在所有的浏览器下都不被允许，而语义嵌套约束，浏览器大多会容错处理，生成的文档树可能相互不太一样  

<h5 id="3.4.3.1">3.4.3.1 语义嵌套约束</h5>

以下规则均为**[强制]**  
1. li标签用于ul标签或ol标签下  
2. dd标签、dt标签用于dl标签下  
3. thead标签、tbody标签、tfoot标签、tr标签、td标签用于table标签下  

<h5 id="3.4.3.2">3.4.3.2 严格嵌套约束</h5>

以下规则均为**[强制]**  
1. inline-level元素，仅可以包含文本或其他inline-level元素  
2. a标签里不可以嵌套交互式元素a标签、button标签、select标签等  
3. p标签里不可以嵌套块级元素div标签、h1-h6标签、p标签、ul标签、ol标签、li标签、dl标签、dt标签、dd标签、form标签等  

<h5 id="3.4.3.3">3.4.3.3 基本标签嵌套规则</h5>

以下规则均为**[强制]**  
1. body标签可以直接包含块状元素、ins标签、del标签、script标签不可以直接包含行内元素  
2. ins标签和del标签可以包含块状元素或行内元素，其他任何行内元素都不允许包含块状元素  
3. p标签、h1-h6标签可以直接包含行内元素和文本信息，但不允许包含块状元素  
4. dl标签元素只允许包含dt标签和dd标签，同时dt标签不能包含块状元素，只允许包含行内元素，对于dd标签可以包含任何元素  
5. form元素不能够直接包含input元素，因为input元素属于行内元素，form元素仅仅能够包含块状元素  
6. table元素只能够包含caption、colgroup、col、thead、tbody、tfoot元素，不能够直接包含tr元素或其他任何元素  

<h5 id="3.4.3.4">3.4.3.4 其他嵌套规则</h5>

**[强制]所有元素必须正确嵌套**  
- 不允许交叉  

反例：      
```javascript
<span><dfn>交叉嵌套</span></dfn>
```  
正例：      
```javascript
<span><dfn>交叉嵌套</dfn></span>
```  
- 不允许非法的子元素嵌套  

反例：      
```javascript
<ul>
	<h3>列表</h3>
	<li>111</li>
	<li>222</li>
</ul>
```  
正例：      
```javascript
<div>
	<h3>列表</h3>
	<ul>
		<li>111</li>
		<li>222</li>
	</ul>
</div>
```  
- inline元素不能包含block元素  

反例：      
```javascript
<span>
	<h1>这是一个块级h1元素</h1>
	<p>这是一个块级p元素</p>
</span>
```  
正例：      
```javascript
<div>
	<h1>这是一个块级h1元素</h1>
	<p>这是一个块级p元素</p>
</div>
```  

<h3 id="3.5">3.5 属性</h3>

**[强制]属性出现的顺序：class、id、name、data-xxx、src、for、type、href、title、alt、aria-xxx、role，以此保证属性的易读性**      
**[强制]属性必须使用小写字母，其属性值必须用双引号包围**      
**[建议]布尔类型的建议不添加属性值（disabled、checked、selected等属性不用设置值），自定义属性建议以×××-为前缀，推荐使用data-为前缀**      
**[建议]不要在HTML标签中嵌入使用CSS样式，这是一种很山寨的做法，同时不便于样式的管理**      
**[建议]为所有元素定义样式（class属性）**     

<h3 id="3.6">3.6 页面头部</h3>

<h4 id="3.6.1">3.6.1 DOCTYPE</h4>

**[强制]DOCTYPE即文档声明，若是没有写文档声明，则会出现怪异解析。为每个HTML页面的第一行添加声明，这样能够确保在每个浏览器中拥有一致的表现**      
**[强制]使用DOCTYPE来启用标准模式，使用大写的DOCTYPE**      

<h4 id="3.6.2">3.6.2 语言编码</h4>

**[强制]有助于提高页面的可访问性，必须设置正确的lang属性**  
示例：      
```javascript
<html lang = "zh-CN">
```      
**[强制]页面必须指定字符编码的meta，且必须是head的第一个直接子元素**      
示例：      
```javascript
<meta charset = "UTF-8">
```      

<h4 id="3.6.3">3.6.3 CSS和JavaScript引入</h4>

**[强制]引入CSS时必须指明rel="stylesheet"**      
示例：      
```javascript
<link rel = "stylesheet" href = "code-guide.css">
<script type = "text/javascript" src = "code-guide.js"></script>
```      
**[建议]CSS文件外链至head标签之间，这样可以加快网页加载速度，因为这样可以使网页逐步渲染**  
**[建议]JavaScript代码必须放在页面末尾或采用异步加载，因为当加载一个脚本时，页面会暂停加载，直到脚本完全载入，因此会浪费用户很多时间**      

<h4 id="3.6.4">3.6.4 Head内容</h4>

**[强制]title标签必须设置为head标签的直接子元素，并紧随charset声明之后**      
**[强制]所有页面必须注明title名称**      
**[强制]head标签里放置的内容不会在页面中显示，页面中显示的内容是放在body标签里面的，head标签部分除了放置meta、title标签，还有链接到CSS的link标签**      
**[建议]保证favicon可访问。在未指定favicon时，大多数浏览器会请求Web Server根目录下的favicon.ico，为了保证favicon可访问，避免404，必须遵循以下两种方法之一**      
- 在Web Server根目录放置favicon.ico文件
- 使用link指定favicon    

示例：      
```javascript
<link rel = "shortcut icon" href = "path/to/favicon.ico">
```      

<h3 id="3.7">3.7 图片</h3>

**[强制]为所有的图片加上alt属性这样可以让禁用图片或者使用特殊设备的用户无障碍了解你的网页信息，并且对图像搜索引擎友好。如只起装饰作用而没有任何意义的图片可设置alt属性值为空**      
**[强制]所有图形均要标注width及height属性（防止图片变形）**      
**[强制]禁止img标签的src取值为空，延迟加载的图片也要增加默认的src属性值**      

<h3 id="3.8">3.8 表单</h3>

<h4 id="3.8.1">3.8.1 控件标题</h4>

**[强制]文本标题的控件必须使用label标签将其与其标题相关联，有两种方式**      
- 将控件置于label内
- label的for属性指向控件的id    

推荐使用第一种，减少不必要的id，如果DOM结构不允许直接嵌套，则应使用第二种      
示例：      
```javascript
<label><input type = "checkbox" name = "confirm" value = "on">我已确认上述条款</label>
<label>用户：</label><input type = "text" name = "user" id = "user">
```      

<h4 id="3.8.2">3.8.2 按钮</h4>

**[强制]使用button元素或input元素时必须指明type属性值，能获得更友好的输入体验**  
示例：      
```javascript
<button type = "button">按钮</button>
<input type = "date">
```      

<h4 id="3.8.3">3.8.3 可访问性</h4>

**[建议]当使用JavaScript进行表单提交时，应使原生提交功能正常工作。当浏览器JS运行错误或关闭JS时，提交功能将无法工作。如果正确指定了form元素的action属性和表单控件的name属性时，提交仍可继续进行**  
示例：      
```javascript
<form action = "/login" method = "post">
	<p><input name = "username" type = "text" placeholder = "用户名"></p>
	<p><input name = "password" type = "password" placeholder = "密码"></p>
</form>
```      

<h4 id="3.8.4">3.8.4 其他事项</h4>

**[建议]尽量不要使用按钮类元素的name属性，由于浏览器兼容性问题，使用按钮的name属性会带来许多难以发现的问题**      
**[建议]负责主要功能的按钮在DOM中的顺序应该靠前，以提高可访问性。如果在CSS中指定了float: right则可能导致视觉上主按钮在前，而DOM中主按钮靠后的情况**      
反例：      
```javascript
<style>
  .buttons button {
	  float: right;
  }
</style>

<div class = "buttons">
	<button type = "button">取消</button>
	<button type = "submit">提交</button>
</div>
```  
正例：      
```javascript
<style>
  .buttons .button-group {
	  float: right;
  }
</style>

<div class = "buttons">
	<div class = "buttons-group">
		<button type = "button">取消</button>
		<button type = "submit">提交</button>
  </div>
</div>
```      

<h3 id="3.9">3.9 多媒体</h3>

**[强制]使用audio以及video标签来播放音频、视频时，应当注意格式。音频格式：MP3、WAV、Ogg，MP4、WebM、Ogg**      

<h2 id="4">4 具体标签说明</h2>

<h3 id="4.1">4.1 概述</h3>

本章中所列出的标签均为前端开发中常用的标签控件，每个标签具体的属性可以参考：[W3School-HTML](http://www.w3school.com.cn/tags/html_ref_byfunc.asp)      

<h3 id="4.2">4.2 注释标签</h3>

**[强制]HTML使用<!--注释内容，可以跨行注释-->作为注释标签，用来在源文档中插入注释，注释内容不会在浏览器中显示**  
示例：      
```javascript
<!--这里是注释的内容，换行
	这里也会被注释掉-->
```      
**[建议]按照模块添加注释，在每个模块开始和结束的地方添加注释**  
示例：      
```javascript
<!--模块1-->
<div class = "model1"></div>
<!--/模块1-->

<!--模块2-->
<div class = "model2"></div>
<!--/模块2-->
```      

<h3 id="4.3">4.3 DOCTYPE标签</h3>

**[强制]<!DOCTYPE>声明位于文档中的最前面的位置，处于html标签之前，<!DOCTYPE>声明不是一个HTML标签；它是用来告知Web浏览器页面使用了哪种HTML版本**      
示例：      
```javascript
<!--表示html5-->
<!DOCTYPE html>

<!--表示HTML 4.01 Strict-->
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">

<!--表示HTML 4.01 Transitional-->
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">

<!--表示HTML 4.01 Frameset-->
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Frameset//EN" "http://www.w3.org/TR/html4/frameset.dtd">

<!--表示XHTML 1.0 Strict-->
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">

<!--表示XHTML 1.0 Transitional-->
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">

<!--表示XHTML 1.0 Frameset-->
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Frameset//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-frameset.dtd">

<!--表示XHTML 1.1-->
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.1//EN" "http://www.w3.org/TR/xhtml11/DTD/xhtml11.dtd">
```      

<h3 id="4.4">4.4 html标签</h3>

**[强制]html标签告知浏览器这是一个HTML文档,该标签是HTML文档中最外层的元素，是所有其他HTML元素（除了<!DOCTYPE>标签）的容器**      
**[强制]此元素可告知浏览器其自身是一个HTML文档。即使html元素是文档的根元素，它也不包含doctype元素。doctype元素必须位于html元素之前**      
**[强制]在根级html元素中为文档指定一种语言属性（lang属性），这样能帮助语言合成和翻译工具选择正确的语言进行发音和语法处理等**  
示例：      
```javascript
<!DOCTYPE html>
<html lang = "en">
  <head>
    文档头部
  </head>
  <body>
    文档主体
  </body>
</html>
```      

<h3 id="4.5">4.5 head标签</h3>

**[强制]head标签用于定义文档的头部，它是所有头部元素的容器。head标签中的元素可以引用脚本、指示浏览器在哪里找到样式表、提供元信息等等。文档的头部描述了文档的各种属性和信息，包括文档的标题、在Web中的位置以及和其他文档的关系等。绝大多数文档头部包含的数据都不会真正作为内容显示给读者**      
**[强制]下面这些标签可用在head标签中**      
- title标签，在头部中，这个标签是唯一必须的
- style标签
- base标签
- link标签
- meta标签
- script标签
- noscript标签    

反例：      
```javascript
<html>
  <head>
    <!--当没有title标签时是错误的-->
  </head>
  <body>
    文档主体
  </body>
</html>
```  
正例：      
```javascript
<html>
  <head>
    <title>文档的标题</title>
  </head>
  <body>
    文档主体
  </body>
</html>
```      

<h3 id="4.6">4.6 meta标签</h3>

**[强制]meta标签提供的是有关页面的元信息（meta-information）,里面的charset="utf-8"表示字符编码，因为不同国家的语言不同，其转义的方式不同，所以为了不会出现乱码的情况，必须加上一个字符编码，而"utf-8"又被称为万国码**  
**[强制]meta标签永远位于head元素内部，meta标签没有结束标签**  
**[建议]标签的属性有两种**  
- name和content：name属性用于描述网页，它以"名称/值"来表现，而name具体的内容则由content属性来表示，其中，name一般使用较多的是keywords（关键字）、description（简短的描述），便于爬虫查找和分类，如下图所示    

![name和content属性](https://github.com/DIST-XDATA/Code-Conventions/blob/master/images/HTML_image2.png)

- http-equiv与content属性，目前较多是使用它们进行页面的刷新与跳转，如下图所示    

![http-equiv与content属性](https://github.com/DIST-XDATA/Code-Conventions/blob/master/images/HTML_image3.png)

<h3 id="4.7">4.7 title标签</h3>

**[强制]title标签用来表示网页是用来干什么的，title标签的内容会在浏览器的标题栏中进行显示**  
**[强制]meta标签一定是在title标签的前面，原因是：网页的读取顺序是从上到下，要先进行字符编码的设置，不然title里面的内容就有可能出现乱码**  
**[强制]title标签定义浏览器工具栏中的标题，提供页面被添加到收藏夹时的标题，显示在搜索引擎结果中的页面标题**  
**[强制]title标签是head标签中唯一要求包含的东西**  
示例：      
```javascript
<html>
  <head>
    <title>这里是标题</title>
  </head>
  <body>
		文档主体
  </body>
</html>
```      

<h3 id="4.8">4.8 link标签</h3>

**[强制]link标签定义文档与外部资源的关系，link标签最常见的用途是链接样式表**  
**[强制]link元素是空元素，它仅包含属性；此元素只能存在于head部分，不过它可出现任何次数**  
反例：  
```javascript
<html>
  <head>
    <title>这里是标题</title>
  </head>
  <body>
	  <!--错误在于将link标签写在了body标签内-->
    <link rel = "stylesheet" type = "text/css" href = "theme.css"> 
  </body>
</html>
```  
正例：  
```javascript
<html>
  <head>
    <link rel = "stylesheet" type = "text/css" href = "theme.css">
  </head>
  <body>
	  文档主体
  </body>
</html>
```  

<h3 id="4.9">4.9 style标签</h3>

**[强制]style标签定义HTML文档的样式信息。在style标签中，用户可以规定在浏览器中如何呈现HTML文档，每个HTML文档能包含多个style标签**      
**[强制]type属性是必需的，定义style元素的内容，唯一可能的值是"text/css"**      
**[强制]style元素位于head部分中**      
示例：      
```javascript
<!--给h1标签和p标签设置字体颜色-->
<html>
  <head>
    <style type = "text/css">
      h1 {color:red}
      p {color:blue}
    </style>
  </head>
  <body>
    <h1>Header 1</h1>
    <p>A paragraph.</p>
  </body>
</html>
```      

<h3 id="4.10">4.10 script标签</h3>

**[强制]script>标签用于定义客户端脚本，比如JavaScript。script标签既可包含脚本语句，也可以通过"src"属性指向外部脚本文件。JavaScript通常用于图像操作、表单验证以及动态内容更改**  
示例：      
```javascript
<script type = "text/javascript">
  document.write("Hello World!")
</script>
```      
**[强制]如果使用"src"属性，则script标签必须是空的**  
**[建议]有多种执行外部脚本的方法，如下所示**  
- 如果async = "async"：脚本相对于页面的其余部分异步地执行（当页面继续进行解析时，脚本将被执行）
- 如果不使用async且defer = "defer"：脚本将在页面完成解析时执行
- 如果既不使用async也不使用defer：在浏览器继续解析页面之前，立即读取并执行脚本  

<h3 id="4.11">4.11 body标签</h3>

**[强制]body标签定义文档的主体，包含文档的所有内容（比如文本、超链接、图像、表格和列表等等）**  
示例：      
```javascript
<html>
  <head>
    <title>文档的标题</title>
  </head>
  <body>
    文档的内容
  </body>
</html>
```      

<h3 id="4.12">4.12 h1-h6标签</h3>

**[强制]用来定义HTML标题，h1定义重要等级最高的标题，h6定义重要等级最低的标题**  
**[强制]由于h元素拥有确切的语义，要慎重地选择恰当的标签层级来构建文档的结构。因此，不要利用标题标签来改变同一行中的字体大小。应当使用层叠样式表定义来达到漂亮的显示效果**  
**[建议]如果是博客，应把h1标签留给文章标题**  
示例：      
```javascript
<h1>这是标题 1</h1>
<h2>这是标题 2</h2>
<h3>这是标题 3</h3>
<h4>这是标题 4</h4>
<h5>这是标题 5</h5>
<h6>这是标题 6</h6>
```      

<h3 id="4.13">4.13 p标签</h3>

**[强制]用于定义段落，p标签会自动在其前后创建一些空白。浏览器会自动添加这些空间，用户也可以在样式表中规定**  
示例：      
```javascript
<p>这是一个很短的行</p>
```      

<h3 id="4.14">4.14 form标签</h3>

**[强制]form标签用于创建供用户输入的HTML表单，也可用于向服务器传输数据。该标签可以包含一个或多个如下的表单元素：input、textarea、button、select、option、optgroup、fieldset、label标签**    
示例：      
```javascript
<form action = "form_action.asp" method = "get">
  <p>First name: <input type = "text" name = "fname"></p>
  <p>Last name: <input type = "text" nam e= "lname"></p>
  <input type = "submit" value = "Submit">
</form>
```      

<h3 id="4.15">4.15 input标签</h3>

**[强制]input标签规定了用户可以在其中输入数据的输入字段，该标签在form标签中使用，用来声明允许用户输入数据的input控件，输入字段可通过多种方式改变，取决于type属性**  
示例：      
```javascript
<form action  ="form_action.asp" method = "get">
  <!--文本域-->
  First name: <input type = "text" name = "fname">
  Last name: <input type = "text" name = "lname">
  <!--密码域-->
  <input type = "password" name = "password">
  <!--复选框-->
  <input type = "checkbox" name = "checkbox1">
  <!--单选按钮-->
  <input type = "radio" name = "radio1">
  <!--按钮-->
  <input type = "button" value = "Hello world ">
  <!--上传文件-->
  <input type = "button" value = "Hello world ">
  <!--提交表单按钮-->
  <input type = "submit" value = "Submit">
</form>
```      

<h3 id="4.16">4.16 textarea标签</h3>

**[强制]textarea标签定义一个多行的文本输入控件，文本区域中可容纳无限数量的文本，其中的文本的默认字体是等宽字体（通常是Courier）。可以通过cols和rows属性来规定textarea的尺寸大小，不过更好的办法是使用CSS的height和width属性**  
示例：      
```javascript
<textarea rows = "3" cols = "20">
  在这里，你可找到你所需要的HTML标准
</textarea>
<textarea style = "width: 100px; height: 100px;">
  在这里，你可找到你所需要的HTML标准
</textarea>
```      
**[建议]在文本输入区内的文本行间，用"%OD%OA"（回车/换行）进行分隔**  

<h3 id="4.17">4.17 button标签</h3>

**[强制]button标签定义一个按钮，该标签内部，用户可以放置内容，比如文本或图像。这是该标签与使用input标签创建的按钮之间的不同之处**  
**[强制]始终为button标签规定type属性，不同的浏览器button标签的type属性使用不同的默认值，Internet Explorer的默认类型是"button"，而其他浏览器中（包括W3C规范）的默认值是"submit"**    
示例：      
```javascript
<button type = "button">我可以被点击</button>
```      

<h3 id="4.18">4.18 select标签</h3>

**[强制]select标签用来创建下拉列表，select标签中的option标签定义了列表中的可用选项**  
示例：      
```javascript
<select>
  <option value ="volvo">Volvo</option>
  <option value ="saab">Saab</option>
  <option value = "opel">Opel</option>
  <option value = "audi">Audi</option>
</select>
```      

<h3 id="4.19">4.19 label标签</h3>

**[强制]label标签为input标签定义标注（标记），label标签不会向用户呈现任何特殊效果。不过，它为鼠标用户改进了可用性。如果用户在label标签内点击文本，就会触发此控件。就是说，当用户选择该标签时，浏览器就会自动将焦点转到和标签相关的表单控件上**  
**[建议]label标签的for属性应当与相关元素的id属性相同，for属性可把label绑定到另外一个元素**  
示例：      
```javascript
<!--带有两个输入字段和相关标记的简单HTML表单-->
<form>
  <label for = "male">Male</label>
  <input type = "radio" name = "sex" id = "male">
  <br>
  <label for = "female">Female</label>
  <input type = "radio" name = "sex" id = "female">
</form>
```      

<h3 id="4.20">4.20 img标签</h3>

**[强制]img>标签定义HTML页面中的图像，有两个必需的属性：src和alt，从技术上讲，图像并不会插入HTML页面中，而是链接到HTML页面上。img标签的作用是为被引用的图像创建占位符**  
示例：      
```javascript
<img src = "dist.jpg" alt = "上海数慧系统技术有限公司">
```      
**[建议]通过在a标签中嵌套img标签，给图像添加到另一个文档的链接**  

<h3 id="4.21">4.21 canvas标签</h3>

**[强制]canvas标签通过脚本（通常是JavaScript）来绘制图形（比如图表和其他图像），canvas标签只是图形容器，用户必须使用脚本来绘制图形**  
示例：      
```javascript
<!--通过 canvas 元素来显示一个红色的矩形-->
<canvas id = "myCanvas"></canvas>
<script type = "text/javascript">
  var canvas = document.getElementById('myCanvas');
  var ctx = canvas.getContext('2d');
  ctx.fillStyle = '#FF0000';
  ctx.fillRect(0, 0, 80, 100);
</script>
```      
**[建议]Internet Explorer 8以及更早的版本不支持canvas标签**  

<h3 id="4.22">4.22 a标签</h3>

**[强制]a标签定义超链接，用于从一个页面链接到另一个页面。a标签最重要的属性是href属性，它指定链接的目标**  
示例：      
```javascript
<a href = "http://www.dist.com.cn">上海数慧系统技术有限公司</a>
```      
**[强制]如果不使用href属性，则不可以使用如下属性：download, hreflang, media, rel, target以及type属性**  
**[强制]被链接页面通常显示在当前浏览器窗口中，除非规定了另一个目标（target属性）**  
**[强制]在所有浏览器中，链接的默认外观如下**  
- 未被访问的链接带有下划线而且是蓝色的
- 已被访问的链接带有下划线而且是紫色的
- 活动链接带有下划线而且是红色的    

**[建议]使用CSS来设置链接的样式**  

<h3 id="4.23">4.23 ul标签</h3>

**[强制]ul标签定义无序列表，ul标签与li标签一起使用，创建无序列表**  
示例：      
```javascript
<ul>
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ul>
```      

<h3 id="4.24">4.24 ol标签</h3>

**[强制]ol标签定义了一个有序列表，列表排序以数字来显示。ul标签与li标签一起使用，定义列表选项**  
示例：      
```javascript
<ol>
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ol>
```      

<h3 id="4.25">4.25 li标签</h3>

**[强制]li标签定义列表项目，li标签可用在有序列表ol标签、无序列表ul标签和菜单列表menu标签中**  
示例：      
```javascript
<!--ol标签和li标签-->
<ol>
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ol>
<!--ul标签和li标签-->
<ul>
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ul>
```      

<h3 id="4.26">4.26 div标签</h3>

**[强制]div标签定义HTML文档中的一个分隔区块或者一个区域部分，div标签常用于组合块级元素，以便通过CSS来对这些元素进行格式化。如果如果用id或class来标记div标签，那么该标签的作用会变得更加有效。默认情况下，浏览器通常会在div标签前后放置一个换行符，然而，用户可以通过使用CSS改变这种情况**    
示例：      
```javascript
<div class = "content-head">
  <h3>这是标题</h3>
  <p>这是一行</p>
</div>
```      

<h3 id="4.27">4.27 span标签</h3>

**[强制]span标签用于对文档中的行内元素进行组合。span标签没有固定的格式表现。当对它应用样式时，它才会产生视觉上的变化。如果不对span标签应用样式，那么span元素中的文本与其他文本不会任何视觉上的差异，span标签提供了一种将文本的一部分或者文档的一部分独立出来的方式**  
示例：      
```javascript
<p><span>some text</span>some other text</p>
<!--例子解释：
如果不对span元素应用样式，那么span元素中的文本与其他文本不会任何视觉上的差异。尽管如此，上例中的span元素仍然为p元素增加了额外的结构。可以为span应用id或class属性，这样既可以增加适当的语义，又便于对span元素应用样式。可以对同一个span元素应用class或id属性，但是更常见的情况是只应用其中一种。这两者的主要差异是，class用于元素组（类似的元素，或者可以理解为某一类元素），而id用于标识单独的唯一的元素
-->
```      

<h3 id="4.28">4.28 table标签</h3>

**[强制]若设计的界面可以用HTML+CSS实现，则尽量不要使用table标签**  
**[强制]table标签定义HTML表格，一个HTML表格包括table标签，一个或多个tr、th以及td标签**  
**[强制]tr标签定义表格行，th标签定义表头，td标签定义表格单元。更复杂的HTML表格也可能包括caption、col、colgroup、thead、tfoot以及tbody标签**  
示例：      
```javascript
<table>
  <tr>
    <th>月份</th>
    <th>金额</th>
  </tr>
  <tr>
    <td>一月</td>
    <td>100块</td>
  </tr>
</table>
```      

<h4 id="4.28.1">4.28.1 table标签使用规范</h4>

**[建议]尽量不使用百分比进行宽高控制**  
**[建议]table尽量横切，便于加快下载速度**  
**[建议]table位置说明，这里所说的table位置是指表格位于页面左、中、右，一般不指上、中、下**  
示例：      
```javascript
<!--table居左，由于缺省值是居左，所以这里的align = left可以不写-->
<table align = left>
<!--table居中-->
<table align = center>
<!--table居右-->
<table align = right>
```      
**[建议]table缩进，应尽量避免表格嵌套过多的情况发生，对于不可避免的表格嵌套，应以以下方法写，每级table以4个空格或1个TAB缩进，属于本级table下的tr、td标签应对齐本级table标签**  
**[建议]定义表格宽、高，一般简单的定义表格的宽高，就在table、tr或td标签里面定义width和height属性值就可以了，有一些技巧，如下所示**  
- 同列表格的宽：同列表格如果宽度一样，只写第一行定义的宽度，其他的允许不写
- 同行表格的高：同行表格如果高一样，则把height属性写入tr标签中，td标签内部需要做单独定义，另外其他同行相同的定义，如背景颜色等，均可写入tr标签  

<h2 id="5">5 其他规范</h2>

以下规范内容均为**[强制]**    
1. **开发中随时进行标准验证**  
2. **压缩前端代码**  
3. 书写链接时，建议在URL地址后面加上'/'，例如：href = "http://.../.../"  
4. 不属于标签部分的特殊符号都用编码表示，出现在内容中的特殊符号都需要用编码形式表现出来，例如："<"用&lt表示，">"用&gt表示，"&"用&amp表示，"用&quot表示，尽量用&nbsp;表示空格  
5. body中必须标明background-color属性，无背景色时赋值#fff  
6. 对16进制数的标识一定要加"#"  
7. 禁止在字符串尾部加空格方式控制屏幕位置  
8. 字体字号需要规范使用，突出主次层级  

<h2 id="6">6 补充说明</h2>

<h3 id="6.1">6.1 IE兼容说明</h3>

**[建议]优先使用最新版本的IE和Chrome内核**  
**[建议]使用如下所示的代码**  
示例：      
```javascript
<meta http-equiv = "X-UA-Compatible" content = "IE = edge, chrome = 1">
```      
**[建议]如果CSS样式表基本定型，那么可以为IE单独建立一个样式表，然后仅对IE生效**  
示例：      
```javascript
<!--[if it IE 7]>
  <link rel = "stylesheet" type = "text/css" media = "screen" href = "path/to/ie.css/"/>
<![end if]-->
```      

<h3 id="6.2">6.2 SEO优化</h3>

**[建议]SEO：是由英文Search Engine Optimization缩写而来，中文译为"搜索引擎优化"。SEO是指通过站内优化比如网站结构调整、网站内容建设、网站代码优化等以及站外优化，比如网站站外推广、网站品牌建设等，使网站满足搜索引擎收录排名需求，在搜索引擎中提高关键词排名**  
示例：      
```javascript
<head>  
  <meta charset = "utf-8">
  <!-- 兼容IE -->
  <meta http-equiv = "X-UA-Compatible" content = "IE = edge,chrome = 1">  
  <!-- SEO优化 -->  
  <title>Style Guide</title>  
  <meta name = "keywords" content = "your keywords">  
  <meta name = "description" content = "your description">  
  <meta name = "author" content = "author, email address">  
</head>  
```      

<h3 id="6.3">6.3 viewport（移动端）</h3>

以下规范内容均为**[建议]**    
1. viewport：一般指的是浏览器窗口内容区的大小，不包含工具条、选项卡等内容  
2. width：浏览器宽度，输出设备中的页面可见区域宽度  
3. device-width：设备分辨率宽度，输出设备的屏幕可见宽度  
4. initial-scale：初始缩放比例  
5. maximum-scale：最大缩放比例    

示例：      
```javascript
<!--为移动端设备优化，设置可见区域的宽度和初始缩放比例-->
<meta name = "viewport" content = "width = device-width, initial-scale = 1.0">
```      

<h3 id="6.4">6.4 IOS图标（移动端）</h3>

以下规范内容均为**[建议]**    
1. apple-touch-icon：图片自动处理成圆角和高光等效果  
2. apple-touch-icon-precomposed：禁止系统自动添加效果，直接显示设计原图    

示例：      
```javascript
<!--iPhone和iTouch，默认57像素，必须有-->
<link rel = "apple-touch-icon-precomposed" href = "/apple-touch-icon-57x57-precomposed.png">
<!--iPad，72像素，可以没有，但推荐有-->
<link rel = "apple-touch-icon-precomposed"     href = "/apple-touch-icon-72x72-precomposed.png" sizes = "72x72">
<!--Retina iPhone和Retina iTouch，114像素，可以没有，但推荐有-->  
<link rel = "apple-touch-icon-precomposed" href = "/apple-touch-icon-114x114-precomposed.png" sizes = "114x114">
<!--Retina iPad，144像素，可以没有，但推荐有-->
<link rel = "apple-touch-icon-precomposed" href = "/apple-touch-icon-144x144-precomposed.png" sizes = "144x144">
```      

*本规范文档将不断修改更新，请各位批评指正*
