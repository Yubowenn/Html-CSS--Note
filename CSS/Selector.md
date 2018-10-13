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


## 类选择器
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


## ID选择器
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