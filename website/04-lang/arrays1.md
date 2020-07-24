---
layout: page
title: Arrays
permalink: /lang/arrays/1/
---


# Arrays


Array.pop - not pure. Do not recommend to use.
Array.splice - not pure. Do not recommend to use.

    const schools = [
        "Yorktown",
        "Washington & Lee",
        "Wakefield"
    ]

<br/>

### Join

    console.log( schools.join(", ") )
    // "Yorktown, Washington & Lee, Wakefield"


### Filter

<br/>

sample 1

    const wSchools = schools.filter(school => school[0] === "W")
    console.log( wSchools )
    // ["Washington & Lee", "Wakefield"]


<br/>

sample 2

    const cutSchool = (cut, list) =>
            list.filter(school => school !== cut)
            
            
    console.log(cutSchool("Washington & Lee", schools).join(" * "))
    // "Yorktown * Wakefield"


    console.log(schools.join("\n"))
    // Yorktown
    // Washington & Lee
    // Wakefield

<br/>

### Map

<br/>

sample 1

    const highSchools = schools.map(school => `${school} High School`)

    console.log(highSchools.join("\n"))
    // Yorktown High School
    // Washington & Lee High School
    // Wakefield High School

    console.log(schools.join("\n"))
    // Yorktown
    // Washington & Lee
    // Wakefield

<br/>

sample 2


    const highSchools = schools.map(school => ({ name: school }))
    console.log( highSchools )
    // [
    // { name: "Yorktown" },
    // { name: "Washington & Lee" },
    // { name: "Wakefield" }
    // ]


<br/>

sample 3


    let schools = [
        { name: "Yorktown"},
        { name: "Stratford" },
        { name: "Washington & Lee"},
        { name: "Wakefield"}
    ]
    const editName = (oldName, name, arr) =>
        arr.map(item => {
            if (item.name === oldName) {
                return {
                    ...item,
                    name
                }
            } else {
                return item
            }
        })
    let updatedSchools = editName("Stratford", "HB Woodlawn", schools)
    console.log( updatedSchools[1] )
    console.log( schools[1] )

    or


    const editName = (oldName, name, arr) =>
        arr.map(item => (item.name === oldName) ?
            ({...item,name}) :
            item
        )


<br/>

sample 4

    const schools = {
      "Yorktown": 10,
      "Washington & Lee": 2,
      "Wakefield": 5
    }
    const schoolArray = Object.keys(schools).map(key =>
        ({
            name: key,
            wins: schools[key]
        })
    )
    console.log(schoolArray)


<br/>

### reduce

<br/>

sample 1

    const ages = [21,18,42,40,64,63,34]
    const maxAge = ages.reduce((max, age) => {
      console.log(`${age} > ${max} = ${age > max}`)
      if (age > max) {
          return age
      } else {
          return max
      }
    }, 0)
    console.log('maxAge', maxAge)


<br/>

sample 2



    const ages = [21,18,42,40,64,63,34];
    // less syntax
    const max = ages.reduce(
        (max, value) => (value > max) ? value : max,
        0
    )
    console.log('max', max)


<br/>

sample 3

    const colors = [
        {
            id: '-xekare',
            title: "rad red",
            rating: 3
        },
        {
            id: '-jbwsof',
            title: "big blue",
            rating: 2
        },
        {
            id: '-prigbj',
            title: "grizzly grey",
            rating: 5
        },
        {
            id: '-ryhbhsl',
            title: "banana",
            rating: 1
        }
    ]
    const hashColors = colors.reduce(
        (hash, {id, title, rating}) => {
            hash[id] = {title, rating}
            return hash
        },
        {}
    )
    console.log(hashColors)


<br/>

sample 4

    const colors = ["red", "red", "green", "blue", "green"];
    const distinctColors = colors.reduce(
        (distinct, color) =>
            (distinct.indexOf(color) !== -1) ?
                distinct :
                [...distinct, color],
        []
    )
    console.log(distinctColors)


<br/>

**Links:** 

https://github.com/MoonHighway/learning-react/tree/master/chapter-03



<br/>

### Convert comma separated string to array


    var selections = [];
    selections.push({"field":"Year", "selected":"2000, 2002, 2004, 2006, 2008"});

    var field = selections["0"].field;
    var selected1 = selections["0"].selected;


    var temp1 = new Array();
    temp1 = selected1.split(",");

    // res ["2000", " 2002", " 2004", " 2006", " 2008"]

    var temp2 = new Array();
      temp2 = selected1.split(",").map(function(item) {
    	  return parseInt(item, 10);
    });

    // res [2000, 2002, 2004, 2006, 2008]


<br/>

### Example 2    


    var selections = [];
    selections.push({"field":"Territory code", "selected":"ABW, AFG, AGO, AIA, ALB"});


    var field1 = selections["0"].field;
    var selected1 = selections["0"].selected;

    var temp = new Array();
      temp = selected1.split(",");

      console.log("temp");
      console.log(temp);

      var res = [];

      for (var i = 0; i < temp.length; i++) {
        // console.log(temp[i]);
        res.push({qText:temp[i].trim()});
      }


      // res:


      [
          {
            "qText": "ABW"
          },
          {
            "qText": "AFG"
          },
          {
            "qText": "AGO"
          },
          {
            "qText": "AIA"
          },
          {
            "qText": "ALB"
          }
     ]



<br/>


### Create an Array of Object programmatically


    self.processLocationData = function (data) {

        var res = [];

          for (var i = 0; i < data.items.length; i++) {
            res.push(
                {
                    StartDate: rimLibs.dateFormatDefault(new Date(data.items[i].StartDate)),
                    EndDate: rimLibs.dateFormatDefault(new Date(data.items[i].EndDate)),
                    Item: data.items[i].Item
                }
            );
          }


        self.observableDatasource(res);
        document.getElementById('ring-container').style.display = 'none';
        document.getElementById('chart-container').style.display = 'inline';
    }  
