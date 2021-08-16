---
layout: page
title: Qlik Sense 3.0 Working Examples with selections
description: Qlik Sense 3.0 Working Examples with selections
keywords: Qlik Sense 3.0 Working Examples with selections
permalink: /commercial/qlik/3.x/working-with-selections-programmatically/
---

# [Qlik Sense 3.0] Working Examples with selections:

    var myApp = qlik.currApp();

    var fieldName = "Year";
    var field = myApp.field(fieldName);

<br/>

    field.selectAll();

<br/>

    myApp.field(fieldName).select([0], false, false);
    myApp.field(fieldName).selectMatch('1997', true);
    myApp.field(fieldName).select([0, 1, 2], true, true);

    myApp.field(fieldName).selectAll();
    myApp.field(fieldName).clear();

    myApp.field('Territory code').selectValues([{qText: 'CHN'},{qText: 'USA'}], false, false);
    myApp.field(fieldName).selectValues([1997, 1998, 1999, 2000], true, true);
