一个简单的输入关键字添加标签效果

实现功能：
* 输入关键字加空格键添加tag标签
* 按Backspace键删除一个标签
* 输入关键字后，鼠标失去焦点添加tag标签
* keyWord.init方法初始化方法

```html
<script src="https://cdn.bootcss.com/jquery/1.12.4/jquery.js"></script>
<script type="text/javascript" src="aspect.js"></script>
<script type="text/javascript" src="keyWord.js"></script>
```

```javascript
$(function () {
    var keyWord = $("#wordInput").keyWord({
        panel: '#wordTags',
        value: '#wordHiddenInput',
        max: 3,
        tips: '最多只能输入3项'
    });

    keyWord.init('php,java,前端开发')
});

```