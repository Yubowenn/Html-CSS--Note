# CSS选择器
* 在CSS样式中介绍了什么是选择器，这里介绍一下选择器的分类。

## 标签选择器
* 标签选择器就是html中本来的标签，例如：&#60;html&#62;,&#60;body&#62;,&#60;h1&#62;等等  
这里与样式章节中介绍的嵌入式基本形式一样，  
举例：
```html
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
<title>认识html标签</title>
<style type="text/css">
h1{
    font-weight:normal;
    color:red;
}
</style>
</head>
<body>
    <h1>勇气</h1>
</body>
</html>
```


## 类选择器与ID选择器
### 类选择器
* 类选择器是最常用的CSS样式编码。
* 语法：
```html
.类选器名称{css样式代码;}
```
1. 英文圆点开头
2. 其中类选器名称可以任意起名（但不要起中文噢）
具体使用方法分为两步：  
第一步：用标签将要修饰的标签标记起来，然后为该标签设置一个类：
```html
<span class="stress">胆小如鼠</span>
```
第二步：设置类选择器（在head标签中）
```html
.stress{color:red;}
```
### ID选择器
* 类似于类选择器，但是有不同  
1. 在选择器中的属性不是class，而是改为：id=“ID名称”；
2. ID选择符的前面是井号（#）号，而不是英文圆点（.）  
举例：
```html
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
<title>认识html标签</title>
<style type="text/css">
#setGreen{
color:green;
}
</style>
</head>
<body>
    <p>到了三年级下学期时，我们班上了一节<span id="setGreen">公开课</span></p>
</body>
</html>
```
### 类和ID选择器的区别
* 相同点：可以应用于各种元素
* 不同点：
1. ID选择器只能在文档中使用一次。而类选择器可以使用多次。  
举例：
```html
<p>三年级时，我还是一个<span class="stress">胆小如鼠</span>的小女孩，上课从来不敢回答老师提出的问题，生怕回答错了老师会批评我。就一直没有这个<span class="stress">勇气</span>来回答老师提出的问题。</p>
```
以上代码的表述是正确的，如果将两个class="stress"改为id="stress"则不行  
根据测试，在一个文档中，ID选择器的ID如果不同，是可以使用多次的。但是像上述代码中把相同类名的多个元素都用相同的ID来替换，这样是不行的。
2. 可以使用类选择器词列表方法为一个元素同时设置多个样式。而ID选择器做不到  
举例(这不是完整代码，完整的需要添加head和body)：
```html
.stress{
    color:red;
}

.bigsize{
    font-size:25px;
}
<p>到了<span class="stress bigsize">三年级</span>下学期时，我们班上了一节公开课...</p>
```
以上代码的表述是正确的，如果更改为id="stress bigsize"则不行。


## 子选择器
* 还有一个比较有用的选择器子选择器，即大于符号(>),用于选择指定标签元素的第一代子元素。  
举例(这不是完整代码，完整的需要添加head和body)：
```html
.food>li{border:1px solid red;}

<ul class="food">
    <li>水果
        <ul>
        	<li>香蕉</li>
            <li>苹果</li>
            <li>梨</li>
        </ul>
    </li>
    <li>蔬菜
    	<ul>
        	<li>白菜</li>
            <li>油菜</li>
            <li>卷心菜</li>
        </ul>
    </li>
</ul>
```
这行代码会使class名为food下的子元素li（水果、蔬菜）加入红色实线边框。  
为了方便理解，下面将以上代码的样式设置代码稍作修改,想想会变成什么样：
```html
.food>li>ul>li{border:1px solid red;}
```


## 包含选择器
* 加入空格,用于选择指定标签元素下的后辈元素。  
举例：
```html
.first  span{color:red;}
```
* 包含选择器与子选择器的区别：
1. 子选择器（child selector）仅是指它的直接后代，或者你可以理解为作用于子元素的第一代后代。而后代选择器是作用于所有子后代元素。
2. 后代选择器通过空格来进行选择，而子选择器是通过“>”进行选择。即，>作用于元素的第一代后代，空格作用于元素的所有后代。  
举例（这不是完整代码）：
```html
.food li{border:1px solid red;}

<ul class="food">
    <li>水果
        <ul>
        	<li>香蕉</li>
            <li>苹果</li>
            <li>梨</li>
        </ul>
    </li>
    <li>蔬菜
    	<ul>
        	<li>白菜</li>
            <li>油菜</li>
            <li>卷心菜</li>
        </ul>
    </li>
</ul>
```
同样举上面自选择器的例子，将.food>li改为.food li。那么结果是每一个li标记起来的元素都会加上红色方框。


## 通用选择器<span>