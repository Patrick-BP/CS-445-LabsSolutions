# Lab6 - JS DOM

## Exercise 01
- Create a swap.html page which has 2 pictures and 1 button on it.
- You can use any picture you want.
- The button is named Swap.
- When you click the Swap button, the location of two pictures are swaped.

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



