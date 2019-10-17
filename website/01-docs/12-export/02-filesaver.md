---
layout: page
title: Export By FileSaver.js
permalink: /export/filesaver/
---

<br/>


# Export to Excel By FileSaver.js

<a href="https://github.com/eligrey/FileSaver.js" rel="nofollow">FileSaver</a>


<br/>

My Example:

    var vTitleXXX = 'ABCD';

    var vEncodeHead = '<html><head><meta charset="UTF-8"></head><body>';
    var vReportName = '';

    vReportName += '<b style="color:#39639c"><font size="6">';
    vReportName += vTitleXXX;
    vReportName += '</b></font><br>';


    var HTML = '<table style="font-weight: bold"><tr style="background-color:red"><td>a</td><td>b</td></tr><tr><td>1</td><td>2</td></tr><tr><td>1</td><td>2</td></tr></table>';

     var Qlik = new Blob([vEncodeHead +vReportName  + HTML + '</body></html>'], {
    		type: "application/vnd.ms-excel;charset=utf-8"
     });

     saveAs(Qlik, "XXX.xls");


<br/>

Another example with export in Word:

https://github.com/iviasensio/SmartExport
