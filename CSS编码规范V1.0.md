#XDATA-CSS编码规范
## 1、css选择器  
 css选择器大致有为：    
    1.  **id选择器**（#id）     
    2.  **类选择器**(.class)        
    3.  **标签选择器**（span、div、p）  
    4.  **相邻选择器**  (E+F等)     
    5.  **后代选择器**（ul li）     
    6.  **属性选择器** (a[title=’名字’])    
    7.  **伪类选择器** <span:hover;div:before>  
    
**按类型**分为元素、关系、伪类、属性、伪对象选择器。
***
### - 元素选择器：

选择符 | 类型|版本|简介 |
-------------|---------|--------|-----------|
|* | 通配符选择器|css2|所有对象| 
|E | 标签选择器|css1|HTML标签|
|#id | id选择符|css1|唯一标识| 
|.class | 类选择符|css1|class属性|
### - 关系选择器

选择符 | 类型|简介 |
-------------|------------|-----------|
|E F| 后代选择器|所有被E元素包含的F元素
| 
|E>F| 子选择器|E元素的所有**直接**子元素F
|
|E+F| 相邻选择器|在E元素之后F元素
| 
|E~F| 兄弟选择器|E元素所有兄弟元素F
|
### - 属性选择器

选择符 | 简介 |
-------------|-----------|
|E[att]|有att属性的E元素素| 
|E[att="val"]|att属性值等于val的E元素|
|E[att～="val"]| att属性且属性值为用空格分隔,一个等于val的E元素| 
|E[att\|="val"]| att属性且属性值为以val开头并用连接符"-"分隔的字符串的E元素|
|E[att^="val"]| att属性且属性值为以val开头的字符串的E元素	|
|E[att$="val"]| att属性且属性值为以val结尾的字符串的E元素	|
|E[att*="val"]| att属性且属性值为包含val的字符串的E元素。	|

### - 伪类选择器

选择符 | 简介 |
--------------------------|-----------------------------------|
|E:link|超链接a在未被访问前的样式| 
|E:visited|超链接a在已被访问的样式|
|E:hover|元素在鼠标悬浮悬停时的样式|
|E:active|元素在被激活时的样式|
|E:lang()|匹配使用特殊语言的E元素|
|E:not()|匹配不含有s选择符的元素E|
|E:root|匹配E元素在文档的根元素|
|E:fist-child| 元素的第一个子元素样式| 
|E:enabled、E:disenabled| 元素在可用状态和禁用状态|
|E:first-of-type| 元素中第一个同级元素的样式|
##  注：
    子元素的选择： E:fist-child（第一个子元素）、E:last-child（最后一个子元素）、E:nth-child(n)（第n个子元素）、E:only-child（唯一一个子元素）、E:nth-last-child(n)（倒数第n个子元素）    
    同级元素的选择（类似子元素选择）：E:first-of-type）、E:last-of-type、E:only-of-type、E:nth-of-type(n)、E:nth-last-of-type(n)

### - 伪对象选择器
在书写时可以写“:”或者“::”  

选择符 | 简介 |
--------------------------|-----------------------------------|
|E:first-letter/E::first-letter|设置对象第一个字符样式| 
|E:first-line/E::first-line|设置对象第一行样式|
|E:before/E::before| 设置对象前的内容，用content| 
|E:after/E::after| 设置对象后的内容，用content|
|E::selection| 设置对象被选择时的颜色|

## 2、CSS优先级     
#### 对于样式的优先级处理是利用权叠加的机制
    -   通配选择符的权值 0,0,0,0  
    -   标签的权值为 0,0,0,1   
    -   类的权值为 0,0,1,0     
    -   ID的权值为 0,1,0,0     
    -   important的权值为最高 1,0,0,0     
    
使用规则：**权叠加在一起的值大的优先，如果权重相同则后定义优先。**  

在使用的时候需要注意以免重复冗余。  
    **使用关键点：**    
1.  样式与选择器的类型和数量影响权重相关。
2.  样式与样式的定义顺序相关。  

**优先级的顺序**：  important > 内联 > ID > 类 > 标签 通配符 


## 3、CSS的引入方式
有4种方式引入：  
  
    1. 利用style属性在标签中进行，这样缺乏统一性。   
    如：<span stye="color:red">
    2. 使用<STYLE>标签进行对样式规则的书写，这样缺乏灵活性。
    如：
    <STYLE TYPE="text/css">  
    body {      
      margin：0px;   
      padding: 0px;
    }

    </STYLE> 
    3. link方法利用.css文件，多个文件可以对同一个css样式进行使用。     
    如：
    <link rel=stylesheet type="text/css" href="a.css"> 
    4. @important 对.css文件进行引入类似于link.  
    如： 
    <STYLE TYPE="text/css">  
    @important url(css/a.css);
    </STYLE> 


## 4、执行效率
#### css执行规则：样式系统从右向左匹配元素，左边有选择符则继续直到匹配元素或者不匹配而退出。 
    
因此在利用后代选择器的方式会很低效尽量不要选择太多层**最多不要超过4层**，如：html body div ul
li{ }。
   
   
#### 在实际应用中，在解析按照效率从高到低排序    
**排序**：1.id选择器（#id）2.类选择器 （.class）3.标签选择器（div,h1,p）4.相邻选择器（h1+p）5.子选择器（ul < li）6.后代选择器（li a）7.通配符选择器（*）8.属性选择器（a[title="title"]）9.伪类选择器（a:hover,li:nth-child）

## 5、书写
- 少使用通配符的形式（{margin:0px;padding:0px}）会导致效率低下，造成不必要元素修改。    

- 不要使用元素的特性（颜色、位置、大小）来命名class或id，因选择按意义命名，例如：#navigator{}、#headerbar{}等。   

- 子元素使用相同的样式的时候，直接在父元素中进行处理。  例如:#container li {}、#container p{}等 样式在#container{}中处理。
- 在实际处理用多相同样式时利用多重选择器h1,h2,h3{}   

- 在处理样式时，适当利用注释规，将同一部分按照从外到内的方式进行。例如：    
    
    ```
    /*** Header***/
    #header{}
    #header h1{}
    /***Container***/
    #container{}
    #container .class{}
    /***Footer***/
    #footer{}
    #footer button{}
    
    ```
- 保持css样式的可读性，在使一个属性保持一行。例如：
    ```
    #id{
        position:absolute;
        bottom:10px;
        left:10px;
    }
    ```
    在书写顺序按照：    
1.**位置属性**(position, top, right, z-index, display, float等)   
2.**大小**(width, height, padding, margin)  
3.**文字系列**(font, line-height, letter-spacing, color- text-align等)    
4.**背景**(background, border等)    
5.**其他**(animation, transition等)     
- 使用相关前缀的写法    
    1.普通的class，就如前面所说，采用小写+中划线，功能名称+内容缩写的形式，例如：friend-link-title  
    
    2.普通的 id（用于页面中控制大容器的样式，如header，footer，和锚点）用驼峰格式，例如：friendLink
    
## 6、命名规范
```
-CSS命名规范(规则)常用的CSS命名
头：header
内容：content/container
导航：nav
侧栏：sidebar
栏目：column
页面外围控制整体布局宽度：wrapper
左右中：left right center
登录条：loginbar
标志：logo  使用专有名词等等
-id命名规则
1.界面结构
2.导航
3.功能划分

- 注意事项：

1.一律小写;     
2.尽量用英文;   
3.尽量不缩写，除非一看就明白的单词。

-CSS样式表文件命名
主要的 master.css
模块 module.css
基本共用 base.css
布局、版面 layout.css
主题 themes.css
专栏 columns.css
文字 font.css
表单 forms.css
补丁 mend.css
打印 print.css

```



