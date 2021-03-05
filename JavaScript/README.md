1.使用setTimeout替代setInterval，setInterval是间隔固定时间开始执行函数，setTimeout是执行函数结束后间隔固定时间再开始下一次执行函数
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
2.防抖，节流
