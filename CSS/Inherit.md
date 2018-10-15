# CSS继承、层叠与特殊性

## 继承
* 也就是样式的继承，在选择器中提到过子标签，可以通过子选择器来对子标签设置样式。  
有些样式当只对父标签设置时，子标签会默认对父标签样式的继承。  
举例：
```html
p{color:red;}

<p>三年级时，我还是一个<span>胆小如鼠</span>的小女孩。</p>
```
这样，p标签内的子标签span内的胆小如鼠也会变成红色（其实想起来很正常）  
再比如：
```html
p{border:1px solid red;}

<p>三年级时，我还是一个<span>胆小如鼠</span>的小女孩。</p>
```
将样式换成了方框border，这个时候显示的结果就只有在整段p标签的元素有方框，而不会给span标签内的胆小如鼠额外添加一个标签（其实想起来也很正常）
* 也就是说，不同的样式的继承性不同。这里介绍了两种color和border，下面也会陆续更新，to be continue