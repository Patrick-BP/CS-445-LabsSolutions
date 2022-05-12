
# Lab9 - fetch   https://patrick-bp.github.io/CS445/lab9/

Today's lab is used to practice using fetch to get data from sever side. Since we haven't learnt how to create server side, we choose Random User APIs which is a free and easy to use service to generate random user data for application testing.

Read Random User APIs, then create a html page which displays a list of 5 employees. On the same page, there's a Refresh button, when click the button, new 5 employees will be fetched/displayed without loading the entire page.

The below is an example of the appearance of the html page. You don't need to have the same style. The importance is the feature.

## html 

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-ka7Sk0Gln4gmtz2MlQnikT1wXgYsOg+OMhuP+IlRH9sENBO0LRn5q+8nbTov4+1p" crossorigin="anonymous"></script>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">
    <script src="myscript.js" ></script>
    <style>
        .container2{width: 40%;margin: auto;}
    </style>

    <title>Lab9</title>
    
</head>
<body>
    <div class="container2 ">
<h1 class="text-center p-4">Employees List</h1>

<div id="wrapper"></div>
    
<div class="d-flex justify-content-center"><button type="button" id="btn" class="btn btn-success rounder-5 mt-4 fs-4 text-center p-4">Refresh</button></div>
    </div>
    
</body>
</html>
```

## javascript

```javascript
"use strict";
/* eslint-disable */
window.onload = function(){
    let wrapper = document.getElementById("wrapper");
     document.getElementById("btn").onclick = function(){
        wrapper.innerHTML = "";
        fetch(`https://randomuser.me/api/?results=3`)
.then(res => res.json())
.then(data => {
    data.results.forEach(element => {
        console.log(element)
         let temp = `<div id="container" class="container d-flex border-top justify-content-between pt-4 mb-4 ">
        <div><img src="${element.picture.large}" class="p-4" alt=""></div>
        <div class="text-end align-middle fs-5">
        <div class="fw-bold"> ${element.name.first} ${element.name.last}</div>
        <div>phone: ${element.phone} </div>
        <div> ${element.email}</div> 
        </div>
        </div>` ;
        wrapper.innerHTML += temp;
    });

})
    };
    
fetch(`https://randomuser.me/api/?results=3`)
.then(res => res.json())
.then(data => {
    data.results.forEach(element => {
        console.log(element)
         let temp = `<div id="container" class="container d-flex border-top justify-content-between pt-4 mb-4 ">
        <div><img src="${element.picture.large}" class="img-thumbnail " alt=""></div>
        <div class="text-end align-middle fs-5">
        <div class="fw-bold"> ${element.name.first} ${element.name.last}</div>
        <div>phone: ${element.phone} </div>
        <div> ${element.email}</div> 
        </div>
        </div>` ;
        wrapper.innerHTML += temp;
    });
 
})
}


```
