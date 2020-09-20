---
layout: page
title: pdfmake
description: pdfmake
keywords: pdfmake
permalink: /export/pdf/pdfmake/
---

# pdfmake

<br/>

pdfmake - can make export on client and server side. For sever side needs node.js

<br/>

Need to copy pdfmake.min.js (or pdfmake.js), vfs_fonts.js

<br/>

{% highlight html linenos %}

<!DOCTYPE html>
<html>
<head>
	<title>Test</title>
	<meta charset="UTF-8">

    <script src="pdfmake.js"></script>
    <script src="vfs_fonts.js"></script>
    <script src="script.js"></script>

</head>
<body>
	<h1>Hello!</h1>

    <input id="clickMe" type="button" value="Download PDF" onclick="myFunc();" />

</body>
</html>

{% endhighlight %}

<br/>

**script.js**

<br/>

{% highlight html linenos %}

var docInfo = {

    info: {
        title: 'PDF Doc',
        author: 'Marley',
        subject: 'Theme',
        keywords: 'My keywords'
    },

    pageSize: 'A4',
    pageOrientation: 'landscape',
    pageMargins: [50,50,30,60],

    header: function(currentPage, pageCount){
        return {
            text: currentPage.toString() + ' of ' + pageCount,
            alignment: 'right',
            margin: [0, 30, 10, 50]
        }
    },


    footer: [
        {
            text:'Some Footer',
            alignment: 'center'
        }
    ],

    content: [
        {
            text: 'Paragraph Text',
            fontSize: 20
        }
    ]

}

var myFunc = function(){
pdfMake.createPdf(docInfo).download('PdfFileName.pdf');
}

{% endhighlight %}
