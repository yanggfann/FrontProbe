# JavaScript简介

*  JavaScript是脚本语言。

  * JavaScript 是一种轻量级的编程语言。
  * JavaScript 是可插入 HTML 页面的编程代码。
  * JavaScript 插入 HTML 页面后，可由所有的现代浏览器执行。

* JavaScript：直接写入HTML输出流

  ```
  document.write("<h1>这是一个标题</h1>");
  ```

  * 只能在 HTML 输出中使用 document.write。如果您在文档加载后使用该方法，会覆盖整个文档。

* JavaScript：对事件的反应

  ```
  <button type="button" onclick="alert('欢迎!')">点我!</button>
  ```

  * alert() 函数对于代码测试非常方便。
  * 在点击 点我！ 按钮时，调用onclick的函数。

* JavaScript：改变HTML内容

  ```
  x=document.getElementById("demo");  //查找元素
  x.innerHTML="Hello JavaScript";    //改变内容
  ```

  **document.getElementById**方法是 HTML DOM(**D**ocument **O**bject **M**odel) 中定义的

* JavaScript：改变HTML样式

  ```
  x=document.getElementById("demo")  //找到元素 
  x.style.color="#ff0000";           //改变样式
  ```

# JavaScript用法

* HTML 中的脚本必须位于 `<script>` 与 `</script>` 标签之间；脚本可被放置在 HTML 页面的 `<body>` 和 `<head> `部分中。

* **`<script>`**标签

  * 如需在 HTML 页面中插入 JavaScript，请使用 `<script> `标签。
  * `<script>` 和`</script>`会告诉 JavaScript 在何处开始和结束。
  * `<script>` 和`</script>`之间的代码行包含了JavaScript。

* 外部的JavaScript

  * 也可以把脚本保存到外部文件中。外部文件通常包含被多个网页使用的代码。

  * 外部 JavaScript 文件的文件扩展名是 .js。

  * 如需使用外部文件，请在 <script> 标签的 "src" 属性中设置该 .js 文件

    ```
    <!--HTML5的DOCTYPE声明-->
    <!DOCTYPE html>
    <html>
    <head>
    <script src="myScript.js"></script>
    </head>
    </html>
    ```

    * `<!DOCTYPE>` 声明必须是 HTML 文档的第一行，位于` <html> `标签之前。
    * `<!DOCTYPE> `声明不是 HTML 标签；它是指示 web 浏览器关于页面使用哪个 HTML 版本进行编写的指令。

# JavaScript输出

 JavaScript没有任何打印或者输出的函数。

* JavaScript显示数据
  - 使用 **window.alert()** 弹出警告框。
  - 使用 **document.write()** 方法将内容写到 HTML 文档中。
  - 使用 **innerHTML** 写入到 HTML 元素。
  - 使用 **console.log()** 写入到浏览器的控制台。

# JavaScript事件

常见的HTML事件

| 事件        | 描述                         |
| ----------- | ---------------------------- |
| onchange    | HTML 元素改变                |
| onclick     | 用户点击 HTML 元素           |
| onmouseover | 用户在一个HTML元素上移动鼠标 |
| onmouseout  | 用户从一个HTML元素上移开鼠标 |
| onkeydown   | 用户按下键盘按键             |
| onload      | 浏览器已完成页面的加载       |

# JavaScript字符串

**字符串属性**

| 属性        | 描述                       |
| ----------- | -------------------------- |
| constructor | 返回创建字符串属性的函数   |
| length      | 返回字符串的长度           |
| prototype   | 允许您向对象添加属性和方法 |

**字符串方法**

| 方法                | 描述                                                         |
| ------------------- | ------------------------------------------------------------ |
| charAt()            | 返回指定索引位置的字符                                       |
| charCodeAt()        | 返回指定索引位置字符的 Unicode 值                            |
| concat()            | 连接两个或多个字符串，返回连接后的字符串                     |
| fromCharCode()      | 将 Unicode 转换为字符串                                      |
| indexOf()           | 返回字符串中检索指定字符第一次出现的位置                     |
| lastIndexOf()       | 返回字符串中检索指定字符最后一次出现的位置                   |
| localeCompare()     | 用本地特定的顺序来比较两个字符串                             |
| match()             | 找到一个或多个正则表达式的匹配                               |
| replace()           | 替换与正则表达式匹配的子串                                   |
| search()            | 检索与正则表达式相匹配的值                                   |
| slice()             | 提取字符串的片断，并在新的字符串中返回被提取的部分           |
| split()             | 把字符串分割为子字符串数组                                   |
| substr()            | 从起始索引号提取字符串中指定数目的字符                       |
| substring()         | 提取字符串中两个指定的索引号之间的字符                       |
| toLocaleLowerCase() | 根据主机的语言环境把字符串转换为小写，只有几种语言（如土耳其语）具有地方特有的大小写映射 |
| toLocaleUpperCase() | 根据主机的语言环境把字符串转换为大写，只有几种语言（如土耳其语）具有地方特有的大小写映射 |
| toLowerCase()       | 把字符串转换为小写                                           |
| toString()          | 返回字符串对象值                                             |
| toUpperCase()       | 把字符串转换为大写                                           |
| trim()              | 移除字符串首尾空白                                           |
| valueOf()           | 返回某个字符串对象的原始值                                   |

# JavaScript类型转换

**JavaScript数据类型**

5种数据类型：

- string
- number
- boolean
- object
- function

3种对象类型：

- Object
- Date
- Array

2种不包含任何值的数据类型：

- null
- undefined

**将数字转换为字符串**

```
String(123)
(123).toString()
```

| 方法            | 描述                                                 |
| --------------- | ---------------------------------------------------- |
| toExponential() | 把对象的值转换为指数计数法。                         |
| toFixed()       | 把数字转换为字符串，结果的小数点后有指定位数的数字。 |
| toPrecision()   | 把数字格式化为指定的长度。                           |

**将字符串转换为数字**

全局方法 **Number()** 可以将字符串转换为数字。

字符串包含数字(如 "3.14") 转换为数字 (如 3.14).

空字符串转换为 0。

其他的字符串会转换为 NaN (不是个数字)。

| 方法         | 描述                               |
| ------------ | ---------------------------------- |
| parseFloat() | 解析一个字符串，并返回一个浮点数。 |
| parseInt()   | 解析一个字符串，并返回一个整数。   |

# JavaScript var let const

*  var 关键字声明的变量不具备块级作用域的特性，它在 {} 外依然能被访问到。
* let 声明的变量只在 let 命令所在的代码块内有效。
* const 声明一个只读的常量，一旦声明，常量的值就不能改变。