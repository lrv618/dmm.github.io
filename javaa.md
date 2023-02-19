# JAVA

## javaSE



### java基础

#### 关键字

![20201119232639560](F:\study\java\photo\20201119232639560.png)



#### 标识符



`java所有组成部分都需要名字。类名、变量名、方法名都称为标识符`

```java
public class Demo01 {
    public static void main(String[] args) {

        //标识符(大小写敏感）
        String CAT = "eee";

        System.out.println(CAT);  //eee
        //不相同
        String cat = "eee";
        //eg:
        String Ahello = "aaa";
        String hello = "bbb";
        String _hello = "ccc";
        String $hello = "ddd";
        //标识符可以用字母（A-Z或者a-z、$、_)开始


    }
}
```



##### 数据类型



强类型语言

​		要求变量的使用要严格符合规定，所有变量就必须先定义后才使用

弱类型语言

java的数据类型分为两类

​		 基本类型

​		 引用类型

![image-20230109213846433](C:\Users\邓猫猫\AppData\Roaming\Typora\typora-user-images\image-20230109213846433.png)



```java
public class demo02 {
    public static void main(String[] args) {
        String a="邓茂臻";  //注意""; bai'so
        int num=0;

        //八大基本数据类型
        
        //整数
        int num1= 10;  //最常用
        byte num2 =20;
        short num3 =30;
        long num4 =30L; //long类型要在数字后面＋L

        //小数（浮点数）
        float num5 = 50.1F;  //float类型要在数字后面＋F
        double num6 =3.141592653;

        //字符类型
        char name ='国';    //注意'';

        //字符串
        String name1="邓茂臻";  //注意"";

        //布尔值:是非
        boolean flag = true;
        //boolean flag =flase;
    }
}
```



###### 数据类型拓展

![image-20230110184126567](F:\study\java\photo\image-20230110184126567.png)



![image-20230110184247001](F:\study\java\photo\image-20230110184247001.png)



![image-20230110184623245](F:\study\java\photo\image-20230110184623245.png)



#### 位与字节

![image-20230109215725019](C:\Users\邓猫猫\AppData\Roaming\Typora\typora-user-images\image-20230109215725019.png)



#### 类型转换

注意：

1.不能对布尔值进行转换

2.不能对象类型转换为不相干的类型

3.在把高容量转换到低容量的时候，强制类型转换

4.转换的时候可能存在内存溢出，或者精度缺失



```
强制转换 （类型）变量名  高--底
自动转换               低--高
```

![image-20230110185605140](F:\study\java\photo\image-20230110185605140.png)



```java
public class demo06 {
    public static void main(String[] args) {
        int money = 10_0000_0000;
        int years = 20;
        int total = money*years;      //-1474836480
        long total2 = money*years;     //默认是int，转换之前存在问题
        long total3 = money*((long)years);  //先把一个数转换成long,再计算

        System.out.println(total3);  //输出结果20000000000
    }
}
```



#### 变量与常量



##### 变量

![image-20230114005453563](F:\study\java\photo\image-20230114005453563.png)





![image-20230114010716732](F:\study\java\photo\image-20230114010716732.png)



##### 变量作用域

![image-20230114005551488](F:\study\java\photo\image-20230114005551488.png)



```java
public class demo08 {

    //属性：变量
    //实列变量
    String name;
    int age = 123_456_789;

    //类变量 static
    static double salary = 2500;

    /*实列变量：从属于对象；如果不自行初始化，这个类型的默认值为0.0.0
      布尔值：默认是flase
      除了基本类型，其余的都是null;
     */

    //main方法
    public static void main(String[] args) {
        //局部变量；必须声名和初始化值
        int i = 10;
        System.out.println(i);

        //变量类型  变量名 = new demo08();
        demo08 demo08 = new demo08();
        System.out.println(demo08.age);
        System.out.println(demo08.name);

        //类变量 static
        System.out.println(salary);
    }
}
```



##### 常量

![image-20230114005741008](F:\study\java\photo\image-20230114005741008.png)



```java
public class demo09 {

    //修饰符，不存在先后顺序
    static final double PI =3.14;

    public static void main(String[] args) {
        System.out.println(PI);
    }
}
```



#### 运算符

![image-20230114164153787](F:\study\java\photo\image-20230114164153787.png)

​                              逻辑运算符：                                         位运算符：

%取于                    &&与（都为真才是ture)                     &：与

==等于                  || 或（有一个为真，结果为true)        |：或

!=不等于               !非(结果取反)                                       ^:异或

​                                                                                            ~：取反

##### 算术运算符、赋值运算符

```java
public class Demo01 {
    public static void main(String[] args) {
        //二元运算符
        //ctrl+d：复制当前行到下一行
        int a =10;
        int b =20;
        int c =25;
        int d =25;

        System.out.println(a+b);
        System.out.println(a-b);
        System.out.println(a*b);
        System.out.println(a/(double)b);
    }
}
```

运行结果

![image-20230114175922229](F:\study\java\photo\image-20230114175922229.png)



```java
public class Demo02 {
    public static void main(String[] args) {
        long a =123_123_123_123_123L;
        int b =123;
        short c =10;
        byte d =8;

        System.out.println(a+b+c+d);//long
        System.out.println(b+c+d);//int
        System.out.println(c+d);//int

    }
}
```

运行结果

![image-20230114180036208](F:\study\java\photo\image-20230114180036208.png)



```java
public class Demo03 {
    public static void main(String[] args) {
        //关系运算符返回结果： 正确，错误 布尔值
        int a = 10;
        int b = 10;
        int c = 21;

        System.out.println(c%a); //c/a 21/10

        System.out.println(a>b);
        System.out.println(a<b);
        System.out.println(a==b);
        System.out.println(a!=b);
    }
}
```

运行结果

![image-20230114180207339](F:\study\java\photo\image-20230114180207339.png)



##### 自增、自减运算符

```java
public class Demo04 {
    public static void main(String[] args) {
        // ++ -- 自增 自减 一元运算符
        int a = 3;   //a的初始值为3

        int b =a++;  //执行完这行代码后，先给b赋值，再自增
        //a++ a=a+1;

        System.out.println(a);
        System.out.println("===========================");

        int c =++a;  //执行完这行代码前，先自增，再给b赋值
        //++a a=a+1;

        System.out.println(a);

        System.out.println("===========================");

        System.out.println(b);
        System.out.println(c);

        System.out.println("===========================");

        //幂运算  2^3=2*2*2=8
        double pow = Math.pow(2,3);
        System.out.println(pow);


    }
}
```



运行结果

![image-20230114185342318](F:\study\java\photo\image-20230114185342318.png)



##### 逻辑运算符

```java
public class Deno05 {
    public static void main(String[] args) {
        //与（and) 或（or) 非（取反）
        boolean a = true;
        boolean b = false;

        System.out.println("a&&b:" + (a&&b)); //逻辑与运算：两个变量都为真，结果才为ture
        System.out.println("a||b:" + (a||b));  //逻辑或运算：两个变量一个为真，则结果才为ture
        System.out.println("!(a&&b):"+  !(a&&b)); //如果是真，则变为假，如果是假则变为真

        System.out.println("======================================");

        //短路运算  第一个为假后,后面直接短路，不用运算
        int c =5;
        boolean d = ((c<4)&&(c++<4));
        System.out.println(d);
        System.out.println(c);
    }
}
```

运行结果

![image-20230114224314213](F:\study\java\photo\image-20230114224314213.png)



##### 位运算符

```java
public class Demo06 {
    public static void main(String[] args) {
        /*
        A= 0011 1100
        B= 0000 1101

        A&B = 0000 1100  (两个都为1才为1）   &:与
        A|B = 0011 1101  （其中一个为1就为1）   |:或
        A^B = 0011 0001  （如果两个相同则为0，不同则为1）  ^:异或
        ~B  = 1111  0010  （两个相同则为1，不同则为0）  ~:取反

        2*8=16 2*2*2*2
        <<  左移  *2
        >>  右移  /2
        
        0000 0000    0
        0000 0001    1
        0000 0010    2
        0000 0011    3
        0000 0100    4
        0000 1000    8
        0001 0000    16

         */
        System.out.println(2<<3);   //16
    }
}
```



##### 扩展运算符

```java
public class Demo07 {
    public static void main(String[] args) {
        int a =10;
        int b =20;

        a+=b; //a= a+b
        a-=b; //a =a-b

        System.out.println(a);

        //字符串连接符； + , String
        System.out.println(a+b);
        
        System.out.println("==========================");
        System.out.println(""+a+b);
        System.out.println(a+b+"");
    }
}
```



##### 三元运算符（import)

 x ? y : z
如果x==true,则结果为y,否则结果为z

```java
public class Demo08 {
    public static void main(String[] args) {
        //x ? y : z
        //如果x==true,则结果为y,否则结果为z

        int score = 50;
        String type = score < 60 ?"不及格":"及格";//重中之重
        //if
        System.out.println(type);  //不及格
    }
}
```



#### 包机制



![image-20230115112052550](F:\study\java\photo\image-20230115112052550.png)

```
import com.dmz.base.*; //导入这个包下所有的类class
import java.util.Date; 
```



#### javaDoc生成文档



```java
package com.dmz.base;

//javadoc命令用来生成自己的API文档

/**
 * @author dmz   //作者
 * @version 1.0  //版本
 * @since 1.1    //指明需要的最低jdk版本
 * param         //参数名
 * return        //返回值
 * throws        //异常抛出情况
 */
public class Doc {
    String name;

    /**
     *
     * @param name
     * @return
     * @throws Exception
     */

    public String test(String name) throws Exception{
        return name;
    }
}
```



cmd F:\study\java\java\src\com\dmz\base  导航栏打开命令行

```
通过cmd生成javadoc文件 javadoc -encoding UTF-8 -charset UTF-8  Doc.java  //-encoding UTF-8 -CHAREST UTF-8  让enconding(编码)UTF-8中的charest(字符集)也变成UTF-8
```





### java流程控制



#### 用户交互scanner

##### scanner对象

![image-20230116114443821](F:\study\java\photo\image-20230116114443821.png)



![image-20230116121808970](F:\study\java\photo\image-20230116121808970.png)



##### next();

```java
public static void main(String[] args) {
    
    //创建一个扫描器对象，用于接收键盘数据
    Scanner scanner = new Scanner(System.in);
    
    System.out.print("请输入：");
    
    //判断用户是否有输入字符串
    if (scanner.hasNext()){
        
        //使用next方式接收
        String str=scanner.next();
        System.out.println("输出的内容为："+str);
       
       //属于IO流（输入输出流）的类如果不关闭会一直占用资源，用完要关闭
        scanner.close();
    }
}
```



##### nextLine();

```java
public static void main(String[] args) {
    Scanner scanner = new Scanner(System.in);
    System.out.println("请输入数据:");
    
    String str = scanner.nextLine();
    System.out.println("输出内容为："+str);
    
    scanner.close();
}
```



```java
import java.util.Scanner;

    public static void main(String[] args) {
        //创建一个扫描器对象，用于接收键盘数据
        Scanner scanner = new Scanner(System.in);
        
        System.out.print("请输入：");
        
        //判断用户是否有输入字符串
        if (scanner.hasNextLine()){
            
            //使用nextLine方式接收
            String str=scanner.nextLine();
            System.out.println("输出的内容为："+str);
            
            //属于IO流（输入输出流）的类如果不关闭会一直占用资源，用完要关闭
            scanner.close();
        }
    }
```



##### scanner进阶使用

判断是否整数

```java
public static void main(String[] args) {
    Scanner scanner = new Scanner(System.in);

    /*从接盘接收数据
    //int i =0;
    float f = 0.0f;*/

    System.out.println("请输入整数:");

    if (scanner.hasNextInt()){
        int i = scanner.nextInt();
        System.out.println("整数数据"+i);
    }else {
        System.out.println("请输入不是整数数据");
    }


    if (scanner.hasNextFloat()){
        float f = scanner.nextFloat();
        System.out.println("小数数据"+f);
    }else {
        System.out.println("请输入不是小数数据");
    }


    scanner.close();
}
```

​			我们可以输入多个数字，并求其总和与平均数，每输入一个数字用回车确认，通过输入非数字来结束输入并输出结果。

```java
public static void main(String[] args) {
    //我们可以输入多个数字，并求其总和与平均数，每输入一个数字用回车确认，通过输入非数字来结束输入并输出结果
    Scanner scanner = new Scanner(System.in);

    //和
    double sum=0;
    //计算输入多少个数字
    int m =0;
    System.out.println("请输入数据：");
    
    //通过循环判断是否还有输入，并在里面对每次进行求和和统计
    while (scanner.hasNextDouble()){
        double x= scanner.nextDouble();  //判断是否还有输入数字

        m=m+1; //亦可以m++
        sum = sum +x;
        System.out.println("你输入了第"+m+"个数据，然后当前结构sum="+sum);
        
    }

    System.out.println(m+"个数的和为："+sum);
    System.out.println(m+"个数的平均数："+(sum/m));

    scanner.close();
}
```



#### 顺序结构

![image-20230116181016839](F:\study\java\photo\image-20230116181016839.png)



#### 选择结构



*if语句至多1个else语句，else语句在所有的else if 语句之后，*

*if 语句可以有若干个else if 语句，它们必须在else语句之前，*

*一旦其中一个else if 语句检测为true，其他else if 以及else 语句都将跳过执行。*



##### if单选择结构

![image-20230116181444538](F:\study\java\photo\image-20230116181444538.png)



##### if双选择结构

![image-20230116225013126](F:\study\java\photo\image-20230116225013126.png)



eg:

```java
public static void main(String[] args) {
    //考试分数>=60分合格，<60分不合格

    Scanner scanner = new Scanner(System.in);

    System.out.println("请输入成绩：");
    int score = scanner.nextInt();

    if (score>=60) {
        System.out.println("及格");
    }else {
        System.out.println("不及格");
    }

    scanner.close();
```



##### if多选择结构

![image-20230116225357763](F:\study\java\photo\image-20230116225357763.png)



```java
public static void main(String[] args) {

    Scanner scanner = new Scanner(System.in);


    System.out.println("请输入成绩：");
    int score = scanner.nextInt();

    if (score==100) {
        System.out.println("S");
    }
    else if (score<100 && score>=90){
        System.out.println("A");
    }
    else if (score<90 && score>=80){
        System.out.println("B");
    }
    else if (score<80 && score>=70){
        System.out.println("C");
    }
    else if (score<70 && score>=60){
        System.out.println("D");
    }
    else if (score<60 && score>=0){
        System.out.println("E");
    }
    else {
        System.out.println("程序出错，请重新输入");
    }

    scanner.close();
}
```



##### switch多选择结构

![image-20230117220904872](F:\study\java\photo\image-20230117220904872.png)



```java
public class SwitchDemo02 {
    public static void main(String[] args) {
        String name = "lisi";
        //JDK7的新特性，表达式结果可以是字符串
        //字符的本质还是数字
        //反编译 java---class(字节码文件)---反编译(IDEA)

        switch(name){
            case "zhangsan":
                System.out.println("张三");
                break;
            case "lisi":
                System.out.println("李四");
                break;
            default:
                System.out.println("输出错误");
        }
    }
}
```



反编码

```java
package com.dmz.struct;

public class SwitchDemo02 {
    public SwitchDemo02() {
    }

    public static void main(String[] args) {
        String name = "lisi";
        byte var3 = -1;
        switch(name.hashCode()) {
        case -1432604556:
            if (name.equals("zhangsan")) {
                var3 = 0;
            }
            break;
        case 3322003:
            if (name.equals("lisi")) {
                var3 = 1;
            }
        }

        switch(var3) {
        case 0:
            System.out.println("张三");
            break;
        case 1:
            System.out.println("李四");
            break;
        default:
            System.out.println("输出错误");
        }

    }
}
```



#### 循环结构



##### while循环

![image-20230117230228365](F:\study\java\photo\image-20230117230228365.png)



```java
public static void main(String[] args) {
    //输出1~100
    int i = 0;
    while (i<100){
        i++;
        System.out.println(i);
    }
}
```



```java
public static void main(String[] args) {
    //计算1+2+3+...100=？

    int i =0;
    int sum =0;

    while (i<=100){
        sum = sum + i;
        i++;
    }
    System.out.println(sum);
```



##### do...while循环

![image-20230118004513477](F:\study\java\photo\image-20230118004513477.png)



##### While和do -While的区别

while先判断后执行。dowhile是先执行后判断。

do-while总是保证循环会被至少执行一次，这就是主要差别。

```java
public class DoWhileDemo02 {
    public static void main(String[] args) {
        int a =0;
        while (a<0){
            System.out.println(a);
            a++;
        }
        System.out.println("========================");
        do{
            System.out.println(a);
            a++;
        }while(a<0);
    }
}
```



![image-20230118005840228](F:\study\java\photo\image-20230118005840228.png)



##### for循环

![image-20230118010100896](F:\study\java\photo\image-20230118010100896.png)



IDEA快捷方式键：100.for



for循环说明：

​        最先执行初始化步骤。可以声名一种类型，但可初始化一个或多个循环控制变量，也可以是空语句。

​       然后，检测布尔表达式的值。如果是ture，循环体被执行。如果是flase,循环终止，开始执行循环体后面的语句。

​		执行一次循环后，更新循环控制变量（迭代因子控制循环变量的增减）。

​		再次检测布尔表达式，循环执行上面的过程。



```java
public class ForDemo01 {
    public static void main(String[] args) {
        int a = 1; //初始化条件

        while (a <= 100) {//条件判断
            System.out.println(a);//循环体
            a += 2;//迭代
        }
        System.out.println("while循环结束！");

        System.out.println("=======================================");

             //初始化   //条件判断  //迭代
        for (int i = 1; i <= 100; i++) {
            System.out.println(i);
        }

        System.out.println("for循环结束！");
        
}
```



eg：

1.计算0-100之间的奇数和偶数的和

```java
public static void main(String[] args) {
    //计算0-100之间的奇数和偶数的和
    
    int oddSum = 0;
    int evenSum = 0;

    for (int i = 0; i <= 100; i++) {
        if(i%2==0){  //偶数
            evenSum+=i;  //evenSum = evenSum+i;
        }else{     //奇数
            oddSum+=i;
        }
    }
    System.out.println("奇数的和："+oddSum);
    System.out.println("偶数的和："+evenSum);
}
```



2.用while或for循环输出1-1000之间能被5整除的数，并每行输出3个

```java
public static void main(String[] args) {

    for (int i = 0; i <= 1000; i++) {
        if (i%5==0){
            System.out.print(i+"\t");
        }
        if (i%(5*3)==0){
            System.out.print("\n");
        }
    }
}
```



3.打印九九乘法表

解题思路

/*1.先打印第一列

   2.把固定的1再用一个循环包起来

   3.去掉重复项，i<=j

   4.调整样式*/

```java
public static void main(String[] args) {
    for (int j = 1; j <= 9; j++) {
        for (int i = 1; i <= j; i++) {
            System.out.print(j+"*"+i+"="+(j*i)+"\t");
        }
        System.out.println();
    }
}
```

![image-20230118020938391](F:\study\java\photo\image-20230118020938391.png)



##### 增强for循环

![image-20230118021424598](F:\study\java\photo\image-20230118021424598.png)



```java
public static void main(String[] args) {
    int[] numbers = {10,20,30,40,50}; //定义了一个数组

    for (int i = 0; i <5; i++) {
        System.out.println(numbers[i]);
    }
    System.out.println("===========================");
    
    //增强for循环
    //遍历数组元素
    for(int x:numbers){
        System.out.println(x);
    }
}
```



#### break &continue

![image-20230118110808486](F:\study\java\photo\image-20230118110808486.png)



##### break

```java
public static void main(String[] args) {
    int i =0;
    while (i<100){
        i++;
        System.out.println(i);
        if (i==30){
            break;
        }
```



##### continue

```java
public static void main(String[] args) {
    int i =0;
    while (i<100){
        i++;
        if (i%10==0){
            System.out.println();
            continue;
        }
    }
}
```



break在任何循环语句的主体部分，均可用break控制循环流程

break用于强行退出循环，不执行剩下的语句（break语句也在switch语句中使用）

continue语句用循环语句中，用于终止某次循环过程，即跳过循环中尚未执行的语句，接着进行下一次是否执行循环判定



不建议使用

```java
public static void main(String[] args) {
    //打印101-150之间所有的质数
    //质数是指在大于1的自然数中，除了1和它本身以外不再有其他原因的自然数
    int count =0;

    outer:for (int i=101;i<150;i++){
          for(int j=2;j<i/2;j++){
            if (i%j==0){
                continue outer;
            }
        }
        System.out.print(i+"\t");
    }
}
```



#### 打印三角形及debug

![image-20230118185100685](F:\study\java\photo\image-20230118185100685.png)

```java
public static void main(String[] args) {
    for (int i = 1; i < 5; i++) {
        for (int j = 5; j >= i; j--) {
            System.out.print(" ");
        }
        for (int j = 1; j <= i; j++) {
            System.out.print("*");
        }
        for (int j = 1; j < i; j++) {
            System.out.print("*");
        }
        System.out.println();
    }
}
```



### java方法



![image-20230120182011101](F:\study\java\photo\image-20230120182011101.png)





```java
//main方法
public static void main(String[] args) {
    
    //实际参数：实际调用传递给它的参数
    int sum = add(1,2);
    System.out.println(sum);
}

//加法(方法）
//形式参数，用来定义作用的
public static int add(int a,int b){
    return a+b;
}
```



![image-20230131114111607](F:\study\java\photo\image-20230131114111607.png)



```java
public static void main(String[] args) {
   /* int sum = add(1,2);
    System.out.println(sum);
    */
    test();

}

//加法(方法）
public static int add(int a,int b){
    return a+b;
}

public static void test() {

    for (int i = 0; i <= 1000; i++) {
        if (i%5==0){
            System.out.print(i+"\t");
        }
        if (i%(5*3)==0){
            System.out.print("\n");
        }
    }
}
```





#### 方法定义和调用

![image-20230131223723968](F:\study\java\photo\image-20230131223723968.png)



```java
    public static void main(String[] args) {

        int max = max(10,20);
        System.out.println(max);
    }
    //比大小
       //修饰符    返回值类型   方法名   参数类型  参数名
    public static    int      max     (int    num1,   int  num2){

        int result=0;

        if (num1==num2){
            System.out.println("num1==num2");
            return 0;//终止方法
        }

        if (num1>num2){
            result = num1;
        }else {
            result = num2;
        }

        return result;
    }
```



```java
public static void main(String[] args) {

}


/*
  修饰符   返回值类型   方法名(...){
     //方法体
     return 返回值；
 */

//return 结束方法，返回一个结果
public String sayHello() {
    return "hello,world";
}

public void print(){
    return ;
}

public int max(int a, int b) {

    return a > b ? a : b; //三元运算符！(是为a,否者为b)
}

//数组下标越界
public void readFile(String file) throws IOException{

}
```



##### 静态方法调用

```java
//静态方法 static
public static void main(String[] args) {
    Student.say();
}

public class Student {
    //静态方法
    public static void say(){
        System.out.println("学生说话了");
    }
```



##### 非静态方法调用

```java
public static void main(String[] args) {
    //静态调用非静态一定要 new
    //实列化这个类 new
    //对象类型  对象名 = 对象值；
    Student student = new Student();
    student.say();
}

public class Student {
    //非静态方法
    public  void say(){
        System.out.println("学生说话了");
    }
```







#### 方法重载



![image-20230201112732305](F:\study\java\photo\image-20230201112732305.png)



```java
 public static void main(String[] args) {

        int max = max(10,20,30);
        //double max = max(10.5,20.0);
        System.out.println(max);
    }
    //比大小
       //修饰符    返回值类型   方法名   参数类型  参数名
    public static    int      max     (int    num1,   int  num2  , int num3){

        int result=0;

        if (num1==num2){
            System.out.println("num1==num2");
            return 0;//终止方法
        }

        if (num1>num2){
            result = num1;
        }else {
            result = num2;
        }

        return result;
    }


    public static    double      max     (double    num1,   double  num2){

        double result=0;

        if (num1==num2){
            System.out.println("num1==num2");
            return 0;//终止方法
        }

        if (num1>num2){
            result = num1;
        }else {
            result = num2;
        }

        return result;
    }
}
```



#### 形参和实参

```java
public static void main(String[] args) {

    //实际参数和形式参数的类型要对应！
    int add = Demo03.add(1,2);
      System.out.println(add);
}


public  static int add(int a , int b){
    return a+b;
}
```



#### 值传递

```java
 //值传递
 public static void main(String[] args) {
     int a =1;
     System.out.println(a);

     System.out.println("====================");
     
     Demo04.change(a);
     System.out.println(a); //1 
 }
//返回值为空
 public static void change(int a){
     a = 10;

 }
```



#### 引用传递

```java
public class Demo05 {
    public static void main(String[] args) {
        Person person = new Person();

        System.out.println(person.name); //null

        Demo05.change(person);

        System.out.println(person.name); //dmz

    }

    public static void change(Person person){
        
        //person是一个对象：指向的 ---> Person person = new Person();这是一个具体的人，可以改变属性!
        person.name = "dmz";
    }

}

//定义一个person类，有一个属性：name
class Person {
    String name; //null

}
```



#### 命令行传参



![image-20230201115811191](F:\study\java\photo\image-20230201115811191.png)



```java
public static void main(String[] args) {
    //args.length 数组长度
    for (int i = 0; i < args.length ; i++) {
        System.out.println(args[i]);
    }
}
```



![image-20230201115859385](F:\study\java\photo\image-20230201115859385.png)



#### 可变参数（不定项参数）



![image-20230201223736703](F:\study\java\photo\image-20230201223736703.png)



```java
public static void main(String[] args) {
       Demo04 demo04 = new Demo04();
       demo04.test(1,2,3,4,55,6);
}
public void test(int... i){
    System.out.println(i[0]);
    System.out.println(i[1]);
    System.out.println(i[2]);
    System.out.println(i[3]);
    System.out.println(i[4]);
    System.out.println(i[5]);
}
```



#### 递归



![image-20230202000806054](F:\study\java\photo\image-20230202000806054.png)



![image-20230202002735864](F:\study\java\photo\image-20230202002735864.png)



```java
public static void main(String[] args) {
    System.out.println(f(3));
}

/*
2 2*f(1)
3 3*f(2)
 */
//di'gui
public static int f(int n){
    if (n==1){
        return 1;
    }else {
        return n*f(n-1);
    }
}
```



### java数组



#### 数组的声名与创建

![image-20230203011527272](F:\study\java\photo\image-20230203011527272.png)



![image-20230202232046903](F:\study\java\photo\image-20230202232046903.png)



![image-20230202234607121](F:\study\java\photo\image-20230202234607121.png)



```java
public static void main(String[] args) {
    int[] nums; //1.声名一个数组    //int num2[];  跟c、c++语法相似

    nums = new int[10];  //2.创建一个数组

    //声名和创建写在一起的写法 int[] nums = new int[10];

     //3.给数组元素赋值
    nums[0] = 1;
    nums[1] = 2;
    nums[2] = 3;
    nums[3] = 4;
    nums[4] = 5;
    nums[5] = 6;
    nums[6] = 7;
    nums[7] = 8;
    nums[8] = 9;
    nums[9] = 10;

    //计算所有元素的和

    int sum = 0;
    //获取数组长度：arrays.length

    for (int i = 0; i < nums.length ; i++) {
        sum = sum + nums[i];
    }

    System.out.println("总和为："+sum);
}
```



#### 三种初始化及内存分析



![image-20230203005351580](F:\study\java\photo\image-20230203005351580.png)



![image-20230203005327849](F:\study\java\photo\image-20230203005327849.png)



![image-20230203005541843](F:\study\java\photo\image-20230203005541843.png)



```java
public static void main(String[] args) {
        //静态初始化  创建 + 赋值
        int[] a= {1,2,3,4,5,6,7,88,9};

        System.out.println(a[1]);
        
        System.out.println("=============================");


        //动态初始化(包含默认初始化）
        int[] b = new int[10];
        b[0] = 10;
        b[1] = 20;

        System.out.println(b[0]);
        System.out.println(b[1]);
        System.out.println(b[2]);
        System.out.println(b[3]);

    }
```



![image-20230203010939350](F:\study\java\photo\image-20230203010939350.png)





#### 下标越界

![image-20230203011624426](F:\study\java\photo\image-20230203011624426.png)



```java
int[] a= {1,2,3,4,5,6,7,88,9};
for (int i = 0; i <a.length ; i++) {
    System.out.println(a[0]);
}
```



#### 数组的使用



For-Each循环

```java
    public static void main(String[] args) {
        int[] arrays = {1,2,3,4,5};

        //打印全部的数组元素
        for (int i = 0; i <arrays.length ; i++) {
            System.out.println(arrays[i]);
        }

        System.out.println("==========================");

        //计算所有元素的和
        int sum =0;
        for (int i = 0; i <arrays.length ; i++) {
            sum = sum + arrays[i];
        }
        System.out.println("sum="+sum);

        System.out.println("==========================");

        //查找最大元素
        int max = arrays[0];

        for (int i = 0; i < arrays.length ; i++) {
            if (arrays[i]>max){
                max = arrays[i];
            }
        }

        System.out.println("max="+max);
```



数组作方法入参

```java
public static void main(String[] args) {
    int[] arrays = {1,2,3,4,5};

    //JDK1.5 没有下标
    //增强型循环
  for (int array : arrays) {
     System.out.println(array);
  }
```



```java
 printArray(reverse);
}
   //打印数组元素
    public static void printArray(int[] arrays){
        for (int i = 0; i <arrays.length ; i++) {
            System.out.print(arrays[i]+" ");
        }
```



数组作返回值

```java
        int[] reverse = reverse(arrays);

        printArray(reverse);
    }

    //反转数组
    public static int[] reverse(int[] arrays){
        int[] result = new int[arrays.length];

        //反转操作
        for (int i = 0,j=result.length-1; i < arrays.length ; i++,j--) {
            //result[]=arrays[i];
            result[j] = arrays[i];
        }

        return result;
    }


    //打印数组元素
    public static void printArray(int[] arrays){
        for (int i = 0; i <arrays.length ; i++) {
            System.out.print(arrays[i]+" ");
        }


    }
```



#### 多维数组



![image-20230204030719015](F:\study\java\photo\image-20230204030719015.png)



```java
public static void main(String[] args) {

    //[4][2]
    /*
       1,2 array[0]
       2,3 array[1]
       3,4 array[2]
       4,5 array[3]
     */
    int[][] array = {{1,2},{2,3},{3,4},{4,5}};

    System.out.println(array.length);

    System.out.println(array[0].length);

    System.out.println(array[0][1]);

    System.out.println("===============================");

    for (int i = 0; i < array.length; i++) {
        for (int j = 0; j < array[i].length ; j++) {
            System.out.println(array[i][j]);
        }
    }
    
}
```



#### Arrays类



```java
public static void main(String[] args) {
    int[] a = {1,2,3,456,369,88};

    System.out.println(a);

    //打印数组元素Arrays.toString
    //System.out.println(Arrays.toString(a));
    printArray(a);
}

public static void printArray(int[] a){
    for (int i = 0; i <a.length ; i++) {
        if (i==0){
            System.out.print("[");
        }if (i==a.length-1){
            System.out.print(a[i]+"]");
        }else {
            System.out.print(a[i]+",");
        }

    }
}
```



```java
public static void main(String[] args) {
    int[] a = {1,2,3,456,369,88};

   // System.out.println(a);

    //打印数组元素Arrays.toString
    //System.out.println(Arrays.toString(a));
    //printArray(a);

    Arrays.sort(a);  //数组进行排序：升序

    System.out.println(Arrays.toString(a));
}

public static void printArray(int[] a){
    for (int i = 0; i <a.length ; i++) {
        if (i==0){
            System.out.print("[");
        }if (i==a.length-1){
            System.out.print(a[i]+"]");
        }else {
            System.out.print(a[i]+",");
        }

    }
```



![image-20230204111514653](F:\study\java\photo\image-20230204111514653.png)





#### 冒泡排序



![image-20230204183947446](F:\study\java\photo\image-20230204183947446.png)



```java
    public static void main(String[] args) {
        int[] a = {1,2,3,456,369,88,7};

        int[] sort = sort(a);  //调用完我们自己写的排序方法以后，返回一个排序后的数组

        System.out.println(Arrays.toString(sort));
    }

    //冒泡排序
    //1.比较数组中，两个相邻的元素，如果第一个比第二个数大，我们就交换它们的位置
    //2.每一次比较，就会产生一个最大，或者最小的数字；
    //3.下一轮可以 少一次排序
    //4.依次循环。直到结束。


    public static int[] sort(int[] array){
        //临时变量
        int temp = 0;

        //外层循环，判断我们这个要走多少次
        for (int i = 0; i <array.length-1 ; i++) {

            boolean flag = false; //通过flag标识位减少没有意义的比较(省略最后一轮比较）

            //内层循环，比价判断两个数，如果第一个数，比第二个数大，则交换位置
            for (int j = 0; j < array.length-1-i ; j++) {
                if (array[j+1]> array[j]){   //由小到大，array[j+1]< array[j]
                    temp = array[j];
                    array[j] = array[j+1];
                    array[j+1] = temp;

                }
            }

            if (flag==false){
                break;
            }
        }
        return array;
    }
```



#### 稀疏数组



![image-20230204190508084](F:\study\java\photo\image-20230204190508084.png)



![image-20230204235750801](F:\study\java\photo\image-20230204235750801.png)



```java
public static void main(String[] args) {
    //创建一个二维数组11*11   0：没有棋子   1：黑棋   2：白棋
    int[][] array1 =new int[11][11];
    array1[1][2] = 1;
    array1[2][3] = 3;
    //输出原始数组

    System.out.println("输出原始数组");

    for (int[] ints : array1) {
        for (int anInt : ints) {
            System.out.print(anInt+"\t");
        }
        System.out.println();
    }


    //转换位稀疏数组保存
    //获取有效值个数
    int sum = 0;
    for (int i = 0; i <11 ; i++) {
        for (int j = 0; j < 11; j++) {
            if (array1[i][j]!=0){
                sum++;
            }
        }
    }
    System.out.println("有效值个数:"+sum);

    //2.创建一个稀疏数组的数组
    int[][] array2 = new int[sum+1][3];

    array2[0][0] = 11;
    array2[0][1] = 11;
    array2[0][2] = sum;

    //遍历二维数组，将非零的值，存放在稀疏数组中
    int count=0;
    for (int i = 0; i <array1.length ; i++) {
        for (int j = 0; j <array1[i].length ; j++) {
            if (array1[i][j]!=0){
                count++;
                array2[count][0]=i;
                array2[count][1]=j;
                array2[count][2]=array1[i][j];
            }
        }
    }
    //输出稀疏数组
    System.out.println("稀疏数组");

    for (int i = 0; i <array2.length ; i++) {
        System.out.println(array2[i][0]+"\t"
                           +array2[i][1]+"\t"
                           +array2[i][2]+"\t");
    }

    System.out.println("============================================");
    System.out.println("还原");

    //1.读取稀疏数组
    int[][] array3 = new int[array2[0][0]] [array2[0][1]];

    //2.给其中的元素还原它的值
    for (int i = 1; i <array2.length ; i++) {
        array3[array2[i][0]] [array2[i][1]] = array2[i][2];
    }

    //3.打印
    System.out.println("输出还原数组");

    for (int[] ints : array3) {
        for (int anInt : ints) {
            System.out.print(anInt+"\t");
        }
        System.out.println();
    }
}
```





### 面对对象

##### 类与对象

> 1.类与对象
>     类是一个模板；抽象，对象是一个具体的实列
>
> 2.方法
>     定义、调用！
>
> 3.对应的引用
>     引用类型： 基本类型（8）
>         对象是通过引用来操作： 栈-->堆
>
> 4.属性：字段Filed 成员变量
>     默认初始化：
>         数字： 0   0.0
>         char:   u0000
>         boolean:  false
>         引用： null
>     
>     修饰符   属性类型   属性名 = 属性值
>
> 5.对象的创建和使用
>
>     - 必须使用new 关键字创造对象 ，构造器  person dmz = new Person();
>         - 对象的属性  dmz.name
>         - 对象的方法  dmz.sleep()
>
>   6.类
>     静态属性  属性
>     动态的行为  方法



#### 类与对象的创建

![image-20230214154740913](F:\study\java\photo\image-20230214154740913.png)



![image-20230214155100053](F:\study\java\photo\image-20230214155100053.png)



```java
package com.dmz.oop.Demo02;

//学生类
public class Student {

    //属性：字段
    String name;
    int age;

    //方法
    public void study(){
        System.out.println(this.name+"在学习");
    }
}
```



```java
package com.dmz.oop.Demo02;


//一个项目应该只存在一个main方法
public class Application {
    public static void main(String[] args) {

        //类：抽象的，实列化
        //类实列化后返回一个自己的对象
        //student对象就是一个Student类的具体实列

        Student xiaoming = new Student();
        Student xh = new Student();


        xiaoming.name = "小明";
        xiaoming.age = 3;

        System.out.println(xiaoming.age);
        System.out.println(xiaoming.name);

        xh.name = "小红";
        xh.age = 3;


        System.out.println(xh.age);
        System.out.println(xh.name);

    }
}
```



#### 构造器详解

```java
public class Person {
    //一个类即使什么都不写，它也会存在一个方法
    //显示的定义构造器
    String name;
    int age;
    
    
    //实列初始化
    //1.使用new关键字，必须要有构造器
    //2.用来初始化值
    public Person(){
        this.name = "dmz";
    }
    
    //有参构造:一旦定义了有参构造，无参构造就必须显示定义
    public Person(String name){
        this.name = name;
    }
    
    //alt+insert  一键生成


    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
}

/*
构造器：
       1. 和类名相同
       2.没有返回值
    作用：
        1.new 本质在调用构造方法
        2.初始化对象的值
     注意点：
        1.定义有参构造之后，如果想使用无参构造，显示的定义一个无参的构造
 */
```



```java
public static void main(String[] args) {

    //new 实列化了一个对象
    Person person =  new Person("dmz",23);

    System.out.println(person.name);
}
```



#### 创建对象内存分析

![image-20230215165902530](F:\study\java\photo\image-20230215165902530.png)







```java
public static void main(String[] args) {

    Pet dog  = new Pet();
    dog.name = "旺财";
    dog.age = 3;
    dog.shout();

    System.out.println(dog.name);
    System.out.println(dog.age);

    Pet cat = new Pet();
    
}
```



```java
public class Pet {

        String name;
        int age;

        //无参构造
        public void shout(){
            System.out.println("叫了一声");
        };

}
```





#### 封装

封装的意义
1.提高程序的安全性，保护数据
2.隐藏代码的实现细节
3.统一接口
4.系统可维护性增加



```java
public class Application {
    public static void main(String[] args) {
        Student s1 = new Student();

        s1.setName("dmz");

        System.out.println(s1.getName());
        //s1.getName().sout

        s1.setAge(11);

        System.out.println(s1.getAge());
    }
}
```



```java
public class Student {

    //属性私有
    private String name;   //名字
    private String id;     //学号
    private String sex;    //性别
    private int age;       //年龄

    //提供一些可以操作这个属性的方法
    //提供一些public 的 get、set方法

    //get 获得这个数据
    public String getName(){
        return this.name;
    }

    //set 给这个数据设置值
    public void setName(String name){
        this.name = name;
    }

    public String getId() {
        return id;
    }

    public void setId(String id) {
        this.id = id;
    }

    public String getSex() {
        return sex;
    }

    public void setSex(String sex) {
        this.sex = sex;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        if (age>120 || age<0){
            this.age = 0;
        }else {
            this.age = age;
        }
    }
```





#### 继承



子类继承父类，就会拥有父类的全部方法！

一个儿子只能有一个爸爸，一个爸爸能有多个儿子。



##### this

```java
public class Person /*extends object*/ {
    //public
    //protected
    //default
    //private

    private int money = 10_0000_0000;

    public int getMoney() {
        return money;
    }

    public void setMoney(int money) {
        this.money = money;
    }

    public void say(){
        System.out.println("说了一句话");
        
        
        
    }
```



```java
//学生 is 人  子类
public class Student extends Person{
}
```



```java
public class Application {
    public static void main(String[] args) {

        Student student = new Student();
        student.say();

        System.out.println(student.money);
    }
```



##### super

super注意点：

​		1.super调用 父类构造方法，必须在 构造方法的第一个

​		2.super必须只能出现在 子类的方法 或 构造方法 中

​		3.super和this 不能同时调用构造方法



VS this:

​		代表的对象不同；

​					this: 本身调用者这个对象

​					super: 代表父类对象的应用

​		前提

​					this: 没有继承也可以使用

​					super: 只能在继承条件下才可以使用

​		构造方法

​					this( ); 本类的构造

​					super( );  父类的构造



```java
public class Person /*extends object*/ {

    public Person() {
        System.out.println("Person无参执行了");
    }

    //public
    //protected
    //default
    //private

    protected String name = "dmz";

    public void print(){
        System.out.println("Person");
    }

    }
```



```java
//学生 is 人  子类
public class Student extends Person{

    public Student() {
        //隐藏代码；调用了父类的无参构造
        super();  //调用父类构造器，必须要在子类构造器的第一行

        System.out.println("student无参执行了");
    }

    private String name = "dmm";

    public void print(){
        System.out.println("Student");
    }

    public void test1(){
        print();
        this.print();
        super.print();
    }


    public void test(String name){
        System.out.println(name);  //输出传递给它的参数（邓茂臻）
        System.out.println(this.name);  //输出dmm(类里面的名字）
        System.out.println(super.name);  // 输出dmz(父类里面的名字）
    }
```



```java
public class Application {
    public static void main(String[] args) {

       Student student = new Student();
       //student.test("邓茂臻");

      // student.test1();
```



##### 方法重写



重写：需要有继承关系，子类重写父类的方法！

​	1.方法名必须相同

​	2.参数列表必须相同

​	3.修饰符:范围可以扩大但不能缩小： public>protected>default>private

​	4.抛出异常：范围，可以被缩小，但不能被扩大： ClassNotFoundException --> Exception(大)



重写,子类的方法和父类必须一致，方法体不同！



为什么需要重写：

1.父类的功能，子类不一定要实现，或者不一定要满足。

Alt + Insert ; override





```java
public class B {

    public  void test(){
        System.out.println("B=>test()");
    }
```



```java
//继承
public class A extends B{

    //@Override 重写
    @Override  //注解：有功能的注释
    public void test() {
        System.out.println("A=>test()");  //输出结果A=>test()
    }

    /* public  void test(){
        System.out.println("A=>test()");
    }*/
```



```java
public static void main(String[] args) {

    //静态的方法和非静态的方法区别很大
    //静态方法：方法的调用之和左边，定义的数据类型有关
    //非静态方法：重写

    A a = new  A();
    a.test();//A

    //父类的引用指向了子类
    B b = new A();   //子类重写了父类的方法
    b.test();//B
```



#### 多态



多态注意事项：

1. 多态是方法的多态，属性没有多态

2. 父类和子类，有联系   类型转换异常  ClassCastException

3. 存在条件： 继承关系：方法需要重写，父类的引用指向子类对象   Father f1 = new Son( );

   不能重写的方法

   1.static 方法，属于类，不属于实列

   2.final  常量；

   3，private方法；没办法重写

   

```java
package com.dmz.oop.Demo06;

public class Person {

    public void run(){
        System.out.println("run");
    }
}
```



```java
package com.dmz.oop.Demo06;

public class Student extends Person{

    @Override
    public void run() {
        System.out.println("son");
    }

    public void eat() {
        System.out.println("eat");
    }
}
```



```java
public class Application {
    public static void main(String[] args) {
        //一个对象的实际类型是确定的
        //new Student();
        //new person();

        //可以指向的引用类型不确定:父类的引用指向子类

        //Student 能调用的方法都是自己的或者继承父类的
        Student s1 = new Student();

        //person父类型，可以指向子类，但是不能调用子类独有的方法
        Person s2  = new Student();
        Object s3  = new Student();

        //对象能执行哪些方法主要看对象左边的类型，和右边关系不大
        ((Student)s2).eat();
        s1.eat();
    }
```





##### instanceof和类型转换



1.父类引用指向子类的对象

2.把子类转换为父类，向上转型

3.把父类转换为子类，向下转型：强制转换

4.方便方法的调用，减少重复代码！简介



```java
public static void main(String[] args) {

    
    //Object  > Person > Teacher
    //Object > String
    //Object > Person > Student
    Object object = new Student();

    //System.out.println(X instanceof Y);  能不能编译通过

    System.out.println(object instanceof Student);  //true
    System.out.println(object instanceof Person);   //true
    System.out.println(object instanceof Object);   //true
    System.out.println(object instanceof Teacher);   //false
    System.out.println(object instanceof String);    //false

    System.out.println("============================");

    Person person = new Student();
    System.out.println(person instanceof Student);  //true
    System.out.println(person instanceof Person);   //true
    System.out.println(person instanceof Object);   //true
    System.out.println(person instanceof Teacher);   //false
    //System.out.println(person instanceof String);    //编译器报错

    System.out.println("============================");
    Student student = new Student();
    System.out.println(student instanceof Student);  //true
    System.out.println(student instanceof Person);   //true
    System.out.println(student instanceof Object);   //true
    //System.out.println(student instanceof Teacher);   //编译器报错
    //System.out.println(student instanceof String);    //编译器报错
```



##### static关键字详解



final无法继承类



```java
public class Student {

    private static int age;  //静态变量  多线程
    private double score;    //非静态变量

    public void run(){

    }

    public static void go(){

    }

    public static void main(String[] args) {
            go();
        /* Student s1 = new Student();

        System.out.println(Student.age);
        System.out.println(s1.age);
        System.out.println(s1.score);*/
    }
```



```java
public class Person {
    {//2：赋予初始值
        System.out.println("匿名代码块");//代码块（匿名代码块）
    }

    static {//1   只执行一次
        System.out.println("静态代码块");//静态代码块
    }

    public Person(){//3
        System.out.println("构造代码块");
    }


    public static void main(String[] args) {
        Person person1 = new Person();
        System.out.println("===================");
        Person person2 = new Person();
    }
```



```java
//静态导入包
import static java.lang.Math.random;
import static java.lang.Math.PI;

public class Test {
    public static void main(String[] args) {
        System.out.println(random());
        System.out.println(PI);
```





##### 抽象类



抽象类存在的意义：提高开发效率



```java
//abstract 抽象类： 类：extends: 单继承   （接口可以多继承）
public abstract class Action {
    //约束,有人帮我们实现
    //abstract，抽象方法，只有方法名字，没有方法的实现
    public abstract void doSomething();

    //1.不能new这个抽象类，只能靠子类去实现它：约束！
    //2.抽象类中可以写普通的方法
    //3.抽象方法必须在抽象类中
    //抽象的抽象：约束

}
```



##### 接口





作用：

​	1.约束

​	2.定义一些方法，让不同的人实现~ 10--> 1

​	3.public abstract

​	4.public static final

​	5.接口不能被实列化~，接口中没有构造方法~

​	6.implement可以实现多个接口

​	7.必须要重写接口的方法



```java
//interface 定义的关键字,接口都需要有实现类
public interface UserService {

    //接口中所有定义都是抽象的 public abstract
    void add(String name);
    void delete(String name);
    void update(String name);
    void query(String name);


}
```



```java
//抽象类： extends
//类  可以实现接口 implements 接口
//实现了接口的类，就需要重写接口中的方法
public class UserServiceImpl implements UserService,TimeService{

    //ctrl +i
    @Override
    public void add(String name) {

    }

    @Override
    public void delete(String name) {

    }

    @Override
    public void update(String name) {

    }

    @Override
    public void query(String name) {

    }

    @Override
    public void timer() {

    }
```



```java
public interface TimeService {
    void timer();
}
```







##### 内部类





```java
public class Outer {
    private int id=10;
    public void out(){
        System.out.println("这是外部类的方法");
    }

    class Innner{
        public void in(){
            System.out.println("这是内部类的方法");
        }

        //获得外部类的私有属性
        public void getID(){
            System.out.println(id);
        }

    }
```



```java
public class Application {
    public static void main(String[] args) {
        // new
        Outer outer = new Outer();
        //通过这个外部类来实列化内部类
        Outer.Innner inner = outer.new Innner();
        inner.getID();
    }
```



### 异常



