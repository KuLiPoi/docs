## HTML 骨架

html的基本语法

```html
<!-- 告知浏览器文档使用的HTML规范 -->
<!DOCTYPE html>
<!-- HTML 根标签&告知浏览器文档使用的语言-->
<html lang="zh-CN">
<head>
    <!-- 字符编码格式 -->
    <!-- 
        GB2312 简体中文
        BIG5   繁体中文
        GBK    简繁体均有 兼容GB2312
        UTF-8  全世界通用
     -->
    <meta charset="UTF-8">
    <!-- Title 设置网站名称 -->
    <title>Document</title>
</head>
<body>
    <!-- 元素包含文档的所有内容 -->
</body>
</html>
```

## HTML 标签

- 双标签：分为开始标签和结束标签 如 ` <tilte> </title>`
- 单标签：没有结束标签 `<br />`

### 标签关系

- 嵌套关系

  ```html
  <head>
  		<title></title>
  </head>	
  ```

- 并列关系

  ```html
  <head></head>
  <body></body>
  ```

### 标签语义化

在合适的地方放合适的标签，先确定语义，再选合适的CSS，让代码在没有CSS的情况下依旧有良好的可读性。

### 常用标签

#### 排版标签

- 标题标签：根据标题的重要性依次递减

  ```html
      <h1>一级标签</h1>
      <h2>二级标签</h2>
      <h3>...</h3>
  ```

- 段落标签：把文档分成若干段落

  ```html
  <p>我是个p</p>
  <p>我也是个p</p>
  ```

- 水平线标签：横线 `<hr />`

- 换行标签：`<br />`

- Div ：`<div> 布局用的 一行只有一个div </div>`

- Span：`<span> 布局用的 一行可以显示多个 </span>`

#### 文本格式化标签

- 加粗：`<strong></strong> <b></b>`
- 斜体：`<em></em> <i></i>`
- 删除线：`<del></del> <s></s>`
- 下划线：`<ins></ins> <u></u>`

### 属性标签

#### 图片标签

```html
	 <!--
        src     文件路径
        alt     替换文本
        title   提示文本
        width   宽度
        height  高度
        border  图像的边框宽度
    -->
    <img src="https://cdn.kulipoi.com/img/20210806154155.png" alt="别当欧尼酱了" title="欧尼酱" width="200" border="1" />
```

#### 链接标签

```html
    <!--
        herf    要访问的URL地址
        target  打开方式 self：当前窗口打开/blank：新窗口打开
    -->
    <a href="https://docs.kulipoi.com" target="blank">文档库</a>
```

### 注释标签

```
    <!--
        这是注释
    -->
```