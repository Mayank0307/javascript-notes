# javascript-notes
Semicolons used to end a statement. You can choose to not write them *(because there is ASI: Automatic Semicolon Insertion in Javascript)*.

### Declaring a variable:

`var**first** = 'Soumya';` 

`let**first** = 'Soumya';`

`const**first** = 'Soumya';`

(here value is 'Soumya')

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
