# JavaScript Variables

## assignment02

1.  What is a variable in JavaScript?

    - "A variable in JavaScript is a container for storing data values. It allows us to store, update, and retrieve information in a program. We can declare variables using `var`, `let`, or `const`, with `let` and `const` being preferred in modern JavaScript due to better scoping rules."

2.  What are the variable naming conventions in JavaScript?

    - In JavaScript, variable naming conventions follow these rules:

    **Must start with a letter, `_`, or `$`** (e.g., `firstName`, `_privateVar`, `$price`).  
    **Cannot use reserved keywords** like `let`, `const`, `if`, etc.  
    **Case-sensitive** (`myVar` and `myvar` are different).  
    **Use camelCase for variables and functions** (e.g., `userName`, `totalAmount`).  
    **Use uppercase for constants** (e.g., `MAX_LIMIT`).  
    **Be descriptive** (e.g., `userAge` instead of `x`).

3.  What is the difference between declaration, initialization, and re-assignment?

    **Declaration:** Declaring a variable means creating it using `var`, `let`, or `const` without assigning a value.

    ```javascript
    let x; // Declared but not initialized
    ```

    **Initialization:** Assigning an initial value to a declared variable.

    ```javascript
    let x = 10; // Declared and initialized
    ```

    **Re-assignment:** Updating the value of a variable after initialization.

    ```javascript
    x = 20; // Re-assigned a new value
    ```

    🔹 **`const` variables cannot be re-assigned after initialization.**

4.  What are the different types of scope in JavaScript?

    - In JavaScript, there are three main types of scope:

    **Global Scope** – Variables declared outside any function or block are accessible anywhere in the script.  
    **Function Scope** – Variables declared with `var` inside a function are only accessible within that function.  
    **Block Scope** – Variables declared with `let` and `const` inside a block (`{}`) are only accessible within that block.

    **Example:**

    ```javascript
    var globalVar = "I am global"; // Global Scope

    function testFunction() {
      var functionVar = "I exist only in this function"; // Function Scope
    }

    if (true) {
      let blockVar = "I exist only inside this block"; // Block Scope
      const blockConst = "I am also block-scoped";
    }
    ```

    In modern JavaScript, `let` and `const` are preferred due to their block scope, which helps avoid unintended variable overwrites.

5.  What does scope mean in the context of Javascript variables?

    - In JavaScript, **scope** refers to the accessibility of variables in different parts of the code. There are three main types:

    **Global Scope** – Variables declared outside functions are accessible anywhere in the script.  
    **Function Scope** – Variables declared with `var` inside a function are accessible only within that function.  
    **Block Scope** – Variables declared with `let` or `const` inside a block `{}` are only accessible within that block.

    Using `let` and `const` ensures better scope management, preventing unintended variable access or modification.

6.  What are let, var, and const? What is the difference between them?

    - **`var`, `let`, and `const`** are used to declare variables in JavaScript, but they have different scopes and behaviors:

    **`var`** – Function-scoped, can be re-declared and updated, but has issues like hoisting and lack of block scope.  
    **`let`** – Block-scoped, can be updated but not re-declared in the same scope, making it safer than `var`.  
    **`const`** – Block-scoped, cannot be re-assigned, ensuring the value remains constant (though objects and arrays can still be modified).

    **Key Difference:** `var` is function-scoped, while `let` and `const` are block-scoped. `const` prevents reassignment, while `let` allows it.

7.  How do you determine the typeof() variable in javascript?

    - You can determine the type of a variable in JavaScript using the `typeof` operator.

    ### Example:

    ```javascript
    console.log(typeof "Hello"); // "string"
    console.log(typeof 42); // "number"
    console.log(typeof true); // "boolean"
    console.log(typeof {}); // "object"
    console.log(typeof null); // "object" (this is a known JavaScript quirk)
    console.log(typeof undefined); // "undefined"
    console.log(typeof function () {}); // "function"
    ```

    - "In JavaScript, we use the `typeof` operator to determine the data type of a variable. It helps in debugging and type checking. However, we should be aware that `typeof null` returns `'object'` due to a historical bug in JavaScript."

8.  What is hoisting? Explain with a code e.g.

    - **Hoisting** in JavaScript is a behavior where variable and function declarations are moved (or "hoisted") to the top of their scope before code execution. This means you can use variables and functions before they are declared in the code.

    ### **Example of Hoisting:**

    ```javascript
    console.log(a); // undefined (due to hoisting)
    var a = 10;

    foo(); // Works because function declarations are fully hoisted
    function foo() {
      console.log("Hello, Hoisting!");
    }
    ```

    ### **Explanation:**

    - Variables declared with `var` are hoisted but initialized with `undefined`.
    - Functions declared with `function` are fully hoisted, meaning they can be called before their declaration.
    - `let` and `const` variables are hoisted but remain in a **temporal dead zone (TDZ)** until they are assigned a value.

9.  What is a temporal dead zone (TDZ)?

    - A **Temporal Dead Zone (TDZ)** in JavaScript is the period between the start of a variable’s scope and its initialization where accessing the variable results in a **ReferenceError**. This happens with `let` and `const` because they are hoisted but remain **uninitialized** until their declaration is encountered in the code.

    ### Example:

    ```javascript
    console.log(x); // ReferenceError: Cannot access 'x' before initialization
    let x = 10;
    ```

    ### Key Points:

    - Only affects `let` and `const` (not `var`).
    - Prevents access before initialization.
    - Helps catch bugs related to accessing variables too early.

10. Create a greeting alert. Hint:(use => prompt, variable-message, alert)

    - Here's a short interview-style answer:

    ```javascript
    let name = prompt("Enter your name:");
    let message = `Hello, ${name}! Welcome to our site.`;
    alert(message);
    ```

    **Explanation:**

    - `prompt()` asks the user for their name.
    - The input is stored in the `name` variable.
    - A greeting message is created using template literals.
    - `alert()` displays the message in a pop-up box.

11. Write some code so that the values of the below variables switch around Let a = 5, let b = 8. Switch the value so that a holds the value 8 and the variable b holds the value.

    - A short and efficient way to swap the values of `a` and `b` in JavaScript is by using **destructuring assignment**:

    You can swap the values of `a` and `b` without using a temporary variable by using **array destructuring**:

    ```javascript
    let a = 5;
    let b = 10;

    let temp = a;
    a = b;
    b = temp;

    console.log(a); // 10
    console.log(b); // 5
    ```

# Javascript Simple Quiz on Variables

1. : Variables defined with let cannot be redeclared.
   - a. True
   - b. False

- Answer a.True

2. Select whether the below JS code is valid or not:

   ```javascript
   let x = "Hello Peter Doe";
   let x = 0;
   ```

   - a. Valid
   - b. Invalid

- Answer b. Invalid

3. Select whether the below JS code is valid or not:

   ```javascript
   var x = "John Doe";
   var x = 0;
   ```

   - a. Valid
   - b. Invalid

- Answer a. Valid

4. Variables defined with const cannot be Reassigned.
   - a. True
   - b. False

- Answer a. True

5. Variables defined with const can be Redeclared.
   - a. True
   - b. False

- Answer b. False

6. Select whether the below JS code is valid or not:

   ```javascript
   const PI = 3.141592653589793;
   PI = 3.14;
   ```

   - a. Valid
   - b. Invalid

- Answer b. Invalid

7. Select whether the below JS code is valid or not:

   ```javascript
   const PI = 3.141592653589793;
   PI = PI + 10;
   ```

   - a. Valid
   - b. Invalid

- Answer b. Invalid

8. A value must be assigned to a const variable when it is declared
   - a. True
   - b. False

- Answer a. True

9. Select whether the below JS code is valid or not:

   ```javascript
   const PI;
   PI = 3.14159265359;
   ```

   - a. Valid
   - b. Invalid

- Answer b. Invalid

10. Select whether the below JS code is valid or not:

    ```javascript
    const cars = ["Ford", "Honda", "BMW"];
    cars[0] = "Nissan";
    ```

    - a. Valid
    - b. Invalid

- Answer a. Valid

11. Select whether the below JS code is valid or not:

    ```javascript
    const cars = ["Ford", "Honda", "BMW"];
    cars = ["Toyota", "Suzuki", "Audi"];
    ```

    - a. Valid
    - b. Invalid

- Answer b. Invalid

12. Select whether the below JS code is valid or not:

    ```javascript
    var x = 2;
    var x = 3;
    ```

    - a. valid
    - b. invalid

- Answer a. Valid

13. Select whether the below JS code is valid or not:

    ```javascript
    const x = 2;
    {
      const x = 3;
    }
    {
      const x = 4;
    }
    ```

    - a. Valid
    - b. Invalid

- Answer a. Valid

14. What will be the console output of the below javascript code?
    ```javascript
    const a = 34;
    let b = 56;
    console.log((a = b));
    ```
    - a. Uncaught type error: Assignment to constant
      variable
    - b. 56
    - c. False
    - d. 34

- Answer a. Uncaught type error: Assignment to constant
  variable
