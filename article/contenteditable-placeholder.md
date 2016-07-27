## 可编辑div的placeholder实现

有些场景，需要用div模拟输入框，然而placeholder属性只对input, textarea有效，下面是纯CSS实现方案

```html
<div contenteditable="true" placeholder="请输入"></div>
```
```css
[contenteditable=true]:empty:not(:focus):before{
    content:attr(placeholder);
    color: #999;
}
```
<div>
    <style>
        [contenteditable=true]{
            padding: 4px 6px;
            border: 1px solid #ccc;
        }
        [contenteditable=true]:empty:not(:focus):before{
            content:attr(placeholder);
            color: #999;
        }
    </style>
    <p>试试看吧</p>
    <div contenteditable="true" placeholder="请在这随便输入点什么吧"></div>
</div>

###### 参考：
[http://stackoverflow.com/questions/20300138/is-it-possible-to-add-placeholder-in-div-tag](http://stackoverflow.com/questions/20300138/is-it-possible-to-add-placeholder-in-div-tag)
