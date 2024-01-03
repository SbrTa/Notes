## Explain “this” keyword.
The “this” keyword refers to the object that the function is a property of. The value of the “this” keyword will always depend on the object that is invoking the function.

Example 1:

```
function doSomething() {
  console.log(this);
}
doSomething();
```

Since the function is invoked in the global context, the function is a property of the global object.

Example 2:

```
var obj = {
    name:  "Alice",
    getName: function(){
      console.log(this.name);
    }
}
   
obj.getName(); //Alice
```

In the above code, at the time of invocation, the getName function is a property of the object obj , therefore, this keyword will refer to the object obj, and hence the output will be “Alice”.

Example 3:

```
var obj = {
    name:  "Alice",
    getName: function(){
      console.log(this.name);
    } 
}
       
var getName = obj.getName;
       
var obj2 = {name:"Bob", getName };
obj2.getName(); // Bob
```

The output will be “Bob”.

Although the getName function is declared inside the object obj, at the time of invocation, getName() is a property of obj2, therefore the “this” keyword will refer to obj2.

The silly way to understand the “this” keyword is, whenever the function is invoked, check the object before the dot. The value of this . keyword will always be the object before the dot.

## Explain Scope and Scope Chain in javascript.
There are three types of scopes in JS:

- Global Scope: Variables or functions declared in the global namespace have global scope, which means all the variables and functions having global scope can be accessed from anywhere inside the code.
    ```
    var globalVariable = "Hello world";
    
    function sendMessage(){
      return globalVariable; // can access globalVariable since it's written in global space
    }
    function sendMessage2(){
      return sendMessage(); // Can access sendMessage function since it's written in global space
    }
    sendMessage2();  // Returns “Hello world”
    ```

- Function Scope: Any variables or functions declared inside a function have local/function scope, which means that all the variables and functions declared inside a function, can be accessed from within the function and not outside of it.
    ```
    function awesomeFunction(){
      var a = 2;
    
      var multiplyBy2 = function(){
        console.log(a*2); // Can access variable "a" since a and multiplyBy2 both are written inside the same function
      }
    }
    console.log(a); // Throws reference error since a is written in local scope and cannot be accessed outside
    
    multiplyBy2(); // Throws reference error since multiplyBy2 is written in local scope
    ```

- Block Scope: Block scope is related to the variables declared using let and const. Variables declared with var do not have block scope. Block scope tells us that any variable declared inside a block { }, can be accessed only inside that block and cannot be accessed outside of it.
    ```
    {
      let x = 45;
    }
    
    console.log(x); // Gives reference error since x cannot be accessed outside of the block
    
    for(let i=0; i<2; i++){
      // do something
    }
    
    console.log(i); // Gives reference error since i cannot be accessed outside of the for loop block
    ```

- Scope Chain: JavaScript engine also uses Scope to find variables. Let’s understand that using an example:
    ```
    var y = 24;
    
    function favFunction(){
      var x = 667;
      var anotherFavFunction = function(){
        console.log(x); // Does not find x inside anotherFavFunction, so looks for variable inside favFunction, outputs 667
      }
    
      var yetAnotherFavFunction = function(){
        console.log(y); // Does not find y inside yetAnotherFavFunction, so looks for variable inside favFunction and does not find it, so looks for variable in global scope, finds it and outputs 24
      }
    
      anotherFavFunction();
      yetAnotherFavFunction();
    }
    favFunction();
    ```

As you can see in the code above, if the javascript engine does not find the variable in local scope, it tries to check for the variable in the outer scope. If the variable does not exist in the outer scope, it tries to find the variable in the global scope.

If the variable is not found in the global space as well, a reference error is thrown.


## Explain passed by value and passed by reference.
In JavaScript, primitive data types are passed by value and non-primitive data types are passed by reference.
```
var y = 234;
var z = y;
```
In the above example, the assign operator knows that the value assigned to y is a primitive type (number type in this case), so when the second line code executes, where the value of y is assigned to z, the assign operator takes the value of y (234) and allocates a new space in the memory and returns the address. Therefore, variable z is not pointing to the location of variable y, instead, it is pointing to a new location in the memory.

```
var obj = { name: "ABC", surname: "DEF" };
var obj2 = obj;
```
In the above example, the assign operator directly passes the location of the variable obj to the variable obj2. In other words, the reference of the variable obj is passed to the variable obj2.

## What is an Immediately Invoked Function (IIFE / IIFY) in JavaScript?
An Immediately Invoked Function ( known as IIFE and pronounced as IIFY) is a function that runs as soon as it is defined.

Syntax of IIFE :

```
(function(){ 
  // Do something;
})();
```

To understand IIFE, we need to understand the two sets of parentheses that are added while creating an IIFE :
```
(function(){ 
  // Do something;
})
```

While executing javascript code, whenever the compiler sees the word “function”, it assumes that we are declaring a function in the code. Therefore, if we do not use the first set of parentheses, the compiler throws an error because it thinks we are declaring a function, and by the syntax of declaring a function, a function should always have a name.

The second set of parenthesis:
```
(function (){
  //Do something;
})();
```

From the definition of an IIFE, we know that our code should run as soon as it is defined. A function runs only when it is invoked. If we do not invoke the function, the function declaration is returned and have to assign a name.

Therefore to invoke the function, we use the second set of parenthesis.


## What are object prototypes?
All javascript objects inherit properties from a prototype. For example,
- Date objects inherit properties from the Date prototype
- Math objects inherit properties from the Math prototype
- Array objects inherit properties from the Array prototype.
- On top of the chain is Object.prototype. Every prototype inherits properties and methods from the Object.prototype.
- A prototype is a blueprint of an object. The prototype allows us to use properties and methods on an object even if the properties and methods do not exist on the current object.

Let’s see prototypes help us use methods and properties:
```
var arr = [];
arr.push(2);

console.log(arr); // Outputs [2]
```

In the code above, as one can see, we have not defined any property or method called push on the array “arr” but the javascript engine does not throw an error.

The reason is the use of prototypes. As we discussed before, Array objects inherit properties from the Array prototype.

The javascript engine sees that the method push does not exist on the current array object and therefore, looks for the method push inside the Array prototype and it finds the method.

Whenever the property or method is not found on the current object, the javascript engine will always try to look in its prototype and if it still does not exist, it looks inside the prototype's prototype and so on.



