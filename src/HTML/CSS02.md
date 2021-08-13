## DISPLAY 显示模式

### 块级元素 (Block-level)

1. 独占一行
2. 宽度高度外边距内边距可控
3. 默认宽度是父级宽度的100%
4. 是一个容器，内部可以放行内元素或者块级元素
5. **P标签内不要放块元素**

### 行内元素 (Inline-level)

1. 相邻行内元素在一行，一行可以显示多个
2. 高度，宽度的直接设置是无效的
3. 默认宽度就是他本身内容的宽度
4.  行内元素只能容纳文本或者其他行内元素

### 行内块元素 (Inline-block)

1. 和相邻内元素在一行上，但是之间会有空白缝隙，一行可以显示多个行内块
2. 默认宽度就是他本身内容的宽度
3. 宽度，行高，外边距，内边距都可控制

### 显示模式的转换

- 块级转行内元素`display:inline;`
- 把行内元素转换为块级 `display: block;`
- 转换为行内块元素 `display: inline-block;`

## BackGround 背景

### Background-color (背景颜色)

```css
.bg {
		width: 1920px;
		height: 1080px;
		background-color: red;
}
```

### Background-image (背景图片)

```css
.bg {
		width: 1920px;
		height: 1080px;
		background-image: url(https://cdn.kulipoi.com/img/20210810210401.jpg);
}
```

### Background-repeat (背景平铺)

```css
.bg {
		width: 1920px;
		height: 1080px;
		background-image: url(https://cdn.kulipoi.com/img/20210810210401.jpg);
		background-repeat: no-repeat;
		/* repeat-x 横向平铺 / repeat 平铺 / repeat-y 竖着平铺 / no- repeat 不平铺 */
}
```

### Background-position (背景位置)

* 必须指定 `background-image`属性
* 可以使用精准坐标或者方位名词
* 如果仅指定一个方位名词，则另一个默认居中
* 如果仅指定一个x坐标，则另一个默认为居中的y坐标

```css
.bg {
		width: 1920px;
		height: 1080px;
		background-image: url(https://cdn.kulipoi.com/img/20210810210401.jpg);
		background-positon: center; 
		/* top / bottom / right / left / x:x / y:y */
}
```

### Background-attachment (背景附着)

```css
.bg {
		width: 1920px;
		height: 1080px;
		background-image: url(https://cdn.kulipoi.com/img/20210810210401.jpg);
		background-attachment: fixed;
		/* fixed 固定 / scroll 滚动 */
}
```

### Background RGBA (背景透明度)

```css
.bg {
		width: 1920px;
		height: 1080px;
		background: rgba(0, 0, 0, 0.3);
}
```

