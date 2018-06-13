=================================Question:
Basic JavaScript: Profile Lookup

We have an array of objects representing different people in our contacts lists.

A lookUpProfile function that takes name and a property (prop) as arguments has been pre-written for you.

The function should check if name is an actual contact's firstName and the given property (prop) is a property of that contact.

If both are true, then return the "value" of that property.

If name does not correspond to any contacts then return "No such contact"

If prop does not correspond to any valid properties of a contact found to match name then return "No such property"

```JavaScript
*******Answer*********
function lookUpProfile(name, prop){
// Only change code below this line
  // answer = ""
    var answer = "No such contact";
  contacts.some(function(arg) {
    if (name != arg.firstName) {
      answer = answer
    } else if (arg.hasOwnProperty(prop) === false) {
      answer = "No such property";
    } else if(name == arg.firstName && arg.hasOwnProperty(prop) == true){answer = arg[prop]; }
  });
  return answer;

// Only change code above this line
}
```
// Change these values to test your function
lookUpProfile("Akira", "likes");

====================Basic JavaScript: Generate Random Whole Numbers with JavaScript

It's great that we can generate random decimal numbers, but it's even more useful if we use it to generate random whole numbers.

    Use Math.random() to generate a random decimal.
    Multiply that random decimal by 20.
    Use another function, Math.floor() to round the number down to its nearest whole number.

Remember that Math.random() can never quite return a 1 and, because we're rounding down, it's impossible to actually get 20. This technique will give us a whole number between 0 and 19.

Putting everything together, this is what our code looks like:

Math.floor(Math.random() * 20);

We are calling Math.random(), multiplying the result by 20, then passing the value to Math.floor() function to round the value down to the nearest whole number.

Use this technique to generate and return a random whole number between 0 and 9.

```JavaScript
**********Answer***********
function randomWholeNum() {

  // Only change code below this line.
  var answer = "",
  x = ""
  x= Math.floor(Math.random() * 20);
  if (x > 9) {
    x = Math.floor(Math.random() * 10)
    answer = x
  }else{ answer = x}
  return answer;

}
```

===========================Question
Basic JavaScript: Generate Random Whole Numbers within a Range

Instead of generating a random number between zero and a given number like we did before, we can generate a random number that falls within a range of two specific numbers.

To do this, we'll define a minimum number min and a maximum number max.

Here's the formula we'll use. Take a moment to read it and try to understand what this code is doing:

Math.floor(Math.random() * (max - min + 1)) + min

Create a function called randomRange that takes a range myMin and myMax and returns a random number that's greater than or equal to myMin, and is less than or equal to myMax, inclusive.


```JavaScript
*****************Answer***************
// Example
function ourRandomRange(ourMin, ourMax) {

  return Math.floor(Math.random() * (ourMax - ourMin + 1)) + ourMin;
}

ourRandomRange(1, 9);

// Only change code below this line.

function randomRange(myMin, myMax) {

  return Math.floor(Math.random() * (myMax - myMin + 1)) + myMin;;
   // Change this line

}

// Change these values to test your function
var myRandom = randomRange(5, 15);
```


==================================Question
Basic JavaScript: Use the parseInt Function

The parseInt() function parses a string and returns an integer. Here's an example:

var a = parseInt("007");

The above function converts the string "007" to an integer 7. If the first character in the string can't be converted into a number, then it returns NaN.

Use parseInt() in the convertToInteger function so it converts the input string str into an integer, and returns it.


```JavaScript
*********************Answer**********
function convertToInteger(str) {
   return parseInt(str)
}

convertToInteger("56");


```

================================Question
Basic JavaScript: Use the Conditional (Ternary) Operator

The conditional operator, also called the ternary operator, can be used as a one line if-else expression.

The syntax is:

```JavaScript
condition ? statement-if-true : statement-if-false;

The following function uses an if-else statement to check a condition:

    function findGreater(a, b) {
    if(a > b) {
    return "a is greater";
    }
    else {
    return "b is greater";
    }
    }

This can be re-written using the conditional operator:

    function findGreater(a, b) {
    return a > b ? "a is greater" : "b is greater";
    }
```

Use the conditional operator in the checkEqual function to check if two numbers are equal or not. The function should return either true or false.


```JavaScript
******************Answer*************
function checkEqual(a, b) {

return a == b ? true:false;
}


checkEqual(1, 2);

```

===============================Question
Basic JavaScript: Use Multiple Conditional (Ternary) Operators

In the previous challenge, you used a single conditional operator. You can also chain them together to check for multiple conditions.

The following function uses if, else if, and else statements to check multiple conditions:

```JavaScript
    function findGreaterOrEqual(a, b) {
    if(a === b) {
    return "a and b are equal";
    }
    else if(a > b) {
    return "a is greater";
    }
    else {
    return "b is greater";
    }
    }
```

The above function can be re-written using multiple conditional operators:
```JavaScript
    function findGreaterOrEqual(a, b) {
    return (a === b) ? "a and b are equal" : (a > b) ? "a is greater" : "b is greater";
    }
```
Use multiple conditional operators in the checkSign function to check if a number is positive, negative or zero.

```JavaScript
***************************Answer
function checkSign(num) {
  return (num == 0) ? "zero" :(num > 0) ? "positive": "negative" ;
}

checkSign(10);

```

==============================Questions
ES6: Explore Differences Between the var and let Keywords

One of the biggest problems with declaring variables with the var keyword is that you can overwrite variable declarations without an error.

```JavaScript
    var camper = 'James';
    var camper = 'David';
    console.log(camper);
    // logs 'David'
```

As you can see in the code above, the camper variable is originally declared as James and then overridden to be David.

In a small application, you might not run into this type of problem, but when your code becomes larger, you might accidentally overwrite a variable that you did not intend to overwrite.

Because this behavior does not throw an error, searching and fixing bugs becomes more difficult.

A new keyword called let was introduced in ES6 to solve this potential issue with the var keyword.

If you were to replace var with let in the variable declarations of the code above, the result would be an error.

    let camper = 'James';
    let camper = 'David'; // throws an error

This error can be seen in the console of your browser.

So unlike var, when using let, a variable with the same name can only be declared once.

Note the "use strict". This enables Strict Mode, which catches common coding mistakes and "unsafe" actions. For instance:

    "use strict";
    x = 3.14; // throws an error because x is not declared

Update the code so it only uses the let keyword.

```JavaScript
********************Answer***********
let catName;
let quote;
function catTalk() {
  "use strict";

  catName = "Oliver";
  quote = catName + " says Meow!";

}
catTalk();

```
=========================Question=======
ES6: Compare Scopes of the var and let Keywords

When you declare a variable with the var keyword, it is declared globally, or locally if declared inside a function.

The let keyword behaves similarly, but with some extra features. When you declare a variable with the let keyword inside a block, statement, or expression, its scope is limited to that block, statement, or expression.

For example:
```JavaScript
    var numArray = [];
    for (var i = 0; i < 3; i++) {
    numArray.push(i);
    }
    console.log(numArray);
    // returns [0, 1, 2]
    console.log(i);
    // returns 3
```
With the var keyword, i is declared globally. So when i++ is executed, it updates the global variable. This code is similar to the following:
```JavaScript
    var numArray = [];
    var i;
    for (i = 0; i < 3; i++) {
    numArray.push(i);
    }
    console.log(numArray);
    // returns [0, 1, 2]
    console.log(i);
    // returns 3
```
This behavior will cause problems if you were to create a function and store it for later use inside a for loop that uses the i variable. This is because the stored function will always refer to the value of the updated global i variable.
```JavaScript
    var printNumTwo;
    for (var i = 0; i < 3; i++) {
    if(i === 2){
    printNumTwo = function() {
    return i;
    };
    }
    }
    console.log(printNumTwo());
    // returns 3
```
As you can see, printNumTwo() prints 3 and not 2. This is because the value assigned to i was updated and the printNumTwo() returns the global i and not the value i had when the function was created in the for loop. The let keyword does not follow this behavior:
```JavaScript
    'use strict';
    let printNumTwo;
    for (let i = 0; i < 3; i++) {
    if (i === 2) {
    printNumTwo = function() {
    return i;
    };
    }
    }
    console.log(printNumTwo());
    // returns 2
    console.log(i);
    // returns "i is not defined"
```
i is not defined because it was not declared in the global scope. It is only declared within the for loop statement. printNumTwo() returned the correct value because three different i variables with unique values (0, 1, and 2) were created by the let keyword within the loop statement.

Fix the code so that i declared in the if statement is a separate variable than i declared in the first line of the function. Be certain not to use the var keyword anywhere in your code.

This exercise is designed to illustrate the difference between how var and let keywords assign scope to the declared variable. When programming a function similar to the one used in this exercise, it is often better to use different variable names to avoid confusion.


```JavaScript
************************Answer
function checkScope() {
"use strict";
  let i = "function scope";

  if (true) {
   let i = "block scope";
    console.log("Block scope i is: ", i);
  }
  console.log("Function scope i is: ", i);
  return i;
}

```
==================================Question

ES6: Mutate an Array Declared with const

The const declaration has many use cases in modern JavaScript.

Some developers prefer to assign all their variables using const by default, unless they know they will need to reassign the value. Only in that case, they use let.

However, it is important to understand that objects (including arrays and functions) assigned to a variable using const are still mutable. Using the const declaration only prevents reassignment of the variable identifier.


```JavaScript
    "use strict";
    const s = [5, 6, 7];
    s = [1, 2, 3]; // throws error, trying to assign a const
    s[2] = 45; // works just as it would with an array declared with var or let
    console.log(s); // returns [5, 6, 45]
```
As you can see, you can mutate the object [5, 6, 7] itself and the variable s will still point to the altered array [5, 6, 45]. Like all arrays, the array elements in s are mutable, but because const was used, you cannot use the variable identifier s to point to a different array using the assignment operator.

An array is declared as const s = [5, 7, 2]. Change the array to [2, 5, 7] using various element assignment.


```JavaScript
**********************Answer
const s = [5, 7, 2];
function editInPlace() {
  "use strict";
  // change code below this line
  s[0] = 2;
  s[1] = 5;
  s[2] = 7
  // s = [2, 5, 7]; <- this is invalid

  // change code above this line
}
editInPlace();

```
===================================Question

ES6: Prevent Object Mutation

As seen in previous challenge, const declaration alone doesn't really protect your data from mutation. To ensure your data doesn't change, JavaScript provides a function Object.freeze to prevent data mutation.

Once the object is freezed, you can no longer add/update/delete properties from it. Any attempt at changing the object will be rejected without any error.
```JavaScript
    let obj = { name:"FreeCodeCamp" review:"Awesome" }; Object.freeze(obj); obj.review = "bad"; //will be ignored. Mutation not allowed obj.newProp = "Test"; // will be ignored. Mutation not allowed console.log(obj); // { name: "FreeCodeCamp", review:"Awesome"}
```
In this challenge you are going to use Object.freeze to prevent mathematical constants from changing. You need to freeze MATH_CONSTANTS object so that noone is able alter the value of PI or add any more properties to it.


```JavaScript
*****************************Answer
function freezeObj() {
  "use strict";
  const MATH_CONSTANTS = {
    PI: 3.14
  };
  // change code below this line
    Object.freeze(MATH_CONSTANTS)

  // change code above this line
  try {
    MATH_CONSTANTS.PI = 99;
  } catch( ex ) {
    console.log(ex);
  }
  return MATH_CONSTANTS.PI;
}
const PI = freezeObj();


```
===========================Question
ES6: Use Arrow Functions to Write Concise Anonymous Functions

In JavaScript, we often don't need to name our functions, especially when passing a function as an argument to another function. Instead, we create inline functions. We don't need to name these functions because we do not reuse them anywhere else.

To achieve this, we often use the following syntax:
```JavaScript
    const myFunc = function() {
    const myVar = "value";
    return myVar;
    }
```
ES6 provides us with the syntactic sugar to not have to write anonymous functions this way. Instead, you can use arrow function syntax:
```JavaScript
    const myFunc = () => {
    const myVar = "value";
    return myVar;
    }
```
When there is no function body, and only a return value, arrow function syntax allows you to omit the keyword return as well as the brackets surrounding the code. This helps simplify smaller functions into one-line statements:
```JavaScript
    const myFunc= () => "value"
```
This code will still return value by default.

```JavaScript
***********************Answer****
  "use strict";
const magic = () => new Date();

```

==========================Question
ES6: Write Arrow Functions with Parameters

Just like a normal function, you can pass arguments into arrow functions.
```JavaScript
    // doubles input value and returns it
    const doubler = (item) => item * 2;
```
You can pass more than one argument into arrow functions as well.

Rewrite the myConcat function which appends contents of arr2 to arr1 so that the function uses arrow function syntax.


```JavaScript
********************************Answer *******
  "use strict";
const myConcat = (arr1, arr2) =>
 arr1.concat(arr2);

// test your code
console.log(myConcat([1, 2], [3, 4, 5]));
```


================================Question====

ES6: Write Higher Order Arrow Functions

It's time we see how powerful arrow functions are when processing data.

Arrow functions work really well with higher order functions, such as map(), filter(), and reduce(), that take other functions as arguments for processing collections of data.

Read the following code:
```JavaScript
    FBPosts.filter(function(post) {
    return post.thumbnail !== null && post.shares > 100 && post.likes > 500;
    })
```
We have written this with filter() to at least make it somewhat readable. Now compare it to the following code which uses arrow function syntax instead:

```JavaScript
    FBPosts.filter((post) => post.thumbnail !== null && post.shares > 100 && post.likes > 500)

```
This code is more succinct and accomplishes the same task with fewer lines of code.

Use arrow function syntax to compute the square of only the positive integers (fractions are not integers) in the array realNumberArray and store the new array in the variable squaredIntegers.

```JavaScript

***************************Answer
const realNumberArray = [4, 5.6, -9.8, 3.14, 42, 6, 8.34];
const squareList = (arr) => {
  "use strict";
  // change code below this line

  const squaredIntegers = arr
    .filter(num => num%1 ===0)
    .map(num=> num*num)

  // change code above this line
  return squaredIntegers;
};
// test your code
const squaredIntegers = squareList(realNumberArray);
console.log(squaredIntegers);

```

=================================Question
ES6: Set Default Parameters for Your Functions

In order to help us create more flexible functions, ES6 introduces default parameters for functions.

Check out this code:
```JavaScript
    function greeting(name = "Anonymous") {
    return "Hello " + name;
    }
    console.log(greeting("John")); // Hello John
    console.log(greeting()); // Hello Anonymous
```

The default parameter kicks in when the argument is not specified (it is undefined). As you can see in the example above, the parameter name will receive its default value "Anonymous" when you do not provide a value for the parameter. You can add default values for as many parameters as you want.

Modify the function increment by adding default parameters so that it will add 1 to number if value is not specified.


```JavaScript
******************************Answer
const increment = (function() {
  "use strict";
  return function increment(number, value = 1) {
    return number + value;
  };
})();
console.log(increment(5, 2)); // returns 7
console.log(increment(5)); // returns NaN
```

***Question***
ES6: Use the Rest Operator with Function Parameters

In order to help us create more flexible functions, ES6 introduces the rest operator for function parameters. With the *rest operator*, you can create functions that take a variable number of arguments. These arguments are stored in an array that can be accessed later from inside the function.

Check out this code:
```JavaScript
    function howMany(...args) {
    return "You have passed " + args.length + " arguments.";
    }
    console.log(howMany(0, 1, 2)); // You have passed 3 arguments
    console.log(howMany("string", null, [1, 2, 3], { })); // You have passed 4 arguments.
```
The rest operator eliminates the need to check the args array and allows us to apply map(), filter() and reduce() on the parameters array.

Modify the function sum so that it uses the rest operator and it works in the same way with any number of parameters.


**Answer**
```JavaScript
const sum = (function() {
  "use strict";
  return function sum(...args) {
    // const args;
    return args.reduce((acc, val) => acc + val, 0);
  };
})();
console.log(sum(1, 2, 3)); // 6
```



***Question***
ES6: Use the Spread Operator to Evaluate Arrays In-Place

ES6 introduces the spread operator, which allows us to expand arrays and other expressions in places where multiple parameters or elements are expected.

The ES5 code below uses apply() to compute the maximum value in an array:
```JavaScript
    var arr = [6, 89, 3, 45];
    var maximus = Math.max.apply(null, arr); // returns 89
```
We had to use Math.max.apply(null, arr) because Math.max(arr) returns NaN. Math.max() expects comma-separated arguments, but not an array.

The spread operator makes this syntax much better to read and maintain.
```JavaScript
    const arr = [6, 89, 3, 45];
    const maximus = Math.max(...arr); // returns 89
```
...arr returns an unpacked array. In other words, it spreads the array.

However, the spread operator only works in-place, like in an argument to a function or in an array literal. The following code will not work:
```JavaScript
    const spreaded = ...arr; // will throw a syntax error
```
Copy all contents of arr1 into another array arr2 using the spread operator.


**Answer**
```JavaScript
const arr1 = ['JAN', 'FEB', 'MAR', 'APR', 'MAY'];
let arr2;
(function() {
  "use strict";
    arr2= [...arr1]; // change this line
})();
console.log(arr2);
```

***Question***
ES6: Use Destructuring Assignment to Assign Variables from Objects

We saw earlier how spread operator can effectively spread, or unpack, the contents of the array.

We can do something similar with objects as well. Destructuring assignment is special syntax for neatly assigning values taken directly from an object to variables.

Consider the following ES5 code:
```JavaScript
    var voxel = {x: 3.6, y: 7.4, z: 6.54 };
    var x = voxel.x; // x = 3.6
    var y = voxel.y; // y = 7.4
    var z = voxel.z; // z = 6.54
```
Here's the same assignment statement with ES6 destructuring syntax:
```JavaScript
    const { x, y, z } = voxel; // x = 3.6, y = 7.4, z = 6.54
```
If instead you want to store the values of voxel.x into a, voxel.y into b, and voxel.z into c, you have that freedom as well.
```JavaScript
    const { x : a, y : b, z : c } = voxel // a = 3.6, b = 7.4, c = 6.54
```
You may read it as "get the field x and copy the value into a," and so on.

Use destructuring to obtain the length of the input string str, and assign the length to len in line.

**Answer**
```JavaScript
  "use strict";
  function getLength(str) {

  // change code below this line
  const { length: len } = str  // change this
  // change code above this line

  return len; // you must assign length to len in line

}

console.log(getLength('FreeCodeCamp'));
// Explanation const { length } = str is destructuring, so instead of writing const length = str.length you could write the first one.
// const { length : len } = str is assigning const length to len. So you dont need to write
// const len = length;
// Hope u get it :slight_smile:
```

***Question***
ES6: Use Destructuring Assignment to Assign Variables from Nested Objects

We can similarly destructure nested objects into variables.

Consider the following code:
```JavaScript
    const a = {
    start: { x: 5, y: 6},
    end: { x: 6, y: -9 }
    };
    const { start : { x: startX, y: startY }} = a;
    console.log(startX, startY); // 5, 6
```
In the example above, the variable start is assigned the value of a.start, which is also an object.

Use destructuring assignment to obtain max of forecast.tomorrow and assign it to maxOfTomorrow.

**Answer**

```JavaScript
const LOCAL_FORECAST = {
  today: { min: 72, max: 83 },
  tomorrow: { min: 73.3, max: 84.6 }
};

function getMaxOfTmrw(forecast) {
  "use strict";
  // change code below this line
  const { tomorrow: { max:maxOfTomorrow}} = forecast; // change this line
  // change code above this line
  return maxOfTomorrow;
}

console.log(getMaxOfTmrw(LOCAL_FORECAST)); // should be 84.6
```
***Question***
ES6: Use Destructuring Assignment to Assign Variables from Arrays

ES6 makes destructuring arrays as easy as destructuring objects.

One key difference between the spread operator and array destructuring is that the spread operator unpacks all contents of an array into a comma-separated list. Consequently, you cannot pick or choose which elements you want to assign to variables.

Destructuring an array lets us do exactly that:
```JavaScript
    const [a, b] = [1, 2, 3, 4, 5, 6];
    console.log(a, b); // 1, 2
```
The variable a is assigned the first value of the array, and b is assigned the second value of the array.

We can also access the value at any index in an array with destructuring by using commas to reach the desired index:
```JavaScript
    const [a, b,,, c] = [1, 2, 3, 4, 5, 6];
    console.log(a, b, c); // 1, 2, 5
```
Use destructuring assignment to swap the values of a and b so that a receives the value stored in b, and b receives the value stored in a.


**Answer**
```JavaScript
let a = 8, b = 6;
(() => {
"use strict";
// change code below this line
// const [a,b]= [8, 6];
[b,a]=[a, b]
// change code above this line
})();
console.log(a); // should be 6
console.log(b); // should be 8
```
***Question***
ES6: Use Destructuring Assignment with the Rest Operator to Reassign Array Elements

In some situations involving array destructuring, we might want to collect the rest of the elements into a separate array.

The result is similar to Array.prototype.slice(), as shown below:
```JavaScript
    const [a, b, ...arr] = [1, 2, 3, 4, 5, 7];
    console.log(a, b); // 1, 2
    console.log(arr); // [3, 4, 5, 7]
```
Variables a and b take the first and second values from the array. After that, because of rest operator's presence, arr gets rest of the values in the form of an array.

The rest element only works correctly as the last variable in the list. As in, you cannot use the rest operator to catch a subarray that leaves out last element of the original array.

Use destructuring assignment with the rest operator to perform an effective Array.prototype.slice() so that arr is a sub-array of the original array source with the first two elements omitted.


**Answer**
```JavaScript
const source = [1,2,3,4,5,6,7,8,9,10];
function removeFirstTwo(list) {
  "use strict";
  // change code below this line
   const [a,b, ...arr] = list; // change this
  // change code above this line
  return arr;
}
const arr = removeFirstTwo(source);
console.log(arr); // should be [3,4,5,6,7,8,9,10]
console.log(source); // should be [1,2,3,4,5,6,7,8,9,10];
```


***Question***
