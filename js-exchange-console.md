```
  var counter = 0;
  var startMinuts = 30;
  var maxSecound = 10;
  var timer = setInterval(() => {
    if(new Date().getMinutes() == startMinuts) {
        if(new Date().getSeconds() < maxSecound){
            console.log(new Date().getSeconds());
            // code here
        } else {
            clearInterval(timer);
        }

    } }, 10 )
```
