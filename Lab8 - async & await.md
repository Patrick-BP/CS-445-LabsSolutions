# Lab 8 - async & await

## Exercise 01
Based on the isPrime function below which is the solution of yesterday's solution for Exercise 01, create a new function named isPrimeAsync which use async&await keywords to resolve the isPrime function.

```javascript
async function helper(num) {
    for (let i = 2; i <= Math.sqrt(num); i++) {
        if (num % i === 0) 
            throw new Error('oops')
    }
return { prime: true };
}
async function isPrimeAsync(num) {
    try {
        let result = await helper(num);
        console.log(result);
    } catch (e) {
        console.log({ prime: false });
    }

}

console.log('start');
isPrimeAsync(7)
console.log('end');





```
## Exercise 02
Create a method named removeDuplicatesAsync which works only for Array types and removes all duplicates for any array asynchornously. You MUST use async & await When you finish, test using the code below:
```javascript

Array.prototype.removeDuplicatesAsync = async function () {

   async function bar(r) {
      let newArr = [...new Set(r)];
      return newArr;
   }
   let res = await bar(this);
   console.log(res);
}



console.log(`start`);
[4, 1, 5, 7, 2, 3, 1, 4, 6, 5, 2].removeDuplicatesAsync();
console.log(`end`);
```
