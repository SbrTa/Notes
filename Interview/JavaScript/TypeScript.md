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

function calculate(a: number, b: number, calcFun: (a: number, b: number) => number) {
    calcFun(a, b);
}
calculate(1, 2, add)
```
