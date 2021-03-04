1.使用setTimeout替代setInterval
```
/** instead of:
let timerId = setInterval(() => alert('tick'), 2000);
*/
```
```
let timerId = setTimeout(function tick() {
  alert('tick');
  timerId = setTimeout(tick, 2000); // (*)
}, 2000);
```
封装
```
const setInter = function (func, delay) {
  setTimeout(function tick() {
    func();
    setTimeout(tick, delay);
  }, delay)
}

setInter(() => { console.log(1) }, 1000)
```
