# HTML资源与工具

* html在线验证：<http://www.freeformatter.com/html-validator.html>(该网站上还有很多别的工具)

* html在线格式化代码：<http://www.cleancss.com/html-beautify/>

* W3School上的HTML基础教程：<http://www.w3school.com.cn/html/index.asp>

* Html5新特性（了解即可）：<http://www.w3school.com.cn/html5/index.asp>

* CodeForDream上提供的HTML课<http://www.codefordream.com/courses/html_basic/sections>

* 博客写在简书上: <http://jianshu.com](http://jianshu.com/>

  

# HTML学习内容

1. div, span, ul, ol

   * div：定义文档中的节或区域（块级）

     * `<div>`可定义文档中的分区或节（division/section）
     * `<div>`标签可以把文档分割为独立的、不同的部分。它可以用作严格的组织工具，并且不使用任何格式与其关联。

   * span：定义文档中的行内的小块或区域

     * `<span>` 标签被用来组合文档中的行内元素，以便通过样式来格式化它们。

   * ul：无序列表

     * 列表项目使用粗体圆点（典型的小黑圆圈）进行标记。
     * 无序列表始于 `<ul>` 标签。每个列表项始于 `<li>`。

   * ol：有序列表

     * 列表项目使用数字进行标记。
     * 有序列表始于` <ol>` 标签。每个列表项始于 `<li> `标签。

     

2. a, img

   * a：定义超链接

     * `<a>` 标签定义超链接，用于从一张页面链接到另一张页面。

     * `<a>` 元素最重要的属性是 href 属性，它指示链接的目标。

       ```
       <a href="http://www.w3school.com.cn">W3School</a>
       ```

   * img：向网页中嵌入一幅图像

     * 从技术上讲，`<img> `标签并不会在网页中插入图像，而是从网页上链接图像。`<img> `标签创建的是被引用图像的占位空间。

     * `<img>`标签有两个必需的属性：src属性和alt属性

       - src属性：规定显示图像的 URL
       - alt属性：规定图像的替代文本

       ```
       <img src="/i/eg_tulip.jpg"  alt="上海鲜花港 - 郁金香" />
       ```

   

3. form, button, 各种input table

   * HTML 表单用于收集用户输入，`<form>` 元素定义 HTML 表单

   * HTML表单包含表单元素

   * 表单元素指的是不同类型的 input 元素、复选框、单选按钮、提交按钮等等。

   * input元素

     | 类型     | 描述                                                 |
     | -------- | ---------------------------------------------------- |
     | text     | 定义常规文本输入                                     |
     | radio    | 定义单选按钮输入（选择多个选择之一）                 |
     | checkbox | 复选框允许用户在有限数量的选项中选择零个或多个选项。 |
     | submit   | 定义提交按钮（提交表单）                             |

   * `<button>`元素定义可点击的按钮

     ```
     <input type="button" onclick="alert('Hello World!')" value="Click Me!">
     ```

     

   * input text

     ```
     <form action="action_page.php">
     First name:<br>
     <input type="text" name="firstname" value="Mickey">
     <br>
     Last name:<br>
     <input type="text" name="lastname" value="Mouse">
     <br><br>
     <input type="submit" value="Submit">
     </form> 
     ```

   * input radio

     ```
     <form>
     <input type="radio" name="sex" value="male" checked>Male
     <br>
     <input type="radio" name="sex" value="female">Female
     </form>
     ```

   * input checkbox

     ```
     <form>
     <input type="checkbox" name="vehicle" value="Bike">I have a bike
     <br>
     <input type="checkbox" name="vehicle" value="Car">I have a car 
     </form> 
     ```

     

   * 

4. h1, h2, h3 pre

5. table

   * 表格由` <table> `标签来定义。

   * `<caption>`定义表格标题。

   * `<th>`定义表格的表头

   * 每个表格均有若干行（由 `<tr>` 标签定义）

   * 每行被分割为若干单元格（由 `<td> `标签定义）

     

6. h1, h2, h3

   * HTML 标题（Heading）是通过` <h1>` - `<h6>` 等标签进行定义的。`<h1>` 定义最大的标题。`<h6> `定义最小的标题。`h1`, `h2`, `h3`分别表示一号标题，二号标题，三号标题。

   * 请将 HTML heading 标签只用于标题。不要仅仅是为了产生粗体或大号的文本而使用标题。

     ```
     <h1>This is a heading</h1>
     <h2>This is a heading</h2>
     <h3>This is a heading</h3>
     ```

     

7. pre

   * pre：定义预格式化文本

     * 被包围在 `<pre> `元素中的文本通常会保留空格和换行符。文本也会呈现为等宽字体。

     * `<pre>`标签的一个常见应用就是用来表示计算机的源代码。

       ```
       <pre>
       for i = 1 to 10
            print i
       next i
       </pre>
       ```

       

8. em, i

   * em：定义着重文字

     ```
     <em>This text is emphasized</em>
     ```

   * i：定义斜体字

     ```
     <i>This text is italic</i>
     ```

   

9. ul与ol之间的区别

   * ul示例

     ```
     <ul>
     <li>Coffee</li>
     <li>Milk</li>
     </ul>
     ```

   * ol示例

     ```
     <ol>
     <li>Coffee</li>
     <li>Milk</li>
     </ol>
     ```

     

10. div与span之间的区别

    * div示例

      ```
      <html>
      <head>
      <style>
      .cities {
          background-color:black;
          color:white;
          margin:20px;
          padding:20px;
      } 
      </style>
      </head>
      
      <body>
      
      <div class="cities">
      <h2>London</h2>
      <p>
      London is the capital city of England. 
      It is the most populous city in the United Kingdom, 
      with a metropolitan area of over 13 million inhabitants.
      </p>
      </div> 
      
      </body>
      </html>
      ```

    * span示例

      ```
      <html>
      <head>
      <style>
      span.red {
          color:red;
      }
      </style>
      </head>
      
      <body>
      
      <h1>我的<span class="red">重要的</span>标题</h1>
      
      </body>
      </html>
      ```