# CSS排版

## 文字排版
### 字体(font-family)
* 一般网页使用微软雅黑：
```html
body{font-family:"Microsoft Yahei";}
```

### 字号(font-size)、颜色(color)
* 语法：
```html
body{font-size:12px;color:#666}
```

### 粗体(font-weight)
* 语法：
```html
p span{font-weight:bold;}
```

### 斜体(font-style)
* 语法：
```html
p a{font-style:italic;}

<p>三年级时，我还是一个<a>胆小如鼠</a>的小女孩。</p>
```

### 下划线、删除线（text-decoration）
* 下划线(underline)语法：
```html
p a{text-decoration:underline;}

<p>三年级时，我还是一个<a>胆小如鼠</a>的小女孩。</p>
```
* 删除线(line-through)语法：
```html
.oldPrice{text-decoration:line-through;}
```


## 段落排版
### 缩进（text-indent）
* 语法：
```html
p{text-indent:2em;}
<p>1922年的春天，一个想要成名名叫尼克?卡拉威（托比?马奎尔Tobey Maguire 饰）的作家，离开了美国中西部，来到了纽约。那是一个道德感渐失，爵士乐流行，走私为王，股票飞涨的时代。为了追寻他的美国梦，他搬入纽约附近一海湾居住。</p>    
<p>菲茨杰拉德，二十世纪美国文学巨擘之一，兼具作家和编剧双重身份。他以诗人的敏感和戏剧家的想象为"爵士乐时代"吟唱华丽挽歌，其诗人和梦想家的气质亦为那个奢靡年代的不二注解。</p>
```
注意：2em的意思就是文字的2倍大小。也就是首行缩进两个字符。上述事例中，有两段&#60;p&#62;标记的段落。样式设置的结果是，每一段都首行缩进

### 行间距（行高line-height）
* 语法：
```html
p{line-height:1.5em;}
```

### 中文字间距、字母间距
* 文字和字母间距(letter-spacing)  
语法：
```html
h1{
    letter-spacing:50px;
}
...
<h1>了不起的盖茨比</h1>
```
* 单词间距(word-spacing)  
语法：
```html
h1{
    word-spacing:50px;
}
...
<h1>welcome to ccnu!</h1>
```

### 对齐（text-align）
* 居中：
```html
h1{
    text-align:center;
}
```
也可以设置成居左和居右