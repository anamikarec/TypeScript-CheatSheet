# TypeScript-CheatSheet
### TypeScript Cheat Sheet : A complete Guide to get started with TypeScript  

#### There are two syntaxes for building types: Interfaces and Types. You should prefer interface. Use type when you need specific features.

- Interface is used to declare the type of an object in TypeScript:~
```js
  interface User{
  name : string,
  id:number
}
const employee : User {
  name : "Alice",
  id: 123
}
```
- To declare a class using typescript follow the following schema:~
```js
  class UserCredential{
    name: string;
    id: number;

    constructor( name:string, id:number){
      this.name = name;
      this.id = id;
  }
}

const user : User = new UserCredential("Alish",1);
```
### Composing Types 
#### With TypeScript, you can create complex types by combining simple ones. There are two popular ways to do so: with unions, and with generics.

#### 1.UNION :~

- To Declare a Boolean variable using typescript use the following syntax:~
- Ex.1
```js
 type MyBool = true | false;
```
- Ex.2
```js
  type WindowStates = "open" | "closed" | "minimized";
  type LockStates = "locked" | "unlocked";
  type PositiveOddNumbersUnderTen = 1 | 3 | 5 | 7 | 9;
```
- To declare a function having return type number and accept parameter of type string or array use the following syntax:~
```js

  function getLength(obj: string | string[]):number{
    return obj.length;
  }

  console.log(getLength(["A","B"]));
```
- To learn the type of a variable, use typeof:
```js
    string =>	typeof s === "string"
    number =>	typeof n === "number"
    boolean =>	typeof b === "boolean"
    undefined =>	typeof undefined === "undefined"
    function =>	typeof f === "function"
    array =>	Array.isArray(a)
```
- For example, you can make a function return different values depending on whether it is passed a string or an array:

```js
  function wrapInArray(obj: string | string[]) {
    if (typeof obj === "string") {
      return [obj];
    }
    return obj;
   }
```
#### Generics:~
- Generics provide variables to types. 
- A common example is an array. 
- An array without generics could contain anything. 
- An array with generics can describe the values that the array contains.

```js
  type StringArray = Array<string>;
  type NumberArray = Array<number>;
  type ObjectWithNameArray = Array<{ name: string }>;
  
  
  const arr : StringArray = ["A","B","C"];
  console.log(arr);

  const arr2 : NumberArray = [1,2,3,4];
  console.log(arr2);

  const arr3 : ObjectWithNameArray = [{name:"Anamika"}]
  console.log(arr3);
```

### Structural Type System
- One of TypeScript’s core principles is that type checking focuses on the shape that values have. This is sometimes called “duck typing” or “structural typing”.

- In a structural type system, if two objects have the same shape, they are considered to be of the same type.

```js
    interface Point {
      x: number;
      y: number;
    }

    function logPoint(p: Point) {
      console.log(`${p.x}, ${p.y}`);
    }

    // logs "12, 26"
    const point = { x: 12, y: 26 };
    logPoint(point);
    
  ```
  - In above code, the point variable is never declared to be a Point type. However, TypeScript compares the shape of point to the shape of Point in the type-check. They have the same shape, so the code passes.
  
  - Note :~ The shape-matching only requires a subset of the object’s fields to match.
