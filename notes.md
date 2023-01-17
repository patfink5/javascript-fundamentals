## Javascript Fundamentals

### Executing Javascript
Javascript can be executed on a webpage in a number of ways, including:
- Executed directly in the console
- In a script tag within an html file
- In an external script, linked in your html document

### Variables
- Variables can be created using 'let', 'const' or 'var'.
- variables should only be declared once; repeated declarations result in an error. To overwrite a mutable variable, you just set the existing variable equal to a new value. Variables declared using 'const' are unmutable.
- Best Practices for naming:
    - Aliases for difficult to remember values known prior to execution, like color hex-codes, are stored as caps with underscores, e.g. COLOR_RED
    - Typical variables written in camelCase
- To determine the variable type, use: typeof
- Common Data Types
    - Number, represents integers and floating point numbers
    - BigInt, for integer values that are greater than 2^53 in length
    - Strings
    - Booleans
    - Undefined, null are special values
    - Objects, used to store collections of data and more complex entities
### Expressions    
- If / Else syntax:
    ```
    let shoppingDone = false;
    let childsAllowance;

    if (shoppingDone === true) {
    childsAllowance = 10;
    } else {
    childsAllowance = 5;
    }
    ```
- Switch Statements: takes a single expression/value as an input, and then look through several choices until they find one that matches that value, executing the corresponding code that goes along with it. Syntax:
    ```
    switch (expression) {
    case choice1:
        run this code
        break;

    case choice2:
        run this code instead
        break;

    // include as many cases as you like

    default:
        actually, just run this code
    }
    ```
- Ternary Operator:  Tests a condition and returns one value/expression if it is true, and another if it is false. Can only take 2 choices, but can be more readable than 'if else' statements. Syntax:
    ```
    condition ? run this code : run this code instead

    #Example:
    const greeting = isBirthday
    ? 'Happy birthday Mrs. Smith — we hope you have a great day!'
    : 'Good morning Mrs. Smith.';
    ```

### Functions
- Invoking Functions, syntax:
    ```
    function myFunction() { --Define the function
    alert('hello');
    }

    myFunction(); -- executes the function once
    ```
- Parameters: You can include parameters within the parens when defining the function. If you leave it as empty, the function will typically adopt a default behavior.

- In the above example, we define a function explicitly. However, you can create functions without names. This will often be the case when a function expects to receive another function as a paramter. 

- Return Values: Named simply, return values are the values that are returned when a function completes running. To return a value from a custom function, you need to use the return keyword. Example:
    ```
    function random(number) {
  const result = Math.floor(Math.random() * number);
  return result;
    }
    ```

### Arrays
- Syntax: ``` const array_name = [item1, item2, ...];  ```
- Best Practices: 
    - Declare arrays with the ```const``` keyword
    - Spaces and linebreaks are not needed. Separate items with a comma, within square brackets.
    - You can also create an array, then provide elements:
    ```
    const cars = [];
    cars[0]= "Saab";
    cars[1]= "Volvo";
    cars[2]= "BMW";
    ```
- Built-in Array Methods:
    - ```toString()``` converts an array to a string of (comma separated) array values
    - Similarly, ```join()``` joins all array elements into a string, but you specify the separator.
    - ```pop()``` method removes the last element from an array
    - ```push()``` method adds a new element to an array (at the end)
    - ```shift()``` method removes the first array element and "shifts" all other elements to a lower index.
    - ```unshift()``` method adds a new element to an array (at the beginning), and "unshifts" older elements

- Changing Elements: 
