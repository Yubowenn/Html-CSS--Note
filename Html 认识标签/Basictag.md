# Html标签

## 基本标签

### &#60;p&#62; &#60;/p&#62;标签
* 标签会自带一对引号
* 标签用于引用短句


### &#60;blockquote&#62; &#60;/blockquote&#62;标签
* 用于引用长文本
* 其实际效果与&#60;q&#62;标签的区别在于，&#60;blockquote&#62;标签对引用文本有缩紧效果。


### &#60;br /&#62;标签
* 该标签用于换行操作，在html中，在代码中通过回车换行没有用。
* &#60;br /&#62;是一个空标签，类似的还有&#60;hr /&#62;和
* 补充：输入空格的正确方法为：$nbsq;


### &#60;hr /&#62;标签
* 该标签用于画出分割线。


### &#60;address&#62; &#60;/address&#62;标签
* 该标签用于在网页中添加地址信息，默认以斜体的样式显示。


### &#60;code&#62; &#60;/code&#62;标签
* 用于插入单行代码


### &#60;pre&#62; &#60;/pre&#62;标签
* 用于插入多行代码
* 在&#60;pre&#62; &#60;/pre&#62;中的代码字段，空格、回车可以显示




## 列表标签

### ul-li标签
* ul-li标签前后是没有顺序的，默认在每一项前面带原点
------2018/10/9


### ol-li标签
* ol-li标签前后是有顺序的，每一个li前面会加一个序号，默认从1开始


### &#60;div&#62; &#60;/div&#62;标签
* 该标签相当于一个容器，将单独的逻辑部分独立出来。
* 主要使代码在逻辑上更有层次感，预览显示的时候没有效果。
* &#60;div&#62;标签可以命名，
语法为：
```html
<div  id="版块名称">…</div>
```


### table标签
* table标签用来在网页展示表格数据
* 通过table、tbody、tr、th、td来创建表格；
    &#60;table&#62;&#60;/table&#62;作为整个表格的开头和结尾；
    &#60;tobody&#62;&#60;/tobody&#62;，如果表格很长，可以用此标签来分段，可以一部分一部分的显示，不必加载完所有的表格在显示；
    &#60;tr&#62;&#60;/tr&#62;表示表格的行，有多少对就有多少行；
    &#60;td&#62;&#60;/td&#62;表示表哥的列，有多少对说明此行中有多少列
    &#60;th&#62;&#60;/th&#62;表示表格的头部，单元格的头部



### 表格摘要与标题
* 为表格添加摘要相当于给&#60;table&#62;添加summary属性，
语法为：&#60;table summary="表格简介文本"&#62;
* 为表格添加标题使用&#60;caption&#62;标题文本&#60;/caption&#62;





## 链接标签

### &#60;a&#62;标签
* &#60;a&#62;标签可以实现超链接
语法为：&#60;a  href="目标网址"  title="鼠标滑过显示的文本"&#62;链接显示的文本&#60;/a&#62;
其中title的作用是鼠标移动到目标文字是显示的文本，有提示的作用。
* 默认情况下&#60;a&#62;标签是在当前页面打开链接。也可以设置成在新页面打开链接，
举例为：
```html
<a href="目标网址" target="_blank">click here!</a>
```
* &#60;a&#62;标签还可以链接E-mail地址，通过mailto来实现自动填写邮件的功能.  
注意：当mailto后面有多个参数的时候，第一个参数以？分隔，其他的以&分隔
举例为：


### &#60;img&#62;标签
* 为网页插入图片，
语法为：
```html
<img src="图片地址" alt="下载失败时的替换文本" title = "提示文本">
```
* 1、src：标识图像的位置；
2、alt：指定图像的描述性文本，当图像不可见时（下载不成功时），可看到该属性指定的文本；
3、title：提供在图像可见时对图像的描述(鼠标滑过图片时显示的文本)；




## 交互标签

### &#60;form&#62;&#60;/form&#62;标签
* 该标签是成对出现的，用于将用户输入的数据传入服务器。其中的属性决定了传输的方式，其中的输入数据的方式交给其他的标签来实现（即表单的控件全部在&#60;form&#62;&#60;/form&#62;之间）
* action ：浏览者输入的数据被传送到的地方,比如一个PHP页面(save.php)。
* method ： 数据传送的方式（get/post）。  

* &#60;form&#62;&#60;/form&#62;中添加的文字（没有存在子标签中的）会直接显示出来.这可以用来与输入框等组合在一起起到提示输入什么的作用。

### &#60;input... /&#62;标签
#### 输入框
* 输入框分为文本输入框和密码输入框，这可以由&#60;input.../&#62;&#60的属性来决定
* 语法：
```html
<form>
   <input type="text/password" name="名称" value="文本" />
</form>
```
2018/10/11

#### 单选框和复选框
* html中有两种选择框，radio和checkbox，与其他语言是一样的。
* 语法：
```html
<input   type="radio/checkbox"   value="值"    name="名称"   checked="checked"/>
```
1、value：提交数据到服务器的值（后台程序PHP使用）

2、name：为控件命名，以备后台程序 ASP、PHP 使用

3、checked：当设置 checked="checked" 时，该选项被默认选中
* 注意:同一组的单选radio按钮，name 取值一定要一致  
举例：
```html
<input type="radio" name="radioLove" value="喜欢" checked="checked" />喜欢
<input type="radio" name="radioLove" value="不喜欢" />不喜欢
<input type="radio" name="radioLove" value="无所谓" />无所谓
```

#### 提交按钮
* 提交按钮分为：提交和重置
* 提交按钮：  
语法：  
```html
<input type="submit" value="提交">
```
1.type：只有当type值设置为submit时，按钮才有提交作用  
2.value：按钮上显示的文字
* 重置按钮：  
语法：  
```html
<input type="reset" value="重置">
```
1.type：只有当type值设置为reset时，按钮才有重置作用  
2.value：按钮上显示的文字



### &#60;textarea&#62;&#60;/textarea&#62;标签
* textarea中的内容是多行输入，输入的内容由属性来决定。
* cols ：多行输入域的列数。
* rows ：多行输入域的行数。
* 在<textarea></textarea>标签之间可以输入默认值。
举例：
```html
<form  method="post" action="save.php">
        <label>联系我们</label>
        <textarea cols="50" rows="10" >在这里输入内容...</textarea>
</form>
```


### &#60;select&#62;标签
* 该标签作为下拉列表框来使用，内部需要嵌套&#60;option value='提交值'&#62;选项值&#60;/option&#62;  
说明：  
1.value：向服务器提交的值。  
2.选项值：显示的值  
3.selected="selected"属性默认该选项被选中。  
举例：
```html
<select>
      <option value="看书">看书</option>
      <option value="旅游" selected="selected">旅游</option>
      <option value="运动">运动</option>
      <option value="购物">购物</option>
</select>
```
* 在&#60;select&#62;标签中设置属性```multiple="multiple"```就可以实现下拉框多选的操作  
举例：
```html
<select multiple="multiple">
      <option value="看书">看书</option>
      <option value="旅游">旅游</option>
      <option value="运动">运动</option>
      <option value="购物">购物</option>
</select>
```
在实际操作中，windows系统通过ctrl+单击（mac系统通过command+单机）来进行多选。


### &#60;label...&#62;&#60;/label&#62;标签
* label标签不会向用户呈现任何特殊效果，它的作用是为鼠标用户改进了可用性。如果你在 label 标签内点击文本，就会触发此控件。就是说，当用户单击选中该label标签时，浏览器就会自动将焦点转到和标签相关的表单控件上（就自动选中和该label标签相关连的表单控件上）。  
比如说，“北京”对应了一个复选框，如果说要选中这个复选框，当label标签与该复选框关联的情况下。那么可以点击北京两个字这个标签，就能选中对应的复选框，当然也可以直接点击复选框。
* 语法：  
```html
<label for="控件id名称">
```
举例：
```html
<label for="intrest">你对什么运动感兴趣</label>
  <br />
  <label for="jog">慢跑</label>
  <input type="checkbox" name="intrest" id="jog" />
  <br />
  <label for="climb">登山</label>
  <input type="checkbox" name="intrest" id="climb" />
  <br />
  <label for="basketball">篮球</label>
  <input type="checkbox" name="intrest" id="basketball" />
```
注意label的控件id要与关联的表单控件的id相匹配



