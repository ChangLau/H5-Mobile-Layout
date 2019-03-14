# H5-Mobile-Layout

H5 移动端适配方案（rem 布局、vw 布局、阿里 flexible 布局）

### 阿里 flexible 布局

[参考链接](https://www.w3cplus.com/mobile/lib-flexible-for-html5-layout.html)

```
750px 设计稿作为参考
通过引入阿里flexible CDN 会自动设置html font-size 配置meta信息
font-size会设置为(视窗宽度/10)
计算宽度：设计稿元素宽度 / (750/10) + 'rem'
```

### rem 布局、vw 布局

[参考链接](https://juejin.im/post/5bbb16b9e51d450e7210e1ee)

- rem 布局

```
设置
<meta
    name="viewport"
    content="width=device-width,initial-scale=1,minimum-scale=1,maximum-scale=1,user-scalable=no"
/>
750px设计稿作为参考
设置html font-size为(clientWidth/750) * 100
var html = document.documentElement
function setFont() {
    var cliWidth = html.clientWidth
    html.style.fontSize = 100 * (cliWidth / 750) + 'px'
}
实际应用的时候 如设计稿中长度为375px 则计算为3.75rem(设计稿长度/100)即可
```

- vw 布局

```
设置
<meta
    name="viewport"
    content="width=device-width,initial-scale=1,minimum-scale=1,maximum-scale=1,user-scalable=no"
/>
通过css3设置font-size
html {
    /* 100vw等于视口宽度 1vw等于视口宽度的1/100 */
    font-size: calc(100vw / 750 * 100);
    width: 100%;
    height: 100%;
}
实际应用的时候 如设计稿中长度为375px 则计算为3.75rem(设计稿长度/100)即可
```
