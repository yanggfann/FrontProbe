# 变量

## 变量作用域

* **全局变量**

  在函数外声明的变量作用域是全局的

  全局变量在 JavaScript 程序的任何地方都可以访问

  ```
  var carName = "Volvo";
   
  // 这里可以使用 carName 变量
   
  function myFunction() {
      // 这里也可以使用 carName 变量
  }
  ```

* **函数内的局部变量**

  在函数内声明的变量作用域是局部的（函数内）

  函数内使用** var** 声明的变量只能在函数内访问，如果不使用 var 则是全局变量。

  ```
  // 这里不能使用 carName 变量
   
  function myFunction() {
      var carName = "Volvo";
      // 这里可以使用 carName 变量
  }
   
  // 这里不能使用 carName 变量
  ```

* **块级作用域**

  使用 **var** 关键字声明的变量不具备块级作用域的特性，它在 {} 外依然能被访问到。

  ```
  { 
      var x = 2; 
  }
  // 这里可以使用 x 变量
  ```

  在 ES6 之前，是没有块级作用域的概念的。

  ES6 可以使用 **let** 关键字来实现块级作用域。

  let 声明的变量只在 **let** 命令所在的代码块 **{}** 内有效，在 **{}** 之外不能访问。

  ```
  { 
      let x = 2;
  }
  // 这里不能使用 x 变量
  ```

* **循环作用域**

  * 使用 **var** 关键字

    使用 **var** 关键字，它声明的变量是全局的，包括循环体内与循环体外

    ```
    var i = 5;
    for (var i = 0; i < 10; i++) {
        // 一些代码...
    }
    // 这里输出 i 为 10
    ```

  * 使用 **let** 关键字

    使用 **let** 关键字， 它声明的变量作用域只在循环体内，循环体外的变量不受影响

    ```
    let i = 5;
    for (let i = 0; i < 10; i++) {
        // 一些代码...
    }
    // 这里输出 i 为 5
    ```

## var/let/const关键字的区别

* **重置变量**

  * 使用 **var** 关键字声明的变量在任何地方都可以修改

    ```
    var x = 2;
     
    // x 为 2
     
    var x = 3;
     
    // 现在 x 为 3
    ```

  * 在相同的作用域或块级作用域中，不能使用 **let** 关键字来重置 **var** 关键字声明的变量

    ```
    var x = 2;       // 合法
    let x = 3;       // 不合法
    
    {
        var x = 4;   // 合法
        let x = 5   // 不合法
    }
    ```

  * 在相同的作用域或块级作用域中，不能使用 **let** 关键字来重置 **let** 关键字声明的变量

  * 在相同的作用域或块级作用域中，不能使用 **var** 关键字来重置 **let** 关键字声明的变量

  * **let** 关键字在不同作用域，或不同块级作用域中是可以重新声明赋值的

    ```
    let x = 2;       // 合法
    
    {
        let x = 3;   // 合法
    }
    
    {
        let x = 4;   // 合法
    }
    ```

* **局部变量**

  在函数体内使用 **var** 和 **let** 关键字声明的变量，它们的作用域都是 **局部的**

* **全局变量**

  在函数体外或代码块外使用 **var** 和 **let** 关键字声明的变量，它们的作用域都是 **全局的**

* **HTML代码中使用全局变量**

  在 JavaScript 中, 全局作用域是针对 JavaScript 环境。

  在 HTML 中, 全局作用域是针对 window 对象。

  使用 **var** 关键字声明的全局作用域变量属于 window 对象

  ```
  var carName = "Volvo";
  // 可以使用 window.carName 访问变量
  ```

  使用 **let** 关键字声明的全局作用域变量不属于 window 对象

  ```
  let carName = "Volvo";
  // 不能使用 window.carName 访问变量
  ```

* **重新定义变量**

  * **var**

    使用 **var** 关键字重新声明变量可能会带来问题。

    在块中重新声明变量也会重新声明块外的变量：

    ```
    var x = 10;
    // 这里输出 x 为 10
    { 
        var x = 2;
        // 这里输出 x 为 2
    }
    // 这里输出 x 为 2
    ```

  * **let**

    **let**关键字只在**let**命令所在的代码块{}内有效

    ```
    var x = 10;
    // 这里输出 x 为 10
    { 
        let x = 2;
        // 这里输出 x 为 2
    }
    // 这里输出 x 为 10
    ```

* **const**

  const 用于声明一个或多个常量，声明时必须进行初始化，且初始化后值不可再修改。

  ```
  // 错误写法
  const PI;
  PI = 3.14159265359;
  
  // 正确写法
  const PI = 3.14159265359;
  ```

  * **const** 与 **let** 的相同点：
    * 二者都是块级作用域
    * 都不能和它所在作用域内的其他变量或函数拥有相同的名称
  * **const** 与 **let** 的区别：
    * **const**声明的常量必须初始化，而**let**声明的变量不用
    * **const** 定义常量的值**不能**通过**再赋值**修改，也**不能再次声明**。而 **let** 定义的变量值可以修改。

  * **const**的本质：**const** 定义的变量并非常量，并非不可变，它定义了一个常量引用一个值。使用 **const** 定义的对象或者数组，其实是可变的。下面的代码并不会报错：

    ```
    // 创建常量对象
    const car = {type:"Fiat", model:"500", color:"white"};
     
    // 修改属性:
    car.color = "red";
     
    // 添加属性
    car.owner = "Johnson";
    ```

    但是我们不能对常量对象重新赋值：

    ```
    const car = {type:"Fiat", model:"500", color:"white"};
    car = {type:"Volvo", model:"EX60", color:"red"};    // 错误
    ```

    修改常量数组：

    ```
    // 创建常量数组
    const cars = ["Saab", "Volvo", "BMW"];
     
    // 修改元素
    cars[0] = "Toyota";
     
    // 添加元素
    cars.push("Audi");
    ```

    但是我们不能对常量数组重新赋值：

    ```
    const cars = ["Saab", "Volvo", "BMW"];
    cars = ["Toyota", "Volvo", "Audi"];    // 错误
    ```

## 变量提升(hoisting)

* **变量提升**：函数**声明**和变量**声明**总是会被解释器悄悄地被"提升"到方法体的最顶部。

* **var** 和 **let** 的区别

  JavaScript 中，var 关键字定义的变量可以先使用再声明

  ```
  // 在这里可以使用 carName 变量
   
  var carName;
  ```

  let 关键字定义的变量需要先声明再使用

  ```
  // 在这里不可以使用 carName 变量
  
  let carName;
  ```

* **初始化不会提升**

  JavaScript 只有声明的变量会提升，初始化的不会

  ```
  var x = 5; // 初始化 x
  
  elem = document.getElementById("demo"); // 查找元素 
  elem.innerHTML = x + " " + y;           // 显示 x 和 y
  
  var y = 7; // 初始化 y
  ```

  y 输出了 **undefined**，这是因为变量声明 (var y) 提升了，但是初始化(y = 7) 并不会提升，所以 y 变量是一个未定义的变量。

  类似以下代码：

  ```
  var x = 5; // 初始化 x
  var y;     // 声明 y
  
  elem = document.getElementById("demo"); // 查找元素
  elem.innerHTML = x + " " + y;           // 显示 x 和 y
  
  y = 7;    // 设置 y 为 7
  ```

# 函数式编程 --- 一种编程方式

* 函数式编程：**以函数作为主要载体的编程方式**，用函数去拆解、抽象一般的表达式

* 函数式编程的**优点**

  * 代码简洁，开发快速
  * 接近自然语言，易于理解
  * 更方便的代码管理
  * 易于“并发编程”
  * 可复用性更高
  * 可维护性更好

* 函数声明

  ```
  function functionName(parameters) {
    //执行的代码
  }
  ```

  函数声明后不会立即执行，会在我们需要的时候调用到。

* **箭头函数**

  箭头函数表达式的语法比普通函数表达式更简洁。

  ```
  (参数1, 参数2, …, 参数N) => { 函数声明 }
  
  (参数1, 参数2, …, 参数N) => 表达式(单一)
  // 相当于：(参数1, 参数2, …, 参数N) =>{ return 表达式; }
  ```

* **基本的函数式编程**

  * 一般写法

    ```
    const arr = ['apple', 'pen', 'apple-pen'];
    for(const i in arr){
      const c = arr[i][0];
      arr[i] = c.toUpperCase() + arr[i].slice(1);
    }
    ```

  * 函数式写法一

    ```
    function upperFirst(word) {
      return word[0].toUpperCase() + word.slice(1);
    }
     
    function wordToUpperCase(arr) {
      return arr.map(upperFirst);
    }
     
    console.log(wordToUpperCase(['apple', 'pen', 'apple-pen']));
    ```

  * 函数式写法二

    ```
    console.log(arr.map(['apple', 'pen', 'apple-pen'], word => word[0].toUpperCase() + word.slice(1)));
    ```

  * **注：**

    * **函数式写法一**，利用了函数封装性将功能做拆解（粒度不唯一），并封装为不同的函数，而再利用组合的调用达到目的。这样做使得表意清晰，易于维护、复用以及扩展。其次利用 **高阶函数**，Array.map 代替 for…of 做数组遍历，减少了中间变量和操作。

    * **函数式写法一** 和 **函数式写法二** 之间的主要差别在于，可以考虑函数是否后续有复用的可能，如果没有，则后者更优。

    * **slice()**方法

      * 定义

        slice() 方法可从已有的数组中返回选定的元素。

      * 语法

        ```
        arrayObject.slice(start,end)
        ```

        | 参数  | 描述                                                         |
        | ----- | ------------------------------------------------------------ |
        | start | 必需。规定从何处开始选取。如果是负数，那么它规定从数组尾部开始算起的位置。也就是说，-1 指最后一个元素，-2 指倒数第二个元素，以此类推。 |
        | end   | 可选。规定从何处结束选取。该参数是数组片断结束处的数组下标。如果没有指定该参数，那么切分的数组包含从 start 到数组结束的所有元素。如果这个参数是负数，那么它规定的是从数组尾部开始算起的元素。 |

      * 返回值

        返回一个新的数组，包含从 start 到 end （不包括该元素）的 arrayObject 中的元素。

      * 说明

        该方法并不会修改数组，而是返回一个子数组。

* **链式优化**

  从上面 **函数式写法二** 中可以看出，函数式代码在写的过程中，很容易造成 **横向延展**，即产生多层嵌套：

  ```
  // 一般写法
  console.log(1 + 2 + 3 - 4)
  ```

  ```
  // 函数式写法
  function sum(a, b) {
    return a + b;
  }
   
  function sub(a, b) {
    return a - b;
  }
   
  console.log(sub(sum(sum(1, 2), 3), 4);
  ```

  ```
  //链式优化
  const utils = {
    chain(a) {
      this._temp = a;
      return this;
    },
    sum(b) {
      this._temp += b;
      return this;
    },
    sub(b) {
      this._temp -= b;
      return this;
    },
    value() {
      const _temp = this._temp;
      this._temp = undefined;
      return _temp;
    }
  };
   
  console.log(utils.chain(1).sum(2).sum(3).sub(4).value());
  ```

  **注：**

  面向对象语言中 this 表示当前对象的一个引用。

  但在 JavaScript 中 this 不是固定不变的，它会随着执行环境的改变而改变。

  - 在方法中，this 表示该方法所属的对象。
  - 如果单独使用，this 表示全局对象。
  - 在函数中，this 表示全局对象。
  - 在函数中，在严格模式下，this 是未定义的(undefined)。
  - 在事件中，this 表示接收事件的元素。
  - 类似 call() 和 apply() 方法可以将 this 引用到任何对象。

* **常见的函数式编程模型** ----- **闭包**

  * **闭包：**可以**保留局部变量不被释放**的代码块；创造出了一些函数私有的“持久化变量”
  * **闭包的创造条件：**
    * 存在内、外两层函数
    * 内层函数对外层函数的局部变量进行了引用

  * **闭包的弊端：**

    持久化变量不会被正常释放，持续占用内存空间，很容易造成内存浪费，所以一般需要一些额外手动的清理机制。

  * 举例

    ```
    // 创建一个闭包
    function makeCounter() {
      let k = 0;
     
      return function() {
        return ++k;
      };
    }
     
    const counter = makeCounter();
     
    console.log(counter());  // 1
    console.log(counter());  // 2
    ```

* **常见的函数式编程模型 --- 高阶函数**

  * **高阶函数：**接受或者返回一个函数的函数

  * **map（映射）：**映射是对集合而言的，即把集合的每一项都做相同的变换，产生一个新的集合

    // 一般写法

    ```
    const arr = [1,2,3];
    const rs = [];
    for(const n of arr){
      rs.push(++n);
    }
    console.log(rs)
    ```

    //map改写

    ```
    const arr = [1,2,3];
    const rs = arr.map(n => ++n);
    ```

  