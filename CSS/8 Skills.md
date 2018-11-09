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
