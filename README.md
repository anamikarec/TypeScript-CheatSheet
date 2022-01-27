# TypeScript-CheatSheet
TypeScript Cheat Sheet : A complete Guide to get started with TypeScript  

- interface is used to declare the type of an object in TypeScript
```js
  interface User{
  name : string,
  id:number
}
```

```js
  class UserCredential{
  name: string;
  id: number;

  constructor(name:string,id:number){
    this.name = name;
    this.id = id;
  }
}

 const user : User = new UserCredential("Alish",1);
```
```js
 type MyBool = true | false;
```
```js

  function getLength(obj: string | string[]):number{
    return obj.length;
  }

  console.log(getLength(["A","B"]));
```
