## iscroll 5 使用小记

* 常用配置说明

```js
var scroller = new IScroll('.wrapper',{
    probeType: 2, // 可选参数1，2，3, 区别在于scroll事件的触发时机
    bounceTime: 100, // 回弹用时
    mouseWheel: true, // 开启滚轮
    scrollbars: true, // 开启滚动条
    shrinkScrollbars: 'scale', // 滚动条动态伸缩的效果
    fadeScrollbars: true // 淡入淡出
});
```

* 关于probeType

    * 1：scroll事件只有在滚动条不繁忙的时候触发
    * 2：类似原生scroll事件，回弹时（松手后）不触发scroll
    * 3：松手回弹时也会触发

    *注*：如何获取松手一瞬间的y值？如果probeType为2，很简单，最后的y值就是。如果probeType为3，那么可以通过touchend事件去获取y。


* 内容不足撑满容器的时候无下拉效果问题

    找遍了整个官方文档也没看到怎么处理，只得用min-height撑满，并且得稍稍超出容器的高度，可设置min-height: 100.1%

* 别忘记禁用默认的touchmove事件，如果不禁用在iOS和Android上可能没问题，在windows phone上就华丽丽地挂了。

```js
    document.addEventListener('touchmove', function (e) { e.preventDefault(); }, false);
```

* surface需添加以下样式禁用默认的触摸行为
```css
html {
    touch-action:none;
    -ms-touch-action:none;
}
```

**扫一扫看[demo](http://hingsir.com/demo/iscroll-pull-refresh)**

![二维码](http://qr.liantu.com/api.php?w=256&m=10&bg=f7f7f7&text=http://hingsir.com/demo/iscroll-pull-refresh)

**[iscroll5 官方文档](http://iscrolljs.com/)**
