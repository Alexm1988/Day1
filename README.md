# Day1
Day1_Selenium_homework
//Order of operations (PEMDAS) Java version
//by Richard
//I apologize for any typos, phone keyboards are not fun to use :)

//when reading this, keep in mind that all of this also applies to decrements (--) as well.

//When are post-fix increments executed? Normally Java follows the rule of PEMDAS, but it doesn't always:

public class Program {
    public static void main(String[] args) {
        int a = 2;
        int b = 3;
        int c = 4;
//The next line is messy, but it's like that so I can illustrate a point later. all we are doing are post-fix incrementing a and c, and we are multiplying everything"       ; 
        int d = ((a++ * b) * c++);
        
        System.out.println("d is equivalent to " + d );
        
//output will be "24", which indicates that postfix increments are ignored for both variable c (in the outer parenthesis) AND variable a (in the inner parenthesis). It's not only ignored until the entire expression has been evaluated, but also after d has been assigned the value.

//So for Java, I propose a modification of the tradition PEMDAS order of operations:

// PEMDASDI where D and I stands for post-fix decrement and increment.

//when we include pre-fix, it becomes DIPEMDASDI. we could include pre and post in the acronym, to make it (pre)DIPEMDAS(post)DI, but that would probably make it unnecessarily complicated :)

//these lines were just for testing. feel free to uncomment them of you'd like
//        System.out.println(a);
//        System.out.println(b);
//        System.out.println(c);

//EDIT: perhaps a better way to illustrate this point would've been multiply everything by a variable "e" that has an assigned value of 0 and post increment e:

int e = 0;
int f = (d * e++);
System.out.println("f is equivalent to " + f );

//This would result in f being assigned a value of 0 (24*0) as opposed to 24 (24*1).

    }
}
