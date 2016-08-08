## 微信webview异步设置网页title

如下代码在微信浏览器中是不起作用的
```js
setTimeout(function(){
    document.title = 'new title'
}, 1000)
```
利用iframe实现效果
```js
setTimeout(function(){
    setWeixinTitle('new title')
}, 1000)
function setWeixinTitle(title){
    document.title = title;
    var ifr = document.createElement('iframe')
    ifr.src="/favicon.ico"
    ifr.onload = function(){
        setTimeout(function(){
            document.body.removeChild(ifr)
        }, 0)
    }
    document.body.appendChild(ifr)
}
```

**微信扫一扫看demo**

![二维码](http://qr.liantu.com/api.php?w=256&m=10&bg=f7f7f7&text=http://hingsir.com/demo/weixin-webview-set-title)
