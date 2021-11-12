# JavaScript Preparation Kit
<!--ts-->
# Table of Contents
------------------
* [Javascript Ideal Questions](#javascript-ideal-questions)
* [ECMAscript 6 major changes](#ecmascript-6-major-changes)
  * [ECMAscript 2015 ES6](#ecmascript-2015-es6)
  * [ECMAscript 2016 ES7](#ecmascript-2016-es7)
  * [ECMAscript 2017 ES8](#ecmascript-2017-es8)
  * [ECMAscript 2018 ES9](#ecmascript-2018-es9)
  * [ECMAscript 2019 ES10]($ecmascript-2019-es10)
  * [ECMAscript 2020 ES11](#ecmascript-2020-es11)
<!--te-->

### Javascript Ideal Questions
==============================


1.	How is “==” different from “===”?\
When a "==" operator compares the two variable irrespective of their data types, "===" strictly compares the two variables and also their data types.
Followed by an example: when 1=='1' is true but 1==='1' is false because "===" identifies the latter condition as the comparison of number and an integer.

2.	What is a difference between function’s parameter and function’s argument?\
A function's parameters are the names listed on the functions definitions while a function's arguments are the values passed or assigned to them.

3.	How do you define anonymous function?\
It is a function which is assigned to a variable whose data type is function and stored through it but originally not stored or declared in a program file.

4.	What is for-in loop and for-of loop?\
For-in loop is used to read the index number of the elements in the array. 
For-of loop is used to read the elements of array.

5.	What are map() and forEach() methods?\
These are array methods. map() method receives function as a parameter and returns a whole new array executing the provided function. 
forEach() method returns an undefined value.
map(currentElement, IndexOfElement, Array)

6.	Reduce method default parameters\
reduce(accumulator, currentElement, currentIndex, Array) //call back function
Is useful to get the sum, average, mean, deviation of the elements of a given array.
reduce() method as call back function has an initial value at the last of the expression.
Ex: reduce(accum, currEle, Index, arr), initial value)

7.	Difference between getElementById and querySelector.\
getElementById returns a reference to the element by its ID and if the ID is not specified in the document then it returns null.
querySelector returns the first element within the document that matches the specified group of selectors, or null if no matches is found. It can also return all three class, id, element.

8.	Difference between onClick() and addEventListener()…\
onClick() overwrites the evensts if multiple events are assigned to an element where as addEventListener() can add more than one events to an element.

9.	Difference between setTimeout() and setInterval().\
setTimeout() enables the user to continue a function only once after waiting for a certain time whereas setInterval allows us to resume the function over and over and still continue…

10. ECMAscript 2014 ES5\
‘use strict ’; asks us to follow the traditional way of javascript coding by following the declaration properly.
```
'use strict';
x=3.14;		//since ‘use strict’; is used one must define the var properly
console.log(x);
//console: ReferenceError: x is not defined
```
```
//once I define the variable properly

'use strict';

var x=3.14;
console.log(x);
//console: 3.14
```
### ECMAscript 6 major changes
====================================

a.	**“let” and “const”**\
Variable declared using var and let keyword can be changed and modified whereas const is more like a constant which if used, does not allow user to alter the values assigned passing through it.
Also, var has function scope which means that the variable declared using it inside of a function or any loop
But let and const have block scope which means that if a variable is declared using ‘let’ and ‘const’ outside a block ‘{ }’, it cannot be passed outside the block for use.

b.	**Template literals**\
`${}` \
Makes code easily readable. Easy to use and implement if comfortable using it. Use of backticks, inside where a variable is referred by using a dollar($) sign outside the curly braces and called inside those braces. 

c.	**Default parameters/arguments**\
Values can be assigned to the parameters by default while creating a function to make things easier. It has large scope. In a project if I’m taking more than two parameters in a function and I want one or two of those parameters to have certain values throughout the function expression, I can assign default value to those parameters to make things easier and lighter for me.

### ECMAscript 2015 ES6
-----------------------

d.	**Destructuring**

**array destructuring**
Asks to break the array and destructure it. Assign the main array to array of variables.
```
let myArrray = [‘Sam’, ‘Ram’, ‘Nam’];
let name1 = myArray[0];
let name2 = myArrray[1];
let name3 = myArray[2];
```
```
//but with the help of array destructuring
let [name1, name2, name3] = myArray;		          //saves time, makes work easy
```

**Object destructuring**
```
const myProfile = {
	myName: ‘Sam’,
	myAge: 22,
	myJob: ‘code’
}
let name = myProfile.myName;
let age = myProfile.myAge;
console.log(name);
```
```
//but with object destrcturing
let [myName, myAge, myJob, myDegree=’Masters’] = myProfile;
console.log(myName);                                                //makes work easy and is time effective
```

e.	**Object properties**\
No need to write key and value if both are same.
```
let name = 'Sam';
let age = 22;

const myPro = {name, age};	                        //no need to write the value if it is same as key

console.log(name);		                              //feels similar like object destructuring
//console: Sam
```
```
let name = 'Sam';
const myPro = {
    name: 'How are you',
    26: 'is my age'
}

console.log(myPro);	
//console: { '26': 'is my age', name: 'Suup' }
```
```
//but with dynamic object properties 

let name = 'Sam';
const myPro = {
    [name]: 'Suup',	                                //with [variable name] the object receives the value of global scope
    26: 'is my age'		                              //[20+6]
}

console.log(myPro);	
//console: { '26': 'is my age', Sam: 'Suup' }
```

f.	**Arrow function**\
Use of fat arrow symbol(“=>”) to refer to a function expression make things easier. But key difference between fat arrow function and traditional function is that we cannot call the function prior to the function expression while using the fat arrow expression. While in a traditional function I can call the function to console before or after the function expression, that would not matter. However, in most cases we call the function after the end of the expression to ease the debugging process and prevent future possible error. 
But with arrow function we MUST call the function after the function expression. So, primarily the main advantage of using the array function is to improve the readability of the function and save time as it shortens the code.
Note: Cannot use “this.” keyword as argument
```
#traditional
var a,b;
function sum(a,b){
    return result=(a+b);
}
console.log(sum(2,3));
```
```
#fat-arrow function
const sum = (a,b) => `result=${a+b}`; 
console.log(sum(3,2));
```

h.	**Spread operators**\
```
const colors = ['red', 'blue', 'green'];
const myColors = ['red', 'blue', 'green', 'pink', 'yellow'];
```
```
//with the help of spread operator(...variable name), I don’t need to repeat the array elements of colors in myColors
//I can simply write;

const myFavColor = [...colors, 'pink', 'yellow'];

console.log(myFavColor);
```

#### ECMAscript 2016 ES7
------------------------

**Array.prototype.includes**
```
//array includes
const colors = ['red', 'blue', 'purple'];

const isPresent = colors.includes('red');

console.log(isPresent);
```

**Exponentiation Operator**
```
console.log(Math.pow(2,3));
```
```
//can also be written as 
console.log(2**3);		                                      
//with exponentiation operator
```	

#### ECMAscript 2017 ES8
-------------------------
 
Async
Await

**String padding**
padStart(), padEnd() are methods used to get the space before or after the string values in console…user can define the amount of space as required

```
//string padding
const myName = 'Sam';

console.log(myName);
console.log(myName.padStart(5));
console.log(myName.padEnd(5));
```

**Object.values()**
Helps easily get access to the properties of the objects…
```
//Object.values()
const person ={name:'Sam', age:23};

console.log(Object.values(person));    //console: [ 'Sam', 23 ]
console.log(Object.entries(person));//console: [[ 'name', 'Sam' ],[ 'age', 23 ]]
//stores the values of object in individual array
```

####  ECMAscript 2018 ES9
-------------------------

Introduced the concept of rest element when working with the array destructuring but for objects… 
Spread properties allows to create a new object by combining the properties of the object passed after the spread operator.
```
//spread operator for objects
const person = {name:'Sam', age:23, goal:'codeMaster'};

const favPerson  = {...person, job: 'Developer'};   //(...)spread operator + variable name passes the properties of the objects to the new object

console.log(favPerson);
//console: { name: 'Sam', age: 23, goal: 'codeMaster', job: 'Developer' }
```
####  ECMAscript 2019 ES10
--------------------------

**Flat() method**
Before the flat array was not able to flat the elements of array inside of an array inside an array to 1D array…
```
const arr = [
    ['name1', 'name2'],
    ['name3', 'name4'],
    ['name5',  ['name6', 'name7']]
]

let flatArr = arr.reduce((accumulator, currentVal) => {
        return accumulator.concat(currentVal);
    })
    console.log(flatArr);
//console: [ 'name1', 'name2', 'name3', 'name4', 'name5', [ 'name6', 'name7' ]] 
```
But lets see how flat()method helps
Here you go:
```
const arr = [
    ['name1', 'name2'],
    ['name3', 'name4'],
    ['name5',  ['name6', 'name7']]
]    
    console.log(arr.flat());
//console: [ 'name1', 'name2', 'name3', 'name4', 'name5', [ 'name6', 'name7' ]] 
```
Here; the problem is not solved yet because while flattening the array the method used (any), only flattens by one level (default). So flat() too does the same work by default but if we set the value as parameter inside the parenthesis i.e. lets do flat(2) and lets see what we get:
```
const arr = [
    ['name1', 'name2'],
    ['name3', 'name4'],
    ['name5',  ['name6', 'name7']]
]    
    console.log(arr.flat(2));
```
our result is:
```
console: [
  'name1', 'name2',
  'name3', 'name4',
  'name5', 'name6',
  'name7'
]   
```
But still the work has become easier with the flat() method as user doesnot need to write a bunch of code. We need to raise the parameter inside the parenthesis to be able to flat.

**Object.fromEntries()**\
Convets the array of objects back to object with properties…
```
//Object.fromEntries()
const person ={name:'Sam', age:23};

const newObj = Object.entries(person); //console:[['name', 'Sam'],['age', 23]]
console.log(Object.fromEntries(newObj)) //console: { name: 'Sam', age: 23 }
```

####  ECMAScript 2020 ES11
--------------------------

####  BigInt
Write  ‘n’ at the end of the integer number which is beyond MAX_SAFE_INTEGER to prevent browser from crashing because of the large number.
BigInt is one of the most anticipated feature of javascript. 
```
let num = Number.MAX_SAFE_INTEGER;
console.log(num);
//9007199254740991 is the max-number in integer which javascript can handle
```
```
let newNum = 9007199254740991n + 15n;
console.log(newNum);                    //console: 9007199254741006n

console.log(typeof(newNum));    //console: bigint
```
