## HTML 表格

### 表格属性

```html
    <!--
        border          边框 
        width           宽度
        height          高度
        align           水平对其方式 left right center

        // html5 中不再支持
        cellspacing     单元格间距 外边距
        cellspadding    文本距离单元格边框的距离
    -->
    
    <table width="300" height="150" align="left" cellspadding="20" border="1" cellspacing=“0”>
        <tr><td>Name</td>
            <td>Age</td>
            <td>Gender</td>
        </tr>
        <tr><td>Tony</td> 
            <td>12</td> 
            <td>boy</td>
        </tr>
        <tr><td>MM</td> 
            <td>122</td> 
            <td>？</td>
        </tr>
    </table>
```

### 表头属性

```html
        <!-- 自动加粗且居中 -->
        <tr><th>Name</th>
            <th>Age</th>
            <th>Gender</th>
        </tr>
```

### 表格标题标签

```html
<table>
		<caption>Table Title </caption>
</table>
```

### 表格的合并

```html
    <table width="300" height="150" align="left" border="1">
        <caption>合并</caption>
        <tr>
            <th>1</th>
            <th>2</th>
            <th>3</th>
        </tr>
        <tr>
            <td>31</td> 
            <td>21</td> 
            <!-- 跨行合并 -->
            <td rowspan="2">21</td>
        </tr>
        <tr>
            <td>33</td> 
            <td>22</td> 
        </tr>
        <tr>
            <!-- 跨列合并 -->
            <td colspan="2">22</td> 
            <td>vv</td>
        </tr>
    </table>
```

## HTML 列表

### 无序列表

`<ul>`标签只能包含`<li>`，放入其他标签是不被允许的

```html
<ul>
   <li></li>
</ul>
```

### 有序列表

```html
<ol>
		<li></li>
</ol>
```

### 自定义列表

```html
<dl>
		<dt></dt>
  	<!-- dt 和 dd 是并列关系 -->
 		<dd></dd>
</dl>
```

## HTML 表单

一个完整的表单一般是由，表单控件，提示信息，和表单域三个部分组成

### 表单标签

- Input 标签

  ```html
      <!--
          type     text/password/radio/checkbox/buttom/submit/reset/image/file
          name     控件名称
          value    控件默认文本值
          size     控件宽度
          checked  默认选中
          maxlenth 允许的最多字符数
      -->
      Username：<input type="text" value="请输入用户名" name="username" maxlength="8"> <br>
      Password：<input type="password" name="password"> <br>
      Gender：<input type="radio" name="gender" checked> 男 <input type="radio" name="gender"> 女 <br>
      SavePWD：<input type="checkbox" checked> 保存密码  <br>
      <input type="button" value="需要value值的普通按钮"> <br>
      <input type="submit" value="提交「默认为提交"> <br>
      <input type="reset" value="重置表单"> <br>
      <input type="image" src="https://cdn.kulipoi.com/img/20210806155424.png"> <br>
      Upload File: <input type="file" name="flie"> <br>
  ```

- label 标签

  ```html
      <Label>Username：<input type="text" value="请输入用户名"></label> <br>
      <Label for="pwd">Password：</Label><input type="password" name="password" id="pwd"> <br>
  ```

- testarea 标签

  ```html
  Comment：<textarea></textarea>
  ```

- select 下拉标签

  ```html
      <select>
          <option>天津</option>
          <option>上海</option>
          <option>北京</option>
      </select>
  ```

### 表单域

```html
    <form action="/check" method="GET" name="POST">
        ID : <input type="text" name="id">
        <input type="submit">
    </form>
```

