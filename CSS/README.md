1. Position


2.div铺满屏幕，要先设置html,body高宽


```
<style>
      *{
          margin: 0;
          padding: 0;
       }
       html,body{
           width: 100%;
           height: 100%;
      }
      div{
           width:100%;
           height: 100%;
          background: yellow;
      }
</style>
```
  
3. 一行三列


```
body {
  width: 90%;
  max-width: 900px;
  margin: 0 auto;
}

div:nth-of-type(1) {
  width: 36%;
  float: left;
}

div:nth-of-type(2) {
  width: 30%;
  float: left;
  margin-left: 4%;
}

div:nth-of-type(3) {
  width: 26%;
  float: right;
}
```
```
.box {
  display: flex;
  justify-content: space-between;
}
```
```
.box {
  column-count: 3;
}
```
```
.box {
  display: grid;
}
.one{
  grid-row:1;
  grid-column:1;
}
.two{
  grid-row:1;
  grid-column:2;
}
.three{
  grid-row:1;
  grid-column:3;
}
```

4. 重排重绘

重排：元素位置发生变化，也叫回流，即layout会重新排序。
重绘：元素样式发生变化，但是位置不变。即Paint阶段重新绘制。
重排一定会导致重绘。
避免：
  1.CSS样式尽量批量修改
  2.为元素提前设置好高宽，不因多次渲染改变位置
  3.避免table布局

5. 垂直水平居中
