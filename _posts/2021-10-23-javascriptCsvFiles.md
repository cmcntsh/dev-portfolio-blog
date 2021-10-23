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

- PaPa Parse seems to be an easy library to use. <a href = "https://www.papaparse.com/" target = "_blank">https://www.papaparse.com/</a>

An example CSV file.

```Csv
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

```Html
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

```JavaScript
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

- Spring Framework <a href = "https://spring.io/projects/spring-framework" target = "_blank">https://spring.io/projects/spring-framework</a>
- VMWare Virtual Platform
- Graylog <a href = "https://www.graylog.org/" target = "_blank">https://www.graylog.org/</a>
- ElasticSearch <a href = "https://www.elastic.co/" target = "_blank">https://www.elastic.co/</a>
- Tonaquint <a href = "https://tonaquint.com/" target = "_blank">https://tonaquint.com/</a>
