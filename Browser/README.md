1. 事件循环

![image](https://res.cloudinary.com/practicaldev/image/fetch/s--hPFPTZp2--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/p54casaaz9oq0g8ztpi5.gif)

```
console.log('start')

setTimeout(() => {
  console.log('timeout')
}, 0)

const m = new Promise((res, rej) => {
  console.log('1')
  
  setTimeout(() => {
    res('12')
    console.log('123')
  }, 0)
 })
 
 m.then(res => console.log(res))
 
 console.log('end')
  
```
结果
```
start
1
end
timeout
123
12
```
```
console.log('start')

setTimeout(() => {
  console.log('timeout')
}, 0)

const m = new Promise((res, rej) => {
  console.log('1')
  res('12')
  console.log('123')
 })
 
 m.then(res => console.log(res))
 
 console.log('end')
  
```
结果
```
start
1
123
end
12
timeout
```
