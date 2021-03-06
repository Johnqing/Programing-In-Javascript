# 表达式

表达式是JavaScript中的一个短语，解释器会将其计算出一个结果。程序中的常量是最简单的一类表达式。

将简单的表达式在组合成复杂的表达式最常用的方法就是使用运算符。运算符按照特定运算规则对操作数进行运算。

## 原始表达式

原始表达式包括常量，关键字和变量.

## 对象和数组的初始化表达式

数组初始化表达式是通过一对方括号和其内由逗号隔开的列表构成的。例如

    []
    [1+2,3+4]
也可以进行嵌套：
 
    [[1,2,3],[4,5,6]];
也可以通过逗号省略某些元素：

    [1,,,,5]
对象初始化跟数组初始化非常相似，只是方括号被花括号代替，并且每个字表达式都包含一个属性吗和一个冒号作为前缀：

    var p = {x:2.3, y:-1.2}

## 函数定义表达式
   
    var quare = function(x) { return x * x;}

## 属性访问表达式
    
    o.x

## 调用表达式

    f(0)
    Math.max(x, y, z)
    a.sort()

## 对象创建表达式

    new Object()
    new Point(2,3)

## 运算符概述

JavaScript中有许多运算符用于算术表达式，比较表达式，逻辑表达式，赋值表达式。多数运算符都是由标点符号表示，比如"+"和"="。另外一些运算符则是由关键字表示，比如delete和instanceof。

运算符可以根据其操作数的个人进行分类。多数的运算符为二元运算符 例如*。 同样也有一些一元运算符，例如，表达式-x中“-”运算符，条件判断运算符 ?: 是一个三元运算符。

一些运算符可以作用与任何数据类型，但是仍然希望它们的操作数是指定类型的数据，并且大多数运算符返回一个特定类型的值。通常会根据需要对操作数进行类型转换

左值是一个古老的属于，它是指 表达式只能出现在赋值运算符的左侧。在JavaScript中，变量，对象属性和数组元素均是左值。ECMAScript规范允许内置函数返回一个左值，但自定义的函数则不能返回左值。

## 算术表达式

    1 + 2
    "hello" + " " 
    "1" + "2"

## 关系表达式

关系运算符用于测试两个值之间的关系，关系表达式总是返回一个布尔值，通常在if, while或者for语句中使用关系表达式，用以控制程序的执行流程。

== 和 ===运算符用于比较两个值是否相等，他们对相等的定义不尽相同。两个运算符允许任意类型的操作数，如果操作数相等则返回true,否则返回false。====也称为严格相等运算符，它用来检测两个操作数是否严格相等。== 运算符称做相等运算符，它用来检测两个操作数是否相等，这个相等的定义非常宽松，可以允许进行类型转换。由于 == ===的结合性都是从左到右，所以在执行==操作的时候，执行左侧的类型转换。 ！= ！==运算符的检测规则是==和===运算符的求反。

比较运算符用来检测两个操作数的大小关系。例如 < > <= >=. 比较操作符的操作数可能是任意类型的，然而之后数字和字符串才是真正执行比较操作符，因为那些不是数字和字符串的操作数都将进行类型转换。

in运算符希望它的左操作数是一个字符串或可以转换为字符串，希望它的右操作数是一个对象。如果右侧的对象拥有一个名为左操作数值的属性名，那么表达式返回true,例如：

    var point = {x:1, y:1};
    "x" in point

instanceof运算符希望左操作数是一个对象，右操作数标识对象的类。如果左侧的对象是右侧类的实例，则表达式返回true。例如：

    var d = new Date();// 通过Date()构造函数来创建一个新对象
    d instanceof Date;// 计算结构为true, d是由Date()创建的

## 逻辑表达式

逻辑运算符 && || ！是对操作数进行布尔算术运算，经常和关系运算符一起使用
    
    if(a === b && c == d ) {
        // some code
    }

## 赋值表达式

JavaScript使用"="运算符来给变量或者属性赋值 例如：

    i = 0
    o.x = 1

=运算符希望它的左操作数是一个左值， 右操作数可以使任意类型的任意值。

除了常规的赋值运算，JavaScript还支持许多其他的赋值运算符，这些运算符将赋值运算符和其他运算符连接起来，提供了一种更为快捷的运算方式。例如：
   
    total += sales_tax

等价于

    total = total + sales_tax

## 表达式计算

和其他许多解释性语言一样，JavaScript同样可以解释运行由JavaScript源代码组成的字符串， 并产生一个值。JavaScript通过管局函数eval()来完成这个工作：

    eval("3+2") //=>5

## 其他运算符

条件运算符（?:）是JavaScript中唯一的一个三元操作符：

    x > 0 ? x : -x //求x的绝对值

typeof运算符是一元运算符，放在其单个操作数的前面，操作数可以使任意类型。返回值为表示操作数类型的一个字符串：

typeof最常用的用法是写在表达式中， 就像这样：

    (typeof value == "string") ? "'" + value + "'" : value

delete是一元操作符， 它用来删除对象属性或者数组元素.

    var o = {x:1, y:2}//定义一个对象
    delete o.x  //删除一个属性
    "x" in o    //=> false:这个属性在对象中不再存在
