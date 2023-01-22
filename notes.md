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

- Changing Elements: Array elements are accessed by their index number starting with [0]
    - You can overwrite an element directly
    ```
    # Change Banana to Kiwi
    const fruits = ["Banana", "Orange", "Apple", "Mango"];
    fruits[0] = "Kiwi";
    ```
    - length property provides an easy way to append a new element to an array:
    ```
    const fruits = ["Banana", "Orange", "Apple", "Mango"];
    fruits[fruits.length] = "Kiwi";
    ```
    
    - Note: You can use the delete keyword to remove elements from an array, but it will leave `undefined` holes in an array. Recommended to use pop or shift instead to remove elements.
    
    - `concat()` method creates a new array by merging (concatenating) existing arrays:
    ```
    const myGirls = ["Cecilie", "Lone"];
    const myBoys = ["Emil", "Tobias", "Linus"];

    const myChildren = myGirls.concat(myBoys);
    ```

    - `splice()` method adds new items to an array. `slice()` method slices out a piece of an array.

### Loops

- The basic loop structure is the `For...Of` loop, w/ below syntax. What the example does is: for the items in the list `cats` get the first item, assign that item to the variable `cat` and run the code in the brackets (printing it to the console). Then repeat for each item until the end of the list:
    ```
    const cats = ['Leopard', 'Serval', 'Jaguar', 'Tiger', 'Caracal', 'Lion'];

    for (const cat of cats) {
    console.log(cat);
    }
    ```
- `map()`takes each item in a collection and create a new collection containing the changed items:
    ```
    function toUpper(string) {
    return string.toUpperCase();
    }

    const cats = ['Leopard', 'Serval', 'Jaguar', 'Tiger', 'Caracal', 'Lion'];

    const upperCats = cats.map(toUpper);

    console.log(upperCats);
       // [ "LEOPARD", "SERVAL", "JAGUAR", "TIGER", "CARACAL", "LION" ]
    ```
- You can use `filter()` to test each item in a collection, and create a new collection containing only items that match:
    ```
    function lCat(cat) {
    return cat.startsWith('L');
    }

    const cats = ['Leopard', 'Serval', 'Jaguar', 'Tiger', 'Caracal', 'Lion'];

    const filtered = cats.filter(lCat);

    console.log(filtered);
    // [ "Leopard", "Lion" ]
    ```
- For Loop:
    ```
    for (initializer; condition; final-expression) {
    // code to run
    }
    ````
    -  An initializer — this is usually a variable set to a number, which is incremented to count the number of times the loop has run. It is also sometimes referred to as a counter variable.    
    -   A condition — this defines when the loop should stop looping. This is generally an expression featuring a comparison operator, a test to see if the exit condition has been met. 
    - A final-expression — this is always evaluated (or run) each time the loop has gone through a full iteration. It usually serves to increment (or in some cases decrement) the counter variable, to bring it closer to the point where the condition is no longer true.
    - Example: Calculating Squares:
    ```
    const results = document.querySelector('#results');

    function calculate() {
    for (let i = 1; i < 10; i++) {
        const newResult = `${i} x ${i} = ${i * i}`;
        results.textContent += `${newResult}\n`;
    }
    results.textContent += '\nFinished!';
    }

    const calculateBtn = document.querySelector('#calculate');
    const clearBtn = document.querySelector('#clear');

    calculateBtn.addEventListener('click', calculate);
    clearBtn.addEventListener('click', () => results.textContent = '');
    ```
- Break Statement: You can exit a loop before all iterations have completed using a break statement. E.g. if you wanted to loop through an array of phone contacts until you found a match, you can log the output and break the loop.

- `continue` statement works similarly to break, but instead of breaking out of the loop entirely, it skips to the next iteration of the loop

- The `While Loop` works similarly to the `For Loop`, except that the initializer variable is set before the loop, and the final-expression is included inside the loop after the code to run. Syntax:
    ```
    initializer
    while (condition) {
    // code to run

    final-expression
    }
    ```

    ```
    const cats = ['Pete', 'Biggles', 'Jasmine'];

    let myFavoriteCats = 'My cats are called ';

    let i = 0;

    while (i < cats.length) {
    if (i === cats.length - 1) {
        myFavoriteCats += `and ${cats[i]}.`;
    } else {
        myFavoriteCats += `${cats[i]}, `;
    }

    i++;
    }

    console.log(myFavoriteCats);     // "My cats are called Pete, Biggles, and Jasmine."
    ```
- The `Do...While` loop is also similar, with the initializer coming before the loop starts. The main difference being a `do...while` loop always executes at least once, because the condition comes after the code in the loop. In `while` and `for` loops, the condition check comes before the code, so if it is not met, it will not run ever.  
- **Warning:** With while and do...while — as with all loops — you must make sure that the initializer is incremented or, depending on the case, decremented, so the condition eventually becomes false. If not, the loop will go on forever, and either the browser will force it to stop, or it will crash. This is called an infinite loop.  