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