# JavaScript_Review_10_Questions_Participation
10 JavaScript Questions to cover with the class

<hr/>

### JavaScript Template Literals
MSJS practice question 16

You have the following HTML page:

```
<!DOCTYPE html>
<html>
<head>
         <title>Intro to JavaScript</title>
          	<meta charset="utf-8" />
</head>
<body>
         <script>
                  function formatMailLabel(name, address, city, state, zip) {
                           return `${name}::${address}::${city}::${state}::${zip}`;
                  }
         </script>

         <script>
                  function checkInput(field) {
                           if (!field)
                                    return false;

                           const MAX = 20;
                           return field.length <= 20;
                  }
         </script>

         <script>
                  function doAction(data) {
                           if (!data)
                                    return ' ';
                           var newData = ' ';
                           for (var i = data.length - 1; i >= 0; i--) {
                                    newData += data[i];
                           }
                           return newData;
                  }
         </script>

         <script>
                  var name = "JavaScript Tester";
                  var address = "123 Main Street";
                  var city = "Atlanta", state = "GA", zip = "12345";
                  var result = "Here is the info:\n"
                  if (checkInput(name)) {
                           result = doAction(name);
                           result += "\n" + formatMailLabel(name, address, city, state, zip);
                  }
                  console.log(result);
         </script>
</body>
</html>
```

* What will be displayed in the console when you preview the page?

Option 1:

Here is the info:

retseT tpircSavaJ

JavaScript Tester::123 Main Street::Atlanta::GA::12345

Option 2:

Here is the info:

Option 3:

retseT tpircSavaJ

JavaScript Tester::123 Main Street::Atlanta::GA::12345

Option 4:

An error message will be displayed because there are multiple script tags in the body.

<hr/>

### JavaScript Execution Context
MSJS practice question 17

The following HTML page has two script sections in the body and references a JavaScript file in the header:
```
<!DOCTYPE html>
<html>
<head>
         <title>Intro to JavaScript</title>
          	<meta charset="utf-8" />
         <script src="Scripts/Common5.js"></script>
</head>
<body>
         <div id="result" class="format-output"></div>
         <script>
                  function doAction(data, size) {
                           if (!data || size <= 0)
                                    return ' ';
                           var newData = data.substring(0, size);
                           var result = newData.split('|');
                           return result;
                  }
         </script>

         <script>
                  var info = "This|is|a|test that illustrates some key points about scripts"
                  var output = doAction(info, 31);
                  document.getElementById("result").innerHTML = output.join('#');
         </script>
</body>
</html>

Common5.js

function doAction(data, size) {
         if (!data || size <= 0)
                  return ' ';
         var newData = data.substring(0, size);
         var result = newData.split(' ');
         return result;
} 
```

* What will be displayed when you preview this page in the browser?


This|is|a|test#that#illustrates

This|is|a|test#that#illustrates#some#key#points#about#scripts

Nothing will be displayed on the screen and an error will display in the console

This#is#a#test that illustrates

<hr/>

### Try/Catch/Throw
MSJS practice question 19

The body of the HTML page contains the following script: 
```
    <script>
             var fileInfo = 'Could not process the file';
             var reportInfo = 'The daily report was not generated';
             var invoiceInfo = 'The invoices were not created';
             try {
                      logInfo(fileInfo, reportInfo, invoiceInfo);
             }
             catch (e) {
                      console.log('Could not call the function to log the info!');
             }
             finally {
                      console.log('Executed the finally block');
             }

             function logInfo(info) {
                      var date = new Date();
                      console.log(`INFO: ${info}; LOGGED ON ${date}`);
             }
    </script>
```
* What will be displayed in the console when this page is previewed in the browser?

INFO: Could not process the file; LOGGED ON Fri Nov 03 2018 20:19:53 GMT-0400 (Eastern Standard Time)
Could not call the function to log the info!
Executed the finally block

Could not call the function to log the info!
Executed the finally block

INFO: Could not process the file; LOGGED ON Fri Nov 03 2018 20:19:53 GMT-0400 (Eastern Standard Time)
Executed the finally block

Could not call the function to log the info!

<hr/>

### Input/Confirm (undefined/null)
MSJS practice question 26

The script in the following HTML page prompts the user for values and shows the results in an alert popup window:
```
<!DOCTYPE html>
<html>
<head>
         <title>Intro to JavaScript</title>
          	<meta charset="utf-8" />
</head>
<body>
         <script>
                  var input = prompt("Enter a window size between 1 and 50", 25);
                  var result = -1;
                  input = parseInt(input);
                  if (input == null)
                           result = 10;
                  else if (input == undefined)
                           result = 20;
                  else {
                           for (var i = 0; i < input; i++) {
                                    if (i % 2 == 0)
                                             result += i;
                                    else
                                             result += i + 1;
                           }
                 }
                  alert('The "result" is: ' + result);
         </script>
</body>
</html>
```
* What will be the alert if the user enters the value 8?


The "result" is: 39

The "result" is: 10

The "result" is: 31

The "result" is: 20

<hr/>

### Typeof/null/undefined/hoisting
MSJS practice question 30

The following code snippet declares some variables and calls a function to print their types:

        var x;
        var y = true;
        var z = 123;
        var t = 34.65;
        var u = 'JavaScript';
        var v = { first: 'JavaScript', last: 'Tester' };
        var w = new Date();
        var m = null;
        var n = undefined;

        function findType() {
            var result = `type of x: ${typeof (x)}\n
                type of y: ${typeof (y)}\n
                type of z: ${typeof (z)}\n
                type of t: ${typeof (t)}\n
                type of u: ${typeof (u)}\n
                type of v: ${typeof (v)}\n
                type of w: ${typeof (w)}\n
                type of m: ${typeof (m)}\n
                type of n: ${typeof (n)}\n`

            alert(result);
        }

        findType();

* What are the types of the variables?


type of x: undefined
type of y: boolean
type of z: number
type of t: number
type of u: string
type of v: object
type of w: date
type of m: null
type of n: undefined

type of x: undefined
type of y: boolean
type of z: number
type of t: float
type of u: string
type of v: object
type of w: object
type of m: null
type of n: undefined

type of x: undefined
type of y: boolean
type of z: number
type of t: number
type of u: string
type of v: object
type of w: object
type of m: object
type of n: undefined

type of x: null
type of y: boolean
type of z: number
type of t: float
type of u: string
type of v: object
type of w: object
type of m: undefined
type of n: undefined

<hr/>

### HTML5 Form Elements how fields are submitted) (required, email, password, reset, etc.)
MSJS practice question 120

A form on a page contains the following markup:

```
<form method="get">
         <div>
                  <label for="name">Name:</label>
                  <input type="text" id="name" name="fullName" required>
         </div>
         <div>
             <label for="mail">Email:</label>
                  <input type="email" id="mail" name="emailAdress">
         </div>
         <div>
                  <label for="phone">Phone:</label>
                  <input type="tel" id="phone" name="mainPhone">
         </div>
         <div>
                  <label for="temp">Temp preference:</label>
                  32
                  <input type="range" id="temp" name="tempPreference" 
                       value="65" min="32" max="96" step="2">
                  96
         </div>
         <div>
                  <input type="submit" value="Submit">
         </div>
</form>
```

* A user enters the following values in the form and clicks Submit:

Email: test@gmail.coml
Phone: 555-123-4587
Temp: 66

* What will be the value of the request URL?

http://localhost:35132/Account/FormTest?name=&mail=test%40gmail.com&phone=555-123-4587&temp=66

http://localhost:35132/Account/FormTest?fullName=&emailAdress=test%40gmail.com&mainPhone=555-123-4587&tempPreference=66

There will be no request URL

http://localhost:35132/Account/FormTest?fullName=&emailAdress=test%40gmail.com&mainPhone=555-123-4587&tempPreference=66

<hr/>

### Extra on Array Functions: sort, filter, forEach, etc.
MSJS practice question 40

You have the following HTML page:

```
<!DOCTYPE html>
<html>
<head>
         <title>Intro to JavaScript</title>
          	<meta charset="utf-8" />
</head>
<body>
         <script>
                  var employees = [
                           { name: 'James', salary: 10000 },
                           { name: 'Bryan', salary: 7000 },
                           { name: 'Tim', salary: 14000 },
                           { name: 'Jessica', salary: 21000 },
                           { name: 'Lisa', salary: 33000 },
                           { name: 'tom', salary: 8000 }
                  ];

                  employees.sort(function (a, b) {
                           var x = a.name.toLowerCase();
                           var y = b.name.toLowerCase();
                           if (x < y) return -1;
                           else if (x > y) return 1;
                           else return 0;
                  });

                  employees.forEach(function (item) {
                           console.log(`Name: ${item.name}, Salary: ${item.salary.toFixed(2)}`);
                  })
       
         </script>
</body>
</html>

```
* What shows in the console when the page is loaded in the browser?

Name: Bryan, Salary: 7000.00
Name: tom, Salary: 8000.00  
Name: James, Salary: 10000.00  
Name: Tim, Salary: 14000.00
Name: Jessica, Salary: 21000.00  
Name: Lisa, Salary: 33000.00


Name: James, Salary: 7000.00  
Name: Bryan, Salary: 10000.00  
Name: Tim, Salary: 21000.00  
Name: Jessica, Salary: 33000.00  
Name: Lisa, Salary: 14000.00  
Name: tom, Salary: 8000.00


Name: Bryan, Salary: 7000.00  
Name: James, Salary: 10000.00  
Name: Jessica, Salary: 21000.00  
Name: Lisa, Salary: 33000.00  
Name: Tim, Salary: 14000.00  
Name: tom, Salary: 8000.00


Name: Bryan, Salary: 7000.00  
Name: James, Salary: 10000.00  
Name: Jessica, Salary: 21000.00  
Name: Lisa, Salary: 33000.00 
Name: tom, Salary: 8000.00 
Name: Tim, Salary: 14000.00


<hr/>

### DOM and BOM
MSJS practice question 28

The following script displays information about the screen:

```
    <script>
             var result =
                  `screen.width = ${screen.width}
                      screen.height = ${screen.height}
                      screen.availWidth = ${screen.availWidth}
                      screen.availHeight = ${screen.availHeight}
                      screen.colorDepth = ${screen.colorDepth}
                      screen.pixelDepth = ${screen.pixelDepth}`;
             alert(result);
    </script>
```

* For each of the following statements about these properties, answer True or False for the following questions:

screen.availHeight > screen.height

screen.colorDepth > screen.pixelDepth

screen.availHeight < screen.height

screen.colorDepth < screen.pixelDepth


<hr/>

### Dates
MSJS practice question 28

A date is declared as follows:

```
var d2 = new Date('March 11, 2005 02:30:00');
```

Answer the following questions? 

The getDate() function will return: ___

The getUTCDate() function will return: ___

The getMonth() function will return: ___


<hr/>

### Let, Const
MSJS practice question 54

```
You preview the following page in the browser:

<!DOCTYPE html>
<html>
<head>
    <title>Intro to JavaScript</title>
	<meta charset="utf-8" />
    <style>
        .format-output {
            width: 300px;
            height: 100px;
            border: 1px solid blue;
            font:bold 20px "courier new";
            text-align:center;
        }
    </style>
</head>
<body>
    <div id="result" class="format-output"></div>
    <script>
        let names = ['Apple', 'Orange', 'Banana', 'Kiwi'];

        {
            let names = ['Blue', 'Green', 'Orange', 'Yellow', 'Red'];

            function findIndex(element) {
                if (!element) return;
                for (var i = 0; i < names.length; i++) {
                    if (names[i].toLowerCase() === element.toLowerCase())
                        return i;
                }
            }
        }

        function getBefore(i) {
            if (i <= 0) return;
            return names[i - 1];
        }
        
        names.sort();
        var index = findIndex('orange');

        document.getElementById("result").innerHTML = getBefore(index);
    </script>
</body>
</html>
```

* Which word will be displayed on the screen?

Yellow

Green

Banana

Kiwi


