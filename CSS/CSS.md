# CSS的资源与工具

* CSS在线验证：<http://codebeautify.org/cssvalidate>(该网站上还有很多别的工具)
* 学习CSS布局：<http://learnlayout.com/>
* CSS基础教程：<http://www.w3school.com.cn/css/index.asp>
* CSS3新特性(了解即可)：<http://www.w3school.com.cn/css3/>
* CodeForDream上提供的CSS课程：<http://www.codefordream.com/courses/css_basic/sections>

# CSS学习内容

1. CSS的作用

   * HTML：超文本标记语言(**H**yper **T**ext **M**arkup **L**anguage)
   * CSS：层叠样式表(**C**ascading **S**tyle **S**heets)

2. 引用CSS文件到HTML网页里的[方法](http://www.divcss5.com/rumen/r56.shtml)

   * 直接在div中使用CSS样式制作div+CSS网页
   * HTML中使用style自带式
   * 使用@import引用外部CSS文件
   * **推荐**使用link引用外部CSS文件

3. 基本的CSS功能：设置宽度、文字大小、颜色、底色等

   * 设置网页边框底色

     ```
     CSS代码：
     body{
     	border-style: solid;
     	border-color: red;
     }
     ```

   * 按钮居中

     ```
     CSS代码：
     .center{
         text-align: center;
     }
     HTML代码：
     <div class = "center"><button type = "button" onclick = "alert('成绩：100分')"><span id = "white">计算分数</span></button></div>
     ```

   * 

4. 基本的CSS选择器：#main, .error

   * 类选择器以点号显示

     * 文本居中

     ```
     CSS代码：
     .center{
         text-align: center;
     }
     HTML代码：
     <h1 class = "center">标题</h1>
     ```

   * id选择器以`#`来定义

     * 设置文字颜色

     ```
     CSS文件代码：
     #red{
         color: red
     }
     HTML文件代码：
     <span id = "red">我是红色</span>
     ```

   * 派生选择器

     ```
     h2 strong {
     	color: blue;
     }
     ```

   * 属性选择器

     ```
     input[type="text"]
     {
       width:150px;
       display:block;
       margin-bottom:10px;
       background-color:yellow;
       font-family: Verdana, Arial;
     }
     ```

   * 

5. CSS选择器#main > .images与#main .images与#main,.images的区别

   * #main > .images

     * `>`为子结合符

     * 选择作为main元素子元素的所有images

   * #main .images

     * main元素有一个包含images的class属性

   * #main,.images

     * 逗号分隔，表示将任意多个选择器分组在一起，
     * 同一规则将应用到#main和.images两个选择器中

6. CSS的伪元素

   CSS伪元素用于向某些选择器设置特殊效果

   * `:first-line`伪元素
     * 用于向文本的首行设置特殊样式
     * 只能用于块级元素
     * 可应用于:first-line`伪元素的属性：
       * font
       * color
       * background
       * word-spacing
       * letter-spacing
       * text-decoration
       * vertical-align
       * text-transform
       * line-height
       * clear
   * `:first-letter`伪元素
     - 用于向文本的首字母设置特殊样式
     - 只能用于块级元素
     - 可应用于:first-letter`伪元素的属性：
       - font
       - color
       - background
       - margin
       - padding
       - border
       - text-decoration
       - vertical-align
       - text-transform
       - line-height
       - clear

7. 不推荐使用table来布局的原因

   * table比其它html标记占更多的字节
   * table会阻挡浏览器渲染引擎的渲染顺序
   * table里显示图片时需要你把单个、有逻辑性的图片切成多个图
   * 在某些浏览器中，table里的文字的拷贝会出现问题
   * table会影响其内部的某些布局属性的生效
   * table一旦设计完成，很难通过CSS让它展现新的面貌