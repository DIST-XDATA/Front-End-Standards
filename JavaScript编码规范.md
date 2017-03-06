# XDATA-JavaScript编码规范  

## 目录

[1. 概述](#1)  
  
[2. 总体命名规则](#2)  
  
 [2.1 基本命名规范](#2.1)  
  
  [2.1.1 命名方法](#2.1.1)  
  
  [2.1.2 命名规则](#2.1.2)  

  [2.1.3 其他规则](#2.1.3)  
  
 [2.2 特殊命名规则](#2.2)  
  
[3. 详细命名规则](#3)  
  
 [3.1 JavaScript文件](#3.1)  
  
 [3.2 布局](#3.2)  
  
 [3.3 变量](#3.3)  
  
 [3.4 语句](#3.4)  

  [3.4.1 简单语句](#3.4.1)  
  
  [3.4.2 复合语句](#3.4.2)  
  
  [3.4.3 语句标示](#3.4.3)  
  
  [3.4.4 其他事项](#3.4.4)  
  
 [3.5 函数](#3.5)  
  
[4. 注释](#4)  

 [4.1 注释内容](#4.1)  
  
 [4.2 注释规范](#4.2)  
  
[5. 其他注意事项](#5)  

## 1 概述<h2 id="1"></h2>

一个优秀的程序员应该能够编写既能让电脑识别的代码又能让其他开发人员能够看懂并愿意去看的规范代码（规范代码就是结构清晰、可读性高、代码易于维护、不至于太过程化而杂乱无章），也就是书写可维护性的代码    

**基本概念**    

  - 可维护代码需要遵循以下规则：  
  - 可理解性：其他人可以接手代码并理解它的意图和一般途径而无须原开发人员的完整解释  
  - 直观性：代码中的东西一看就能明白，不管其操作过程多么复杂  
  - 可适应性：代码在重复使用时只要求更改传入的参数而不要求修改或重写代码以达到要求  
  - 可扩展性：在代码架构上已考虑到未来允许对核心功能进行扩展  
  - 可调试性：当有地方出错时，代码可以给予开发人员足够的信息来尽可能直接的确定问题所在，一种让代码变得可维护的简单途径就是形成一套JavaScript代码的书写约定    

**编写目的**    

  - 为前端开发人员的JavaScript代码编写提供参考依据和统一标准    

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

## 2 总体命名规范<h2 id="2"></h2>

### 2.1 命名基本规范<h3 id="2.1"></h3>

#### 2.1.1 命名方法<h4 id="2.1.1"></h4>

命名方法通常有以下几类
  1. camel命名法    
示例：
```javascript
var thisIsAnApple = ''; 
```
  2. pascal命名法    
示例：
```javascript
var ThisIsAnApple = '';
```
  3. 下划线命名法    
示例：
```javascript
var this_is_an_apple = '';
```
  4. 中划线命名法    
示例：
```javascript
var this-is-an-apple = '';
```

#### 2.1.2 命名规则<h4 id="2.1.2"></h4>

根据不同类型的内容，必须严格采用如下的命名法    
**[强制]变量名，必须采用camel命名法，若变量名称由一个单词组成，必须为小写字母**    
反例：  
```javascript
var Element = '';
var accountelement = '';
var AccountElement = '';
```
正例：  
```javascript
var element = '';
var accountElement = '';
```
**[强制]函数名，必须采用camel命名法，使用动词或动词短语为其命名**    
反例：  
```javascript
function Value(){
  // ...
}
function elementvalue(){
  // ...
}
function ElementValue(){
  // ...
}
```
正例：  
```javascript
function getValue(){
  // ...
}
function getElementValue(){
  // ...
}
function setElementValue(){
  // ...
}
```
**[强制]函数参数名，必须采用camel命名法**    
反例：  
```javascript
function funcName(Element){
  // ...
}
function funcName(accountelement){
  // ...
}
function funcName(AccountElement){
  // ...
}
```
正例：   
```javascript
function funcName(element){
  // ...
}
function funcName(accountElement){
  // ...
}
```
**[强制]类的方法/属性，必须采用camel命名法**    
示例：    
```javascript
// TestClass为一个类
function TestClass(valueOne, valueTwo){
  this.testValueOne = valueOne;
  this.testValueTwo = valueTwo;
}
```
**[强制]私有（保护）成员，必须以下划线开头，且必须采用camel命名法**    
反例：    
```javascript
Element
_Element
_accountelement
_AccountElement
_SetValue()
```
正例：    
```javascript
_element
_accountElement
_setValue()
```
**[强制]常量名，必须使用全部大写的下划线命名法**    
反例：    
```javascript
isDebugEnabled
ISDEBUGENABLED
```
正例：    
```javascript
IS_DEBUG_ENABLED
```
**[强制]类名，必须使用pascal命名法**    
反例：    
```javascript
function testClass(){
  // ...
}
```
正例：    
```javascript
function TestClass(){
  // ...
}
```
**[强制]枚举名，必须使用pascal命名法**    
反例：    
```javascript
var targetstate = {
    READING: 1,
    READED: 2,
    APPLIED: 3,
    READY: 4
};
```
正例：    
```javascript
var TargetState = {
    READING: 1,
    READED: 2,
    APPLIED: 3,
    READY: 4
};
```
**[强制]枚举的属性，必须使用全部大写的下划线命名法**    
反例：    
```javascript
var TargetState = {
    READBOOK: 1,
    readed: 2,
    appliedProgram: 3,
    ready_to_go: 4
};
```
正例：    
```javascript
var TargetState = {
    READ_BOOK: 1,
    READED: 2,
    APPLIED_PROGRAM: 3,
    READY_TO_GO: 4
};
```
**[强制]命名空间，必须使用camel命名法**    
反例：    
```javascript
equipments.HeavyWeapons = {};
equipments.heavyweapons = {};
```
正例：    
```javascript
equipments.Heavyweapons = {};
```

#### 2.1.3 其他规则<h4 id="2.1.3"></h4>

**[强制]所有的变量名必须使用英文名称**    
反例：    
```javascript
var 变量 = '';
```
正例：    
```javascript
var element = '';
```    
**[强制]常量必须在对象（类）或者枚举变量的前部声明（命名规则参考变量命名）**    
**[强制]对于简写单词，不能使用大写名称作为变量名**    
反例：    
```javascript
var XML = null;
```
正例：    
```javascript
var Xml = null;
```    
**[强制]公有变量必须清楚的表达自身的属性，因此应避免字义含糊不清**    
反例：    
```javascript
// 鼠标响应事件
var mseEvtHdlr = null;
```
正例：    
```javascript
// 鼠标响应事件
var mouseEventHandler = null;
```    
**[建议]类/构造函数可以使用扩展其基类的名称命名，这样可以正确、迅速的找到其基类的名称，例如：基类名称为EventHandler，扩展类名称为UIEventHandler、MouseEventHandler。基类可以在明确描述其属性的前提下，缩短其命名**    
**[建议]命名同时还需要关注语义，例如：变量名应当使用名词，函数名应当用动宾短语，类名应当用名词等**    
**[建议]变量如果有较广的作用域，可以将其设计为一个类的成员，相对的如作用域较小或为私有变量则使用简洁的单词进行命名**    

### 2.2 特殊命名规范<h3 id="2.2"></h3>

**[强制]"get/set"不要和一个字段相连，除非其被定义为私有变量**    
**[强制]复数必须有其公共的名称约定**    
**[强制]补充用语必须使用补充词，例如：get/set、add/remove、create/destroy、start/stop、insert/delete、begin/end等**    
**[建议]compute作为变量名应为已经计算完成的变量，find作为变量名应为已经查找完成的变量，initialize或者init作为变量应为已经实例化（初始化）完成的类或者其它类型的变量**    
**[建议]以is开头的变量名应设置为布尔值，同理其开头也可以为has、can、should或者b**    
示例：    
```javascript
var isFinished = true;
var hasSelected = true;
var canSelect = true;
var shouldExist = true;
var bSelected = true;
```    
**[建议]UI（用户界面）控制变量应在名称后加控制类型，例如：leftComboBox、TopScrollPane等**    
**[建议]以num、count或者n开头的变量名约定为数字**    
示例：    
```javascript
var numStrLength = 0;
var countStrLength = 0;
var nStrLength = 0;
```    
**[建议]以str或者s开头的变量名约定为字符串**    
示例：    
```javascript
var strTitle = '';
var sTitle = '';
```    
**[建议]以a开头的变量名约定为数组**    
示例：    
```javascript
var aExample = [];
```    
**[建议]以r开头的变量名约定为正则表达式**    
示例：    
```javascript
var rJudge = /^[0-9-]*$/;
```    
**[建议]以o开头的变量名约定为表示以上未涉及到的其他对象**    
**[建议]重复变量建议使用i、j、k、l、m、n（依次类推）等名称的变量**    
示例：    
```javascript
for (var i = 0, j < length; i < j; i++) {
  // ...
}
```    
**[建议]能缩写的名称尽量使用缩写**    
**[建议]避免使用有歧义的布尔变量名称，例如：isNotError、isNotFound等**    
反例：    
```javascript
var isNotError = true;
var isNotFound = true;
```
正例：    
```javascript
var isError = true;
var isFound = true;
```    
**[建议]方法如果返回一个类，则应该在名称上说明返回了什么，如果是一个过程，则应该说明做了什么**    
**[建议]代表jQuery对象的变量的命名以$开头，这样一眼就能看出来这是一个jQuery变量**    

## 3 详细命名规范<h2 id="3"></h2>

### 3.1 JavaScript文件<h3 id="3.1"></h3>

**[强制]JavaScript程序应该独立保存在后缀为js的文件中**    
**[强制]JavaScript代码不应被包含在HTML文件中，除非这是段特定只属于此部分的代码，在HTML中的JavaScript代码会明显增加文件大小**    

### 3.2 布局<h3 id="3.2"></h3>

#### 3.2.1 空格<h4 id = "3.2.1"></h4>

**[强制]二元运算符（除了点、左大括号和左方括号之外）两侧必须有一个空格，一元运算符与操作对象之间不允许有空格（除非操作符是个单词，比如typeof）**    
示例：    
```javascript
var a = !arr.length;
a++;
a = b + c;
```    
**[强制]用作代码块起始的左括号（{）前必须有一个空格**    
反例：    
```javascript
if (condition){
	// …
}
while (condition){
	// …
}
function funcName(){
	// …
}
```
正例：    
```javascript
if (condition) {
	// …
}
while (condition) {
	// …
}
function funcName() {
	// …
}
```    
**[强制]if/else/for/while/function/switch/do/try/catch/finally关键字后，必须有一个空格**    
示例：    
```javascript
if (condition) {
	// …
}
while (condition) {
	// …
}
(function () {
	// …
})();
```    
**[强制]在对象创建时，属性中的:之后必须有空格，:之前不允许有空格**    
反例：    
```javascript
var obj = {
	a : 1,
	b:2,
	c :3
};
```
正例：    
```javascript
var obj = {
	a: 1,
	b: 2,
	c: 3
};
```    
**[强制]函数声明、具名函数表达式、函数调用中，函数名和左括号（(）之间不允许有空格**    
反例：    
```javascript
function funcName () {
	// …
}
var funcName = function funcName () {
	// …
}
funcName ();
```
正例：    
```javascript
function funcName() {
	// …
}
var funcName = function funcName() {
	// …
}
funcName();
```    
**[强制]逗号（,）和分号（;）前不允许有空格，如果不位于行尾，逗号（,）和分号（;）后必须跟一个空格**    
反例：    
```javascript
callFunc(a , b);
```
正例：    
```javascript
callFunc(a, b);
```    
**[强制]在函数调用、函数声明、括号表达式、属性访问、if/for/while/switch/catch等语句中，()和[]内紧贴括号部分不允许有空格**    
反例：    
```javascript
callFunc( param1, param2, param3 );
save( this.list[ this.indexes[ i ] ] );
needIncreament && ( variable += increament );
if ( num > list.length ) {
	// …
}
while ( len-- ) {
	// …
}
```
正例：    
```javascript
callFunc(param1, param2, param3);
save(this.list[this.indexes[i]]);
needIncreament && (variable += increament);
if (num > list.length) {
	// …
}
while (len--) {
	// …
}
```    
**[强制]单行声明的数组与对象，如果包含元素，{}和[]内紧贴括号部分不允许包含空格。声明包含元素的数组与对象，只有当内部元素的形式较为简单时，才允许写在一行。元素复杂的情况，应当换行书写**    
反例：    
```javascript
var arr1 = [ ];
var arr2 = [ 1, 2, 3 ];
var obj1 = { };
var obj2 = { name: ‘obj’ };
var obj3 = {name: ‘obj’, age: 20, sex: 1};
```
正例：    
```javascript
var arr1 = [];
var arr2 = [1, 2, 3];
var obj1 = {};
var obj2 = {name: ‘obj’};
var obj3 = {
  name: ‘obj’,
  age: 20,
  sex: 1
};
```    
**[强制]行尾不得有多余的空格**    
**[强制]函数参数与左括号之间不能有空格，每个参数之间应该用逗号加一个空格隔开**    
反例：    
```javascript
function funcName( param1,param2 , param3) {
  // statement
}
```
正例：    
```javascript
function funcName(param1, param2, param3) {
  // statement
}
```    
**[强制]每个控制部分，比如for语句中的分号（;）后面须跟一个空格**    
反例：    
```javascript
for (var i = 0, j < length;i < j;i++) {
  // statement
}
```
正例：    
```javascript
for (var i = 0, j < length; i < j; i++) {
  // statement
}
```    

#### 3.2.2 缩进<h4 id = "3.2.2"></h4>

**[强制]缩进使用4个空白符或1个TAB的制表位**    
**[强制]表达式的缩进与变量声明应一致**    
**[强制]代码折叠起来进行表示，感官上完全并且合乎逻辑**    
**[强制]函数的参数应采用明确的缩进，缩进规则与其他块保持一致**    

#### 3.2.3 换行<h4 id = "3.2.3"></h4>

**[强制]每个独立语句结束后必须换行**    
**[强制]避免每行超过80个字符，当一条语句一行写不下时，要考虑换行。超长的不可分割的代码允许例外，比如复杂的正则表达式，长字符串不在例外之列**    
**[强制]在运算符号（最好是逗号）后换行，在运算符后换行可以减少因为复制粘贴产生的错误被分号掩盖的几率，下一行应该缩进8个空格或2个TAB符**    
**[强制]运算符换行时，运算符必须在新行的行首**    
反例：    
```javascript
if (user.isAuthenticated() &&
user.isInRole(‘admin’) &&
user.hasAuthority(‘add-admin’) ||
user.hasAuthority(‘delete-admin’)) {
	// …
}
var result = number1 + number2 + number3 +
   number4 + number5;
```
正例：    
```javascript
if (user.isAuthenticated()
&& user.isInRole(‘admin’)
&& user.hasAuthority(‘add-admin’)
|| user.hasAuthority(‘delete-admin’)) {
	// …
}
var result = number1 + number2 + number3
     + number4 + number5;
```    
**[强制]在函数声明、函数表达式、函数调用、对象创建、数组创建、for语句等场景中，不允许在逗号（,）或分号（;）前换行**    
反例：    
```javascript
var obj = {
	a: 1
	, b: 2
	, c: 3
};
foo(
	aVeryVeryLongArgument
	, anotherVeryLongArgument
	, callback
);
```
正例：    
```javascript
var obj = {
	a: 1,
	b: 2,
	c: 3
};
foo(
	aVeryVeryLongArgument,
	anotherVeryLongArgument,
	callback
);
```    
**[建议]不同行为或逻辑的语句集，使用空行隔开，更易阅读**

### 3.3 变量<h3 id="3.3"></h3>

**[强制]变量名应由26个大小写字母（a...z,A...Z），10个数字（0...9）和下划线中的元素组成，避免使用国际化字符（如中文）**    
反例：    
```javascript
var 变量 = '';
```
正例：    
```javascript
var element = '';
var _element = '';
```    
**[强制]变量必须在声明初始化以后才能使用，即便是null类型**    
反例：    
```javascript
var strElement;
strElement = '字符串';
```
正例：    
```javascript
var strElement = '';
strElement = '字符串';
```    
**[强制]变量不能产生歧义**    
**[强制]相关的变量集应该放在同一代码块中，非相关的变量集不应该放在同一代码块中**    
**[强制]变量应尽量保持最小的生存周期**    
反例：    
```javascript
var strElement = '';
function funcName() {
  strElement = '给字符串变量赋值';
  return strElement;
}
```
正例：    
```javascript
function funcName() {
  var strElement = '';
  strElement = '给字符串变量赋值';
  return strElement;
}
```    
**[强制]尽量避免使用幻数（直接使用的常数），应使用常量代替**    
反例：    
```javascript
var numRadius = 10;
// 这里直接使用了3.1415926
// 无法很快的理解这个常数是什么意思
var numGirth = 2 * numRadius * 3.1415926;
```
正例：    
```javascript
var numRadius = 10;
var PI = 3.1415926;
var numGirth = 2 * numRadius * PI;
```    
**[强制]浮点变量必须指明小数点后一位（即使是0）**    
**[强制]浮点变量必须指明实部（即使是0，用0.0进行表示）**    

### 3.4 语句<h3 id="3.4"></h3>

#### 3.4.1 简单语句<h4 id="3.4.1"></h4>

**[强制]每一行最多包含一条语句，将分号（;）放到每条简单语句的结尾处**    
反例：    
```javascript
// 语句末尾没有加分号（;）
var strExample = ''
```
正例：    
```javascript
var strExample = '';
```    
**[强制]一个函数赋值或对象赋值也是赋值语句，应该以分号（;）结尾**    

#### 3.4.2 复合语句<h4 id="3.4.2"></h4>

**[强制]复合语句必须被包含在{}（大括号）内**    
**[强制]被括起的语句必须多缩进4个空格或1个TAB键**    
反例：    
```javascript
if (condition) {
var strElement = '';
strElement = '这是一个字符串变量';
}
```
正例：    
```javascript
if (condition) {
  var strElement = '';
  strElement = '这是一个字符串变量';
}
```    
**[强制]左大括号（{）应在符合语句起始行的结尾处，右大括号（}）应与左大括号（{）的那一行开头对齐**    
反例：    
```javascript
if (condition)
{
  // ...
}
```
正例：    
```javascript
if (condition) {
  // ...
}
```    
**[强制]大括号应该在所有复合语句中使用，即使只有一条语句，当它们是控制结构的一部分时，比如一个if或for语句，这样做可以避免以后添加语句时造成的错误**    
反例：    
```javascript
if (condition)
  var strElement = '';
```
正例：    
```javascript
if (condition) {
  var strElement = '';
}
```    

#### 3.4.3 语句标示<h4 id="3.4.3"></h4>

  语句标示是可选的，只有以下语句必须被标示：return、if、while、do、for、switch、try    

##### 3.4.3.1 return语句<h5 id="3.4.3.1"></h5>

**[强制]一条有返回值的return语句不要使用括号来括住返回值，如果返回表达式，则表达式应与return关键字在一行**    
反例：    
```javascript
function funcName() {
  var a = 10;
  var b = 20;
  return (a + b);
}
function funcName() {
  var a = 10;
  var b = 20;
  return
    a + b;
}
```
正例：    
```javascript
function funcName() {
  var a = 10;
  var b = 20;
  return a + b;
}
```    

##### 3.4.3.2 if语句<h5 id="3.4.3.2"></h5>

**[强制]if语句应如以下格式进行表示**    
示例：    
```javascript
if (condition) {
  statements;
} else if (condition) {
  statements;
} else {
  statements;
}
```    

##### 3.4.3.3 for语句<h5 id="3.4.3.3"></h5>

**[强制]for语句应如以下格式进行表示**    
示例：    
```javascript
for (initialization; condition; update) {
  statements;
}
```    
**[建议]for循环语句使用技巧，例如如下所示的for循环语句**    
示例：    
```javascript
for (i = 0; i < myArray.length; i++) {
  statements;
}
```    
**[建议]每次判断i是否达到临界值时都要获取一遍myArray的length属性，这样做影响效率，可以用以下的形式**    
示例：    
```javascript
for (i = 0, max = myArray.length; i < max; i++) {
  statements;
}
```    

##### 3.4.3.4 for语句<h5 id="3.4.3.4"></h5>

**[强制]while语句应如以下格式进行表示**    
示例：    
```javascript
while (condition) {
  statements;
}
```    

##### 3.4.3.5 do语句<h5 id="3.4.3.5"></h5>

**[强制]不像别的复合语句，do语句总是以分号（;）结尾，应如以下格式进行表示**    
示例：    
```javascript
do {
  statements;
} while (condition);
```    

##### 3.4.3.6 switch语句<h5 id="3.4.3.6"></h5>

**[强制]每个case相互对齐，每一组statements（除了default）都应以break、return或者throw结尾，不要让它顺次往下执行，应如以下格式进行表示**    
示例：    
```javascript
switch (expression) {
  case expression:
    statements;
  default:
    statements;
}
```    

##### 3.4.3.7 try语句<h5 id="3.4.3.7"></h5>

**[强制]try语句应如以下格式进行表示**    
示例：    
```javascript
try {
  statements;
} catch (variable) {
  statements;
} finally {
  statements;
}
```    

##### 3.4.3.8 width语句<h5 id="3.4.3.8"></h5>

**[强制]with语句可以用来引用某个特定对象中已有的属性，但不能用来给对象添加属性，要给对象创建新的属性，必须明确地引用该对象。在编写代码中尽量不要使用with语句**    

##### 3.4.3.9 {}和[]<h5 id="3.4.3.9"></h5>

**[强制]使用{}代替new Object()，使用[]代替new Array()**    
反例：    
```javascript
var arrayExample = new Array();
var oExample = new Object();
```
正例：    
```javascript
var arrayExample = [];
var oExample = {};
```    
**[建议]当成员是一组有序的数字时使用数组来保存数据，当成员名是无规律的字符串或其他时使用对象来保存数据**    

#### 3.4.4 其他事项<h4 id="3.4.4"></h4>

##### 3.4.4.1 循环/重复变量规范<h5 id="3.4.4.1"></h5>

**[强制]如果只对块进行循环控制，则必须使用for循环**    
**[强制]循环变量应该在循环开始前就被初始化，如使用for循环，则使用for语句初始化循环变量**    
示例：    
```javascript
for (var i = 0, j < length; i < j; i++) {
  // statement
}
```    
**[建议]可以使用do...while语句（但使用时要注意不要出现死循环）**    
**[建议]可以使用break和continue语句（但要注意二者的区别），应尽量避免使用continue语句，它很容易使程序的逻辑过程晦涩难懂**    

##### 3.4.4.2 条件表达式<h5 id="3.4.4.2"></h5>

**[强制]不允许在条件表达式中加入块**    
**[建议]应该尽量避免复杂的条件表达式，如有必要可以使用临时布尔量**    
**[建议]在使用if/else进行条件判断时，经常发生的情况应该放在if后面的代码中，而另一种不常发生的情况应放在else后面的代码中**    
示例：    
```javascript
if (condition) {
  // 经常发生的情况
} else {
  // 不经常发生的情况
}
```    

### 3.5 函数<h3 id="3.5"></h3>

  1. 函数命名
  * 函数名与左括号之间不应该有空格，在右括号与开始程序体的左大括号之间应插入一个空格，函数程序体应缩进4个空格或1个TAB符，例如
```javascript
function outer(c, d) {
  var e = c * d;
  function inner(a, b) {
    return (e * a) + b;
  }
  return inner(0, 1);
}
```
  * 函数名的命名规则与变量命名一样，采用驼峰命名规则，首字母需要小写，约定以f开头，例如fGetValue()
  * 统一使用动词或者动词+名词形式，例如：fGetVersion()、fSubmitForm()、fInit()
  * 涉及返回逻辑值的函数可以使用is，has，contains等表示逻辑的词语代替动词，例如：fIsObject()、fHasClass()、fContainsElment()
  * 对象方法命名使用f+对象类名+动词+名词形式；例如：fnAddressGetEmail()
  * 某事件响应函数命名方式为f+触发事件对象名+事件名或者模块名，例如：fDivClick()，fAddressSubmitButtonClick()
  2. 函数方法常用的动词

| 方法名               | 注释          | 方法名              | 注释       |
| :----------------:  | :----------: | :-----------------: | :-------: |
| get/set             | 获取/设置     | add/remove          | 增加/删除  |
| create/destory      | 创建/移除     | start/stop          | 启动/停止  |
| open/close          | 打开/关闭     | read/write          | 读取/写入  |
| load/save           | 载入/保存     | create/destory      | 创建/销毁  |
| begin/end           | 开始/结束     | backup/restore      | 备份/恢复  |
| import/export       | 导入/导出     | split/merge         | 分割/合并  |
| inject/extract      | 注入/提取     | attach/detach       | 附着/脱离  |
| bind/separate       | 绑定/分离     | view/browse         | 查看/浏览  |
| edit/modify         | 编辑/修改     | select/mark         | 选取/标记  |
| copy/paste          | 复制/粘贴     | undo/redo           | 撤销/重做  |
| insert/delete       | 插入/移除     | add/append          | 加入/添加  |
| clean/clear         | 清理/清除     | index/sort          | 索引/排序  |
| find/search         | 查找/搜索     | increase/decrease   | 增加/减少  |
| play/pause          | 播放/暂停     | launch/run          | 启动/运行  |
| compile/execute     | 编译/执行     | debug/trace         | 调试/跟踪  |
| observe/listen      | 观察/监听     | build/publish       | 构建/发布  |
| input/output        | 输入/输出     | encode/decode       | 编码/解码  |
| encrypt/decrypt     | 加密/解密     | compress/decompress | 压缩/解压缩|
| pack/unpack         | 打包/解包     | parse/emit          | 解析/生成  |
| connect/disconnect  | 连接/断开     | sent/receive        | 发送/接收  |
| download/upload     | 下载/上传     | refresh/synchronize | 刷新/同步  |
| update/revert       | 更新/复原     | lock/unlock         | 锁定/解锁  |
| check out/check in  | 签出/签入     | submit/commit       | 提交/交付  |
| push/pull           | 推/拉         | expand/collapse     | 展开/折叠  |
| begin/end           | 起始/结束     | start/finish        | 开始/完成  |
| enter/exit          | 进入/退出     | abort/quit          | 放弃/离开  |
| obsolete/depreciate | 废弃/废旧     | collect/aggregate   | 收集/聚集  |

  3. 不推荐构造超长函数，当函数超过100行，就要想想是否能将函数拆为两个或多个函数
  4. 函数调用返回的错误信息，统一使用变量ex（exception）或者err（error）对其进行定义
  5. 一个函数的参数控制在6个以内

## 4 注释<h2 id="4"></h2>

### 4.1 注释内容<h3 id="4.1"></h3>

  1. JS文件开头注释
  * [建议]JavaScript文件在开头应包含类似以下注释说明，修改人、修改时间及修改描述这三项要实时更新，保证为最新
```javascript
/*
*@fileName:文件名
*@fileDesc:文件功能描述
*@author:创建人
*@createTime:创建时间
*@modifiedBy:修改人
*@modifiedTime:修改时间
*@modifiedDesc:修改描述
*/
```
  2. 大功能区注释
  * [建议]在大功能区（或难以理解的部分）代码的开头添加注释，对其功能、参数及返回值进行描述*（具体详见JSDOC注释规范）*
```javascript
/*
*@desc:功能描述
*@param:参数描述
*@return:返回值
*/
```
  3. 单行注释
  * [建议]放在行末尾，对该行代码进行说明，//后面跟一个空格再跟注释内容
```javascript
// 注释内容
```
  4. 特殊标记
  * *（具体详见JSDOC注释规范）*
  * TODO：有功能待实现，此时需要对将要实现的功能进行简单说明
  * FIXME：该处代码运行没问题，但可能由于时间赶或其他原因，需要修正，此时需要对如何修正进行简单说明
  * HACK：为修正某些问题而写的不太好或者使用了某些诡异手段的代码，此时需要对思路或诡异手段进行描述
  * XXX：该处存在陷阱，此时需要对陷阱进行描述
  5. 其他注释说明
  * *（具体详见JSDOC注释规范）*
  * 命名空间注释使用@namespace
  * 类或构造函数注释使用@class
  * 类的继承信息注释使用@extends
  * 使用包装方式扩展类成员时，通过@lends进行重新指向
  * 类的属性或方法等成员信息使用@public/@protected/@private中的任意一个，指明可访问性。当函数是内部函数，外部不可访问时，可以使用@inner标识。重写父类方法时，应当添加@override标识
  * 事件注释使用@event，事件参数的标识与方法描述的参数相同
  * 常量注释使用@const，并包含说明和类型信息
  * 对于类型未定义的复杂结构的注释，可以使用@typeof标识来定义
  * AMD模块使用@module或@exports标识，对于已使用@moudle标识为AMD模块的引用，在namepaths中必须增加"moudle:"作为前缀（若namepaths没有前缀，则生成的文档中将无法正确生成链接）

### 4.2 注释规范<h3 id="4.2"></h3>

  1. 在对函数进行声明时，应用JSDOC对其进行相应的注释说明
  2. 注释应该是解释为什么和做什么，而不是介绍是什么
  3. 总是使注释保持最新
  4. 变量声明时，使用行尾注释，其他情况下，使用单行注释并于标识的代码对齐
  5. 不注释难以理解的代码，而应该重写它
  6. 避免多余的或不适当的注释
  7. 对由循环和逻辑分支组成的代码使用注释
  8. 使用具有一致的风格和语言书写注释
  9. 用空白将注释同注释分隔符分开。在没有颜色提示的情况下查看注释时，这样做会使注释很明显且容易被找到

## 5 其他注意事项<h2 id="5"></h2>

  1. 善于使用IDEA自带的一些功能操作使代码布局更加美观
  2. 总是检查数据，要检查你的方法输入的所有数据，一方面是为了安全性，另一方面是为了可用性
  3. 部署前需要压缩JavaScript文件
  4. 在方法顶端定义所有变量，在大部分情况下var语句应该为方法体内的第一个语句
  5. 尽量少使用全局变量，隐式的全局变量应该从来不使用，同时也应尽量避免全局函数的使用
  6. 代码结构应该提供最好的可读性
  7. 不要在命名中使用里使用$，把它留给JQuery，也不要使用反斜杠（/）
  8. 在每个简单语句末尾添加一个;(分号)
  9. 谨慎使用逗号操作符，一般包括在for语句的控制部分的、对象字面量、数组字面量、var语句和参数列表
  10. 不要在if和while语句块中对条件部分赋值
  11. 避免与null进行比较
  12. 始终使用===和!==操作符会更好，==和!=操作符会做类型强制转换
  13. 不要使用===来和假值做比较，if(obj)一般都可以达到目的
  14. 注意不要在+后面跟+或++。这种模式令人混淆
  15. eval方法是JavaScript里最易滥用的特性。除非解析JSON数据，否则不要使用它
  16. 为了避免混乱，在HTML中使用双引号，在JavaScript中使用单引号
  17. 不要为了偷懒而省略引号和{}
  18. 当需要缓存this时需要使用self变量（也可以是其他变量，例如obj、widget等）进行缓存
  19. 如果针对的是不断运行的代码，不应该使用setTimeout，而应该是用setInterval，因为setTimeout每一次都会初始化一个定时器，而setInterval只会在开始的时候初始化一个定时器
  20. 删除dom节点之前，一定要删除注册在该节点上的事件，否则将会产生无法回收的内存。另外，在removeChild和innerHTML = ''二者之间，尽量选择后者，因为前者无法有效地释放dom节点
  21. 在JavaScript中，我们可以使用for(;;)、while()、for(in)三种循环，事实上，这三种循环中for(in)的效率极差，尽量使用for(;;)循环和while()循环，其中while()循环效率最好

*本规范文档将不断修改更新，请各位批评指正*
