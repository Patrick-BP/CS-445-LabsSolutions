# Lab2 - Typescript

## Exercise 01

```javascript
class University{
    name:String;
    dept:String;
    constructor(name:string , dept:string){
        this.name = name;
        this.dept = dept;
    }
    graduation(year:number):void{
        console.log(`Graduating ${this.dept} ${year} students`)
    }

}
let miu: University = new University("MIU", "MSD");
miu.graduation(2021)
```
## Exercise 02

```javascript
let bankAccount:{
    money:number,
   deposit(value:number):void
};

bankAccount = {
    money:2000,
    deposit(value){
        this.money += value;
    }
};

let myself : {
    name: string,
    bankAccount:typeof bankAccount;
    hobbies: Array<string>
}

myself = {
    name: "John",
    bankAccount: bankAccount,
    hobbies: ["Violin", "Cooking"]
};

myself.bankAccount.deposit(3000);
console.log(typeof bankAccount);
console.log(myself);
  ```
  
## Exercise 03

```javascript
    class Car{
    name:string;
    acceleration:number;
    constructor(name:string){
        this.name = name;
        this.acceleration = 0;
    }
    honk():void{
        console.log(`${this.name} is saying: Tooooooooot!`);
    }
    accelerate(speed:number):void{
        this.acceleration = this.acceleration + speed;
    }
}

let car: Car = new Car("BMW");
car.honk();
console.log(car.acceleration);
car.accelerate(60);
console.log(car.acceleration);

```
    
## Exercise 04

```javascript
    let baseObject: {
    width: number,
    length: number
};

baseObject = {
    width:0,
    length:0
}
let rectangle: any;

rectangle = Object.create(baseObject);

rectangle.width = 5;
rectangle.length = 2;

rectangle.calcSize = function ():number{
    return this.width * this.length;
};

console.log(rectangle.calcSize());
```
