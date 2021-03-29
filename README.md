# javascript-notes

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
    


### Types:
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
    
