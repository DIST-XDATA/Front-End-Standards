#XDATA-CSS编码规范
## 目录
* [前言](#前言)
* [1 命名规范](#1)
  * [1.1 命名基本规范](#1.1)
  * [1.2 命名空间](#1.2)
  * [1.3 命名参考](#1.3)
* [2 代码风格 ](#2)
  * [2.1 文件](#2.1)
  * [2.2 缩进](#2.2)
  * [2.3 空格](#2.3)
  * [2.4 行长度](#2.4)
  * [2.5 选择器](#2.5)
  * [2.6 属性](#2.6)
 
 
##前言
统一的命名规范，便于多人开发维护时代码统一，减少项目沟通和交接的成本，增加代码的语义化。

<h2 id="1">1 命名规范</h2>
<h3 id="1.1">1.1命名基本规范</h3>
**[强制]保持 Class 命名为全小写，可以使用短划线（不要使用下划线和 camelCase 命名）。短划线应该作为相关类的自然间断**

反例：  
```css
 .Btn {...}
 .btnDanger {...}
```  
正例：  
```css
.btn {...}
.btn-danger {...}
```  
**[强制]可以是单个单词，也可以是组合单词，要求能够描述清楚模块和元素的含义，使其具有语义化**
**[强制]不得使用 123456…,red,blue,left,right之类的（如颜色、字号大小等）矢量命名**
**[建议]尽量用单个单词简单描述class名称**

反例：  
```css
 .left {...}
 .2 {...}
```  
正例：  
```css
.warpper {...}
.logo {...}
```  
**[建议]双单词或多单词组合方式：形容词-名词、命名空间-名词、命名空间-形容词-名词**

反例：  
```css
 .title {...}
 .list {...}
```  
正例：  
```css
.cell-title {...}
.news-list {...}
```  
**[强制]不得过度使用简写。.btn 可以很好地描述 button，但是 .s 不能代表任何元素。**

反例：  
```css
 .b {...}
 .atr {...}
```  
正例：  
```css
.btn {...}
.author {...}
```  
**[强制]命名时使用最近的父节点或者父 class 作为前缀**

反例
```css
 .header {...}
 .logo {...}
```  
正例：  
```css
 .header {...}
 .header-logo {...}
```  
**[建议]Class 的命名应该尽量短，也要尽量明确。**

反例：  
```css
 .navigation {...}
```  
正例：  
```css
.nav {...}
``` 
<h3 id="1.2"> 1.2 命名空间</h3>

在编码思想上，我们可以将页面拆分成不同的层级（布局、模块、元件）
通过统一的命名规范定义命名的范围，成为CSS class & id命名空间

布局: 以语义化的单词layout作为命名空间，例如主栏布局命名 layout-main，只改变layout-命名空间后面的命名，layout始终保留。布局的命名空间为layout-xxx。
模块：页面是由一个或多个模块组成，模块的英文单词是module，规范简写成mod，如新闻模块mod-news，照片展示模块mod-photo-show。模块的命名空间为mod-xxx 。
元件：元件是属于模块内部的，也可以说模块是由元件和它内部的自有元素组成。如用户照片信息元件cell-user-photo。元件的命名空间为cell-xxx 。

### 1.3 命名参考

#### 1.3.1 页面框架命名，一般具有唯一性，推荐用ID命名

| ID名称        | 命名          |
| ------------- |:-------------:|
|头部     | header| 
|脚部      | footer    |  
|侧栏 | sideBar      |  
|布局 | layout      |  
|主体 | main      |  
|容器 | wrapper      |  
|栏目 | column      |  

#### 1.3.2 模块结构命名

| class名称        | 命名          |
| ------------- |:-------------:|
|模块(如：通知模块)    | mod (mod-notice)| 
|部件(如：查询部件)      | widget(widget-quuery)   |  
|内容 | content      |  
|次级内容 | sub-content      | 

#### 1.3.3 一般元素命名

| class名称        | 命名          | class名称        | 命名          | class名称        | 命名          |
| ------------- |:-------------:| ------------- |:-------------:| ------------- |:-------------:|
|二级|	sub	|面包屑|	breadcrumb|标志	|logo	|
|登陆	|login	|注册	|register/reg|搜索	|search	|
|状态	|status	|按钮	|btn|滚动	|scroll	|
|标签页	|tab|列表	|list|	短消息|	msg/message|
|当前的	|current	|摘要	|summary|设置	|set	|
|成功|	suc|按钮	|btn|	文本|	txt|
|颜色	|color/c|	背景	|bg|弹出层	|pop	|
|添加	|add	|删除	|del|操作|	op	|
|信息	|info|密码	|pwd|预览	|pvw|
|确认	|confirm	|取消	|cancel|报错	|error|

<h2 id="2">2 代码风格</h2>

<h3 id="2.1"> 2.1 文件</h3>

**[建议] CSS 文件使用无 BOM 的 UTF-8 编码。**

解释：

UTF-8 编码具有更广泛的适应性。BOM 在使用程序或工具处理文件时可能造成不必要的干扰

<h3 id="2.2"> 2.2 缩进</h3>

**[强制] 使用 4 个空格做为一个缩进层级，不允许使用 2 个空格 或 tab 字符。**

反例：  
```css
.selector {
  margin: 0;
  padding: 0;
}
```  
正例：  
```css
.selector {
    margin: 0;
    padding: 0;
}
```  
<h3 id="2.3"> 2.3 空格</h3>
**[强制] 选择器 与 `{` 之间必须包含空格。**

反例：  
```css
.selector{
  margin: 0;
  padding: 0;
}
```  
正例：  
```css
.selector {
    margin: 0;
    padding: 0;
}
```  
**[强制] 属性名 与之后的 : 之间不允许包含空格， : 与 属性值 之间必须包含空格。**
反例：  
```css
margin:0;
```  
正例：  
```css
margin: 0;
```  
**[强制] 列表型属性值 书写在单行时，, 后必须跟一个空格。**

反例：
```css
font-family: Arial,sans-serif;
```  
正例：  
```css
font-family: Arial, sans-serif;
```  
<h3 id="2.4"> 2.4 行长度</h3>

**[强制] 每行不得超过 120 个字符，除非单行不可分割。**

解释：

常见不可分割的场景为URL超长。

**[建议] 对于超长的样式，在样式值的 空格 处或 , 后换行，建议按逻辑分组。 **

反例：
```css
background: transparent url(aVeryVeryVeryLongUrlIsPlacedHere)   no-repeat 0 0;

background-image:url(aVeryVeryVeryLongUrlIsPlacedHere) url(anotherVeryVeryVeryLongUrlIsPlacedHere);

background-image: -webkit-gradient(linear,left bottom,left top,color-stop(0.04, rgb(88,94,124)),color-stop(0.52, rgb(115,123,162))
);
```  
正例：  
```css
/* 不同属性值按逻辑分组 */
background:
    transparent url(aVeryVeryVeryLongUrlIsPlacedHere)
    no-repeat 0 0;

/* 可重复多次的属性，每次重复一行 */
background-image:
    url(aVeryVeryVeryLongUrlIsPlacedHere)
    url(anotherVeryVeryVeryLongUrlIsPlacedHere);

/* 类似函数的属性值可以根据函数调用的缩进进行 */
background-image: -webkit-gradient(
    linear,
    left bottom,
    left top,
    color-stop(0.04, rgb(88,94,124)),
    color-stop(0.52, rgb(115,123,162))
);
``` 
<h3 id="2.5"> 2.5 选择器</h3>

**[强制] 当一个 rule 包含多个 selector 时，每个选择器声明必须独占一行。**

反例：
```css
.post, .page, .comment {
    line-height: 1.5;
}
```  
正例：  
```css
.post,
.page,
.comment {
    line-height: 1.5;
}
``` 

**[强制] >、+、~ 选择器的两边各保留一个空格。**


反例：
```css
main>nav {
    padding: 10px;
}

label+input {
    margin-left: 5px;
}

input:checked~button {
    background-color: #69C;
}
```  
正例：  
```css
main > nav {
    padding: 10px;
}

label + input {
    margin-left: 5px;
}

input:checked ~ button {
    background-color: #69C;
}

``` 
** [强制] 属性选择器中的值必须用双引号包围。不允许使用单引号，不允许不使用引号**

反例：
```css
article[character='juliet'] {
    voice-family: "Vivien Leigh", victoria, female;
}
```  
正例：  
```css
article[character="juliet"] {
    voice-family: "Vivien Leigh", victoria, female;
}
``` 
<h3 id="2.6"> 2.6 属性</h3>

**[强制] 属性定义必须另起一行。**

反例：
```css
.selector { margin: 0; padding: 0; }
```  
正例：  
```css
.selector {
    margin: 0;
    padding: 0;
}
``` 
**[强制] 属性定义后必须以分号结尾。**

反例：
```css
.selector {
    margin: 0
}
```  
正例：  
```css
.selector {
    margin: 0;
}
``` 
## 3 通用

### 3.1 选择器

**[强制] 如无必要，不得为 id、class 选择器添加类型选择器进行限定。**

解释：

在性能和维护性上，都有一定的影响。

反例：
```css
dialog#error,
p.danger-message {
    font-color: #c00;
}
```  
正例：  
```css
#error,
.danger-message {
    font-color: #c00;
}
``` 
**[建议] 选择器的嵌套层级应不大于 3 级，位置靠后的限定条件应尽可能精确。**

反例：
```css
.page .header .login #username input {}
.comment div * {}
```  
正例：  
```css
#username input {}
.comment .avatar {}
``` 

### 3.2 属性缩写

** [建议] 在可以使用缩写的情况下，尽量使用属性缩写。**

反例：
```css
.post {
    font-family: arial, sans-serif;
    font-size: 12px;
    line-height: 1.5;
}
```  
正例：  
```css
.post {
    font: 12px/1.5 arial, sans-serif;
}
``` 
**[建议] 使用 border / margin / padding 等缩写时，应注意隐含值对实际数值的影响，确实需要设置多个方向的值时才使用缩写。**

解释：

border / margin / padding 等缩写会同时设置多个属性的值，容易覆盖不需要覆盖的设定。如某些方向需要继承其他声明的值，则应该分开设置。

```
/* centering <article class="page"> horizontally and highlight featured ones */
article {
    margin: 5px;
    border: 1px solid #999;
}
```
反例：
```css
.page {
    margin: 5px auto; /* introducing redundancy */
}

.featured {
    border: 1px solid #69c; /* introducing redundancy */
}
```  
正例：  
```css
.page {
    margin-right: auto;
    margin-left: auto;
}

.featured {
    border-color: #69c;
}
``` 
### 3.3 属性书写顺序
**[建议] 同一 rule set 下的属性在书写时，应按功能进行分组，并以 Formatting Model（布局方式、位置） > Box Model（尺寸） > Typographic（文本相关） > Visual（视觉效果） 的顺序书写，以提高代码的可读性。**

解释：
* Formatting Model 相关属性包括：position / top / right / bottom / left / float / display / overflow 等
* Box Model 相关属性包括：border / margin / padding / width / height 等
* Typographic 相关属性包括：font / line-height / text-align / word-wrap 等
* Visual 相关属性包括：background / color / transition / list-style 等

另外，如果包含 content 属性，应放在最前面。

示例:
```css
.sidebar {
    /* formatting model: positioning schemes / offsets / z-indexes / display / ...  */
    position: absolute;
    top: 50px;
    left: 0;
    overflow-x: hidden;

    /* box model: sizes / margins / paddings / borders / ...  */
    width: 200px;
    padding: 5px;
    border: 1px solid #ddd;

    /* typographic: font / aligns / text styles / ... */
    font-size: 14px;
    line-height: 20px;

    /* visual: colors / shadows / gradients / ... */
    background: #f5f5f5;
    color: #333;
    -webkit-transition: color 1s;
       -moz-transition: color 1s;
            transition: color 1s;
}
```
### 3.4 清除浮动

**[建议] 当元素需要撑起高度以包含内部的浮动元素时，通过对伪类设置 clear 或触发 BFC 的方式进行 clearfix。尽量不使用增加空标签的方式。**

解释：

触发 BFC 的方式很多，常见的有：

* float 非 none
* position 非 static
* overflow 非 visible

如希望使用更小副作用的清除浮动方法，参见 [A new micro clearfix hack](http://nicolasgallagher.com/micro-clearfix-hack/) 一文。

另需注意，对已经触发 BFC 的元素不需要再进行 clearfix。

### 3.5 !important

**[建议] 尽量不使用 !important 声明。**

**[建议] 当需要强制指定样式且不允许任何场景覆盖时，通过标签内联和 !important 定义样式。**

解释：

必须注意的是，仅在设计上 确实`不允许任何其它场景覆盖样式` 时，才使用内联的` !important` 样式。通常在第三方环境的应用中使用这种方案。下面的 `z-index` 章节是其中一个特殊场景的典型样例。

### 3.6 z-index

**[建议] 将 z-index 进行分层，对文档流外绝对定位元素的视觉层级关系进行管理。**

解释：

同层的多个元素，如多个由用户输入触发的 Dialog，在该层级内使用相同的 z-index 或递增 z-index。

建议每层包含100个 z-index 来容纳足够的元素，如果每层元素较多，可以调整这个数值。

**[建议] 在可控环境下，期望显示在最上层的元素，z-index 指定为 999999。**

解释：

可控环境分成两种，一种是自身产品线环境；还有一种是可能会被其他产品线引用，但是不会被外部第三方的产品引用。

不建议取值为 `2147483647`。以便于自身产品线被其他产品线引用时，当遇到层级覆盖冲突的情况，留出向上调整的空间。
**[建议] 在第三方环境下，期望显示在最上层的元素，通过标签内联和 !important，将 z-index 指定为 `2147483647`。**
解释：

第三方环境对于开发者来说完全不可控。在第三方环境下的元素，为了保证元素不被其页面其他样式定义覆盖，需要采用此做法。

## 4 值与单位
