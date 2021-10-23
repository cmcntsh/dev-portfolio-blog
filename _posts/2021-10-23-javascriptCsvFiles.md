---
layout: post
comments: false
title: Working with CSV Files in JavaScript
categories: [CSV, JavaScript]
---

Some example of working with CSV files with JavaScript.

# Opening CSV files with JavaScript

## Challenges

There are a few examples of how to parse strings for csv files using JavaScript. One of the challenges with doing that, though is trying to code to cover different formats and exceptions. It might be a good idea to use an exiting library to do the heavy lifting.

## Requirements

Open a CSV file and load the contents into a JavaScript array so the data can be used in an application.

## Library

- PaPa Parse seems to be an easy library to use. <a href = "https://www.papaparse.com/" target = "_blank">https://www.papaparse.com/</a>

## Example

An example CSV file.

```
category,correct,answer2,answer3,answer4
a,right,wrong,wrong,wrong
a,right,wrong,wrong,wrong
a,right,wrong,wrong,wrong
b,right,wrong,wrong,wrong
b,right,wrong,wrong,wrong
b,right,wrong,wrong,wrong
c,right,wrong,wrong,wrong
c,right,wrong,wrong,wrong
c,right,wrong,wrong,wrong
```

An example HTML file.

```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<body>

    <input type="file" id="uploadFile" accept=".csv">
    <button id="uploadConfirm">Upload File</button>

    <p><button type="button" id="logVar">Log</button></p>

    <script src="https://cdn.jsdelivr.net/npm/papaparse@5.3.1/papaparse.min.js"></script>

    <script src="script.js"></script>
</body>

</html>
```

An example JavaScript file.

```
let questionsArr = [];
const uploadConfirm = document.querySelector('#uploadConfirm').addEventListener('click', () => {
    Papa.parse(document.querySelector('#uploadFile').files[0], {
        download: true,
        header: true,
        skipEmptyLines: true,
        complete: function(results){
            console.log(results);
            console.log(results.data);
            for (i=0; i < results.data.length; i++) {
                questionsArr.push(results.data[i]);
            }
            console.log(questionsArr);
            
        }
        
    }); 
    
});

const logButton = document.querySelector('#logVar').addEventListener('click', makeLog);


function makeLog() {
    //console.log(questionsArr);
    console.log(typeof questionsArr);
    console.log(questionsArr);
    console.log(questionsArr[8]);
}

```

# Saving CSV files with JavaScript

Data from a JavaScript array can be saved to a CSV file. PaPa Parse can help with this also.

## Example using PaPa Parse

This solution came from <a href = "https://stackoverflow.com/questions/52240221/download-save-csv-file-papaparse" target = "_blank">https://stackoverflow.com/questions/52240221/download-save-csv-file-papaparse</a>

An example HTML file.

```

```

An example JavaScript file.

```
const objects = [
    {firstName: 'John', lastName: 'Smith', age: 30},
    {firstName: 'Jane', lastName: 'Doe', age: 35}
];

const downloadCSV = function(){
    var csv = Papa.unparse(objects);
    console.log(objects);
    console.log(csv);
    var csvData = new Blob([csv], {type: 'text/csv;charset=utf-8;'});
    var csvURL =  null;
    if (navigator.msSaveBlob) {
        csvURL = navigator.msSaveBlob(csvData, 'download.csv');
    } else {
        csvURL = window.URL.createObjectURL(csvData);
    }
    var tempLink = document.createElement('a');
    tempLink.href = csvURL;
    tempLink.setAttribute('download', 'download.csv');
    tempLink.click();
}

downloadCSV();
```

## Example not using PaPa Parse

This solution came from <a href = "https://stackoverflow.com/questions/14964035/how-to-export-javascript-array-info-to-csv-on-client-side" target = "_blank">https://stackoverflow.com/questions/14964035/how-to-export-javascript-array-info-to-csv-on-client-side</a>

An example HTML .html file.

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <script src="script.js"></script>
</body>
</html>
```

An example JavaScript .js file.

```
const rows = [
    ["name1", "city1", "some other info"],
    ["name2", "city2", "more info"]
];

let csvContent = "data:text/csv;charset=utf-8," 
    + rows.map(e => e.join(",")).join("\n");
var encodedUri = encodeURI(csvContent);
var link = document.createElement("a");
link.setAttribute("href", encodedUri);
link.setAttribute("download", "my_data.csv");
document.body.appendChild(link); // Required for FF

link.click(); // This will download the data file named "my_data.csv".
```
