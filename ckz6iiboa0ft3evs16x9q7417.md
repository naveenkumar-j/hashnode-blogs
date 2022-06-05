## Java lab Assignment 3

1.A training centre conducts a total of 7 tests for its students. Students are allowed to skip few tests. Let there be 25 students in the batch. So in the main class for every student, read the number of tests taken and the marks scored in each test. A class ‘TestDetails’ should be defined with a 2D array of float type to store the marks of all the students. Define a method ‘storeMarks()’ that will receive the following details for every student from the main class and create in the 2D array, those many columns equal to the number of tests, so as to store the marks. There is no need to store the number of tests. Define another method ‘displayMarks()’ to print the details. 
Also the training centre wishes to keep those students in notice period who have taken < 3 tests and those who have not scored ≥ 50 in at least 3 tests. Derive another class ‘NoticePeriod’ from ‘TestDetails’ that includes a method to count and print the number of students in bench. Also it should print the ID of those students assuming the row index of the array to be their ID. While checking do not proceed to check the marks in all tests, if the student has already scored more than 50 in 3 tests. Instantiate this class from the main class and do the required processing.

**Code:**

**TestDetails.java:**

```
public class TestDetails {
    protected float marks[][]; // array to store marks of students

    // constructor
    public TestDetails()
    {
        marks=null;
    }
     // method to store the marks of the students
    public void storeMarks(float inMarks[][])
    {
        marks = new float[inMarks.length][];
        for(int i=0;i<inMarks.length;i++)
        {
            marks[i] = new float[inMarks[i].length];
            for(int j=0;j<inMarks[i].length;j++)
                marks[i][j] = inMarks[i][j];
        }
    }
    // method to display the marks of the students
       public void displayMarks()
       {
           for(int i=0;i<marks.length;i++)
           {
               System.out.println("Student "+i+" : ");
               for(int j=0;j<marks[i].length-1;j++)
                   System.out.print(marks[i][j]+", ");
               System.out.print(marks[i][marks[i].length-1]);
           }
           System.out.println();
       }
}
      

``` 

**NoticPeriod.java:**


```
public class NoticePeriod extends TestDetails{
// method to print the ids of the students on the bench and print the number of students on bench
    public void printBench()
    {
        System.out.print("Students ID who are on bench : ");
        int benchStudents = 0;
        int countAbove50;
        // loop to calculate the number of students on bench
        for(int i=0;i<marks.length;i++)
        {
            if(marks[i].length < 3)
            {
                benchStudents++;
                System.out.print(i+" ");
            }
            else
            {
                countAbove50 = 0;
                for(int j=0;j<marks[i].length;j++)
                {
                    if(marks[i][j] >= 50)
                        countAbove50++;
                        if(countAbove50 >= 3)
                            break;
                }
                if(countAbove50 < 3)
                {
                    System.out.print(i+" ");
                    benchStudents++;
                }
            }
        }
        System.out.println("Total Students on bench : "+benchStudents);
    }
}

``` 





**Main.java:**

```
import java.util.Scanner;

public class Main {
    public static void main(String[] args)
    {
        NoticePeriod notice = new NoticePeriod();
        float marks[][] = new float[25][];
        Scanner scan = new Scanner(System.in);

        // loop to get the number of marks for each student and marks for each student
        for(int i=0;i<marks.length;i++)
        {
            System.out.print("Enter the number of marks for Student-"+i+" (max 7 marks): ");
            int numMarks = scan.nextInt();
            marks[i] = new float[numMarks];
            for(int j=0;j<marks[i].length;j++)
            {
                System.out.print("Enter marks-"+(i+1)+" : ");
                marks[i][j] = scan.nextFloat();
            }
        }
        notice.storeMarks(marks);
        notice.displayMarks();
        System.out.println();
        notice.printBench();
        scan.close();
    }
}


``` 




**OUTPUT:**


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1643867631694/Jw-ALHrnv.png)
