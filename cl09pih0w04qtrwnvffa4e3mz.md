## Java Lab Assignment 4

**1) Write a java code to concatenate two strings, compare strings:**

**Code:**

```
import java.util.*;
public class Main {
 public static void main(String[] args){
 Scanner sc=new Scanner(System.in);
 System.out.print("Enter first string: ");
 String str1=sc.next();
 System.out.print("Enter second string: ");
 String str2=sc.next();
 System.out.println("The string1 you entered: "+str1);
 System.out.println("The string2 you entered: "+str1);
System.out.println("Concatenation of "+str1+" and "+str2+" is:
"+str1.concat(str2));
 if(str1.equals(str2)){
 System.out.println("The strings "+str1+" and "+str2+" are equal");
 }
 else{
 System.out.println("The strings "+str1+" and "+str2+" are not equal");
 }
 }
}
``` 
**OUTPUT:**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1646234211341/3z8FzIXf6.png)

**2.Find the given word exists in the sentence**
**Code:**

```
import java.util.*;
public class SecondQuestion {
public static void main(String[] args){
Scanner sc=new Scanner(System.in);
 System.out.print("Enter a sentance: ");
 String sentence=sc.nextLine();
 System.out.print("Enter a word to find in the above sentance: ");
 String word=sc.next();
 if(sentence.contains(word)){
 System.out.println("The word "+word+" is present in the sentence:
"+sentence);
 }
 else{
 System.out.println("The word "+word+" is not present in the sentence:
"+sentence);
   }
  }
}

``` 
**OUTPUT:**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1646234342881/xAtct_hL_.png)


