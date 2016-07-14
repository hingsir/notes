## iOS webview非原生键盘（如搜狗）遮挡输入框解决方案

给输入框绑定focus事件
```js
$('input').on('focus', function(){
    setTimeout(function () {
        document.activeElement.scrollIntoViewIfNeeded();
    }, 300);
})
```
参考：[https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollIntoViewIfNeeded](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollIntoViewIfNeeded)
