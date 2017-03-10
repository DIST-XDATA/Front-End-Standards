#XDATA-CSS编码规范

## 前言
统一的命名规范，便于多人开发维护时代码统一，减少项目沟通和交接的成本，增加代码的语义化。

## 1 命名规范
### 1.1 命名基本规范
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
### 1.2 命名空间

在编码思想上，我们可以将页面拆分成不同的层级（布局、模块、元件）
通过统一的命名规范定义命名的范围，成为CSS class & id命名空间

布局: 以语义化的单词layout作为命名空间，例如主栏布局命名 layout-main，只改变layout-命名空间后面的命名，layout始终保留。布局的命名空间为layout-xxx。
模块：页面是由一个或多个模块组成，模块的英文单词是module，规范简写成mod，如新闻模块mod-news，照片展示模块mod-photo-show。模块的命名空间为mod-xxx 。
元件：元件是属于模块内部的，也可以说模块是由元件和它内部的自有元素组成。如用户照片信息元件cell-user-photo。元件的命名空间为cell-xxx 。

### 1.3 命名参考

1. 页面框架命名，一般具有唯一性，推荐用ID命名

| ID名称        | 命名          |
| ------------- |:-------------:|
|头部     | header| 
|脚部      | footer    |  
|侧栏 | sideBar      |  
|布局 | layout      |  
|主体 | main      |  
|容器 | wrapper      |  
|栏目 | column      |  

2. 模块结构命名

| class名称        | 命名          |
| ------------- |:-------------:|
|模块(如：通知模块)    | mod (mod-notice)| 
|部件(如：查询部件)      | widget(widget-quuery)   |  
|内容 | content      |  
|次级内容 | sub-content      | 

3. 一般元素命名
| class名称        | 命名          | class名称        | 命名          | class名称        | 命名          |
| ------------- |:-------------:| ------------- |:-------------:| ------------- |:-------------:|
二级|	sub	|面包屑|	breadcrumb
标志	|logo	|广告	|bner(禁用banner或ad)
登陆	|login	|注册	|register/reg
搜索	|search	|加入	|join
状态	|status	|按钮	|btn
滚动	|scroll	|标签页	|tab
文章列表	|list|	短消息|	msg/message
当前的	|current	|提示小技巧	|tips
图标	|icon|	注释|	note
指南	|guide	|服务	|service
热点	|hot	|新闻	|news
下载	|download	|投票	|vote
合作伙伴	|partner	|友情链接	|link
版权|	copyright|	演示|	demo
下拉框	|select	|摘要	|summary
翻页	|pages|	主题风格|	themes
设置	|set	|成功|	suc
按钮	|btn|	文本|	txt
颜色	|color/c|	背景	|bg
边框	|border/bor|	居中|	center
上	|top/t	|下|	bottom/b
左	|left/l	|右	|right/r
添加	|add	|删除	|del
间隔	|sp|	段落	|p
弹出层	|pop	|公共	|global/gb
操作|	op	|密码	|pwd
透明	|tran|	信息	|info
重点	|hit	|预览	|pvw
单行输入框|	input|	首页	|index
日志	|blog	|相册|	photo
留言板	|guestbook|	用户|	user
确认	|confirm	|取消	|cancel
报错	|error||


