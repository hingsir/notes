## height: auto 过渡效果实现

transition对于height来说必须是具体的数值才有效，并不适用于auto，可以借助max-height来模拟，虽然效果不是特别的好，隐藏时会有延时，而且max-height数值越大越明显。

```css
#menu #list {
    max-height: 0;
    transition: max-height 0.15s ease-out;
    overflow: hidden;
    background: #d5d5d5;
}

#menu:hover #list {
    max-height: 500px;
    transition: max-height 0.25s ease-in;
}
```
```html
<div id="menu">
    <a>hover me</a>
    <ul id="list">
        <!-- Create a bunch, or not a bunch, of li's to see the timing. -->
        <li>item</li>
        <li>item</li>
        <li>item</li>
        <li>item</li>
        <li>item</li>
    </ul>
</div>
```
[Run JSFiddle demo >>](http://jsfiddle.net/thechrisjordan/3Fc7D/23/)

**扫一扫看[demo](http://hingsir.com/demo/height-auto-transition)**

![二维码](http://qr.liantu.com/api.php?w=256&m=10&text=http://hingsir.com/demo/height-auto-transition)

查看更多解决方案：[http://stackoverflow.com/questions/3508605/how-can-i-transition-height-0-to-height-auto-using-css](http://stackoverflow.com/questions/3508605/how-can-i-transition-height-0-to-height-auto-using-css)
