

# JavaScript Fundamentals

#### ✅ 1. What are the data types present in JavaScript?
JavaScript has the following data types:
- Primitive Types: Number, String, Boolean, Undefined, Null, Symbol (added in ECMAScript 6)
- Object

#### ✅ 2. What is the difference between null and undefined?
- `null` is a value that represents the intentional absence of any object value.
- `undefined` is a primitive value automatically assigned to variables that have been declared but not assigned a value.

#### ✅ 3. How does JavaScript handle type coercion?
Type coercion in JavaScript is the automatic conversion of values from one data type to another during operations. JavaScript is a loosely typed or dynamically typed language, meaning that variables do not have a fixed data type, and the interpreter can automatically convert values to a different type based on the context of the operation.

There are two types of type coercion:

- Implicit Type Coercion:
  - JavaScript automatically converts values from one type to another without any explicit instruction from the developer.
  - It often occurs during operations involving different data types, such as addition or comparison.
  - The + operator, for example, can perform both addition and string concatenation, leading to implicit type coercion.
  ```
  var number = 5;
  var stringNumber = "10";
  var result = number + stringNumber;
  console.log(result); // Outputs: "510"
  ```

- Explicit Type Coercion:
  - Developers can explicitly convert values from one type to another using functions or operators.
  - Examples include using Number(), String(), parseInt(), or other conversion functions.
  ```
  var stringNumber = "123";
  var number = Number(stringNumber);
  console.log(number); // Outputs: 123
  ```

#### ✅ 4. Explain the concept of hoisting in JavaScript.
Hoisting is a behavior in JavaScript where variable and function declarations are moved to the top of their containing scope during the compilation phase. This allows you to use variables and functions before they are declared in the code.

#### ✅ 5. What is the scope in JavaScript?
Scope refers to the context in which variables are declared and accessed. JavaScript has two types of scope:
- Global Scope: Variables declared outside any function are in the global scope.
- Local Scope: Variables declared inside a function are in the local scope.

#### ✅ 6. What is the difference between == and ===?
- `==` is the equality operator, which performs type coercion if the operands are of different types.
- `===` is the strict equality operator, which checks both value and type without coercion.

#### ✅ 7. Describe closure in JavaScript. Can you give an example?
A closure is a function that has access to variables from its outer (enclosing) scope, even after that scope has finished executing. Here's an example:

```javascript
function outerFunction() {
  let outerVariable = 'I am from outer scope';

  function innerFunction() {
    console.log(outerVariable);
  }

  return innerFunction;
}

const closureExample = outerFunction();
closureExample(); // Outputs: I am from outer scope
```

#### ✅ 8. What is the 'this' keyword and how does its context change?
The `this` keyword in JavaScript refers to the object to which a function belongs in its execution context. The context of `this` changes based on how a function is invoked:
- **Global Context:** In the global scope or when a function is not part of any object, `this` refers to the global object (e.g., `window` in a browser, `global` in Node.js).
- **Method Context:** When a function is a method of an object, `this` refers to the object that owns the method.
- **Function Context:** When a function is a standalone function (not a method), the value of `this` can be affected by how the function is called. In strict mode, it is `undefined` in this case; otherwise, it refers to the global object.
- **Constructor Context:** When a function is used as a constructor with the `new` keyword, `this` refers to the newly created instance of the object.

#### ✅ 9. What are arrow functions and how do they differ from regular functions?
Arrow functions in JavaScript are a concise way to write functions, introduced in ECMAScript 6. They have a shorter syntax and differ from regular functions in a few key ways:
- **No 'this' Binding:** Arrow functions do not have their own `this` binding; instead, they inherit `this` from the enclosing scope.
- **No 'arguments' Binding:** Arrow functions also do not have their own `arguments` object; the `arguments` variable refers to the arguments of the enclosing function.
- **Cannot be Used as Constructors:** Arrow functions cannot be used as constructors with the `new` keyword.
- **No 'super' Binding:** Arrow functions do not have their own `super` binding.

Example:
```javascript
// Regular function
function regularFunction(x) {
  return x * 2;
}

// Arrow function
const arrowFunction = x => x * 2;
```

#### ✅ 10. What are template literals in JavaScript?
Template literals, introduced in ECMAScript 6 (ES6), provide a more flexible and convenient way to create strings in JavaScript. They use backticks (`) as delimiters and support string interpolation, allowing you to embed expressions within the string using ${} syntax.

Example:
```
const name = 'John';
const age = 30;

// Using template literals
const greeting = `Hello, my name is ${name} and I am ${age} years old.`;

console.log(greeting);
// Outputs: Hello, my name is John and I am 30 years old.
```

Key features of template literals:
- String Interpolation: Expressions inside ${} are evaluated and concatenated into the string.
- Multiline Strings: Template literals support multiline strings without the need for escape characters.
- Expression Evaluation: You can include any valid JavaScript expression inside ${} for dynamic content.

Template literals offer a more readable and concise syntax compared to traditional string concatenation, especially when dealing with complex strings or embedding variables and expressions.


# JavaScript Functions and Higher-Order Functions

11. What is a higher-order function in JavaScript?
12. Can functions be assigned as values to variables in JavaScript? 13. How do functional programming concepts apply in JavaScript?
14. What are IIFES (Immediately Invoked Function Expressions)?
15. How do you create private variables in JavaScript?


# JavaScript Objects and Prototypes

16. How do you create an object in JavaScript?
17. What are prototypes in JavaScript?
18. Explain prototypal inheritance.
19. What is the difference between object literals and constructor functions?
20. How do you add or remove properties from an object?


# Asynchronous JavaScript

21. What is the event loop in JavaScript?
22. Explain how callbacks work in JavaScript.
23. What are promises and how do they manage asynchronous code?
24. Explain async/await in JavaScript and how it differs from Promises.
25. What is the Job Queue (or Microtask Queue)?


# DOM Manipulation and Browser APIs

26. How do you select DOM elements using JavaScript?
27. Explain event propagation in the DOM.
28. How do you prevent a form from submitting using JavaScript?
29. What are Web APIs in the context of JavaScript?
30. How can you manipulate the browser history using JavaScript?


# ES2015+ and Modern JavaScript Features

31. What are the new features introduced in ES6?
32. How do you use destructuring assignments in ES6?
33. Explain the use of const and let keywords.
34. What are default parameters in JavaScript functions?
35. Explain the concept of modules in ES6.


# Event Handling

36. How do you handle events in JavaScript?
37. What is event delegation and why is it useful?
38. How do you add and remove an event listener from an element?
39. Can you explain how "this" works in event handlers?
40. What is the difference between event.preventDefault() and event.stopPropagation()?


# Web Storage and Security

41. What is the difference between localStorage, sessionStorage, and cookies?
42. Can you explain Cross-Site Scripting (XSS) and how to prevent it?
43. What is Cross-Origin Resource Sharing (CORS) and how does it work?
44. How does content security policy (CSP) help in preventing security attacks?


# JavaScript Debugging

45. What tools and techniques do you use for debugging JavaScript code?
46. How do you debug a JavaScript application in the browser?
47. Explain the concept and use of breakpoints.
48. How do you handle exceptions in JavaScript?


# Performance and Optimization

49. What techniques can be used to improve JavaScript performance?
50. How does JavaScript minification and bundling contribute to performance?
51. Discuss the importance of web page loading time and performance.
52. Explain how lazy loading works in JavaScript.


# JavaScript Testing

53. What are some JavaScript testing frameworks you know?
54. How can you write unit tests for JavaScript code?
55. What is Test-Driven Development (TDD) in JavaScript?
56. Can you explain the difference between unit and integration testing?


# Networking with JavaScript

57. How do you make HTTP requests in JavaScript?
58. What is the difference between XMLHttpRequest and Fetch API?
59. What is AJAX, and how does it work?
60. How do you use WebSockets in a web application?


# JavaScript Patterns and Best Practices

61. What is a design pattern in JavaScript?
62. Can you explain the module pattern?
63. What is the Singleton pattern in JavaScript?
64. Explain the Revealing Module pattern.
65. What are some best practices for coding in JavaScript?


# JavaScript Algorithms and Data Structures

66. How do you implement a stack and a queue in JavaScript?
67. Explain how to sort an array in JavaScript.
68. How do you check if a string is a palindrome?
69. Describe a recursive function and provide an example.
70. What is the time complexity of JavaScript operations?


# JavaScript Libraries and Frameworks

71. What is the difference between a library and a framework in JavaScript?
72. Explain the Virtual DOM in React.
73. How does data binding work in Angular?
74. What is Vue.js and what sets it apart from other frameworks?
75. Can you describe the jQuery library and its applications?


# JavaScript ES2017+ and Beyond

76. What are async iterators and generators?
77. What is the purpose of the async keyword?
78. Can you explain the use of Object.entries () and Object.values() ?
79. How does JavaScript Handle big integers (BigInt )?
80. What are dynamic imports in JavaScript?


# Browser Compatibility and Transpilation

81. How do you ensure your JavaScript code is cross-browser compatible?
82. What is Babel and how is it used in JavaScript development?
83. What are polyfills, and when would you use them?


# JavaScript and the DOM

84. What is the Document Object Model (DOM)?
85. How do you create, append, or remove an element from the DOM?
86. Describe different ways to find or access HTML elements in the DOM.
87. Explain the difference between innerHTML and textContent.
88. How do you handle DOM events in a memory-efficient way?


# Tooling and Build Systems

89. What is npm, and how do you use it?
90. Discuss the role of Webpack in modern JavaScript development.
91. What is a source map?
92. How do you use ESLint for maintaining JavaScript code quality?
93. What is continuous integration/continuous deployment (CI/CD) in the context of JS development?


# JavaScript and the Web Platform

94. What is the Window object and its significance?
95. Explain the Document object.
96. What new features does HTML5 bring to JavaScript development?
97. Discuss the role of JavaScript in Progressive Web Apps (PWAs).


# JavaScript and Mobile Development

98. Explain how to use JavaScript for mobile development.
99. What is React Native and how does it differ from traditional web apps?
100. How does JavaScript interact with native mobile components?
