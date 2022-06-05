## HTML and CSS cycle sheet

1.Pick 5 corporations and hunt down their current stock prices.

i) Place them in a neatly arranged table with their name, symbol, last
price, 52wk high, 52wk low, and PE ratio. 

ii) The end result should look like the following. Notice that the first
column is aligned left and the rest are centered. 

iii) Now alter the last table using shaded rows and no border

**code:**

```
<html>
<head>
<title>Naveen</title>
</head>
<style>
</style>
<body>
<table border=3px; cellpadding="5" >
<tr><th colspan= "6"><i>My tech stock picks</i></th></tr>
<tbody>
<tr>
<th>NAME</th>
<th align="center">SYMBOL</th>
<th align="center">CURRENT</th>
<th align="center">52WK HI</th>
<th align="center">52WK LO</th>
<th align="center">P/E RATIO</th>
</tr>
<tr>
<td align ="left">Microsoft</td>
<td align ="center">MSFT</td>
<td align ="center">86-3/8</td>
<td align ="center">119-15/16</td>
<td align ="center">75-1/2</td>
<td align ="center">56.09</td>
</tr>
<tr>
<td align ="left">Cisco Systems</td>
<td align ="center">CSCO</td>
<td align ="center">72-1/8</td>
<td align ="center">82</td>
<td align ="center">24-13/16</td>
<td align ="center">400.69</td>
</tr>
<tr>
<td align ="left">America Online</td>
<td align ="center">AOL</td>
<td align ="center">63</td>
<td align ="center">95-13/16</td>
<td align ="center">38-15/32</td>
<td align ="center">350.00</td>
</tr>
<tr>
<td align ="left">Qwest Communication</td>
<td align ="center">Q</td>
<td align ="center">44-7/16</td>
<td align ="center">66</td>
<td align ="center">25-3/4</td>
<td align ="center">74.06</td>
</tr>
<tr>
<td align ="left">Dell Computers</td>
<td align ="center">DELL</td>
<td align ="center">53-59/64</td>
<td align ="center">59-11/16</td>
<td align ="center">31-3/8</td>
<td align ="center">86.97</td>
</tr>
</tbody>
</table>
</body>
</html>
``` 
**OUTPUT:**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1643430208975/KB964EhcF.png)

iii) Now alter the last table using shaded rows and no border.

**Code:**


```
<html>
<head>
<title>Naveen</title>
</head>
<body>
<table cellspacing="0" cellpadding="2" border="0">
<tr bgcolor="#669999">
<th align="center" colspan="6">
<i>My tech stock picks</i></th>
</tr>
<tr><td><font size="2"><b>NAME</b></font></td>
<td align="center"><font size="2"><b>SYMBOL</b></font></td>
<td align="center"><font size="2"><b>CURRENT</b></font></td>
<td align="center"><font size="2"><b>52WK HI</b></font></td>
<td align="center"><font size="2"><b>52WK LO</b></font></td>
<td align="center"><font size="2"><b>P/E RATIO</b></font></td></tr>
<tr bgcolor="#669999"><td>Microsoft</td>
<td align="center">MSFT</td>
<td align="center">86-3/8</td>
<td align="center">119-15/16</td>
<td align="center">75-1/2</td>
<td align="center">56.09</td></tr>
<tr><td>Cisco Systems</td>
<td align="center">CSCO</td>
<td align="center">72-1/8</td>
<td align="center">82</td>
<td align="center">24-13/16</td>
<td align="center">400.69</td></tr>
<tr bgcolor="#669999">
<td>America Online</td>
<td align="center">AOL</td>
<td align="center">63</td>
<td align="center">95-13/16</td>
<td align="center">38-15/32</td>
<td align="center">350.00</td></tr>
<tr><td>Qwest Communications</td>
<td align="center">Q</td>
<td align="center">44-7/16</td>
<td align="center">66</td>
<td align="center">25-3/4</td>
<td align="center">74.06</td></tr>
<tr bgcolor="#669999">
<td>Dell Computers</td>
<td align="center">DELL</td>
<td align="center">53-59/64</td>
<td align="center">59-11/16</td>
<td align="center">31-3/8</td>
<td align="center">86.97</td>
</tr>
</table>
</body>
</html>
``` 
**OUTPUT:**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1643459977669/liml-mdyM.png)


2)Create a web page containing three divisions.

i) The first division displays a digital clock on the rightmost end. 

ii) The width of the first division is 100%.The second division and
third division lay side by side. 

iii) The second division has an image slider and third division has a
color picker and two list box having font-family and size and a
button. When a button is clicked the background color, font and font
size should change for a whole page. Use JavaScript to implement the
above

**Code:**

```
<html>
<head>
<title>Naveen</title>
<script>
function displaytime() {
var today = new Date();
var time = today.getHours() + ":" + today.getMinutes() + ":" +
today.getSeconds();
document.getElementById("id1").value=today;}
var slideIndex=0;
imageSlider();
function imageSlider() {
var i;
var slide=document.getElementsByClassName("fade");
for(i=0;i<slide.length;i++)
{slide[i].style.display="none";}
slideIndex++;
if(slideIndex>slide.length)
{
slideIndex=1;
}
slide[slideIndex-1].style.display = "block";
setTimeout(imageSlider, 2000);
}
function colorChange() {
var color= document.getElementById("pick").value;
document.body.style.backgroundColor=color;
var size=document.getElementById("size").value;
document.getElementById("text").style.fontSize=size;
var y=document.getElementById("fontselect").value;
document.getElementById("text").style.fontFamily=y;
}
</script>
<style>
body {font-family: Verdana,sans-serif;}
.fade {display:none;
height: 360px;
width: 610px;
}
#digitalclock
{
background-color: rgba(44, 193, 204, 0.5);
float: right;
position: absolute;
top:100px;
left: 900px;
padding: 10px;
border-radius: 10px;
}
#color
{
position: absolute;
top: 208px;
left: 658px;
height: 400px;
width: 700px;
padding: 100px;
}* {box-sizing:border-box}
</style>
</head>
<body onload=imageSlider();displaytime();>
<div id="digitalclock">
<input id="id1"type="text">
</div>
<div class="image" >
<div class="fade">
<img name="" src="https://i.ibb.co/vxRf1zc/Eagle-programming.jpg">
<style="height: 350px;width: 600px;">
</div>
<div class="fade">
<img name="imgm" src="https://i.ibb.co/vxRf1zc/Eagle-programming.jpg">
<style="height: 350px;width: 600px;">
</div>
</div>
<div id="color" style="background-color:papayawhip; ">
<div id="newtext">
<p id="text">
I am Naveenkumar J. Follow @eagle_programming on instagram for more coding contents.</p>
</div>
<table id="q1">
<form name="myform" method="get">
<tr>
<td>
Pick Color:
</td>
<td>
<input type="color" id="pick" title="select background color"/>
</td>
</tr>
<tr>
<td>Font Style:</td>
<td>
<select name="list" id="fontselect">
<option value="none" selected disabled>Choose Font</options>
<option value="Times new romen">Times new romen</option>
<option value="Arial">Arial</option>
<option value="loma">Loma</option>
<option value="Century">Century</option>
</select>
</td>
</tr>
<tr>
<td>Size:</td>
<td> <input type="number" id="size" min="10" max="20"/></td>
</tr>
<tr>
<td colspan="2">
<input type="button"onclick="colorChange()" value="submit"/>
</table>
</div>
</body>
</html>
``` 
**OUTPUT:**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1643460378577/MalDe3Mzv.png)





3.Design the following HTML form using HTML and javascript.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1643430399654/BEyHqO635.png)

i)Utilize CSS shorthand background properties to provide color and
image. 

ii)Utilize fieldset tags. 

iii)Check no fields are null.

**Code:**

```
<html>
<style>
.fun{
background-color:lightseagreen;
}
.boom{
background-image: url("https://i.ibb.co/kcMx885/image.png");
background-size: 90%,90%;
background-repeat: no-repeat;
background-position: center;
}
</style>
<head>
<title>Naveen</title>
<script>
function validate()
{
if( document.myForm.name.value == "" )
{
alert( "Please provide your name!" );
return false;
}
if( document.myForm.rad1.value == "" )
{
alert( "Pizza Topping should be selected" );
return false;
}
if( document.myForm.sauce.value == "0" )
{
alert( "Pizza Sauce should be selected" );
return false;
}
if(document.myForm.extra1.checked==false&&
document.myForm.extra2
.checked==false )
{
alert("Please select atleast one of the optional extras");
return false;
}
if( document.myForm.instructions.value == "" )
{
alert( "Delivery Instructions should not be empty" );
return false;
}
return( true );
}
</script>
</head>
<body>
<form name="myForm">
<fieldset class="boom">
<legend>Dominos</legend>
<table class="fun" border=1px; align="center">
<tr><th colspan= "2"><i>Pizza Shop 2.0</i></th></tr>
<tr>
<td>Name</td>
<td align=center;>
<form><input type="text" name="name" id="name"></form>
</td>
</tr>
<tr>
<td>Pizza Topping</td>
<td><ul>
<input type="radio" name="rad1" value="1" id="rad1"/>Supreme<br>
<input type="radio" name="rad1" value="2" id="rad1"/>Vegetarian<br>
<input type="radio" name="rad1" value="2" id="rad1"/>Hawaiian</td>
</tr>
<tr>
<td>Pizza Sauce</td>
<td>
<select name="sauce">
<option value="1" selected="selected">Tomato</option>
<option value="3">chilly</option>
<option value="4">hot</option>
<option value="5">soy</option>
</td>
</tr>
<tr>
<td>Optional extras</td>
<td><input type="checkbox" name="extra1">Extra cheese
<input type="checkbox" name="extra2">Gluten Free base
</td>
</tr>
<tr>
<td colspan="2">Delivery instructions <br> <textarea
name="instructions" maxlength="1000"
size="1000"></textarea></td><br>
</tr>
<tr><td colspan="2"><input type="submit" value="Send my or
der" onclick="validate()"></td></tr>
</table>
</fieldset>
</form>
</body>
</html>
``` 

**OUTPUT:**



![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1643431245013/eHt0-nQq8.png)

4.Design a student registration form which takes student name, register
number, DOB, program, email id, temporary address, permanent address, phone number.

i)Validate the following using JavaScript:

a.Mobile number should be exactly 10 digits.

b.Register number should have alphabets and numbers only.

c. Name should not exceed 30 characters and can be only alphabets.

ii)Email validation:

iii)Provide a checkbox saying “Permanent address is same as temporary
address”. If checked, the value of permanent address should be added
automatically from temp address. And should be in disabled mode


**Code:**

```
<html>
<head>
<title>Naveen</title>
<script>
function validate()
{
if(document.myform.sname.value==0)
{
alert("Student Name must be filled");
return false;
}
if(!/^[a-zA-Z]+$/.test(document.myform.sname.value))
{
alert("Student Name should contain only alphabets");
return false;
}
if(document.myform.sname.value.length>30)
{
alert("Student Name should not exceed 30 characters");
return false;
}
if(document.myform.regno.value==0)
{
alert("Register number must be filled");
return false;
}
if(!/^[0-9a-zA-Z]+$/.test(document.myform.regno.value))
{
alert("Register number should contain only alphabets and numbers");
return false;
}
if(document.myform.emailid.value=="")
{
alert("Email must be filled");
return false;
}
if(!/^[a-zA-Z0-9.!#$%&'*+/=?^_`{|}~-]+@[a-zA-Z0-9-]+(?:\.[azA-Z0-9-]
+)*$/.test(document.myform.emailid.value))
{
alert("Email must be filled in required format");
return false;
}
if(document.myform.tadd.value==0)
{
alert("Temporary Address Must be filled");
return false;
}
if(document.myform.pno.value==0)
{
alert("Mobile number must be filled");
return false;
}
if(!/^[0-9]+$/.test(document.myform.pno.value)){
alert("Mobile number should contain numbers only");
return false;
}
if(document.myform.pno.value.length<10 || document.myform.pno. value.length>10)
{
alert("Mobile number should contain exactly 10 numbers");
return false;
}
}
function disable()
{
if(document.myform.add.checked==true)
{
document.myform.padd.value=document.myform.tadd.value;
document.myform.padd.disabled=true;
}
else
{
document.myform.padd.disabled=false;
document.myform.padd.value="";
}
}
</script>
<style>
.boom{
height: 90%;
width: 40%;
border: 3px solid black;
margin-top: 2.5%;
}
</style>
</head>
<body>
<div class="boom">
<table align="center" cellspacing="5">
<form name="myform" method="POST">
<tr align="center">
<td colspan="2"><h2 style="color:red;"><b><u>Student Registration
Form</u></b></h2></td>
</tr>
<tr>
<td>Student name</td>
<td><input type="text" id="t" name="sname"></td>
</tr><br>
<tr>
<td>Register Number</td>
<td><input type="text" id="t" name="regno"></td>
</tr><br>
<tr>
<td>DOB</td>
<td><input type="date" id="t2" name="dob"></td>
</tr><br>
<tr>
<td>Program</td>
<td><input type="text" id="t" name="prgm"></td>
</tr><br>
<tr>
<td>Email id</td>
<td><input type="text" id="t" name="emailid"></td>
</tr><br>
<tr>
<td>Temporary Address:</td><td><textarea id="tempadd"
type="text" name="tadd"></textarea></td>
</tr><br>
<tr>
<td>Permanent Address:</td><td><textarea id="permadd" type="text" name="padd"></textarea></td>
<td><input id="check" type="checkbox" name="add" onclick="disable();">Same as temporary address</td>
</tr><br>
<tr>
<td>Phone number</td>
<td><input type="text" id="t" name="pno"></td>
</tr><br>
<tr>
<td colspan="2" align="center"><br><br>
<button type="submit" onclick="validate()">Submit</button></td>
</tr>
</form>
</table>
</div>
</body>
</html>
``` 
**OUTPUT:**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1643430832037/4iui-autR.png)

### DOM Events:
5)

i)BSNL has designed a grievance registration form in HTML with
name of customer, address,telecom circle, email and grievance nature in a
list box containing huge bills for limited mobile usage, roaming charges
and frequent service disruption and a submit button.

ii) Write a Javascript DOM event to be enabled when the user submits
the form and display the complaint details in a tabular format.

iii) If no grievance is selected, then invoke another DOM event to display
“ No grievances”.

**Code:**

```
<html>
 <head>
 <title>Naveen</title>
 <script type="text/javascript">
 function ex5validation()
 {
 x=document.myform.cusname.value;
 a=document.myform.address.value;
 tc=document.myform.tcircles;
 y=document.myform.email.value;
 gn=document.myform.list;
 if(test(x))
 {
 if(test1(a))
 {
 if(test2(tc))
 {
 if(test3(y))
 {
 if(test4(gn))
 {
 return true;
 }
 }
 }
 }
 }
 return false;
 }
 function test(x)
 {
 var npat=/^[A-Za-z]+$/;
 if (x.match(npat)) {
 document.getElementById("outtab").rows[1].cells[1].innerHTML=x;
 return true;
 }
 alert("Name must be filled characters");
 return false;
 }
 function test1(a)
 {
 var apat=/\w/;
 if(a.match(apat)) {
 document.getElementById("outtab").rows[2].cells[1].innerHTML=a;
 return true;
 }
 alert("Address must be filled");
 return false;
 }
 function test2(tc)
 {
 if(tc.value)
 {

 document.getElementById("outtab").rows[3].cells[1].innerHTML=tc.value;
 return true;
 }
 alert("Select Telecom Circle");
 return false;
 }
 function test3(y)
 {
 var epat=/^[a-zA-Z0-9]+@[a-zA-Z]+.[a-zA-Z]+$/;
 if(y.match(epat)) {
 document.getElementById("outtab").rows[4].cells[1].innerHTML=y;
 return true;
 }
 alert("Enter email id");
 return false;
 }
 function test4(gn)
 {
 if(gn.value)
 {

 document.getElementById("outtab").rows[5].cells[1].innerHTML=gn.value;
 return true;
 }

 document.getElementById("outtab").rows[5].cells[1].innerHTML="<h2>No grievances</h2>";
 return true;
 }

 </script>
 </head>

<style>
 #t
{
 width:200px;
 height:25px;
}
 #t1
{
 width:200px;
 height:35px;

}
 #t2
{
 width:120px;
 height:25px;

}
 input[type="text"]

{
 border-radius:5px;

}
 select

{
 border-radius:5px;

}
 #t3
{
 width:120px;
 height:25px;

}

 #table1
{
 border-radius:6px;
 color:rgb(22, 16, 16);
 background-color:#19f1f8;
 position:absolute;
 top:32%;
 left:5%;
 opacity:0.8;

}
 #outtab
{
 border-radius:6px;
 color:rgb(0,0,0);
 background-color:#de6de9;
 position:absolute;
 top:31%;
 left:45%;
 opacity:0.8;
 height: 41%;
}
 </style>
 <body>
 <form name="myform" method="post" onsubmit="return ex5validation()">
 <table id="table1" cellspacing="10">
 <tr> <td colspan="2"><h2><b>Registration forms</b></h2></td> </tr>
 <tr><td><b>Name of the Customer</b></td><td><input type="text" id="t" name="cusname"></td></tr></br>
 <tr><td><b>Address</b></td><td><input type="text" id="t"name="address"></td></tr></br>
 <tr><td><b>Telecom Circle</b></td><td><select id="t2" name="tcircles">
 <option value="" selected>-Select-</option>
 <option value="Metro">Metro</option>
 <option value="A">A</option>
 <option value="B">B</option>
 <option value="C">C</option>
 </select></td></tr></br>
 <tr><td><b>Email</b></td><td><input type="text" id="t"name="email"></td></tr></br>
 <tr><td><b>Grievance Nature</b></td><td><select id="t1" name="list" size="1">
 <option value="" selected>-Select-</option>
 <option value="Bills for Limited Mobile Usage">Bills for Limited Mobile Usage</option>
 <option value="Roaming Charges">Roaming Charges</option>
 <option value="Frequent Service Disruption">Frequent Service Disruption</option></select></td></tr></br></br>
 <tr><td colspan="2" align="center"><input type="submit" value="submit"></td></tr></br>
 </table>
 </form>
 <table id="outtab" border="1" bordercolor="white" onsubmit="returndisplay();" >
 <tr><td colspan="2" align="center"><h2>FORM OUTPUT</h2></td></tr>
 <tr><td>Name of the customer</td><td></td></tr>
 <tr><td>Address</td><td></td></tr>
 <tr><td>Telecom Circle</td><td></td></tr><tr><td>Email</td><td></td></tr>
 <tr><td>Grievance Nature</td><td></td></tr>
 <tr><td colspan="2" align="center"><button type="submit" onclick="ex5validation()">Display</button></td></tr>
 </table>
 </body>
</html>
``` 
**OUTPUT:**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1643464825578/ECEkx8p39.png)

6.Develop an online Railway Reservation application.

i) It has top frame with the name “Online Railway Reservation System”
in the middle, there is alogo/image in the left corner using suitable CSS
styles and the left frame with the links for Ticket booking and availability
checking; for each link the target should be the right frame.

ii) Create a Ticket Booking form which should have From and To in a
text box, Train Names in a drop down box, Coach Number in a list box, Date in a date field, Timing in a text box,Passengers Male and female in a
dropdown menu showing the count number and Submit and Reset button.

iii) Assume availability of tickets already declared in the script. Create a
DOM event to display the ticket confirmation details on any HTML
element when ticket is available otherwise display “tickets not available” by invoking any other DOM event.


**Code:**
**Main.html:**

```
<html>
<head>
<title>Naveen</title>
</head>
<frameset rows="20%,*">
<frame src="Head.html"></frame>
<frameset cols="20%,*">
<frame src="Leftframe.html" name="left">
<frame src="Rightframe.html" name="right">
</frameset>
</frameset>
</html>
``` 
**Head.html:**

```
<html>
<head>
<title>Naveen</title>
</head>
<style>
body{
width: 97%;
height: 87%;
}
.heading{
width: 20%;
height: 97%;
float: left;
text-align: center;
}
h1{
text-align: center;
font-size: 50px;
}
.im{
width: 65%;
height: 87%;
float: left;
}
img{
height: 80%;
width: 40%;
margin-left: 10%;
}
</style>
<body>
<div class="heading">
<img src="https://upload.wikimedia.org/wikipedia/en/thumb/4/45/IRC
TC_Logo.svg/1200px-IRCTC_Logo.svg.png">
</div>
<div class="im">
<h1>Online reservation system</h1>
</div>
</body>
</html>
``` 
**Leftframe.html (links frame):**

```
<html>
<head>
<style>
body{
background-color: rgb(148, 217, 230);
}
a{
background-color:#E8E8E8;
font-family:calibri;
font-size:24;
border:5px solid white;
text-decoration: none;
opacity:0.8;
}
</style>
</head>
<body><br/><br/><br/>
<a href="book.html" target="right" >Book Tickets</a></br><br/>
<a href="check.html" target="right">Check Availability of Seats</a>
</body>
</html>
``` 
**Rightframe.html (display of left frame links):**

```
<html>
<head>
<style>
body{
background-image:url("https://i.ibb.co/yV8gWg5/image.png");
background-position:850px 450px;
}
</style>
</head>
<body>
</body>
</html>
``` 
**Book.html:**

```
<html>
<head>
<script type="text/javascript">
function bookvalidation()
{
if( document.myform.sstation.value == "")
{
alert("Source Station should be Entered");
return false;
}
if(!/^[a-zA-Z ]+$/g.test(document.myform.sstation.value))
{alert("Source Station should not contain Invalid Characters");
return false;
}
if( document.myform.dstation.value == "")
{
alert("Destination Station should be Entered");
return false;
}
if(!/^[a-zA-Z ]+$/g.test(document.myform.dstation.value))
{
alert("Destination Station should not contain Invalid Characters");
return false;
}
if( document.myform.tnames.value == "0")
{
alert("Please select the Train Name");
return false;
}
if( document.myform.cnum.value == "")
{
alert("Please select the Coach Number");
return false;
}
if(document.myform.tdate.value == "")
{
alert("Required date should be entered");
return false;
}
if( document.myform.ttime.value == "")
{
alert("Travel Time should be Entered");
return false;
}
if(!/^[0-9:]+$/g.test(document.myform.ttime.value))
{
alert("Time should not contain Invalid Characters");
return false;
}
if( document.myform.mpass.value == "-1")
{
alert("Please select the number of Male Passengers");return false;
}
if( document.myform.fpass.value == "-1")
{
alert("Please select the number of Female Passengers");
return false;
}
return true;
}
function both()
{
bookvalidation();
show();
}
</script>
<style>
a{
font-size:22;
background-color:#E8E8E8;
font-family:calibri;
border:3px solid white;
opacity:0.8;
}
body{
color:white;
background-color: antiquewhite;
background-position:no-repeat;font-family:calibri;
font-size:1;
}
#tab1{
background-color:#329292;
border-radius:5px;
padding:4px;
opacity:0.8;
}
td{
font-size:19;
}
caption{
background-color: #329292;
color:white;
font-size:20;
border-radius:5px;
font-family:arial;
font-weight:bolder;
opacity:0.9;
}
</style>
</head>
<body>
<table id="tab1" cellspacing="10">
<caption><b>Online Ticket Booking Portal<b></caption>
<form name="myform" method="post">
<tr><td><b>From</b></td><td><input type="text" name="sstation"></td></tr><br/>
<tr><td><b>To</b></td><td><input type="text" name="dstation"></td></tr><br/>
<tr><td><b>Train Names</b></td><td><select
name="tnames">
<option value="0" selected>-Select-</option>
<option value="Venkatadri Express">Venkatadri
Express</option><option value="S
eshadri Express">Seshadri Express</option>
<option value="Rajadhani Express">Rajadhani
Express</option>
<option value="Himasagar Express">Himasagar
Express</option>
<option value="Vivek Express">Vivek
Express</option></select></td></tr><br/>
<tr><td><b>Coach Number</b></td><td><select
name="cnum" size="3">
<option value="A">A</option>
<option value="B">B</option>
<option value="C">C</option>
<option value="D">D</option>
<option value="E">E</option>
<option value="F">F</option>
<option value="AB">AB</option>
<option value="HA">HA</option>
<option value="S">S</option></select>
</td></tr><br/>
<tr><td><b>Travel Date</b></td><td><input type="date" name="tdate"></td></tr><br/>
<tr><td><b>Travel Time</b></td><td><input type="text" name="ttime"></td></tr><br/>
<tr><td><b>Male Passengers</b></td><td><select
name="mpass">
<option value="-1" selected>-Select-</option>
<option value="0">0</option>
<option value="1">1</option>
<option value="2">2</option>
<option value="3">3</option>
<option value="4">4</option>
<option value="5">5</option>
<option value="6">6</option>
<option value="7">7</option>
<option value="8">8</option>
<option value="9">9</option>
<option value="10">10</option>
<option value="11">11</option>
<option value="12">12</option>
<option value="13">13</option>
<option value="14">14</option>
<option value="15">15</option>
</select></td></tr><br/>
<tr><td><b>Female Passengers</b></td><td><select
name="fpass">
<option value="-1" selected>-Select-</option>
<option value="0">0</option>
<option value="1">1</option>
<option value="2">2</option><option
value="3">3</option>
<option value="4">4</option>
<option value="5">5</option>
<option value="6">6</option>
<option value="7">7</option>
<option value="8">8</option>
<option value="9">9</option>
<option value="10">10</option>
<option value="11">11</option>
<option value="12">12</option>
<option value="13">13</option>
<option value="14">14</option>
<option value="15">15</option>
</select></td></tr><br/>
<tr><td><input type="reset" name="reset" value="Reset"></td>
<td><button type="submit" onclick="bookvalidation()">Submit</button></td></tr>
<br/>
</form>
</table>
</body>
</html>
``` 
**Check.html:**

```
<html>
<head>
<script>
function checkvalidation()
{
if( document.myform.trainno.value == "")
{alert("Train Number should be Entered");
return false;
}
if(!/^[a-zA-Z0-9 ]+$/g.test(document.myform.trainno.value))
{
alert("Train Number should not contain Invalid Characters");
return false;
}
if(document.myform.traveldate.value == "")
{
alert("Required date should be entered");
return false;
}
if( document.myform.sstation.value == "")
{
alert("Source Station should be Entered");
return false;
}
if(!/^[a-zA-Z ]+$/g.test(document.myform.sstation.value))
{
alert("Source Station should not contain Invalid Characters");
return false;
}
if( document.myform.dstation.value == "")
{
alert("Destination Station should be Entered");
return false;
}
if(!/^[a-zA-Z ]+$/g.test(document.myform.dstation.value))
{
alert("Destination Station should not contain Invalid Characters");
return false;
}
if( document.myform.class.value == "0")
{
alert("Please select the Class");
return false;
}
if( document.myform.quota.value == "0")
{
alert("Please select the Quota");return false;
}
return true;
}
</script>
<style>
body{
color:white;
background-color: antiquewhite;
background-position:850px 450px;
font-family:calibri;
font-size:10;
}
table{
background-color:#329292;
border-radius:5px;
padding:4px;
opacity:0.8;}
td{
font-size:19;
}
caption{
color:rgb(43, 43, 40);
font-size:20;
font-family:arial;
font-weight:bolder;
}
</style>
</head>
<body>
<table align="center" cellspacing="10">
<caption>Seats Availability Enquiry</caption>
<form name="myform" method="post">
<tr><td><b>Enter Train Number</b></td><td><input type="text" name="trainno"></td></tr><br/>
<tr><td><b>Enter Travel Date</b></td><td><input type="date" name="traveldate"</td></tr><br/>
<tr><td><b>Enter Source Station</b></td><td><input type="text" name="sstation"></td></tr><br/>
<tr><td><b>Enter Destination Station</b></td><td><input type="text" name="dstation"></td></tr><br/>
<tr><td><b>Enter Class</b></td><td><select name="class"><option
value="0" sele
cted>-Select</option>
<option value="1">Sleeper Class</option>
<option value="2">Executive Class</option>
<option value="3">First Class</option>
<option value="4">Second Seating</option>
<option value="5">First AC</option>
<option value="6">Second AC</option>
<option value="7">Third AC</option></select>
</td></tr><br/>
<tr><td><b>Enter Quota</b></td><td><select name="quota">
<option value="0" selected>-Select</option>
<option value="1">General Quota</option>
<option value="2">Tatkal Quota</option>
<option value="3">Ladies Quota</option>
<option value="4">Yuva Quota</option>
<option value="5">Defense Quota</option>
<option value="6">Handicapped Quota</option></select>
</td></tr><br/>
<tr><td colspan="2" align="center"><button type="submit" onclick="checkvalidation()">Submit</button></td></tr>
</form>
</table>
</body>
</html>
``` 

**OUTPUT:**


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1643461138529/0f5NfQOAy.png)






