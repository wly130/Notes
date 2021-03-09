## Sass 预处理器

[TOC]

- **可以减少 CSS 重复代码的编写**

#### Sass 变量

- **Sass** 使用 **$** 符号来标识变量

```scss
//定义变量
$变量名: value

//使用变量
div {
    width: $变量名;
}
```

#### Sass 作用域

- **默认作用域为==局部==，只能在当前的层级上有效果**

- **可以使用 `!global` 关键词来设置为全局变量**

  - **所有的全局变量我们一般定义在同一个文件**

  ```scss
  div {
  	$变量名: value !global;  // 全局作用域
  }
  ```

#### Sass 嵌套

> **选择器嵌套**

```scss
nav {
	ul {}
	li {}
	a {}
}
//等于
nav ul {}
nav li {}
nav a {}
```

> **属性嵌套**

```scss
font: {
	family: Helvetica, sans-serif;
	size: 18px;
	weight: bold;
}
//等于
font-family: Helvetica, sans-serif;
font-size: 18px;
font-weight: bold;
```

#### Sass 导入文件

```scss
@import FileName;
```

- **不需要指定文件后缀，Sass 会自动添加后缀 `.scss`不需要指定文件后缀**

> **在文件名的开头添加下划线， 则Sass 不会将其编译到 CSS 文件中**
>
> **在导入语句中不需要添加下划线**

#### @mixin 混入

- **`@mixin` 指令允许我们定义一个可以在整个样式表中==重复使用==的样式**

  ```scss
  @mixin 样式名 {
  	color: red;
    	font-size: 25px;
    	font-weight: bold;
    	border: 1px solid blue;
  }
  ```

- **混入可以接收参数**

  ```scss
  @mixin 样式名($参数1, $参数2){
  	border: $参数1 $参数2;
  }
  
  //定义默认值
  @mixin 样式名($参数1:vlaue1, $参数2:value2){
  	border: $参数1 $参数2;
  }
  
  //可变参数
  @mixin 样式名($参数1...){
  	border: $参数1 $参数2;
  }
  ```

#### @include 引入混入

- **`@include`  指令可以将 `mixin` 引入到文档中**

  ```scss
  div {
      @include 样式名;
  }
  
  //传参
  div {
      @include 样式名(参数);
  }
  ```

#### @extend 继承

- **Sass 一个选择器的样式从另一选择器继承**

> **`.div3` 继承了 `.div1` 和 `.div2` 的样式**

```scss
.div1 {
     border: none;
}

.div2 {
     padding: 15px 30px;
}
 
.div3 {
    @extend  .div1;
    @extend  .div2;
}
```

