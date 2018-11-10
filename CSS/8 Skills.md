# CSS样式设置小技巧

## 水平居中设置
### 行内元素
* 水平居中是通过给父元素设置 ```text-align:center``` 来实现的
* 举例：  
html代码：
```html
<body>
  <div class="txtCenter">我想要在父容器中水平居中显示。</div>
</body>
```
CSS代码：
```css
<style>
  .txtCenter{
    text-align:center;
  }
</style>
```
### 块状元素
#### 定宽块状元素
* 定宽块状元素（块状元素的宽度width为固定值），满足定宽和块状两个条件的元素是可以通过设置“左右margin”值为“auto”来实现居中的。
* 举例：  
html代码：
```html
<body>
  <div>我是定宽块状元素，哈哈，我要水平居中显示。</div>
</body>
```
css代码：
```csss
<style>
div{
    border:1px solid red;/*为了显示居中效果明显为 div 设置了边框*/
    
    width:200px;/*定宽*/
    margin:20px auto;/* margin-left 与 margin-right 设置为 auto */
}

</style>
```
⚠️定宽块状元素一定得满足宽度width是固定值
#### 不定宽块状元素
* 不定宽块状元素，比如网页上的分页导航，因为分页的数量是不确定的，所以我们不能通过设置宽度来限制它的弹性；
* 不定宽度的块状元素有三种方法居中（这三种方法目前使用的都很多）：  
1. 加入 table 标签
* 利用table标签的长度自适应性--即不定义其长度也不默认父元素body的长度（table其长度根据其内文本长度决定）。因此可以看做一个定宽度块元素，然后再利用定宽度块状居中的margin的方法，使其水平居中。
* 第一步：为需要设置的居中的元素外面加入一个 table 标签 ( 包括 &#60;tbody&#62;、&#60;tr&#62;、&#60;td&#62; )。
* 第二步：为这个 table 设置“左右 margin 居中”（这个和定宽块状元素的方法一样）。
举例：  
html代码：
```html
<div>
 <table>
  <tbody>
    <tr><td>
    <ul>
        <li>我是第一行文本</li>
        <li>我是第二行文本</li>
        <li>我是第三行文本</li>
    </ul>
    </td></tr>
  </tbody>
 </table>
</div>

<div class="wrap">
    <table>
        <tbody>
            <tr>
                <td>
                    设置我所在的div容器水平居中
                </td>
            </tr>
        </tbody>
    </table>
</div>
```
css代码：
```css
<style>
table{
    border:1px solid;
    margin:0 auto;
}
.wrap{
    background:#ccc;
    margin:0 auto;
}
</style>
```
2. 设置 display: inline 方法：与第一种类似，显示类型设为行内元素，进行不定宽元素的属性设置
* 第一种实现方法：改变元素的display类型为行内元素，利用其属性直接设置
* 第二种实现方法：改变块级元素的 display 为 inline 类型（设置为 行内元素 显示），然后使用```text-align:center``` 来实现居中效果。这种方法相比第一种方法的优势是不用增加无语义标签，但也存在着一些问题：它将块状元素的 display 类型改为 inline，变成了行内元素，所以少了一些功能，比如设定长度值。  
举例：  
html代码：
```html
<body>
<div class="container">
    <ul>
        <li><a href="#">1</a></li>
        <li><a href="#">2</a></li>
        <li><a href="#">3</a></li>
    </ul>
</div>
</body>
```
css代码：
```css
<style>
.container{
    text-align:center;
}
/* margin:0;padding:0（消除文本与div边框之间的间隙）*/
.container ul{
    list-style:none;
    margin:0;
    padding:0;
    display:inline;
}
/* margin-right:8px（设置li文本之间的间隔）*/
.container li{
    margin-right:8px;
    display:inline;
}
</style>
```
3. 设置 position:relative 和 left:50%：利用 相对定位 的方式，将元素向左偏移 50% ，即达到居中的目的
* 我们可以这样理解：假想ul层的父层（即下面例子中的div层）中间有条平分线将ul层的父层（div层）平均分为两份，ul层的css代码是将ul层的最左端与ul层的父层（div层）的平分线对齐；而li层的css代码则是将li层的平分线与ul层的最左端（也是div层的平分线）对齐，从而实现li层的居中。
* 举例：  
html代码
```html
<body>
<div class="container">
    <ul>
        <li><a href="#">1</a></li>
        <li><a href="#">2</a></li>
        <li><a href="#">3</a></li>
    </ul>
</div>
</body>
```
css代码：
```css
<style>
.container{
    float:left;
    position:relative;
    left:50%
}

.container ul{
    list-style:none;
    margin:0;
    padding:0;
    
    position:relative;
    left:-50%;
}
.container li{float:left;display:inline;margin-right:8px;}
</style>
```


## 垂直居中设置
### 父元素确定的单行文本
* 通过设置父元素的 height 和 line-height 高度一致来实现的。(height: 该元素的高度，line-height: 顾名思义，行高（行间距），指在文本中，行与行之间的 基线间的距离 )。  
line-height 与 font-size 的计算值之差，在 CSS 中成为“行间距”。分为两半，分别加到一个文本行内容的顶部和底部。  
这种文字行高与块高一致带来了一个弊端：当文字内容的长度大于块的宽时，就有内容脱离了块。
* 举例：  
html代码：
```html
<div class="wrap">
    <h2>hi,imooc!</h2>
</div>
```
css代码：
```css
<style>
.wrap h2{
    height:100px;
    line-height:100px;
    background:#999;
}
</style>
```

### 父元素确定的多行文本
* 父元素高度确定的多行文本、图片等的竖直居中的方法有两种：  
1. 使用插入 table  (包括tbody、tr、td)标签，同时设置 vertical-align：middle。  
css 中有一个用于竖直居中的属性 vertical-align，在父元素设置此样式时，会对inline-block类型的子元素都有用。  
举例：  
html代码：
```html
<body>
<table><tbody><tr><td class="wrap">
<div>
    <p>看我是否可以居中。</p>
</div>
</td></tr></tbody></table>
</body>
```
css代码：
```css
table td{height:500px;background:#ccc}
```
这里，td 标签默认情况下就默认设置了 vertical-align 为 middle。并且会给所有带有td标签的多行文字和图片设置垂直居中。因此该css代码也可以写作：```.wrap{height:500px;background:#ccc}```
2. 在 chrome、firefox 及 IE8 以上的浏览器下可以设置块级元素的 display 为 table-cell（设置为表格单元显示），激活 vertical-align 属性，但注意 IE6、7 并不支持这个样式, 兼容性比较差。  
举例：  
html代码：
```html
<div class="container">
    <div>
        <p>看我是否可以居中。</p>
        <p>看我是否可以居中。</p>
        <p>看我是否可以居中。</p>
    </div>
</div>
```
css代码：
```css
<style>
.container{
    height:300px;
    background:#ccc;
    display:table-cell;/*IE8以上及Chrome、Firefox*/
    vertical-align:middle;/*IE8以上及Chrome、Firefox*/
}
</style>
```


## 隐性改变display类型
* 当给元素（不论之前是什么类型元素，display:none 除外）设置以下 2 个句之一：1.```position : absolute ``` 2.```float : left``` 或 ```float:right```时。元素的display显示类型就会自动变为以 display:inline-block（块状元素）的方式显示，当然就可以设置元素的 width 和 height 了，且默认宽度不占满父元素。 