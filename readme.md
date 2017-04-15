一个简单的输入关键字添加标签效果

![keyWord](https://github.com/bxcn/keyWord/blob/master/keyWord.png)

实现功能：
* 输入关键字加空格键添加tag标签
* 按Backspace键删除一个标签
* 输入关键字后，鼠标失去焦点添加tag标签
* keyWord.init方法初始化方法
* 防止输入重复的关键字

```html

<style>
	.block {
		display:flex;
		flex-direction:row;
		align-items:center;
		width:500px;
		height:30px;
		border:1px solid #ddd;
		padding:10px;
		margin:100px auto 0;
	}
	#wordTags {
		display:flex;
		flex-wrap:nowrap;
	}
	input{
		width:100%;
		height:20px;
		border:none;
	}
</style>

<div class="block">
	<div id="wordTags"></div>
	<input id="wordInput" type="text" name="" placeholder="请输入关键词以空格结尾">
	<input id="wordHiddenInput" type="hidden" name="">
</div>

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

属性说明：
* panel:面板的id
* value:隐藏字段的id
* max:最多输入关键字个数
* tips:提示语