---
layout: page
title: Qlik Sense 3.0
permalink: /commercial/qlik/3.x/working-with-field-programmatically/
---


# [Qlik Sense 3.0] Working with field programmatically

<br/>

	var myApp = qlik.currApp();

<br/>

	var fieldName = "Месяц";
	var myField = myApp.field(fieldName);

<br/>

	var myFieldData = myField.getData();

<br/>

	console.log(myFieldData);

<br/>

	$.each(myFieldData, function(key, value) {
		console.log(key, value);
	});


I have trouble with receiving data.  

http://stackoverflow.com/questions/39768658/how-to-receive-data-from-field-in-qlik-sense-3-0





<br/>


	 // Without "app.getList" it not works

	  $.each(myField.getData().rows, function(key, value) {
		 console.log(value.qText);
	  });



	 // It Works

	function getArrayWithMonth(promise, fieldName){

		 console.log("getArrayWithMonth");

		 var loc_selections = [];

		  app.getList("SelectionObject", function(reply){

			 console.log("APP.GETLIST");

			 loc_selections = [];

			  $.each(app.field(fieldName).getData().rows, function(key, value) {

				   // console.log(value.qText);
				   // console.log(value.qElemNumber);

				   loc_selections.push({'monthName':value.qText, 'monthValue':value.qElemNumber});
			  });

			   console.log("END");
			   promise.resolve(loc_selections);

			   console.log("resFUNCTION");
			   console.log(loc_selections);
			   return loc_selections;
		  });

	}


<br/>

      var field = app.field('Year');

	  $.each(field.getData().rows, function(key, value) {
		 // console.log(value.qText);
		 console.log(value.qNum);

	  });
