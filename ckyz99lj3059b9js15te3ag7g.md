## Java Lab assignment 2

1.	Create a class Rectangle by having member variables and methods such as
         i. Variables length and width
         ii. Implement Set() method with two parameters to initialize instance variables of class.
        iii. Implement calculateArea( ) method to calculate the Area of rectangle.
        iv. In the main method create 3 rectangle objects such as rect1, rect2, and rect2.
        v.	Assign the values of rect1 into rect3.
       vi.	Call the method calculateArea( ) in the main() method and display the information.

**Code:
Rectangle.java**
```
public class Rectangle
{
int length,width;
void Set(int l, int w)
{
length=l;
width=w;
}
double calculateArea()
{
double area = length*width;
return area;
}
public static void main(String[] args)
{
Rectangle rect1= new Rectangle();
Rectangle rect2= new Rectangle();
Rectangle rect3= new Rectangle();
rect1.Set(2,4);
rect2.Set(3,5);
rect3=rect1;
double area1=rect1.calculateArea();
double area2=rect2.calculateArea();
double area3=rect3.calculateArea();
System.out.println("The area of rectangle one is: "+area1);
System.out.println("The area of rectangle two is: "+area2);
System.out.println("The area of rectangle three is: "+area3);
}
}

``` 

**OUTPUT:**


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1643424868888/k-Co8M2M8.png)


2.Inherit the class rectangle from question1 into class Cube.  The class cube should have the following.
i.	Declare a variable height in to the class cube.
ii.	Create method calculateCube( ).
iii.	Call the method calculateArea ( ) into the calculateCube ( ) of the class Cube to calculate the cube.
iv.	In the main method, create instance object of Rectangle Rect1 and also instance object for Cube c1.
v.	Call the methods to respective class object and display the information. 


**Code:
Cube.java**

```
class Cube extends Rectangle {
int height;
void Set(int height) {
this.height = height;
}
int calculateCube() {
return 6 * (int)Math.pow(height, 2);
}
public static void main(String[] args) {
Cube c1 = new Cube();
Rectangle rect1 = new Rectangle();
rect1.Set(2, 4);
c1.Set(6);
int rectangleArea = (int) rect1.calculateArea();
int cubeArea = c1.calculateCube();
System.out.println("Area of Rectangle is: " + rectangleArea);
System.out.println("Area of cube is :" + cubeArea);
}
}

``` 

**OUTPUT:**


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1643425005031/hFpke8bu5.png)

3.Design a class for the below diagram.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1643425096500/-fi_B1OD_.png)

**Code:
Circle.java**


```
import java.lang.Math;
import java.util.*;
public class Circle
{
private double radius=1.0;
static private String color="red";
Circle()
{
System.out.println("default constructor");
}
Circle(double r)
{
radius = r;
}
double getRadius()
{
return radius;
}
double getArea()
{
double area;
area =Math.PI*Math.pow(radius,2);
return area;
}
public static void main(String args[])
{
Circle c = new Circle(4);
double rad=c.getRadius();
double area1=c.getArea();
System.out.println("radius of the circle is: "+rad);
System.out.println("color of the circle is: "+color);
System.out.println("area of the circle is: "+area1);
}
}

``` 

**OUTPUT:**


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1643425156260/lh44BU3WL.png)

4.Create an interface Engine with two abstract methods 
    changeGear( int a);
    speedup(int a);
of its return type is void.
Implement the interface methods in a class Vehicle.
The Vehicle class consists of
-Two member variables speed and gear
-Initialize the speed variable and print the value of speed in the speedUp() method.
-Initialize the gear variable and print the value of gear in the changeGear() method.
Create an object for Vehicle and call the implemented methods in the main method.

Code:
TestVehicle.java


```
interface Engine {
	void changeGear(int a);
	void speedUp(int a);
}

class Vehicle implements Engine{
	int speed;
	int gear;
	
	@Override
	public void changeGear(int newGear){		
		gear = newGear;
	}

	@Override
	public void speedUp(int increment){		
		speed = speed + increment;
	}
	
	public void printStates() {
		System.out.println("speed: " + speed
			+ " gear: " + gear);
	}
}

class vehicle1 {	
	public static void main (String[] args) {	
		Vehicle bike=new Vehicle();
        bike.changeGear(1);
        bike.speedUp(4);
		System.out.println("Vehicle present state :");
		bike.printStates();
	}
}

``` 
**OUTPUT:**


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1643425326551/qOWnJp-Kr.png)




5.Create an abstract class EmployeeDetails with two private member name and emp_ID.  A method called commonEmpDetails( ) to print information of name and emp_ID of its return type is void.
Have an abstract method confidentialDetials(int s, String p) of its return type is void.
Extend the abstract class in HR class.
The HR consists of
-Two private member variables salary and performance.
-Implement the confidentialDetails(s,p) method to provide the details of salary and performance.
     In the main method create object for HR and call the methods.
**
Code:
TestHR.java**


```
import java.util.Scanner;
abstract class EmployeeDetails{
    Scanner scn=new Scanner(System.in);
    private int emp_Id;
    private String name;
    void commonEmpDetails(){
        System.out.println("Emp ID :- "+emp_Id);
        System.out.println("Emp Name :- "+name);
    }
    void set_Emp_Details(){
        System.out.print("Enter Emp_ID :- ");
        emp_Id=scn.nextInt();
        scn.nextLine();
        System.out.print("Enter Emp_Name :- ");
        name=scn.nextLine();
    }
    abstract void confidentialDetails(int s,String p);
}
class HR extends EmployeeDetails{
    private int salary;
    private String performance;
    @Override
    void confidentialDetails(int s, String p) {
        salary=s;
        performance=p;
    } 
    @Override
    void commonEmpDetails(){
        super.commonEmpDetails();
        System.out.println("Emp Salary :- "+salary);
        System.out.println("Emp Performance :- "+performance);
    }
    @Override
    void set_Emp_Details(){
        super.set_Emp_Details();
        System.out.print("Enter Emp Salary :- ");
        int s=scn.nextInt();
        System.out.print("Enter Emp Performance :- ");
        String p=scn.next();
        confidentialDetails(s,p);
    }
}
public class TestHR {
    public static void main(String []args) {
        HR obj=new HR();
        obj.set_Emp_Details();
        System.out.println("**********");
        obj.commonEmpDetails();
    }
}

```


**OUTPUT:**


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1643425412474/TfF9jYEOo.png)
 

