<a id="start">start</a>
## JS Tutorial
&emsp;为什么要重新介绍`JavaScript`因为它被认为是误解最深的编程语言。在它骗人的表象背后，有着强大的特性。

&emsp;1995年*Brendan Eich*创造了`JavaScript`。最初的名字是`LiveScript`，但由于当时最流行的编程语言Java，出于市场营销，改名为`JavaScript`，但是它们的相同点特别少。
## JavaScript的数据类型
* [Number](#1)
* [String](#2)
* [Boolean](#3)
* [Sylbom](#4)(new in ES2015)
* [Object](#5)
    - [Function](#6)
    - [Array](#7)
    - [Date](#8)
    - [RegExp](#9)
* [null](#10)
* [undefined](#11)

<h2 id='1'>Numbers</h2>

&emsp;可以用内置函数 `parseInt()` 把一个string类型转化成integer，第二个参数是转化类型:
```javascript
parseInt('123', 10); //123
parseInt('010', 10); //10
parseInt('11', 2); //3
parseInt('10.2aa', 10) //10
```
> 使用`parseFloat()`把string转化成float类型的数。

如果string不是数值类型的，会返回NaN(Not a Number)：
```javascript
parseInt('hello', 10); //NaN
```
NaN和Infinity:
```javascript
NaN + 5; //NaN
isNaN(NaN); //true
1 / 0; //Infinity
-1 / 0; //-Infinity
```
<h2 id='2'>Strings</h2>

```javascript
'hello'.length; //5
'hello'.charAt(0); //'h'
'hello, world'.replace('world','mars'); //'hello, mars'
'hello'.toUpperCase(); //'HELLO'
```
## Variables

&emsp;声明变量的三种方法:`let`, `const`, `var`。

>let声明块级的变量，作用域在块内

```javascript
// myLetVariable is *not* visible out here

for (let myLetVariable = 0; myLetVariable < 5; myLetVariable++) {
  // myLetVariable is only visible in here
}

// myLetVariable is *not* visible out here
```
>const声明的变量是不可以改变的

```javascript
const Pi = 3.14;
Pi = 1; //will throw an error
```

>var没有另外两种方式的限制，块内的变量在块外仍然有效。

## Others

>==不是很严格的相等，两边类型不相等时它会进行强制类型转换。可以使用===避免类型转换。

```javascript
123 == '123'; //true
1 == true; //true
123 === '123'; //false
```

>if

```javascript
var name = 'kittens';
if (name == 'puppies') {
  name += ' woof';
} else if (name == 'kittens') {
  name += ' meow';
} else {
  name += '!';
}
name == 'kittens meow';
```

>while


```javascript
while (true) {
  // an infinite loop!
}

var input;
do {
  input = get_input();
} while (inputIsNotValid(input));
```

>for...of/in

```javascript
for(let value of array){
    //...value
}
for(let property in object){
    //...obkect property
}
```

>switch

```javascript
switch (action) {
  case 'draw':
    drawIt();
    break;
  case 'eat':
    eatIt();
    break;
  default:
    doNothing();
}
```

<h2 id='5'>Objects</h2>

JavaScript中的object可以被认为是name-value集合，类似于Python中的字典.name是一个string，value可以是任何JavaScript值。


>创建一个空object

```javascript
var obj = new Object();
var obj = {};
```

```javascript
var obj = {
    name: 'Carrot',
    details:{
        color:'orange',
        size:'12'
    }
};
obj.detaile.color; //orange
obj['details'][]'size']; //12
```

<h2 id='6'> Functions</h2>

一个简单的function

```javascript
function add(x ,y){
    var total = x + y;
    return total;
}
var add = function(){
    //...
}
```

>function内部有接受参数的变量`arguments`，可以接收所有的参数。也可以使用...variable的格式

```javascript
function avg() {
  var sum = 0;
  for (var i = 0, j = arguments.length; i < j; i++) {
    sum += arguments[i];
  }
  return sum / arguments.length;
}

avg(2, 3, 4, 5); // 3.5
```

```javascript
function avg(...args){
    var sum = 0;
    for(let value of args){
        sum += value;
    }
    return sum/args.length;
}
avg(2, 3, 4, 5); //3.5
```








[start](#start)

