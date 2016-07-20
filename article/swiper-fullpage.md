## swiper整屏切换效果

[swiper](http://www.swiper.com.cn/)是一款强大的移动端触摸滑动插件。但貌似没有类似fullpage那样整屏切换的效果（也可能是我孤陋了），也就是按住某页拖动的时候能同时看到两页，比如下面的栗子

![二维码](http://qr.liantu.com/api.php?w=256&text=http://hingsir.com/demo/swiper-normal)

结合zepto实现整屏切换效果

*  禁止slider滑动，添加`swiper-no-swiping`类

```xml
<div class="swiper-container">
    <div class="swiper-wrapper swiper-no-swiping">
        <div class="swiper-slide">slider1</div>
        <div class="swiper-slide">slider2</div>
        <div class="swiper-slide">slider3</div>
        <div class="swiper-slide">slider4</div>
    </div>
</div>
```

*  禁止document的touchmove事件

```js
$(document).on('touchmove', function(e){
    e.preventDefault()
});
```

*  利用zepto的swipe事件进行切换

```js
var mySwiper = new Swiper('.swiper-container', {
    direction: 'vertical',
    mousewheelControl: true
})

$(document).swipeUp(function(){
    mySwiper.slideNext();
}).swipeDown(function(){
    mySwiper.slidePrev();
})
```

**扫一扫看demo**

![二维码](http://qr.liantu.com/api.php?w=256&text=http://hingsir.com/demo/swiper-fullpage)
