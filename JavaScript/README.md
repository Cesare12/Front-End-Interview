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

防抖：最后一次触发后，停下来，计时到一定时间再执行。
节流：第一次先执行，一定时间内不再执行第二次。
```
function debounce (f, wait) {
  let timer
  return (...args) => {
    clearTimeout(timer)
    timer = setTimeout(() => {
      f(...args)
    }, wait)
  }
}
```
```
function throttle (f, wait) {
  let timer
  return (...args) => {
    if (timer) { return }
    timer = setTimeout(() => {
      f(...args)
      timer = null
    }, wait)
  }
}
```

3.解析url

```
function parse(url) {

    // 一、夹杂在 ? 与 # 之前的字符就是 qs，使用 /\?([^/?#:]+)#?/ 正则来抽取
    // 使用正则从 URL 中解析出 querystring
    // 二、通过 Optional Chain 来避免空值错误
    const queryString = url.match(/\?([^/?#:]+)#?/)[1]
  
    if (!queryString) { return {} }

    queryObj = queryString.split('&').reduce((params, block) => {
        // 三、如果未赋值，则默认为空字符串
        const [_k, _v = ''] = block.split('=')
        // 四、通过 decodeURIComponent 来转义字符，切记不可出现在最开头，以防 ?tag=test&title=1%2B1%3D2 出错
        const k = decodeURIComponent(_k)
        const v = decodeURIComponent(_v)

        if (params[k] !== undefined) {
            // 处理 key 出现多次的情况，设置为数组
            params[k] = [].concat(params[k], v)
        } else {
            params[k] = v
        }
        return params
    }, {})
    return queryObj
}
```
