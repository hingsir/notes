## 在img标签上使用雪碧图

雪碧图的使用非常简单，但要在img标签上使用却需要做点额外的工作，主要有以下两种方案

* 额外的标签
```html
<style>
    .emoji {
        position: relative;
        display: inline-block;
        width: 25px;
        height: 25px;
        overflow:hidden;
    }
    .emoji img{
        position: absolute;
        left: 0;
    }
    .smile img{
        top: 0;
    }
    .laughing img{
        top: -25px
    }
    .blush img{
        top: -50px
    }
    .heart_eyes img{
        top: -75px
    }
</style>
<p class="emoji smile"><img src="../assets/img/emoji.png"></p>
<p class="emoji laughing"><img src="../assets/img/emoji.png"></p>
<p class="emoji blush"><img src="../assets/img/emoji.png"></p>
<p class="emoji heart_eyes"><img src="../assets/img/emoji.png"></p>
```

<div>
    <style>
        .emoji {
            position: relative;
            display: inline-block;
            width: 25px;
            height: 25px;
            overflow:hidden;
        }
        .emoji img{
            position: absolute;
            left: 0;
        }
        .smile img{
            top: 0;
        }
        .laughing img{
            top: -25px
        }
        .blush img{
            top: -50px
        }
        .heart_eyes img{
            top: -75px
        }
    </style>
    <p class="emoji smile"><img src="../assets/img/emoji.png"></p>
    <p class="emoji laughing"><img src="../assets/img/emoji.png"></p>
    <p class="emoji blush"><img src="../assets/img/emoji.png"></p>
    <p class="emoji heart_eyes"><img src="../assets/img/emoji.png"></p>
</div>

* 1×1透明gif
```html
<style>
    .emoji-control {
        display: inline-block;
        width: 25px;
        height: 25px;
        cursor: pointer;
        background-image: url(../assets/img/emoji.png);
        background-size: 25px auto;
        background-repeat: no-repeat;
        vertical-align: middle;
    }
    .emoji-smile {
        background-position: 0 0
    }
    .emoji-laughing {
        background-position: 0 -25px
    }
    .emoji-blush {
        background-position: 0 -50px
    }
    .emoji-heart_eyes {
        background-position: 0 -75px
    }
</style>
<img src="../assets/img/0.gif" class="emoji-control emoji-smile">
<img src="../assets/img/0.gif" class="emoji-control emoji-laughing">
<img src="../assets/img/0.gif" class="emoji-control emoji-blush">
<img src="../assets/img/0.gif" class="emoji-control emoji-heart_eyes">
```
<div>
    <style>
        .emoji-control {
            display: inline-block;
            width: 25px;
            height: 25px;
            cursor: pointer;
            background-image: url(../assets/img/emoji.png);
            background-size: 25px auto;
            background-repeat: no-repeat;
            vertical-align: middle;
        }
        .emoji-smile {
            background-position: 0 0
        }
        .emoji-laughing {
            background-position: 0 -25px
        }
        .emoji-blush {
            background-position: 0 -50px
        }
        .emoji-heart_eyes {
            background-position: 0 -75px
        }
    </style>
    <img src="../assets/img/0.gif" class="emoji-control emoji-smile">
    <img src="../assets/img/0.gif" class="emoji-control emoji-laughing">
    <img src="../assets/img/0.gif" class="emoji-control emoji-blush">
    <img src="../assets/img/0.gif" class="emoji-control emoji-heart_eyes">
</div>

###### 参考：
[http://stackoverflow.com/questions/4335957/using-sprites-with-img-tag](http://stackoverflow.com/questions/4335957/using-sprites-with-img-tag)
