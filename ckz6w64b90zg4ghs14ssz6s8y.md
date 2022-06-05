## Java lab Assignment task 3


1)In a school, students of all classes from std I to X appear for the MathPremierLeague examination. Define a class MPL which stores the details of the marks scored by each class. It should contain the following 4 data members: Standard, number of students, marks[] array to store the scores of all the students of the class in MPL exam and first mark. Create an array of 4 objects for this class. Define a parameterized constructor which receives the values for the first two datamembers from the main() method. From within the constructor, read the marks of all students and hence find the first mark. Define a method findBestClass() to display the standard which has secured the highest first mark. Overload this method to display the standard with the highest classaverage. The marks array should be declared dynamically based on the strength of the class.

**Code:**

**TestMPL.java:**

```
import java.util.Scanner;
class MPL {
    Scanner sc=new Scanner(System.in);
    int standard;
    int num_students;
    public int first;
    public float average;
    int student_first;
    
    MPL(int a,int b){
        standard=a;
        num_students=b;
        mark(num_students);
    }
    
    public void mark(int num_students){
        int max=0;
        int[] marks=new int[num_students];
        int average_class=0;
        System.out.println("Enter the marks of students:");
        for(int i=0;i<num_students;i++){
            marks[i]=sc.nextInt();
            average_class=average_class+marks[i];
            if(marks[i]>max){
                max=marks[i];
                student_first=i+1;
            }
        }
        first=student_first;
        average=average_class/num_students;
    }
    public void display(){
        System.out.println("Standard:"+standard);
        System.out.println("No of students:"+num_students);
        System.out.println("First student:"+first);
        System.out.println("AVerage of the class:"+average);
        
    }
    
}

class TestMPL{
    static MPL obj[]=new MPL[2];
    public static void main(String[] args){
        Scanner sc=new Scanner(System.in);
        int first=0;
        float avg=0;
        
        for(int i=0;i<2;i++){
            System.out.println("Enter the number of students in class"+(i+1));
            int students=sc.nextInt();
            obj[i]=new MPL(i,students);
            obj[i].display();
        }
        bestclass();
        avgbestclass();
        
    }
    public static void bestclass(){
        float max=0;
        int standard=0;
        for(int i=0;i<2;i++){
            if(obj[i].average>max){
                max=obj[i].average;
                standard=i+1;
            }
        }
        System.out.println("The best class on the basis of average is: "+standard);
    }
    public static void avgbestclass(){
        float max=0;
        int standard=0;
        for(int i=0;i<2;i++){
            if(obj[i].first>max){
                max=obj[i].first;
                standard=i+1;
            }
            
        }
        System.out.println("The best class on the basis of average is: "+standard);
    }

}
``` 



**OUTPUT:**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1643887366236/nUTn2bB-z.png)
