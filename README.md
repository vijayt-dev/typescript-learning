# TypeScript

## What is Type Annotation?

TypeScript uses type annotations to explicitly specify types for identifiers such variables, functions, objects, etc.

**Example**

```javascript
let variableName: type;
let variableName: type = value;
```

## TypeScript Number

All numbers in TypeScript are either floating-point values or big integers. The floating-point numbers have the type number while the big integers get the type bigint.

**Example**

```javascript
let counter: number = 0;
```

As in JavaScript, TypeScript supports the number literals for decimal, hexadecimal, binary, and octal literals:

### Decimal numbers

**Example**

```javascript
let counter: number = 1;
```

### Binary Numbers
The binary number uses a leading zero followed by a lowercase or uppercase letter B

**Example**

```javascript
let bin = 0b100;
let anotherBin: number = 0B010;
```

### Octal Numbers

An octal number uses a leading zero followed the letter 0o. The digits after 0o are numbers in the range 0 through 7:

**Example**

```javascript
let octal: number = 0o10;
```

### Hexadecimal numbers

Hexadecimal numbers use a leading zero followed by a lowercase or uppercase letter X (0x or 0X). The digits after the 0x must be in the range (0123456789ABCDEF). 

**Example**

```javascript
let hexadecimal: number = 0XA;
```

### Big Integers

The big integers represent the whole numbers larger than 2^53 – 1. A Big integer literal has the n character at the end of an integer literal like this

**Example**

```javascript
let big: bigint = 9007199254740991n;
```

## TypeScript String

TypeScript uses double quotes (") or single quotes (') to surround string literals.

TypeScript also supports template strings that use the backtick to surround characters.

**Example**

```javascript
let title: string = "Web Developer";
let description = `This TypeScript string can 
span multiple 
lines
`;
```

## TypeScript Boolean

The TypeScript boolean type allows two values: true and false.

**Example**

```javascript
let pending: boolean = true;
```

## TypeScript object Type

The TypeScript object type represents all values that are not in primitive types.

The following are primitive types in TypeScript:

- number
- bigint
- string
- boolean
- null
- undefined
- symbol

**Example**

```javascript
let employee: object;

employee = {
    firstName: 'John',
    lastName: 'Doe',
    age: 25,
    jobTitle: 'Web Developer'
};

console.log(employee);
```

To explicitly specify properties of the employee object, you first use the following syntax to declare the employee object.

**Example**

```javascript
let employee: {
    firstName: string;
    lastName: string;
    age: number;
    jobTitle: string;
};
```

And then you assign the employee object to a literal object with the described properties:

**Example**

```javascript
employee = {
    firstName: 'John',
    lastName: 'Doe',
    age: 25,
    jobTitle: 'Web Developer'
};
```

Or you can combine both syntaxes in the same statement like this:

**Example**

```javascript
let employee: {
    firstName: string;
    lastName: string;
    age: number;
    jobTitle: string;
} = {
    firstName: 'John',
    lastName: 'Doe',
    age: 25,
    jobTitle: 'Web Developer'
};
```

### The empty type {}

TypeScript has another type called empty type denoted by {} , which is quite similar to the object type.

**Example**

```javascript
let vacant: {} = {};
```

## TypeScript Array

A TypeScript array is an ordered list of data. To declare an array that holds values of a specific type, you use the following syntax:

**Example**

```javascript
let arrayName: type[];
let skills: string[];
```

Once you define an array of a specific type, TypeScript will prevent you from adding incompatible values to the array.

### Storing values of mixed types

The following illustrates how to declare an array that hold both strings and numbers:

**Example**

```javascript
let scores : (string | number)[];
scores = ['Programming', 5, 'Software Design', 4]; 
```

## TypeScript Tuple

A tuple works like an array with some additional considerations:

- The number of elements in the tuple is fixed.
- The types of elements are known, and need not be the same.

**Example**

```javascript
let skill: [string, number];
skill = ['Programming', 5];
```

The order of values in a tuple is important. If you change the order of values of the skill tuple to [5, "Programming"], you’ll get an error:

### Optional Tuple Elements

You can define an RGBA tuple with the optional alpha channel value.

**Example**

```javascript
let bgColor: [number, number, number, number?];
bgColor = [0, 255, 255, 0.5];
```

## TypeScript Enum

An enum is a group of named constant values. Enum stands for enumerated type.

**Example**

```javascript
enum Month {
    Jan,
    Feb,
    Mar,
    Apr,
    May,
    Jun,
    Jul,
    Aug,
    Sep,
    Oct,
    Nov,
    Dec
};
```

### Specifying enum members’ numbers

It’s possible to explicitly specify numbers for the members of an enum like this:

**Example**

```javascript
enum Month {
    Jan = 1,
    Feb,
    Mar,
    Apr,
    May,
    Jun,
    Jul,
    Aug,
    Sep,
    Oct,
    Nov,
    Dec
};
```

## TypeScript any Type

The any type allows you to assign a value of any type to a variable.

**Example**

```javascript
let result: any;
```

## TypeScript void Type

The void type denotes the absence of having any type at all. It is a little like the opposite of the any type.

Typically, you use the void type as the return type of functions that do not return a value.

**Example**

```javascript
function log(message): void {
    console.log(messsage);
}
```

Notice that if you use the void type for a variable, you can only assign undefined to that variable. In this case, the void type is not useful.

**Example**

```javascript
let useless: void = undefined;
```

## TypeScript never Type

The never type is a type that contains no values. Because of this, you cannot assign any value to a variable with a never type.

Typically, you use the never type to represent the return type of a function that always throws an error.

**Example**

```javascript
function raiseError(message: string): never {
    throw new Error(message);
}
```

## TypeScript union Type

A union type allows you to store a value of one or serveral types in a variable.

**Example**

```javascript
let result: number | string;
```

## TypeScript Type Aliases

Type aliases allow you to create a new name for an existing type.

**Example**

```javascript
type chars = string;
let messsage: chars;
```

## TypeScript String Literal Types

The string literal types allow you to define a type that accepts only one specified string literal.

**Example**

```javascript
let click: 'click';
click = 'click';
```

The click is a string literal type that accepts only the string literal 'click'. If you assign the literal string click to the click, it will be valid.

## TypeScript Type Inference

Type inference describes where and how TypeScript infers types when you don’t explicitly annotate them.

**Example**

```javascript
let counter = 0;
```

## TypeScript Functions

TypeScript functions are the building blocks of readable, maintainable, and reusable code.

**Example**

```javascript
function add(a: number, b: number): number {
    return a + b;
}
```

## TypeScript Optional Parameters

In JavaScript, you can call a function without passing any arguments even though the function specifies parameters. Therefore, JaveScript supports the optional parameters by default.

**Example**

```javascript
function multiply(a: number, b: number, c?: number): number {

    if (typeof c !== 'undefined') {
        return a * b * c;
    }
    return a * b;
}
```

## TypeScript Default Parameters

JavaScript supported default parameters since ES2015 (or ES6).

**Example**

```javascript
function applyDiscount(price, discount = 0.05) {
    return price * (1 - discount);
}

console.log(applyDiscount(100)); // 95
```

## TypeScript Rest Parameters

A rest parameter allows you a function to accept zero or more arguments of the specified type. In TypeScript, rest parameters follow these rules:

- A function has only one rest parameter.
- The rest parameter appears last in the parameter list.
- The type of the rest parameter is an array type.

**Example**

```javascript
function getTotal(...numbers: number[]): number {
    let total = 0;
    numbers.forEach((num) => total += num);
    return total;
}
```

## TypeScript Interface

- Interface is the structure or skeleton for object.
- Interface in typescript is types for the object.
- The TypeScript compiler uses interface for type-checking (also known as "duck typing" or "structural subtyping") whether the object has a specific structure or not.

**Example**

```javascript
interface Person {
    firstName: string;
    lastName: string;
}

function getFullName(person: Person) {
    return `${person.firstName} ${person.lastName}`;
}

let john = {
    firstName: 'John',
    lastName: 'Doe'
};

console.log(getFullName(john));
```

By convention, the interface names are in the camel case. They use a single capitalized letter to separate words in there names. For example, Person, UserProfile, and FullName.

### Optional properties

An interface may have optional properties. To declare an optional property, you use the question mark (?) at the end of the property name in the declaration.

**Example**

```javascript
interface Person {
    firstName: string;
    middleName?: string;
    lastName: string;
}
```

### Readonly properties

If properties should be modifiable only when the object first created, you can use the readonly keyword before the name of the property.

**Example**

```javascript
interface Person {
    readonly ssn: string;
    firstName: string;
    lastName: string;    
}

let person: Person;
person = {
    ssn: '171-28-0926',
    firstName: 'John',
    lastName: 'Doe'
}
```

### Function types

In addition to describing an object with properties, interfaces also allow you to describe function types.

**Example**

```javascript
interface StringFormat {
    (str: string, isUpper: boolean): string
}

let format: StringFormat;

format = function (str: string, isUpper: boolean) {
    return isUpper ? str.toLocaleUpperCase() : str.toLocaleLowerCase();
};

console.log(format('hi', true));
```

### Class Types

The interface is to define a contract between unrelated classes.

**Example**

```javascript
interface Json {
   toJSON(): string
}

class Person implements Json {
    constructor(private firstName: string,
        private lastName: string) {
    }
    toJson(): string {
        return JSON.stringify(this);
    }
}

let person = new Person('John', 'Doe');
console.log(person.toJson());
```

## Extend Interfaces

An interface can extend one or multiple existing interfaces.

**Example**

```javascript
interface A {
    a(): void
}

interface B extends A {
    b(): void
}

```

### Interfaces extending multiple interfaces

**Example**

```javascript
interface C {
    c(): void
}

interface D extends B, C {
    d(): void
}

**Example**

```javascript
interface Mailable {
    send(email: string): boolean
    queue(email: string): boolean
}

interface FutureMailable extends Mailable {
    later(email: string, after: number): boolean
}

class Mail implements FutureMailable {
    later(email: string, after: number): boolean {
        console.log(`Send email to ${email} in ${after} ms.`);
        return true;
    }
    send(email: string): boolean {
        console.log(`Sent email to ${email} after ${after} ms. `);
        return true;
    }
    queue(email: string): boolean {
        console.log(`Queue an email to ${email}.`);
        return true;
    }
}
```
