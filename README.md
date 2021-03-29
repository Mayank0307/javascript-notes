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

- **String concatenation and interpolation**
    - '+' is used for **concatenation**. It is also used for adding 2 nos.
    - **Concatenation**: when 2 or more strings combined to one
    - **Interpolation**: when you put a variable inside a string
    - Example 1:

    `const name = 'Soumya';`

    `const hello = 'Hello my name is ' + name + '. Nice to meet you.'`

    *(can use double or single quotes)*

    - Example 2:

    ```jsx
    1+1 // 2
    '1'+'1' // 11
    1 + '1' // 11
    ```

    - Example 3:

    ```jsx
    const name = 'Soumya';
    const hello = `Hello my name is ${name}. Nice to meet you. I am ${100+1} years old.`;
    console.log(hello); // Hello my name is Soumya. Nice to meet you. I am 101 years old.
    ```

    - Backticks also used for *tagged template literals*.
    - Backticks are helpful for creating HTML:

        ```jsx
        const html = `
        	<div>
        		<h2>Hey everyone! I am ${name}.</h2>
        	</div>
        `;
        ```
