# CSS样式设置小技巧

## 水平居中设置
### 行内元素
* 水平居中是通过给父元素设置 text-align:center 来实现的
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