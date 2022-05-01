# Lab4 - Design Pattern 2

## Exercise 01
```javascript
class RegularBulbs{
    constructor(){
        this.lumens = "50-100";
        this.years = 1;
    }
    
}
class EnergyBulbs{
    constructor(color){
        this.lumens = "5-40";
        this.years = 10;
        this.color = color;
    }
}

class Factory{
    
    createBulb(type, color){
        let bulb;
        if(type === "regular"){
            bulb = new RegularBulbs();
            
        }else if(type === "energy"){
            bulb = new EnergyBulbs();
            bulb.color = color;
        }
        bulb.type = type;
        return bulb
    }

}


const bulbs = [];
const factory = new Factory();

bulbs.push(factory.createBulb("regular"));
bulbs.push(factory.createBulb("energy", "red"));


for (let i = 0, len = bulbs.length; i < len; i++) {
    console.log(bulbs[i]);
}
```
## Exercise 02
```javascript
class User{
    constructor(name){
        this.name = name;
    }
}
class DecoratedUser{
    constructor(user, street, city){
        this.user = user;
        this.name = user.name;
        this.street = street;
        this.city = city;
    }
        logger(){
            console.log(`Decorated User: ${this.name} , ${this.street} , ${this.city} `);
        };
    
}

const user = new User("Kelly");

const decorated = new DecoratedUser(user, "Broadway", "New York");
decorated.logger();
```
## Exercise 03
```javascript
class Info{
    logging(element){console.log(element)}
}
class Warn{
    logging(element){console.log(element)}
}
class Error{
    logging(element){console.log(element)}
}
class Table{
    logging(element){ console.log(element)}
}


class Strategy{
    event = "";
    setStrategy(event){
        this.event = event
    }

    logging(element){
        return this.event.logging(element);
    }


}

const strategy = new Strategy();

strategy.setStrategy(new Info());
strategy.logging('info....');

strategy.setStrategy(new Warn());
strategy.logging('warn....');

strategy.setStrategy(new Error());
strategy.logging('error....');

strategy.setStrategy(new Table());
strategy.logging(['table', 'table']);
```
## Exercise 04
```javascript
let fibonacci = (function(){
    let memo = {};

    function func(num){
        let value;
        if(num in memo){ 
            value = memo[num]; 
        }else{
            if(num === 0 || num === 1){
                value = 1;
            }else{
                value = func(num-1) + func(num-2); 
            }
            memo[num] = value;
        }
    return value;
    }
return func;
})();


console.time(fibonacci(50))
console.timeEnd(fibonacci(50))  // 20365011074: 0.126ms

 



function fibonacci2(n) {
    if (n <= 1) {
        return 1;
    }
    return fibonacci2(n - 1) + fibonacci2(n - 2);
}

console.time(fibonacci2(50))
console.timeEnd(fibonacci2(50))  // 20365011074: 3:02.244 (m:ss.mmm)


```
