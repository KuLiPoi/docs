##  CSS

### 行内样式表

通过标签的style属性来设置元素的样式，书写方便，权重最高

```css
<h1 style="color: gray; font-size: 18px; ">卧槽</h1>
```

### 内嵌样式表

将css代码集中写到html代码的头部标签中，并用style标签定义

```css
    <style>
        h1 {
            color: green;
            font-size: 20;
        }
        div {
            color: hotpink;
        }
    </style>
```

### 外部样式表

将所有的样式放在一个或多个以css的扩展名的外部样式表文件，通过link标签将外部文件链接到HTML文档中，实现结构样式分离

```html
<link rel="stylesheet" href="/css/styte.css">
```

## CSS选择器

### 基础选择器

- 标签选择器

  元素选择器，用html标签名作为选择器，如 `div span `等

- 类选择器：定义类名，并调用，可以重复使用

  ```html
      <style>
     			// 多类名
        	.font10px {
            	font-size: 10px;
        	}
          .main {
              color: indianred;
          }
      </style>
      
      <div class="main font10px">
      		啦啊啦啦	
      </div>
  ```

- ID选择器：使用#进行调用，有唯一性，不能重复调用

- 通配符选择器：使用*选择所有标签，匹配所有元素，降低页面相应速度，不推荐随便使用。

### 复合选择器

- 后代选择器

  ```css
      .nav a {
            color:darkcyan;
            font-size: 13;
      }    
      <div class="nav">
          <a href="#">Link</a><br>
          <a href="#">Link</a><br>
          <a href="#">Link</a><br>
      </div>
  ```

- 子元素选择器：只选择最近的

  ```css
  div > strong {
  		color: blue;
  }
  ```

- 交集选择器：满足条件 是p且class有red

  ```css
      p.red {
           color: darksalmon;
    	}   
     
     	<div class="red">div red</div>
      <div class="red">div red</div>
      <div class="red">div red</div>
  
      <p class="red">red</p>
      <p class="red">red</p>
      <p class="red">red</p>
  
      <p>Normal</p>
      <p>Normal</p>
      <p>Normal</p>
  ```

- 并集选择器

  ```css
      p,span {
           color: darksalmon;
    	}   
  ```

- 伪类选择器

  ```css
  a:link {
  		color: gray;
  }
  a:visted {
  		color: orange;
  }
  a:hover {
  		color: red;
  }
  a:active {
  		color: blue;
  }
  ```

  

## CSS 文本样式

### font-size (文字大小)

Tips：谷歌浏览器的默认文字大小为16px

```css
p {
		font-size:16px;
}
```

### font-family (字体)

字体之间由逗号隔开，英文字体写在中文字体之前，英文字体不需要引号。

```css
.title {
		font-family: Arial, "Micorsoft YaHei", "宋体";
}
```

### font-weight (字体粗细)

```css
.title {
		font-weight:bold;
		/* bold / normal bolder number(指定多粗) */
}
```

### font-style (字体风格)

一般不用，多用<i>

```css
.title {
		font-style: normal;
		font-style: italic;
}
```

## css外观属性

### text-align (对齐方式)

```css
.tac {
		text-align: center;
}
```

### line-height (行间距)

```css
p {
		line-height: 24px;
}
```

### text-indent (首行缩进)

1em为一个汉字的距离

```
p {
		text-indent: 2em;
}
```

### text-decoration (文本装饰)

```
/* none 空 / underline 下划线/ line-through 删除线 / overline 上划线 */
.title {
		text-decoration: none;
}
```