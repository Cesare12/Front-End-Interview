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

5. 垂直水平居中
