## Primitive type

string, number, boolean

```
let name: string;
```

## Union Type
```
let id: string | number;
id = 'abc';
id = 123;
id = true; // error
```


## Function

```
function add(a: number, b: number): void {
    let sum = a+b;
    return sum; // error
}
```

```
function add(a: number, b: number): number {
    let sum = a+b;
    return sum;
}
```

```
function add(a: number, b: number): number {
    let sum = a+b;
    return sum;
}

function calculate(a: number, b: number, calcFn: (a: number, b: number) => number) {
    calcFn(a, b);
}
calculate(1, 2, add)
```

## type alias keyword
Define object type, function type or Union type.

Function type:
```
type AddFnType = (a: number, b: number) => number;

function add(a: number, b: number): number {
    let sum = a+b;
    return sum;
}

function calculate(a: number, b: number, calcFn: AddFnType) {
    calcFn(a, b);
}
calculate(1, 2, add)
```

Object type:
```
type User = {
    name: string;
    age: number,
    id: number | string;
    isActive: boolean;
};
let user: User;
```

## interface keyword
Define Object type.

```
interface User {
    name: string;
    age: number,
    id: number | string;
    isActive: boolean;
};
let user: User;
```

NB: You can actually use interface to also define function types, but you cann't use interface to define union types. Which you can define with type.


## type vs interface
