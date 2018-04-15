# Basic Types
In typescript, to declare a variable type we follow this style:
```ts
let bool: boolean = false;
```
We start to declare the variable with `let` key word, although it is not necessary to use `let`. We can also use `var` instead of `let`. But `let` provide us with very nice variable scoping.

### Number
Number declaration can be as follow.
```ts
let decimal: number = 6;
let hex: number = 0xf00d;
let binary: number = 0b1010;
let octal: number = 0o744;
```
### String
Declaring string is same as number but we have to use `string` instead of `number`.
```ts
let color: string = "blue";
color = 'red';
```
We can also use _template strings_ to span mutliple lines easily.
```ts
let fullName: string = `Bob Bobbington`;
let age: number = 37;
let sentence: string = `Hello, my name is ${ fullName }.

I'll be ${ age + 1 } years old next month.`;
```
### Array
We can define arrays in two ways. In first way we first use the type element followed by `[]` to denote an array of elements of that type.
```ts
let list: number[]: [1, 2, 3, 4]
```
In second way we use generic array type, `Array<elemType>`:
```ts
let list: Array<number> = [1, 2, 3];
```
### Tuple
Array of fixed elements with fixed types.
```ts
let x: [string, number];

x = ["Bottle", 10]; // OK

x = [10, "Bottle"]; // Error
```
When accessing element outside the known index, The union of the type can be used.
```ts
x[3] = "World" // Ok, 'string' can be assign to 'string' | 'nubmer'

console.log(x[5].toSring()) // Ok, 'string' and 'number' both have method 'toString'

x[6] = false // Error, 'boolean' isn't 'string' | 'number'
```
