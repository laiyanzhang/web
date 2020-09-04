# JavaScript

标签（空格分隔）： JavaScript

---

## 1.DOM改变
- document.write()：位于输出流时会按照文档顺序进行写，在函数中执行时会覆盖整个文档进行写
- element.innerHTML=""改变内容
- element.attribute=""改变属性
- element.style.property=""改变样式
- element.addEventListener(event,function)添加时间监听器

## 2.获取元素
- document.getElementById()
- document.getElementByTagName()
- document.getElementByClassName()

## 3.JavaScript分号
- 使用分号可一行多语句，无分号时执行一条语句
- 文本字符串通过\进行换行

## 4.变量
- 基本类型：number、string、boolean、null、undefined；引用类型：array、object
- 引用类型通过new方法进行创建，并可动态改变属性和方法
- ==：转化为同一类型值进行比较；===：类型不同则不相等，但是对于array、object无区别
- 变量类型转换：Number()、String()
- 自动类型转换：num+string:返回字符串，null+num：null=0，null+string："nullstring"
- 正则表达式：RegExp:/正则表达式主题/修饰符(可选)
  - RegExp.test():return boolean
  - RegExp.exec():return array
- 复制变量：基本类型完全独立的两个变量，引用类型指向同一个对象
- 传递参数：均为值传递，引用类型传入时形参与实参指向同一个对象，但在new方法后形参指向新对象
- var instanceof dataType 检测引用类型 返回boolean
- typeof var 返回数据类型
- JS原生对象
  - 原始类型：空值：null、undefined；包装对象：string、number、Boolean
  - 对象类型：构造器对象：obeject、function、date、array、error、regexp；单体内置对象：Math、JSON、window、arguments
- var、let、const：
  - var变量是整个封闭函数，let变量、const变量为块级作用域{}；
  - const:不可以通过重新赋值改变，并且不能重新声明；当const变量数据类型为对象时可进行内部属性改变，但不能重新整体赋值
  - const、var、let：不可互相重置声明变量，let、const变量不可变量提升
- 非合法标识符时需要加上引号
- 变量可重复声明，重复声明后的值会覆盖先前的值，未赋值时不会覆盖先前的值
- 局部变量与全局变量
  - if与for语句定义的变量是相对的全局变量
  - 未声明变量为全局对象window的一个属性，可以delete
  - 函数内的变量调用将会根据作用域逐级往上
- 垃圾收集：标记清除、引用计数，通过值设为null手工解除对象引用管理内存
- return myArray.constructor.toString().indexOf("Array") > -1;判断是否是数组
- 变量提升：函数变量和变量声明会被解释器提升到方法体顶部，被初始化的变量不会提升，函数提升到变量之上，其他按照声明顺序

## 5.函数
- 函数可重复声明，函数名相同即重复声明，与参数无关
- 实参比形参少：形参为undefined；
- 形参比实参少：不可调用对应的实参，使用arguments[]可以获取参数
- 函数与变量同名时，变量生效
- 两种函数：普通函数与函数对象。函数对象调用：a返回整个函数对象；a()返回函数返回值
- 延长函数内变量作用域：catch块与with（）语句

## 6.事件
- onchange、onclick、onmouseover、onmouseout、onkeydown、onload
- addEventListener/removeEventListener(event,function)

## 7.严格模式
- 在脚本或函数开头使用"use strict"使用严格模式
- 不允许使用未声明变量、删除变量或对象或函数、变量重名，使用八进制、使用转义字符等

## 8.使用误区
- switch默认使用恒等运算符
- 浮点型数据精度无法确定，直接运算产生错误，可将浮点型数据运算为整型数据进行运算
- 代码换行时，第一行代码不完整时，js尝试读取第二行的语句组合完整语句

## 9.表单
- 表单验证：onsubmit="return function()",当function返回false时表单无法提交
- element.checkValidity()：input元素中的数据合法返回true，否则返回false
- element.setCustomValidity():设置错误提示信息，设置后checkValidity()默认为false，需要重设为空才能恢复原样
- element.validationMessage:错误提示信息
- element.validity.data:validity不同的数据属性验证

## 10.void
- javascript:void():仅执行void内的表达式不返回值
- void():仅执行void内表达式不返回值

## 11.异步编程
- setTimeout(function,delay):在time时间之后执行回调函数function
- 异步ajax：XMLHttpRequest.onload=function(){}在请求发送成功时执行函数
- Promise函数实现异步的良好编程风格
  - Promise函数：return Promise对象
  - Promise对象：new Promise(function(resolve,reject){settimeout(function,delay)})
  - resolve():执行成功向下一个then传递一个值；reject():执行失败传递异常给catch，但函数会继续执行除非使用throw跳转至catch实现中断
  - Promise.then(function(){}).then(function(){}).catch(function(){}).finally(function(){});通过then(function(){})为异步排顺序，在内部通过返回一个Promise对象使下一个then相对于这个Promise对象进行操作
  - 异步函数asyc function(){await Promise函数;await Promise函数.....}


  


