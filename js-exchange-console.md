```
var startMinuts = 30;
var timer = setInterval(() => {
if(new Date().getMinutes() == startMinuts) {
clearInterval(timer);
    setTimeout(()=> {
    // code here
}, 400);
} }, 1 )
```
