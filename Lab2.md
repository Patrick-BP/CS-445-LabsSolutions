# Lab2

## Exercise 01

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

## Exercise 02

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
  
  
## Exercise 03
## Exercise 04

