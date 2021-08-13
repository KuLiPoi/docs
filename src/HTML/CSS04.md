## CSS布局的机制

### 普通流

- 块状元素， **独占一行**，自上而下排列
  如 div / hr / p / ul / ol / dl / form / table 等等

- 行内元素，**从左至右顺序排列**

  如 span / a / i / em 等等。

### 浮动流

设置了浮动属性的元素会脱离标准流的控制，移动到指定的位置

```css
/* 最简单的浮动 */
div {
		width: 20px;
		height: 30px;
		float: left;
		/* left / right / none */
}
```

- 浮动元素与父盒子的关系

  1. 子盒子浮动参照父盒子对齐
  2. 子盒子不会和父盒子的边框重叠，也不会超过父盒子的padding

- 父盒子包含多个元素

  如果父盒子中有多个子盒子，则建议其他子盒子**也应该浮动**，避免产生问题。

  ![07009156-8DE0-4B68-9D67-FDFA729F3E49](https://cdn.kulipoi.com/img/20210812213131.png)

  1. 如果上一个盒子浮动，下面的盒子也浮动
  2. 如果上一个盒子是标准流，下面的盒子浮动，则会显示在标准流下方

### 消除浮动

消除浮动主要为了解决父级元素元素因为子级浮动引起内部高度为0的问题，消除浮动之后，父级就会根据子盒子自动检测高度，父级拥有了高度，就不会影响下面的标准流了。

消除浮动之前

![9A0AC322-9C80-4599-B6F1-EB28290446F1](https://cdn.kulipoi.com/img/20210813101309.png)

消除浮动之后

![5877A4FA-240D-485F-A9C1-04498B31C973](https://cdn.kulipoi.com/img/20210813101125.png)

```css
div {
		clear: both;
		/* left / right / both 清除左右两侧浮动 */
}
```

- 额外标签法

  ```css
  .clear {
  		clear: both;
  }
  
  <div class="one"> </div>
  <div class="two"> </div>
  /* 额外的空标签 */
  <div class="clear"> </div>
  ```

- Overflow

  ```css
  .father {
  		overflow: hidden;
  }
  ```

- After伪元素

  是额外标签法的升级版，在结构里不可见

  ```css
  .clearfix:after {
  		content: "";
  		display: block;
  		height: 0;
  		visibility: hidden;
  		clear: both;
  }
  .clearfix {
  		*zoom: 1; /* IE6 IE7 不支持下的 解决方法 */
  }
  
  <div class="father clearfix"></div>
  ```

- 双伪元素消除浮动

  ```css
  .clearfix:before,
  .clearfix:after {
  		content: "";
  		display: table;
  }
  .clearfix:after {
  		clear: both;
  }
  .clearfix {
  		*zoom: 1;
  }
  
  <div class="father clearfix"></div>  
  ```