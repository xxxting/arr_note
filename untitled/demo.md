#数组的用方法

- concat():创建并且返回一个新数组
```angular2
var a5 = [1,2,3];
console.log(a5.concat(4));            //[1,2,3,4]
console.log(a5);                      //[1,2,3]  //原数组不改变
console.log(a5.concat([4,5]));        //[1, 2, 3, 4, 5]
```

- constructor():返回数组的构造函数
```angular2
 function Array() { [native code] }   //返回值
```

- copywithin():在当前数组内部，将指定位置的成员复制到其他位置（会覆盖原有成员），然后返回当前数组
```angular2
     var arr = [1,2,3,4,5,6,7,8,9];
     arr.copyWithin(0,3,6);  
     console.log(arr);//4,5,6,4,5,6,7,8,9
```
- intries():entries() 方法返回一个数组的迭代对象，该对象包含数组的键值对 (key/value)。
            迭代对象中数组的索引值作为 key， 数组元素作为 value。
```angular2
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.entries();  // [0, "Banana"] [1, "Orange"] [2, "Apple"] [3, "Mango"]
```            
- every():every() 方法用于检测数组所有元素是否都符合指定条件（通过函数提供）。
          every() 方法使用指定函数检测数组中的所有元素：
          如果数组中检测到有一个元素不满足，则整个表达式返回 false ，且剩余的元素不会再进行检测。
          如果所有元素都满足条件，则返回 true。
          注意： every() 不会对空数组进行检测。
          注意： every() 不会改变原始数组。
 ```angular2
array.every(function(currentValue,index,arr), thisValue)//函数，数组中的每个元素都会执行这个函数;
//currentValue 必须。当前元素的值
//index  可选。当前元素的索引值
//arr   可选。当前元素属于的数组对象
```
- fill():将一个固定值替换数组的元素。
```angular2
array.fill(value, start, end)

var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.fill("Runoob", 2, 4);//Banana,Orange,Runoob,Runoob
```

- filter():创建一个新的数组，新数组中的元素是通过检查指定数组中符合条件的所有元素。
          注意： filter() 不会对空数组进行检测。
          注意： filter() 不会改变原始数组。
```angular2

var ages = [32, 33, 16, 40];

function checkAdult(age) {
    return age >= 18;
}

function myFunction() {
    document.getElementById("demo").innerHTML = ages.filter(checkAdult);
}   //32,33,40
```          

- find():返回通过测试（函数内判断）的数组的第一个元素的值。
         find() 方法为数组中的每个元素都调用一次函数执行：
         当数组中的元素在测试条件时返回 true 时, find() 返回符合条件的元素，之后的值不会再调用执行函数。 
         如果没有符合条件的元素返回 undefined 
```angular2
var ages = [3, 10, 18, 20];
 
function checkAdult(age) {
    return age >= 18;
}
 
function myFunction() {
    document.getElementById("demo").innerHTML = ages.find(checkAdult);
}    //18
```

- findIndex():返回传入一个测试条件（函数）符合条件的数组第一个元素位置(下标)。
              findIndex() 方法为数组中的每个元素都调用一次函数执行：
              当数组中的元素在测试条件时返回 true 时, findIndex() 返回符合条件的元素的索引位置，之后的值不会再调用执行函数。 
              如果没有符合条件的元素返回 -1
```angular2
var ages = [3, 10, 18, 20];
 
function checkAdult(age) {
    return age >= 18;
}
 
function myFunction() {
    document.getElementById("demo").innerHTML = ages.findIndex(checkAdult);
}  //2
```    

- join():用于把数组中的所有元素放入一个字符串，返回接合所有数组元素之后的字符串。
         
 ```angular2
var arr = new Array("First","Second","Third");
 
var str = arr.join();
document.write("str : " + str ); //str : First,Second,Third
 
var str = arr.join(", ");
document.write("<br />str : " + str ); //str : First,Second,Third
 
var str = arr.join(" + ");
document.write("<br />str : " + str ); //str : First+Second+Third
```

- keys():从数组创建一个包含数组键的可迭代对象。该对象包含了数组的键.
```angular2
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.keys();
```

- lastIndexOf():lastIndexOf() 方法可返回一个指定的元素在数组中最后出现的位置，从该字符串的后面向前查找。
                如果要检索的元素没有出现，则该方法返回 -1。
```angular2
var fruits = ["Banana", "Orange", "Apple", "Mango"];
var a = fruits.lastIndexOf("Apple");    //2
```           

- map():回一个新数组，数组中的元素为原始数组元素调用函数处理后的值。
        map() 方法按照原始数组元素顺序依次处理元素。 
```angular2
var numbers = [4, 9, 16, 25];

function myFunction() {
    x = document.getElementById("demo")
    x.innerHTML = numbers.map(Math.sqrt);
}  //2  3  4  5 
```

- pop():删除 arrayObject 的最后一个元素，把数组长度减 1，并且返回它删除的元素的值。如果数组已经为空，则 pop() 不改变数组
         并返回 undefined 值。(删除并返回数组的最后一个元素)。
```angular2
var arr = new Array(3)
arr[0] = "George"
arr[1] = "John"
arr[2] = "Thomas"

document.write(arr)       //George,John,Thomas

document.write("<br />") 

document.write(arr.pop())  //Thomas

document.write("<br />")

document.write(arr)       //George,John
```         

- push():把它的参数顺序添加到 arrayObject 的尾部。它直接修改 arrayObject，而不是创建一个新的数组。push() 方法和 pop() 方法
         使用数组提供的先进后出栈的功能。(向数组的末尾添加一个或多个元素，并返回新的长度)。
```angular2
var arr = new Array(3)
arr[0] = "George"
arr[1] = "John"
arr[2] = "Thomas"

document.write(arr + "<br />")                //George,John,Thomas
document.write(arr.push("James") + "<br />")  //4
document.write(arr)                           //George,John,Thomas,James
```         

- reduce():接收一个函数作为累加器，数组中的每个值（从左到右）开始缩减，最终计算为一个值。
           reduce() 可以作为一个高阶函数，用于函数的 compose。
           注意: reduce() 对于空数组是不会执行回调函数的。
```angular2
var numbers = [65, 44, 12, 4];
 
function getSum(total, num) {
    return total + num;
}
function myFunction(item) {
    document.getElementById("demo").innerHTML = numbers.reduce(getSum);
} //125
```           

- reduceRight():reduceRight() 方法的功能和 reduce() 功能是一样的，不同的是 reduceRight() 从数组的末尾向前将数组中的数组
                项做累加。
```angular2
var numbers = [65, 44, 12, 4];
 
function getSum(total, num) {
    return total + num;
}
function myFunction(item) {
    document.getElementById("demo").innerHTML = numbers.reduceRight(getSum);
}  //125
```                 
- reverse():用于颠倒数组中元素的顺序。该方法会改变原来的数组，而不会创建新的数组。
```angular2
var arr = new Array(3)
arr[0] = "George"
arr[1] = "John"
arr[2] = "Thomas"

document.write(arr + "<br />")    //George,John,Thomas
document.write(arr.reverse())    //Thomas,John,George
```

- shift():把数组的第一个元素从其中删除，并返回第一个元素的值。
          注意： 此方法改变数组的长度！
```angular2
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.shift()  //Orange,Apple,Mango 
```
- slice():可从已有的数组中返回选定的元素。该方法并不会修改数组，而是返回一个子数组。
```angular2
arrayObject.slice(start,end) //返回一个新的数组，包含从 start 到 end （不包括该元素）的 arrayObject 中的元素。

var arr = new Array(3)
arr[0] = "George"
arr[1] = "John"
arr[2] = "Thomas"

document.write(arr + "<br />")            // George,John,Thomas
document.write(arr.slice(1) + "<br />")   //John,Thomas
document.write(arr)                       //George,John,Thomas
```

- some():用于检测数组中的元素是否满足指定条件（函数提供）。
         some() 方法会依次执行数组的每个元素：
         如果有一个元素满足条件，则表达式返回true , 剩余的元素不会再执行检测。
         如果没有满足条件的元素，则返回false。
````angular2

array.some(function(currentValue,index,arr),thisValue)


var ages = [3, 10, 18, 20];

function checkAdult(age) {
    return age >= 18;
}

function myFunction() {
    document.getElementById("demo").innerHTML = ages.some(checkAdult);
}  //true
````         

- sort():对数组的元素进行排序;
         如果调用该方法时没有使用参数，将按字母顺序对数组中的元素进行排序，说得更精确点，是按照字符编码的顺序进行排序。要实现这一点，首先应把数组的元素都转换成字符串（如有必要），以便进行比较。
         如果想按照其他标准进行排序，就需要提供比较函数，该函数要比较两个值，然后返回一个用于说明这两个值的相对顺序的数字。比较函数应该具有两个参数 a 和 b，其返回值如下：
         若 a 小于 b，在排序后的数组中 a 应该出现在 b 之前，则返回一个小于 0 的值。
         若 a 等于 b，则返回 0。
         若 a 大于 b，则返回一个大于 0 的值。
```angular2
var arr = new Array(6)
arr[0] = "10"
arr[1] = "5"
arr[2] = "40"
arr[3] = "25"
arr[4] = "1000"
arr[5] = "1"

document.write(arr + "<br />")    //10,5,40,25,1000,1
document.write(arr.sort())       //1,10,1000,25,40,5

```

- splice():splice() 方法可删除从 index 处开始的零个或多个元素，并且用参数列表中声明的一个或多个值来替换那些被删除的元素。
           如果从 arrayObject 中删除了元素，则返回的是含有被删除的元素的数组。(从数组中添加/删除项目，然后返回被删除的
           项目。该方法会改变原始数组。)
```angular2

arrayObject.splice(index,howmany,item1,.....,itemX)
//index:必需。整数，规定添加/删除项目的位置，使用负数可从数组结尾处规定位置。
//howmany:必需。要删除的项目数量。如果设置为 0，则不会删除项目
//item1, ..., itemX:可选。向数组添加的新项目。

var arr = new Array(6)
arr[0] = "George"
arr[1] = "John"
arr[2] = "Thomas"
arr[3] = "James"
arr[4] = "Adrew"
arr[5] = "Martin"

document.write(arr + "<br />") //George,John,Thomas,James,Adrew,Martin

arr.splice(2,0,"William")
document.write(arr + "<br />") //George,John,William,Thomas,James,Adrew,Martin

```  

- toLocaleString():把数组转换为本地字符串。首先调用每个数组元素的 toLocaleString() 方法，然后使用地区特定的分隔符把生成
                   的字符串连接起来，形成一个字符串。
```angular2
var arr = new Array(3)
arr[0] = "George"
arr[1] = "John"
arr[2] = "Thomas"

document.write(arr.toLocaleString())  //George, John, Thomas
```                   

- topString():把数组转换为字符串，并返回结果。返回值与没有参数的 join() 方法返回的字符串相同。
```angular2
var arr = new Array(3)
arr[0] = "George"
arr[1] = "John"
arr[2] = "Thomas"

document.write(arr.toString())  //George,John,Thomas

```

- unshift():向数组的开头添加一个或更多元素，并返回新的长度。(unshift() 方法将把它的参数插入 arrayObject 的头部，并将已经
            存在的元素顺次地移到较高的下标处，以便留出空间。该方法的第一个参数将成为数组的新元素 0，如果还有第二个参数，
            它将成为新的元素 1，以此类推。)
```angular2
var arr = new Array()
arr[0] = "George"
arr[1] = "John"
arr[2] = "Thomas"

document.write(arr + "<br />")                     //George,John,Thomas
document.write(arr.unshift("William") + "<br />")  // 4
document.write(arr)                                //William,George,John,Thomas
```            
