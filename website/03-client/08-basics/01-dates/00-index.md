---
layout: page
title: Working with dates in JavaScript
description: Working with dates in JavaScript
keywords: Working with dates in JavaScript
permalink: /client/js/dates/
---

# Working with dates in JavaScript

    var d = new Date("2015-03-25");

<br/>

    function dateFormat(date){

          var dd = date.getDate();
          var mm = date.getMonth()+1; //January is 0!
          var yyyy = date.getFullYear();

          if(dd<10) {
              dd='0'+dd;
          }

          if(mm<10) {
              mm='0'+mm;
          }

          date = dd + '-' + mm + '-' + yyyy;
          // date = yyyy+'-'+mm+'-'+dd;

      return date;
    }

<br/>
<br/>

    var today = new Date();
    var day_7 = new Date();
    day_7.setDate(day_7.getDate() - 7);

    var day_8 = new Date();
    day_8.setDate(day_8.getDate() - 8);

    var day_14 = new Date();
    day_14.setDate(day_14.getDate() - 15);

    console.log(dateFormat(today));
    console.log(dateFormat(day_7));
    console.log(dateFormat(day_8));
    console.log(dateFormat(day_14));

**Result:**

    25.11.2016
    18.11.2016
    17.11.2016
    10.11.2016

<br/>

### Convert String to JavaScript date

    var l_data11 = "2016-11-30";
    var l_data22 = "2016-04-30";

    var l_data1 = new Date(l_data11); // 2016-11-30
    var l_data2 = new Date(l_data22); // 2016-04-30



    console.log("l_data1 XXXX");
    console.log(dateToSQLDate(dateFormat(l_data1)));

    console.log("l_data2 XXXX");
    console.log(dateToSQLDate(dateFormat(l_data2)));



    function dateToSQLDate(data){
        return data.substring(0, 10);
    }

<br/>

==========================================================

<br/>

    var theBigDay = new Date(1962, 6, 7); // 1962-07-07
    theBigDay.setDate(24);  // 1962-07-24
    theBigDay.setDate(32);  // 1962-08-01
    theBigDay.setDate(22);  // 1962-08-22
