# JavaScript-Notes


## Variables and Statements:
Semicolons used to end a statement. You can choose to not write them *(because there is ASI: Automatic Semicolon Insertion in Javascript)*.

### Declaring a variable:

`var **first** = 'Mayank';` 

`let **first** = 'Mayank';`

`const **first** = 'Mayank';`

(here value is 'Mayank')

- `let` and `const` were introduced in ES6 (newer).
- `var` and `let` can be updated but not `const`.

    ```jsx
    var x = 'hey';
    y = 'hi';

    let cool = true;
    cool = false;

    const age = 10;
    age = 11; // wrong: throws error
    ```

- In **strict mode**, we have to define a variable first before assigning a value to it.

    ```jsx
    dog = 'snickers'; // bad coding, don't do this
    console.log(dog); // snickers (no error) 

    'use strict';
    dog = 'snickers'; // error: dog is not defined
    ```

- If we write `var dog;` dog is *undefined.*
- **Scoping:**

   - **var** : *function scoped* (only available inside parent functions)

   - **let** and **const** : *block scoped* (available inside a block denoted by *{ }* )

- **Opinion (what to use):** Use `const` by default; if the value of the variable needs to change then use `let`. Almost never use `var`.
- **Variable naming conventions:**
    - Should not start with capital unless they are a *class*.
    - Must start with **a-z** or **_** or **$**.
    - If a variable is multi-word, you can use:
        - *Camel-case:* `let iLovePizza = true;`
        - *Upper Camel case (in case of classes):* `ILovePizza`
        - *Snake case: `let i_love_pizza=true;`*
    


## Types:
1. String
2. Number
3. Object
4. Boolean
5. Undefined
6. Symbol : Always gives a guaranteed unique identifier
7. Null

Everything except Object is Primitive type, Object is special one.


### Strings:
- used for holding text
- 3 ways to create strings:
    1. using single quotes:

        `const first = 'Soumya';`

    2. using double quotes:

        `const middle = "Ranjan";`

    3. using backticks:

        ```jsx
        	const last = `Mohanty`;
        ```

- single quotes and double quotes are the same thing.

    used for: `"she's cool"` 

    or escaping: `'she\'s cool'`

- backticks:

    ```jsx
    const sentence = `she's so "cool"`;
    console.log(sentence); // she's so "cool"
    ```

- Multi-line string:

    1.

    ```jsx
    const song = 'Oh \
    I like \
    pizza';

    console.log(song); // Oh I like pizza
    ```

    2.

    ```jsx
    const song = `Oh
    I like
    pizza`;

    console.log(song); 
    /*
    Oh
    I like
    pizza
    */
    ```

    2nd one using backticks is mostly used.
    
   
 
 ### Numbers:
    Only **one** type of number in JavaScript whether it has decimal point or not.

```jsx
const age = 100;
const money = 1000.50
console.log(typeof age); // number
console.log(typeof money); // number
```

- `typeof` is used to find out the 'type' of a variable.
- Various operations: addition, subtraction, multiplication, division can be done with nos.
- Example

```jsx
"10" * "10" // 100 (number) - converts the strings to number
```

The above works with *multiplication, division and subtraction and not addition,* because the + sign is also used for concatenation.

- **Math helper methods:**
    - **Math.round, Math.floor, Math.ceil, Math.random** and many others

        ```jsx
        Math.round(2.5); // 3
        Math.floor(2.4); // 2
        Math.ceil(2.4); // 3
        Math.random(); // 0.565262543048269 - random no. between 0 and 1
        ```

- **Modulo and Power operators:**

    ```jsx
    const smarties = 20;
    const kids = 3;
    const eachKidGets = Math.floor(smarties/kids); // 6
    const leftSmarties = smarties % kids; // 2 - modulo operation

    const x = 2 ** 3; // 8 - power operation using power operator (**)
    // or
    const x = Math.pow(2,3); // 8 - power operation using Math.pow
    ```

- Example

```jsx
0.1 + 0.2 // 0.30000000000000004
```

Why? [Explanation](http://0.30000000000000004.com/)

So, when working with money, don't store them as dollars and cents. Store all of the money in cents  as you won't have to deal with fractions only whole nos. When need to display to user, just convert them back.

- **Infinity and Negative Infinity:**

 `typeof Infinity; // number`

 `typeof -Infinity; // number`

- **Not a Number (NaN):**

`10 / 'dog' // NaN`

`typeof NaN // number`


### Objects:
- Everything in JavaScript is an Object.
- Objects are used for collection of data, collection of functionality.
- Example:

    ```jsx
    const person = {
    	name: 'Soumya', // property: value
    	age: 100
    };

    typeof person // object

    person.age = 101;
    console.log(person.age); // 101
    ```


### Null and Undefined:
- Order of properties doesn't matter in an object.
- **Accessing properties:**
    - `person.name // Soumya` (dot notation)



- Used to express 'nothing' in JavaScript.
- If we declare a variable, and don't set anything to it, then it has value `undefined`.

    ```jsx
    let dog;
    console.log(dog); // undefined
    ```

    When we try to access a variable that is created but not defined/set a value, we get `undefined`.

- **null:** value of nothing

    ```jsx
    const somethingNull = null;
    // we have explicitly set the value to be nothing with null
    ```
    
    
    ### Booleans and Equality:
    - A **boolean** variable can be either `true` or `false` .
- Example:

    ```jsx
    const age = 18;
    const ofAge = age > 18;
    console.log(ofAge); // false
    ```

- **Equal signs:**
    - `=` sign: used for assignment/ updation of values

        ```jsx
        let name = 'Soumya';
        name = 'Raja';
        ```

    - Out of `==` and `===`, you should **almost always** use `===`.
    - `==` and `===` are used for equality comparison.

        ```jsx
        console.log(age === 18); // true
        ```

    - `==` vs `===` :

        `===` checks both **type & value.**

        `==` only checks **value.**

        ```jsx
        10 === "10" // false as values are same but types are not
        10 == "10" // true as values are same
        ```
    
## Functions:
### Built in:

- Function allows us to *group together multiple statements,* take in some values, perform some operations and return some value.
- Functions take in data known as *arguments.*
- Function may or may not *return* a value.
- Example:

    ```jsx
    Math.max(10, 12); // 12
    ```

- There are many in-built JavaScript functions.

    e.g: 

    - `console.log('hey');` returns `undefined` , logs `hey`.
    - `parseFloat('2.032565') // 2.032565` (converts string to number)
    - `parseInt('2.032565') // 2` (converts string to number as integer)
    - Many date functions are also present. e.g. `Date.now()` returns no. of milliseconds since January 1, 1970 00:00:00 UTC.
    - DOM functions:
        - Example:

            ```jsx
            <body>
            <p>Hey How ya doin?</p>
            	<script>
            		const para = document.querySelector('p'); // finds p tag in page
            		console.log(para); // <p>Hey How ya doin?</p>
            	</script>
            </body>

            ```

        - Mobile only functions e.g. `navigator.vibrate()`

- Other Examples:

    ```jsx
    scrollTo(0, 200); // scrolls to (x, y) position in page

    scrollTo({
    	top: 500,
    	left: 0,
    	behavior: 'smooth'
    }); // scrolls to position top: 500, left: 0 in a 'smooth' manner
    ```

    The `scrollTo` function returns `undefined`.
    
    ### Custom:
    
    - Functions are **created/ defined** then they are **called**.
- Defining a function:

    ```jsx
    // Function definition

    function calculateBill() {
    	// this is the function body
    	console.log('running calculateBill');
    }
    ```

- Calling a function:

    ```jsx
    // Function call or run

    calculateBill(); // running calculateBill (returns undefined)
    ```

- Variables created inside a function are not available outside the function. e.g. `total` above.

    It is a **temporary variable.** After running of the function is complete, the variable is cleaned up or garbage-collected.

- **Returning value from function:**

    ```jsx
    function calculateBill() {
    	const total = 100 * 1.13;
    	return total; // total is returned
    }

    calculateBill(); // returns 112.999999999
    ```

- Capturing returned value from a function into a variable:

    `const myTotal = calculateBill();`  (myTotal will have value 112.999999999)
    
    ### Arguments & Parameters:
    
    - Parameters are like *placeholders* for data that will be passed to a function.
- Arguments are the actual values passed to a function while calling it

```jsx
function calculateBill(billAmount, taxRate) { // here billAmount, taxRate are parameters
  const total = billAmount + billAmount * taxRate 
  return total;
}

calculateBill(100, 0.13); // here 100, 0.13 are arguments
```

![https://res.cloudinary.com/geekysrm/image/upload/v1576699296/parameters-arguments.jpg](https://res.cloudinary.com/geekysrm/image/upload/v1576699296/parameters-arguments.jpg)

- Parameters are variables local to the function; available only inside the function.
- You can also pass variables as arguments during a function call.
- We can also pass *expressions* as arguments to a function.

    ```jsx
    myTotal3 = calculateBill(20+20+30, 0.3);
    ```

- So, we can either pass direct value or variables holding value or expressions resulting in a value to a function as arguments.
- **Passing functions as arguments:**

    ```jsx
    function doctorize (name) { 
    	return `Dr. ${name}`;
    }

    function yell (name) {
    	return `HEY ${name.toUpperCase()}`;
    }

    // We can pass a function inside another
    yell(doctorize('Soumya')); // HEY DR. SOUMYA
    // Above, returned value of doctorize function is passed to yell function
    ```

    - Default values:

        ```jsx
        function yell (name = 'Silly Goose') {
        	return `HEY ${name.toUpperCase()}`;
        }

        yell('Soumya') // HEY SOUMYA
        yell() // HEY SILLY GOOSE

        // Above, if we don't pass any argument to yell function, then it takes the default value in function definition,
        // here Silly Goose, else it takes whatever we pass as argument.
        ```

    - **Important gotcha:**

        ```jsx
        function calculateBill(billAmount, taxRate = 0.13, tipRate = 0.15) {
          console.log('Running Calculate Bill!!');
          const total = billAmount + billAmount * taxRate + billAmount * tipRate;
          return total;
        }

        // Suppose above, we want to pass the tipRate but not the taxRate and want taxRate to be default,
        // then the only thing we can do is:
         
        calculateBill(100, undefined, 0.66); // here the taxRate will default to 0.13 as 
        // we have passed undefined to it and the tipRate will be 0.66 as passed
        ```

## Different ways to declare functions:

- Functions are **First class citizens:**
    - It means JavaScript functions are values in themselves. They can be stored in variables and passed into other functions, just like any other piece of data in JavaScript. (see 3rd example below)
- **With function keyword**

    *Important:* These are **hoisted**, meaning JavaScript 'hoists' or puts them at the top of the file. So if we try to run a function defined with function keyword before it is defined/ above its definition, there's no error and the function is executed successfully.

    ```jsx
    function doctorize(firstName) {
       return `Dr. ${firstName}`;
    }
    ```

- **Anonymous function - function with no name**

    These are used in *callbacks* and *IIFE: immediately invoked function expressions*.

    ```jsx
    function (firstName) {
     return `Dr. ${firstName}`;
    }
    ```

- **Function Expression**

    *Important:* These are **not hoisted**, meaning JavaScript doesn't put them at the top of the file. So if we try to run a function not defined with function keyword before it is defined/ above its definition, there's an error and the function fails to execute.

    ```jsx
    const doctorize = function(firstName) {
       return `Dr. ${firstName}`;
     };
    ```

- **Arrow Functions**
    - Concise, shorter syntax
    - Don't have own scope in refer to 'this' keyword
    - Are anonymous functions

    ```jsx
    const inchToCM = (inches) => {
    	return inches * 2.54;
    }

    // Implicit return:
    const add = (a, b = 3) => a + b;
    const inchToCM = (inches) => inches * 2.54;

    // In case of only 1 parameter, we can omit the () around it
    const inchToCM = inches => inches * 2.54;

    ```

    - Implicitly returning an object:

        ```jsx
        const makeABaby = (first, last) => ({ name: `${first} ${last}`, age: 0 });
        ```

- **IIFE: Immediately Invoked Function Expression**

    ```jsx
    (function(age) {
      return `You are cool and age ${age}`;
    })(10);

    // Parantheses run first in JavaScript, so we have wrapped the function in ().
    // The function immediately runs.
    // The argument passed here is 10 for parameter age.
    ```

- **Methods:**
    - A function which lives inside an object.
    - For e.g `console.log('hey')`  : here `log` is the function and `console` is the object.
    - **2 Ways to define methods:**

        ```jsx
        const wes = {
          name: 'Westopher Bos',
          // Method!
          sayHi: function() {
            console.log(`Hey ${this.name}`);
            return 'Hey Wes';
          },
          // Arrow function
          wisperHi: () => {
            console.log('hii wesss im a mouse');
          },
          // Short hand Method
          yellHi() {
            console.log('HEY WESSSSS');
          }
        }
        ```

- **Callback functions:**
    - Function that is passed to another function used for something that will happen when something is done.

    ```html
    <body>
      <button class="clickMe">Click Me!</button>
    </body>
    ```

    ```jsx
    // Click Callback
    const button = document.querySelector('.clickMe');

    function handleClick() {
      console.log('Great Clicking!!');
    }

    button.addEventListener('click', handleClick);
    // everytime we click the button, the handleClick function is run.

    button.addEventListener('click', function() {
      console.log('Nice Job!!!');
    });
    // everytime we click the button, the function inside is run.

    // Timer Callback
    setTimeout(() => {
      console.log('DONE! Time to eat!');
    }, 1000);
    // it runs the console.log after each 1 sec or 1000 milliseconds
    ```

## The DOM - Working with HTML and CSS:

### Selecting Elements:
![Capture](https://user-images.githubusercontent.com/52233220/113087637-b25d1780-9201-11eb-921f-12014d7a20a6.PNG)
