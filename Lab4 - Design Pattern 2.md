# Lab4 - Design Pattern 2

## Exercise 01
Implement Factory Method pattern to create two types of light bulbs: regular bulbs and energy saver bulbs.
    - Regular bulbs have a range of lumens between 50 and 100 and last for 1 year.
    - Energy saver bulbs have a range of lumens between 5 and 40 and last for 10 years and comes in multiple colors.

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
Implement Decorator pattern to add a logger to any object (additional class is needed). A logger method will log a message to the console. 
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
Implement Strategy pattern to choose between different logging algorithms, choosing between:

console.info()
console.warn()
console.error()
console.table() accepts an array of objects


```javascript
class Info{
    logging(element){console.info(element)}
}
class Warn{
    logging(element){console.warn(element)}
}
class Error{
    logging(element){console.error(element)}
}
class Table{
    logging(element){ console.table(element)}
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
Create a memoized version of the following fibonacci() recursive method to improve its performance.

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

 

// fibonacci() recursive method

function fibonacci2(n) {
    if (n <= 1) {
        return 1;
    }
    return fibonacci2(n - 1) + fibonacci2(n - 2);
}

console.time(fibonacci2(50))
console.timeEnd(fibonacci2(50))  // 20365011074: 3:02.244 (m:ss.mmm)


```
