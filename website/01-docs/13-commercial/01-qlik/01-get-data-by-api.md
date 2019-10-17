---
layout: page
title: Qlik Sense 3.0 How to programmatically get something by Qlik API
permalink: /commercial/qlik/3.x/get-data-by-api/
---


# [Qlik Sense 3.0] How to programmatically get something by Qlik API


    qlik.currApp().getAppLayout().then(function(applayout) {

        var appName = (applayout.layout && applayout.layout.qTitle) || applayout.qTitle;
        var appId = (applayout.layout && applayout.layout.qFileName) || applayout.qFileName;


        console.log('appName');
        console.log(appName);

        console.log('appId');
        console.log(appId);


        // var app = qlik.openApp(appId);

    });



<br/>

### Other Examples:


    app = qlik.currApp();


**AppList**


    qlik.getAppList(function(list){
        var str = "";
        $.each(list, function(key, value) {
            str +=  value.qDocName + '('+ value.qDocId + ') ';
        });
        console.log(str);
    });



<br/><br/>


    var app = qlik.currApp();


**FieldList**


    app.getList("FieldList", function(reply){
    	var str = "";
    	$.each(reply.qFieldList.qItems, function(key, value) {
    		str +=  value.qName + ' \n';
    	});
    	console.log(str);
    });


**MeasureList**


	app.getList("MeasureList", function(reply){
		var str = "";
		$.each(reply.qMeasureList.qItems, function(key, value) {
		          console.log(value.qData.title);
		});
	});


**DimensionList**


	app.getList("DimensionList", function(reply){
		var str = "";
		$.each(reply.qDimensionList.qItems, function(key, value) {
		          console.log(value.qData.title);
		});
	});



**BookmarkList**

	app.getList("BookmarkList", function(reply){

	// console.log(reply);

		var str = "";
		$.each(reply.qBookmarkList.qItems, function(key, value) {
			str +=  value.qData.title + ' ';
		});
		// alert(str);
		console.log(str);
	});


**SelectionObject**


    app.getObject('CurrentSelections').then(function(reply){

       $.each(reply.layout.qSelectionObject.qSelections, function(key, value) {
        });    
    );


<br/><br/>

// I don know why, that method can be executed many times.

<br/>    

	app.getList("SelectionObject", function(reply){
				var str = "";
				$.each(reply.qSelectionObject.qSelections, function(key, value) {
					console.log(value);
				});
	});


<br/>
<br/>

https://help.qlik.com/en-US/sense-developer/3.0/Subsystems/APIs/Content/MashupAPI/Methods/getList-method.htm



<br/>
<br/>

### Sheet

    var app = qlik.currApp();
    var vSheetId = qlik.navigation.getCurrentSheetId();


    var vTitle = '';


    app.getAppObjectList('sheet', function(getsheets){
        var vId = "";
        var vName ="";

        $.each(getsheets.qAppObjectList.qItems, function(key,value) {
            vId = value.qInfo.qId;
            if(vSheetId.sheetId == vId){

                vName = value.qData.title;
                vTitle += vName;

            }
        });
    });


<br/><br/>

    console.log(app.getObject("jYBsJ"));


<br/>


    var qTable = qlik.table(this);
    console.log(qTable);
