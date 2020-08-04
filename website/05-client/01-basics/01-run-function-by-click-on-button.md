---
layout: page
title: JavaScript Run Function by Click on button
permalink: /client/js/run-function-by-click-on-button/
---

# JavaScript Run Function by Click on button

{% highlight html linenos %}

<!DOCTYPE html>
<html>
<head>
	<title>Test</title>
	<meta charset="UTF-8">

    <script src="script.js"></script>

</head>
<body>
	<h1>Hello!</h1>

    <input id="clickMe" type="button" value="Загрузить PDF" onclick="myFunc();" />

</body>
</html>

{% endhighlight %}

<br/>

**script.js**

<br/>

{% highlight html linenos %}

var myFunc = function(){
console.log('Click');
}

{% endhighlight %}
