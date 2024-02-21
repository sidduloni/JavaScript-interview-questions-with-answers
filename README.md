# JavaScript-interview-questions-with-answers


## S.No 1: What is Ecmascript in JavaScript?
**Ans:** ECMAScript (often abbreviated as ES) is the scripting language specification that JavaScript is based on. It defines the syntax, semantics, and standard library for JavaScript. Different versions of JavaScript, like ES5, ES6 (or ECMAScript 2015), ES2016, and so on, are implementations of the ECMAScript standard.

## S.No 2: What is the difference between `object` and `array` in JavaScript?
**Ans:** 

| Characteristic           | Objects                            | Arrays                            |
|--------------------------|-----------------------------------|-----------------------------------|
| **Structure**            | Collections of key-value pairs.    | Ordered lists of values.          |
| **Declaration Syntax**   | `let person = { key: value };`    | `let fruits = [value1, value2];` |
| **Accessing Values**     | Access using keys.                 | Access using indices.             |
| **Example**              | `person.name`                     | `fruits[0]`                       |
| **Order**                | Order of key-value pairs is not guaranteed. | Order of elements is maintained. |
| **Use Cases**           | Named properties, non-numeric keys. | When order or numerical indices are important. |



## S.No 3: What is the spread operator, rest operator, and default parameter in JavaScript?
**Ans:** 
- Spread Operator (`...`): Used to spread the elements of an array or the properties of an object. It's commonly used for array manipulation and object cloning.

- Rest Operator (`...` in function parameters): Used to collect multiple arguments into a single array parameter. It simplifies working with variable-length argument lists.

- Default Parameter: It allows you to provide default values for function parameters, so if a parameter is not passed or is `undefined`, the default value is used.

## S.No 4: What is deep copy and shallow copy in JavaScript?
**Ans:** 
- 1. Shallow Copy:
A shallow copy of an object creates a new object with a new reference to the top-level properties of the original object. However, it doesn't create copies of nested objects within the original object. Changes to nested objects in the copied object will affect the original object and vice versa. Here's an example:

```javascript
// Original object
const originalObject = {
  name: "John",
  address: {
    city: "New York",
    state: "NY"
  }
};

// Creating a shallow copy
const shallowCopy = Object.assign({}, originalObject);

shallowCopy.name = "Alice"; // Changes only the shallow copy
shallowCopy.address.city = "Los Angeles"; // Also changes the original object

console.log(originalObject); // { name: 'John', address: { city: 'Los Angeles', state: 'NY' } }
console.log(shallowCopy); // { name: 'Alice', address: { city: 'Los Angeles', state: 'NY' } }
```

- 2. Deep Copy:
A deep copy, on the other hand, creates a completely independent copy of an object, including all nested objects and their properties. Changes to the copied object won't affect the original object.

```javascript
// Original object
const originalObject = {
  name: "John",
  address: {
    city: "New York",
    state: "NY"
  }
};

// Creating a deep copy using JSON
const deepCopy = JSON.parse(JSON.stringify(originalObject));

deepCopy.name = "Alice"; // Changes only the deep copy
deepCopy.address.city = "Los Angeles"; // Does not affect the original object

console.log(originalObject); // { name: 'John', address: { city: 'New York', state: 'NY' } }
console.log(deepCopy); // { name: 'Alice', address: { city: 'Los Angeles', state: 'NY' } }
```

## S.No 5: Explain Object.freeze() and Object.seal() in javascript
**Ans:** 
**Object.freeze()**:
- It is immutable
- Helps in preventing existing properties from being changed
- Preventing the new properties to be added to the specific object

**Object.seal()**:
- It is mutable
- Allows existing properties to be modified
- But prevents the addition and deletion of new properties


## S.No 6: Explain typescript over javascript
**Ans:** 
-  Main diff : Js is Dynamically typed and Ts is Statically typed
-  Type safety
-  Strict static typing which makes Ts code safer.
-  Browsers cant execute/understand Ts which requires TS-Compilation, where Js does.
-  Ts supports PROTOTYPING while Js does'nt.
-  It provides: Interfaces, Type Aliases and Abstract classes, where Js does'nt

   Advantages:
-  Ts identifies compilation errors during development which saves time
  
  Disadvantages:
- When .Ts file compilation happens Ts requires an Extra Step
- Learning Ts is more challenging than Js


## S.No 7: What is event bubbling and event capturing in JavaScript?
**Ans:** 
Event Bubbling and Event Capturing are two phases of event propagation in the DOM.

- **Event Bubbling:** In event bubbling, the innermost element's event is handled first, and the event bubbles up through its ancestors. It's the default behavior in most cases.

- **Event Capturing:** In event capturing, the outermost element's event is handled first, and the event trickles down to the target element. Event capturing is less common but can be used by specifying `true` as the third parameter when adding an event listener.

## S.No 8: What is a higher-order function in JavaScript?
**Ans:** A higher-order function is a function that takes one or more functions as arguments or returns a function as its result. Higher-order functions are a powerful concept in functional programming and enable functions to be more flexible and reusable.

## S.No 9: Explain different types of functions in JavaScript
**Ans:** In JavaScript, there are several types of functions:

1. Regular Functions: These are the most common functions used for general code execution.

2. Arrow Functions: Introduced in ES6, arrow functions are more concise and lexically scoped.

3. Anonymous Functions: Functions without a name, often used as arguments to other functions.

4. IIFE (Immediately Invoked Function Expressions): Functions that are defined and executed immediately after their creation.

5. Recursive Functions: Functions that call themselves, often used for repetitive tasks or traversing data structures.

## S.No 10: Generator function in JavaScript
**Ans:** 
A generator function in JavaScript is a special type of function that can be paused and resumed multiple times. This is done using the yield keyword, which tells the function to pause execution and return a value. The function can then be resumed by calling the next() method on the generator object.

Example of a generator function that yields values:
```javascript
function* generatorFunction() {
  yield 1;
  yield 2;
  yield 3;
}

const generator = generatorFunction();

console.log(generator.next().value); // Output: 1
console.log(generator.next().value); // Output: 2
console.log(generator.next().value); // Output: 3
console.log(generator.next().value); // Output: undefined
```
Example of a generator function that generates an infinite sequence:
```javascript

function* infiniteSequence() {
  let i = 0;
  while (true) {
    yield i++;
  }
}

const generator = infiniteSequence();

console.log(generator.next().value); // Output: 0
console.log(generator.next().value); // Output: 1
console.log(generator.next().value); // Output: 2
```

## S.No 11: 
**Ans:** 


## S.No 12: How many ways are there to create objects in JavaScript?
**Ans:** There are several ways to create objects in JavaScript:

1. Object Literal: `Eg: {}`

2. Constructor Functions: `Eg: let person = new Person(x, y, z)`

3. Object.create(): `Eg: let person = Object.create(personPrototype);`
   
4. Class: Introduced in ES6 `Eg: class Person { constructor(name){ this.name }}. - then refer step 2 Eg`


## S.No 13: What is prototype inheritance in JavaScript?
**Ans:** In JavaScript, prototype inheritance is a mechanism that allows objects to inherit properties and methods from a prototype object. Every object in JavaScript has a prototype, and when a property or method is accessed on an object, JavaScript looks up the prototype chain to find it if it doesn't exist directly on the object. This allows for code reuse and more efficient memory usage.

## S.No 14: 
**Ans:** 

## S.No 15: What are the array methods and string methods in JavaScript?
**Ans:** 
- Array methods are functions that can be applied to arrays for manipulation and transformation.
```css
Array methods: `push`, `pop`, `shift`, `unshift`, `map`, `filter`, and `reduce`.
```

- String methods are functions that can be applied to strings for text manipulation.
```css
String methods: `substring`, `split`, `concat`, `indexOf`, and `toUpperCase`.
```

## S.No 16: 
**Ans:** 

## S.No 17: What is throttling and debouncing in JavaScript?
**Ans:** 
- Throttling is a technique to limit the rate at which a function is called. It ensures that the function is executed at a specified interval, preventing it from being called too frequently.

- Debouncing is a technique to ensure that a function is not called repeatedly in a short period. It waits for a pause in events before triggering the function, useful for handling actions like search suggestions or resizing events.

## S.No 18:
**Ans:** 


## S.No 19: 
**Ans:** 

## S.No 20: What is execution context and microtask queue in JavaScript?
**Ans:** 
- Execution Context: Execution context is an environment where JavaScript code is executed. It includes variables, functions, and the scope chain. Each function call creates a new execution context.

- Microtask Queue: The microtask queue is used for managing microtasks, which have higher priority than regular tasks. Promises and `await` create microtasks.

## S.No 21: 
**Ans:** 

## S.No 22: 
**Ans:** 


## S.No 23: What is the difference between `Map` and `Set` in JavaScript?
**Ans:** 
- `Map`: A `Map` is a collection of key-value pairs where the keys can be of any data type. It allows for efficient data retrieval based on keys and supports methods to manage and iterate over the data.

- `Set`: A `Set` is a collection of unique values. It doesn't allow duplicates, making it suitable for storing a list of distinct values. It provides methods for adding, deleting, and checking for the existence of values.

## S.No 24: What are `WeakMap` and `WeakSet` in JavaScript?
**Ans:** 
- `WeakMap`: A `WeakMap` is a special type of map where keys are weakly referenced, which means they do not prevent the key objects from being garbage collected. This is useful for cases where you don't want to create memory leaks.

- `WeakSet`: A `WeakSet` is similar to a `Set` but only holds objects and allows for weak references. This is also used to avoid memory leaks in certain situations.

## S.No 25: 
**Ans:** 


## S.No 26: 
**Ans:**

## S.No 27: 
**Ans:** 

## S.No 28: 
**Ans:** 

## S.No 29: What is a generator function in JavaScript?
**Ans:** A generator function is a special type of function in JavaScript that allows you to pause and resume its execution. It's defined using an asterisk (`function*`) and uses the `yield` keyword to yield control back to the caller temporarily. Generator functions are often used for creating iterators and for asynchronous code.

## S.No 30: How to stop event propagation in JavaScript?
**Ans:** To stop event propagation in JavaScript, you can use the `stopPropagation()` method. It prevents the event from bubbling up the DOM tree during the capturing or bubbling phase. For example:

```javascript
element.addEventListener('click', function(event) {
  event.stopPropagation(); // Stops the click event from further propagation
});
```

## S.No 31: 
**Ans:** 

## S.No 32: 
**Ans:** 

## S.No 33: What is the dead zone in JavaScript?
**Ans:** The dead zone in JavaScript refers to the period between the creation (declaration) and the initialization (assignment) of a variable declared with `let` or `const`. During the dead zone, attempting to access the variable will result in a `ReferenceError`. This concept ensures that variables are not accessed before they are initialized.

## S.No 34: 
**Ans:** 

## S.No 35: What is mutation observer in JavaScript?
**Ans:** A MutationObserver is a JavaScript object that watches for changes in the DOM and triggers a callback function when mutations occur. It's used to observe and react to changes in the structure or attributes of the DOM, such as when elements are added, removed, or modified.

## S.No 36: What is memoization in JavaScript?
**Ans:** Memoization is an optimization technique in JavaScript where the results of expensive function calls are cached to avoid redundant computations. This is particularly useful for functions that take a long time to compute the same result for the same inputs.

## S.No 37 What is the output of the below console
**Ans:**
```javascript
//Q .1:
(function() {
    var a = b = 3;
})();
console.log("a defined? " + (typeof a !== 'undefined'));
console.log("b defined? " + (typeof b !== 'undefined'));
//Output:
// a defined? false
// b defined? true

//Q .2:
console.log(0.1 + 0.2);
console.log(0.1 + 0.2 == 0.3);
//Output
// 0.30000000000000004
// false

//Q .3:
(function() {
    console.log(1);
    setTimeout(function() {
        console.log(2)
    }, 1000);
    setTimeout(function() {
        console.log(3)
    }, 0);
    console.log(4);
})();
//Output:
// 1
// 4
// 3
// 2

//Q .4:
console.log(1 + "2" + "2");
console.log(1 + +"2" + "2");
console.log(1 + -"1" + "2");
console.log(+"1" + "1" + "2");
console.log("A" - "B" + "2");
console.log("A" - "B" + 2);
// Output
//122
// 32
// 02
// 112
// NaN2
// NaN

//Q .5:
var a = {},
    b = {
        key: 'b'
    },
    c = {
        key: 'c'
    };
a[b] = 123;
a[c] = 456;
console.log(a[b]);
// Output
// 456

//Q .6:
(function(x) {
    return (function(y) {
        console.log(x);
    })(2)
})(1);
// Output
// 1

```

## S.No 37: What is the use and benifit of separating collection intead of having all in one collection and vice-versa in mongodb
**Ans:**

Using separate collections
- Firstly, it allows for a more modular and scalable database design. Each collection can be tailored to store a specific type of data, promoting a clear and logical structure. This separation enhances the maintainability of the database, making it easier to update or query specific sets of data without affecting unrelated information.
- Secondly, separating collections can contribute to improved query performance. Smaller collections can lead to more efficient indexing, reducing the time and resources required for queries. Additionally, it allows for better control over access permissions, enabling more granular security settings based on the nature of the data in each collection.

Using single collection
- combining all data into a single collection may simplify initial setup but can lead to decreased performance and hinder the ability to manage and scale the database effectively.

## S.No 38 If the setTimeout function has a delay of 0 milliseconds, even though why is it executed after the normal function execution ?
**Ans**

```javascript
function one() {
  setTimeout(() => {
    console.log("inside timer");
  }, 0);
  console.log("outside timer");
}

one();
```
Reason :
 - Timer function is placed in the event queue to be processed after the current execution context completes.

 - After the current execution context is completed, the function inside the timer is picked up from the event queue and executed. 

 - The use of `setTimeout` with a delay of 0 is often used in scenarios where you want to defer the execution of a function until the next event loop cycle, allowing other synchronous     tasks to complete first.


## S.No 39 Explain Arrow function 
**Ans**

1. **Concise Syntax:**
   Arrow functions have a shorter syntax compared to traditional function expressions, making the code more concise. They are especially useful for short, simple functions.

   Traditional function expression:
   ```javascript
   const add = function(x, y) {
       return x + y;
   };
   ```

   Arrow function:
   ```javascript
   const add = (x, y) => x + y;
   ```

2. **Implicit Return:**
   If the function body consists of a single expression, you can omit the curly braces `{}` and the `return` keyword. The result of the expression is implicitly returned.

   Example:
   ```javascript
   const square = x => x * x;
   ```

3. **No Binding of `this`:**
   Arrow functions do not bind their own `this` value. Instead, they inherit the `this` value from the enclosing execution context. This behavior can be beneficial in certain scenarios, especially when dealing with callbacks and event handlers.

   Example:
   ```javascript
   function Counter() {
       this.count = 0;

       setInterval(() => {
           // 'this' refers to the Counter instance
           this.count++;
           console.log(this.count);
       }, 1000);
   }

   const counter = new Counter();
   ```

4. **No Arguments Object:**
   Arrow functions do not have their own `arguments` object. If you need to access function arguments, you can use the rest parameter syntax.

   Example:
   ```javascript
   const sum = (...args) => args.reduce((acc, val) => acc + val, 0);
   ```

5. **Cannot be Used as Constructors:**
   Arrow functions cannot be used with the `new` keyword to create instances. They lack the internal `[[Construct]]` method necessary for constructor behavior.

   Example:
   ```javascript
   // This will result in an error
   const Person = (name) => {
       this.name = name;
   };

   const person = new Person('John');
   ```

## S.No 40: List React Built-in Hooks  
**Ans:** 
1. useState
2. useEffect
3. useReducer
4. useContext
5. useRef
6. useCallback
7. useMemo
8. useLayoutEffect
9. useDebugValue
10. useImperativeHandle

**Other Custom Hooks:**

11. useId - Used for generating unique Id's.
12. useMedia - Lets us check the current screen size without writing our own code.
13. useForm - Used for managing the form and validation etc.


## S.No 41: Waht is react hook? what are its rules? Explain react hooks
**Ans**
Hooks allow us to "hook" into React features such as state and lifecycle methods.

**There are 3 rules for hooks:**
- Hooks can only be called inside React function components.
- Hooks can only be called at the top level of a component.
- Hooks cannot be conditional

**React Hooks**

**1. useState :**
State refers to data or property that needs to be tracking in an application. State accepts initial value and return 2 values - Current state and a function that updates the state.

**2. useEffect:** 
It allows us to perform side effects such as fetching data, directly updating DOM, timers. It accepts 2 arguments, second argument is optional.
   `useEffect(<function>, <dependency>)`
   If we dont pass 2nd parameter then useEffect runs on every render.
   ```javascript
- No dependency:
useEffect(() => {
//Runs on every render
});

- An empty array:
useEffect(() => {
  //Runs only on the first render
}, []);

- Props or state values
useEffect(() => {
  //Runs on the first render
  //And any time any dependency value changes
}, [prop, state]);
   
   ```
   **Effect Cleanup** :
   - Some effects require cleanup to reduce memory leaks.
   - Timeouts, subscriptions, event listeners, and other effects that are no longer needed should be disposed.
   - We do this by including a return function at the end of the useEffect Hook.

```javascript
useEffect(() => {
    let timer = setTimeout(() => {
    setCount((count) => count + 1);
  }, 1000);

  return () => clearTimeout(timer)
  }, []);
```

**3. useContext :**
- React Context is a way to manage state globally.
- Without Context, we will need to pass the state as "props" through each nested component. This is called **"prop drilling"**.
   
First we need to create context
    
```javascript 
import { useState, createContext } from "react";
const UserContext = createContext()
```
    
Next Wrap child components in the Context Provider
     
```javascript 
function Component1() {
  const [user, setUser] = useState("Jesse Hall");
  return (
    <UserContext.Provider value={user}>
      <h1>{`Hello ${user}!`}</h1>
      <Component2 user={user} />
    </UserContext.Provider>
  );
}
```
Finally use the useContext hook
    
```javascript 
const user = useContext(UserContext);
```

**4. useRef :**
- The useRef Hook allows you to persist values between renders.
- It can be used to access a DOM element directly.
- useRef() only returns one item. It returns an Object called **current**.
- The useRef Hook can also be used to keep track of previous state values.
```javascript
function App() {
  const [inputValue, setInputValue] = useState("");
  const previousInputValue = useRef("");

  useEffect(() => {
    previousInputValue.current = inputValue;
  }, [inputValue]);

  return (
    <>
      <input
	type="text"
	value={inputValue}
	onChange={(e) => setInputValue(e.target.value)}
      />
      <h2>Current Value: {inputValue}</h2>
      <h2>Previous Value: {previousInputValue.current}</h2>
    </>
  );
}
```

**5. useReducer :**
The useReducer Hook is similar to the useState Hook. Used for complex logic

<details>
  <summery>Complete example for useReducer</summery>
  ### Heading
  1. Foo
  2. Bar
     * Baz
     * Qux
  
</details>

**6. useCallback :**
- It returns a memoized callback **function**.
- The useCallback Hook only runs when one of its dependencies update. This can improve performance.

**7. useMemo :**
- It memoize the value

Example of useCallback & useMemo : 
```javascript
useCallback:
useCallback(() => {
    // your code 
  }, [dependency]);

useMemo:
export default memo(Todos);
```
Note:  Both are same. The main difference is that useMemo returns a memoized value and useCallback returns a memoized function.

**8. useLayoutEffect :** 
- Similar to useEffect only difference is it will run after rendering the component but before painting on the screen.

**9. useDebugValue :**
- Used to debug custom hooks using react developer tools.

**10. useImperativeHandle :**
- Used to modify the exposed ref.


