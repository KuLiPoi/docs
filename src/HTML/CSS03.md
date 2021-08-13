## CSS 特性

### CSS的层叠性

层叠性是多种css样式的叠加，css样式遵循**就近原则**

```css
/* 浏览器会选择 下面的 遵循就近原则 不冲突的不会层叠 */
div {
		color: red;
		font-size: 20px;
}
div {
		color: blue;
}
```

### CSS的继承性

子标签会继承父类标签的属性 (文字属性，字体属性，行属性等可以继承)

```Css
/* P标签内的文字为红色 */
div {
		color: red;
}

<div>
		<p> CSS的继承性 </p>
</div>
```

### CSS的优先级

继承 / 通配符选择器 < 标签选择器 < 类选择器 < ID选择器 < 行内样式表 < !important

```css
div {
		color: red !important;
}
```

## Box model (盒子模型)

盒子的组成：content / border / padding / margin

### Border (盒子边框)

```css
div {
		/* width 宽度 / style ：none 无｜solid 实线的｜dashed 虚线的｜dotted 电线的 / color 颜色*/
  	/* 边框可以单独指定样式 如 border-top */
		border-width: 1px;
		border-sytle: solid;
		border-color: black;
  	border-top: 2px solid red;
}
```

### Padding  (内边距)

增加了padding之后，盒子模型大小会变大

```css
div {
		padding-left: 10px;
		padding-right: 10px;
		padding-top: 10px;
		padding-bottom: 10px;
  	padding: 10px; /* 四个边的内边距 均为10px */
  	padding: 10px 20px; /* 上下为10px 左右为20px */
  	padding: 10px 20px 30px; /* 上为10px 左右是20px 下为30 */
  	padding: 10px 20px 30px 40px; /* 上 右 下 左 */
}
```

### Margin (外边距)

```css
div {
		margin-left: 10px;
		margin-right: 20px;
		....
		/* 和padding一样 不多做举例了 */
}
```

### Margin-auto (水平居中)

```css
div {
		width: 500px;
  	margin: auto;
  	/* margin-left: auto margin-right: auto; / margin: 0 auto; */
}
```

### Margin的特性 (一)

通俗的讲，你左边上面的盒子写了一个 bottom 20px ，下面写一了一个 top 10px 结果就是，浏览器只识别了20px，解决的办法就是，将一个盒子的边框直接设置为30px即可

![image-20210812193830148](https://cdn.kulipoi.com/img/20210812193830.png)

### Margin的特性 （二）

如图所示，我们再给purple盒子添加 `margin-top: 10px`之后，包含着purple盒子的orange盒子的margin属性也发生了变化，即发生了垂直外边距合并。

**解决方法**

1. 给外部盒子添加`border-top属性`
2. 给外部盒子添加`padding-top`属性
3. 给外部盒子添加`overflow:hidden`属性

![7F3968A8-0338-4586-A0BE-131AF82DEFB8](https://cdn.kulipoi.com/img/20210812195055.png)

### 盒子模型的稳定性

width > padding > margin

* margin 会造成外边距合并，而且和IE的兼容性不好
* padding 会影响到盒子的大小，需要进行加减计算
* width 基本没有问题 推荐使用