# Lab6 - JS DOM

## Exercise 01   HTML Page: https://patrick-bp.github.io/CS445/Lab6/calculator.html

- Create a swap.html page which has 2 pictures and 1 button on it.
- You can use any picture you want.
- The button is named Swap.
- When you click the Swap button, the location of two pictures are swaped.

## HTML :
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-ka7Sk0Gln4gmtz2MlQnikT1wXgYsOg+OMhuP+IlRH9sENBO0LRn5q+8nbTov4+1p" crossorigin="anonymous"></script>
    
    <title>Document</title>
</head>
<body>
<div class="container mt-4 w-25 d-flex">
    <div id="img1" class="justify-content-start p-3"><img src="img/img1.png"></div>
    <div class="justify-content-center  "><button id="btn" class="btn btn-primary align-items-center">swap</button></div>
    <div id="img2" class="justify-content-end p-3" ><img src="img/img2.png"></div>
    
    
</div>
    
    <script src="script.js"></script>
</body>
</html>

```


## Javascript : 

``` javascript

"use strict";
/* eslint-disable */

let img1 = document.getElementById("img1");
let img2 = document.getElementById("img2");
let btn = document.getElementById("btn");

btn.onclick = swap;

function swap(){  
let x = img1.innerHTML; 
   img1.innerHTML = img2.innerHTML;
   img2.innerHTML = x;
}



```


# Exercise 02  HTML Page: https://patrick-bp.github.io/CS445/Lab6/swap.html

- Create a simple calculator.html page which has 3 inputs and 1 submit on it.
- The first 2 inputs are only allowed to put numbers.
- If you use type any number in the first 2 inputs, then click submit button. JavaScript will sum the two numbers, display the typed number in the first 2 inputs, the      result in the last input.

## HTML

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-ka7Sk0Gln4gmtz2MlQnikT1wXgYsOg+OMhuP+IlRH9sENBO0LRn5q+8nbTov4+1p" crossorigin="anonymous"></script>
    <title>Document</title>
</head>
<body>

    <div class="container mt-4 w-25">
        <h1 class="text-center mb-4">Calculator</h1>
        <div class="input-group mb-3">
        <span class="input-group-text" >First number:</span>
        <input type="number" id="num1"class="form-control" aria-label="Username" aria-describedby="basic-addon1">
      </div>
      <div class="input-grou mb-3">
      <select class="form-select" id="op" aria-label="Default select example">
        <option selected>Please select an operation</option>
        <option value="+">Add</option>
        <option value="-">substract</option>
        <option value="*">Multiply</option>
        <option value="/">Divide</option>
      </select>
    </div>
      <div class="input-group mb-3">
        <span class="input-group-text" >Second number:</span>
        <input type="number"id="num2" class="form-control"  aria-label="Username" aria-describedby="basic-addon1">
      </div>
      <div class="input-group mb-3">
        <span class="input-group-text" id="basic-addon1">Result:</span>
        <input type="text" id="result" class="form-control"   aria-describedby="basic-addon1">
      </div>
      <button type="submit" id="submit" class="btn btn-primary">Submit</button>

    </div>
    
     <script src="calculator.js"></script>
</body>
</html>


```

## Javascript

```javascript
"use strict";
/* eslint-disable */

let input1 = document.getElementById("num1");
let op = document.getElementById("op");
let input2 = document.getElementById("num2");
let result = document.getElementById("result");
let submit = document.getElementById("submit");

submit.addEventListener("click", function(){
    
    for (const option of op.options) {
       
        if(option.selected){
            if(option.value === "+"){
                result.value =   Number(input1.value) + Number(input2.value);
 
                }else if(option.value === "-"){
                    result.value =  Number(input1.value) - Number(input2.value);
                }else if(option.value === "*"){
                    result.value =  Number(input1.value) * Number(input2.value);
                }else if(option.value === "/"){
                    result.value =  Number(input1.value) / Number(input2.value);
                }else{
                    
                    result.value =  "Please use +, -, * or / operators";

                }
        }
    }
    
});
```

