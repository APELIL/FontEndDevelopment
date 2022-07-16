# JavaScript - Fundamental

## ***3 ways to use JavaScript***

- Embedded in html (inline) - not recommend

```html
<body>
  <a href="javascript:alert('hello')">click</a>
</body>
```

- Internal

```html
<body>
  <script>
  alert("hello")
	</script>  
</body>  
```

- External

```html
 <body>
   <script scr = "js/hello.js"></script>
 </body>
```

```javascript
alert("Hi there!")
```

#### ***JavaScript syntax***

```javascript
// print 
console.log()
//dialog
alert（"hello"）
// write content to html page
document.write("hello")
// get data type - typeof
var num  = 'xx'
console.log(typeof num) //out: string
```

## ***JavaScript data types***

- number 

```javas
var num = 10;
```

- string

```javascript
var sex = 'male';
var sex = "female";
// sometimes you nned to use escape character like below
\'
\n
\t
\u4e2d //unicode
//Ascll
\x41
// ``long string
var x = `hello
there
how
are
you`
var name = 'yan'
var test01 = `Thank you,${name}`
```

- boolean

```javascript
var flag1 = true;
var flag2 = false;
```

- undefined and null (2 special types in JS)

  ```javascript
  var a = [1,2,3]
  console.log(a[3]) // return undefined
  ```

  

- object - complex type（a collection of various values）

  - Narrow object 

    ``` javascript
    var obj = {
      name = "mike";
      sex = "male";
      height = "180"
    }
    // fetch object values
    console.log(obj.name)
    console.log(obj.sex)
    // dynamic delete attributes
    delete obj.name //return true
    // dynamically add attributes
    obj.major = "IT"
    // determine if attribute in obj
    'name' in obj // return true 
    
    'toString' in obj // return true, cause parent properties
    // determine if an attributes own by the object -> hasOwnProperty()
    obj.hasOwnProperty('toString') //return false
    obj.hasOwnProperty('age') // return true
    
    ```

- Operator "="

  ```javascript
  == // compare value
  === // compare value and data type
  NaN===NaN // return false
  ```

- Operator "++"

  ```javascript
  var a = 10;
  print(a++) //10
  print(++a) //11 
  ```

- Strict check mode

  ```javascript
  'use strict';//use this syntax to define local variable, then use let
  let i = 10;
  ```

  

- Operator "!"

  ```javascript
  //non-boolean will convert to boolean value while using rebellion
  print(!undefined)//true
  print(!null) // true
  print(!0)//true
  print(!NaN)//true
  print(!'')//true 
  ```

- Switch 

  *break is required in swich syntax to prevent case penetration*

  *penetration example:*

  ```javascript
  <script>
    var situation = "Monday";
  switch(situation){
    case "Monday":
      console.log("Today is Monday");
      //break; <-- if there is no break, console will print out following value Today is Tuesday, Wrong situation... 
    case "Tuesday":
      console.log("Toady is Tuesday");
      break;
    default:
      console.log("Wrong situation");
      break;
  }
  </script>
  ```

  *Example to use switch and case penetration:* 

  ```javascript
  <script>
          // Example of using siwtch and case penetration to determine how many todays in a specific month 
          // 31 days: 1 3 5 7 8 10 12 
          // 30 days" 4 6 9 11
          // 28 or 29 --> 2
  
          var situation = 2;
          var year = 2021;
  
          switch(situation){
              case 1: case 3: case 5: case 7: case 8: case 10: case 12:
                  console.log("31 days");
                  break;
              case 4: case 6: case 9: case 11:
                  console.log("30 days");
                  break;
              case 2:
                  if(year%4 === 0 && year%100!= 0 ){
                      console.log("29 days");
  
                  }else{
                      console.log("28 days")
                  }
                  break;
          }
      </script>
  ```

- Ternary operator

  ```javascript
  // determine if the input value is odd or even
  var num = 10;
  x = num%2 === 0 ? "even" : "odd";
  // in python the ternary operator will be like:
  var = true_val if condition else false_val
  ```

- for loop 

  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <meta http-equiv="X-UA-Compatible" content="IE=edge">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Document</title>
  </head>
  <body>
      <script>
          var example = "multiplicationTable";
          switch(example){
  
          // example 1: print out odd numbers between 0 and 100
          case "printOddNumbers":
              for(var i = 0; i< 100; i++){
                  if(i%2!==0){
                  document.write("odd:"+i);
                  document.write("<br>"); // new line
                  // console.log(i);
                  }
              }
              break;
  
          // example 2: 99 multiplication table , it will be like: 
          /*
          1*1=1
          2*1=2 2*2=4
          3*1=3 3*2=6 3*3=9
          4*1=4 4*2=8 4*3=12 4*4=16
          5*1=5 5*2=10 5*3=15 5*4=20 5*5=25
          6*1=6 6*2=12 6*3=18 6*4=24 6*5=30 6*6=36
          7*1=7 7*2=14 7*3=21 7*4=28 7*5=35 7*6=42 7*7=49
          8*1=8 8*2=16 8*3=24 8*4=32 8*5=40 8*6=48 8*7=56 8*8=64
          9*1=9 9*2=18 9*3=27 9*4=36 9*5=45 9*6=54 9*7=63 9*8=72 9*9=81
          */
          case "multiplicationTable":
              for(var i = 1; i < 10; i++){
                  document.write("<br>");
                  for(var j = 1; j <= i; j++){
                      document.write(i + "*" + j + "=" + (i*j)+ " ");
                  }
              }
              break;
          default: document.write("Wrong case"); break;
      }
      </script>
  </body>
  </html>
  ```

  ```javascript
  //iterate over each element of the array
  var arr01 = [1,2,3]
  //method1
  arr01.forEach(function(e){
    console.log(e)
  } )
  //method2
  for(var num in arr01){
  	console.log(num) //index
    console.log(arr01[num]) 
  }
  //method3
  for(var num of arr01){
  	console.log(num)
  }
  ```

  

- Array

  ```javascript
  // typeof and isArray
  var list1 = [10,20,30]
  //typeof
  console.log(typeof list1)// out: object
  //isArray
  console.log(Array.isArray(list1)) //return true
  
  // push() and pop()
  list1.push()
  list1.pop()
  
  //concat
  var arr1 = [10,20];
  var arr2 = [20,30];
  console.log(arr1.concat(arr2))//out: [10,20,20,30]
  
  //join
  var arr3 = ["hello","world"];
  console.log(arr3.join(" "));//hello world
  
  //using arrary to store objects
  var arr4 = [
    {
      name:"mike",
      major:"IT"
    },
    {
      name:"Ape",
      major:"ITM"
    }
  ]
  
  //indexOf() --> return index of element, if the element is not exist, return -1
  console.log(arr2.indexOf(20))//return 0  
  
  // tail
  .push()
  .pop()
  //head
  .unshift()
  .shift()
  //sort
  .sort()
  //reverse
  .reverse()
  //concat: did not change the original arr, but return a new array
  var arr = ["c","d"]
  arr.concat([1,2])
  //join: print and concat arr
  var arr02 = ["c","d"]
  arr02.join('-')//return c-d
  // multidimensional array
  var arr = [[1,2],[3,4],[5,6]]
  //find
  ```

  - Map and Set ->ES6 new attributes

    - Map

    ```javascript
    var map = new Map([['tom',100],['jack',100]])
    //get
    var query01 = map.get('tom')
    //set
    map.set('yan',98)
    ```

    - Set

    ```javascript
     //deduplication
    var text = new Set([1,2,3,4,4]); //return [1,2,3,4]
    text.add(5);
    text.delete(1);
    console.log(text.has(3))
    ```

    

  ## Function

  ### Basic using of function 1 (*define and call*)

  - digital number can not start in function name
  - if there is no return value, console will print *undefined*

  Way 1:

  ```javascript
  function print(){
    console.log("Hi there!");
  }
  print();
  ```

  Way2:

  ```javascript
  var print1 = function(){
    console.log("Hi there!");
  }
  print1();
  ```

  - `arugument` - > represent the passed value 

    ```javascript
    function add(a,b){
      var temp = 0
      if(arguments.length==2){
        return a+b;
      }else if(arguments.length>=2){
        for (var i = 0; i < arguments.length; i++){          
          temp = temp + arguments[i]
          // console.log(arguments[i])     
        }
        return temp
    ```

  - `rest`

    ```javascript
    function add(a,b,...rest){
      var temp = 0
      if(arguments.length==2){
        temp = a+b;
        return a+b;
      }else if(arguments.length>=2){
        temp = a+b;
        for (var value of rest){
          temp = temp+value
        }
        return temp
    ```

    

  - Self-Executing Function (IIFE)

  ```javascript
  /*way1*/
  (function hello(){
    console.log("hello word!")
  }());
  /*way2*/
  (function hello(){
    console.log("hello word!")
  })();
  ```

  ### Basic using of function 2 (*apply*)

  ```javascript
  var LILRICH = {
    name:'Limin Yang',
    DOB:1996,
    //method 1 to get age
    ageM1: function(){
      let now = new Date().getFullYear();
      return now - this.DOB
    },
    // method 2
    ageM2:getAge
  }
  function getAge(){
    var now = new Date().getFullYear();
    return now - this.DOB
  }
  // method 3 => apply
  console.log(LILRICH.name+' age: '+getAge.apply(LILRICH,[]))
  ```

  

  ## Variable scope 

  - Global variable
  - Local variable
  - In JS, only functions have *scope* concept

  ```javascript
  var num1 = 10;//global
  function print(){
    console.log(num1);
    var num2 = 10;//local
  }
  console.log(num1) 
  ```

  #### **Global variable**=>var

  #### `window`

  ```javascript
  //global variable
  var x = 1;
  // global variables are bundle to window
  window.alert(x)
  ```

  #### Define unique global variable

  ```javascript
  var LILData = {};
  //define global variable
  LILData.name = 'Limin Yang';
  LILData.sum = function(a,b){
    return a+b;
  }
  ```

  #### Local variable =>let to solve local scope conflicts (ES6)

  ```javascript
  function print(){
    for(var i=0;i<10;i++){
      console.log(i)
    }
    console.log(i+1)//return 11
  }
  // to avoid such scope conflict, you can use 'let' to define variable
  ```

  #### Constant => const (ES6)

  ```javascript
  const PI = '3.14' //read only
  ```

  

- Math

```javascript
Math.PI
Math.E
Math.abs()
Math.ceil() /*rounded up*/
Math.floor() /*rounded down*/
Math.max()
Math.min()
Math.round()
Math.random()
```

## Inner Object 

### Standard object

```javascript
typeof 1
'number'
typeof '1'
'string'
typeof true
'boolean'
typeof NaN
'number'
typeof []
'object'
typeof {}
'object'
typeof Math.abs
'function'
typeof undefined
'undefined'
```



### Date

```javascript
/*current time*/
Date();
new Date();
var d1 = new Date(2000,2,1);
var d2 = new Date(2000,3,1);
d2-d1 /*return difference in millseconds*/
```

- Timestamp - Timestamp refers to the total number of seconds from January 01, 1970 00:00:00 GMT until now

- get

  ```javascript
  getTime() /*difference in seconds The number of milliseconds from January 1, 1970 00:00:00 to the present*/
  getDate() /*current day, start from 1*/
  getDay()/*return day of the week e.g., wednsday*/
  getFullYear()
  getMonth()/*start from 0, i.e. 0-11*/
  getHours()
  getMilliseconds()
  getMinutes()
  getSeconds()
  ```

  ```javascript
  var now = new Date();
  now.getTime(); //return 1656901734099
  console.log(new Date(1656901734099))// convert timestamp to Mon Jul 04 2022 12:28:54 GMT+1000 (Australian Eastern Standard Time)
  
  ```

### Json

####  Conversion between Json and Object

```javascript
var obj = {
  name:'Limin Yang',
  age:'25'
}
// to Json
var tojson = JSON.stringify(obj)
console.log(tojson)
//Json to Object
var toObj = JSON.parse('{"name":"Limin Yang", "age":"25"}')
console.log(toObj)
```

### OOP

#### Inherit (round chain)

- **proto**

```javascript
var car = {
  brand:"Mercedes",
  engineStart:function(){
    console.log(this.brand+' starting...')
  }
}

var Tesla = {
  brand:"Tesla"
}
//call parent class 
Tesla.__proto__ = car;

Tesla.engineStart()
```

```javascript
function Student(name){
  this.name = name;
}
//add a new method to Student
Student.prototype.getGrade = function(){
  alert("query grade")
}
var xiaoye = new Student()
xiaoye.getGrade();
```

- **class**

```javascript
class car{
  constructor(brand){
    this.brand = brand;
  }
  engineStart(){
    alert(this.brand+' engine start')
  }
}

class aircraft extends car{
  constructor(brand,mode){
    super(brand);
    this.mode = mode
  }
  flyMode(mode){
    if (this.mode == 1)
    {alert(this.brand+' ready to take off')}
    else{
      alert(this.brand+ ' ready to landing')
    }
  }
}
var Tesla = new car("Tesla")
Tesla.engineStart()
var Boeing = new aircraft("Boeing",1)
Boeing.flyMode()
new aircraft("AirBus",0).flyMode()
```

### HTML and JavaScript

#### 1. operate BOM object

> ***Window***
>
> ```javascript
> window.alert(1)
> undefined
> window.innerHeight
> 2771
> window.innerWidth
> 1280
> window.outerHeight
> 844
> window.outerWidth
> 390
> ```
>
> ***Screen***
>
> ```javascript
> screen.width
> 390
> screen.height
> 844
> ```
>
> ***location***=>represent current page info 
>
> ```javascript
> host: "au.search.yahoo.com"
> href: "https://au.search.yahoo.com/yhs/search?hspart=domaindev&hsimp=yhs-st_emea&p=career+center+usyd&type=dhm_D3LC3_ext_bcr__alt__ddc_srch_searchpulse_net"
> protocol: "https:"
> //refresh web page
> reload: ƒ reload()
> //set new web address
> location.assign('')
> ```
>
> ***cookie***
>
> ```javascript
> document.cookie
> ```
>
> ***history***
>
> ```javascript
> history.back()
> history.forward()
> ```

#### 2. operate DOM object

> ***get, update and delete node***
>
> ```javascript
> <div id="father">
>   <h1> tag 1</h1>
> <p id="p1">p1</p>
> <p class="p2">p2</p>
> </div>
> <script>
>   var father = document.getElementById('father')
>   var Children = father.children;
>   console.log(Children)
>   var h = document.getElementsByTagName('h1')
>   var p = document.getElementById('p1')
>   // modify text
>   p.innerText = '111'
> 	// modify CSS
>   p.style.color = 'red'
>   p.style.padding = '3px'
> </script>
> ```
>
> ***add node***
>
> ```html
>  // get node by id, class or tag name
> // using .append()
> <script>
>   id1.append(id2)
> </script>
> ```
>
> ***create a node***
>
> ```javascript
> // create a p tag
> var newNode = document.createElement('p');
> newNode.id = 'p3';
> p3.innerText = 'This is a new node'
> //then add
> 
> //you can create a <script type='text/javascript'></script> by using JS
> var myScript = document.createElement('script')
> myScript.setAttribute('type','text/javascript')
> ```
>
> 

#### 3. Operate form node

> ***form***
>
> ```html
> <input type=''></input>
> //type can be 
> text
> radio
> checkbox
> password
> ```
>
> ***get 'text' value***
>
> ```html
> <form action="">
>   <span>userName</span>
> <input id='username' type="text">
>   </form>
> <script>
>   var user = document.getElementById('username');
> console.log(user.value)
> </script>
> ```
>
> **for radio, you can use .checked to check if the value is selected**
>
> ***submit form and encrypt by md5***
>
> ```html
> <head>
> <script src="https://cdn.bootcss.com/blueimp-md5/2.10.0/js/md5.min.js"></script>
> </head>
> <body>
>   //onsumbit:"return validateForm()" to ensure successfully validate form
>   <form action="#" methos="post" onsubmit="return validateForm()">
>     <p>        
>     <span>userName</span>
> <input id='username' type="text" name="username">
>   </p>
> <p>
>   <span>passWord</span>
> <input type="password" id="input-pwd">
>   </p>
> <input type="hidden" id="md5-password" name="password">
>   <button type="submit">sumbit</button>
> </form>
> <script>
>     function validateForm(){
>     alert(1);
>     var uname = document.getElementById('username');
>     var pwd = document.getElementById('input-pwd');
>     var md5pwd = document.getElementById('md5-password');
>     md5pwd.value = md5(pwd.value);
>     if(pwd.value.length<3){
>       return false
>     }else{
>       return true
>     }
> 
>   }
> </script>
> ```
>
> 

### JQuery

> #### **Formula** => $('selector').action()
>
> - ***selector***
>
> **e.g.,**
>
> ```html
> <head>
>   ...
>   ...
>     <script src="../lib/jquery.js"></script>//introduce .js file
>     <title>Document</title>
> </head>
> <body>
>     <div>
>         <a href="#" id="aTag">click</a>
>     </div>
>     <script>
>         $('#aTag').click(function(){
>             alert('1')
>         })
>     </script>
> ```
>
> #### ***1. event***
>
> - **mouse**
>
> **e.g., mouseMove**
>
> ```html
> <style>
>     #mouseRegion{
>         width: 600px;
>         height: 600px;
>         background-color: aliceblue;
>     }
> </style>
> <body>
>     mouse position: <p id="mouseP"> </p>
>     <div id="mouseRegion"></div>
>     <script>
>         $(function(){
>             $('#mouseRegion').mousemove(function(e){
>                 $('#mouseP').text(' X: '+e.pageX+' Y: '+ e.pageY)
>             })
>         })
>     </script>
> ```
>
> #### 2. *DOM*
>
> ##### 2.1 text and html
>
> ```javascript
> $('selector').text()
> $('selector').html()
> ```
>
> ##### 2.2 css
>
> ```javascript
> $('selector').css({"color","red "})
> ```
>
> **`display:none`=>.show() & .hide()**
>
> ```javascript
> $('selector').show()
> $('selector').hide ()
> ```
>
> 

