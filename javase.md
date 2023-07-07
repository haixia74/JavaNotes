

# 注释

java规范的三种注释方式：

单行注释：//

多行注释：/*         */  （多行注释不可以嵌套使用）

文档注释(java特有)：/**         */     (注释内容可以被JDK提供的工具javadoc所解析，生成一套以网页文件形式体现



# 排序 数组和查找

## 数组(array)

### 数组介绍

数组可以存放多个同一类型的数据。数组也是一种数据类型，是引用类型即:数(数据)组(一组)就是一组数据
数组快速入门

![image-20230516172239524](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230516172239524.png)

### 数组的定义

数据类型 数组名[]=new 数据类型[大小]

> int a[]=new int[5];

### 数组的使用

- 动态初始化：先声明数组，再创造数组 

![image-20230517154931629](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230517154931629.png)

- 静态初始化：

![image-20230517155459581](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230517155459581.png)

### 注意事项和细节

- 数组是多个相同类型数据的组合，实现对这些数据的统一管理

- 数组中的元素可以是任何数据类型，包括基本类型和引用类型，但是不能混用

- 默认值数组创建后，如果没有赋值，有int 0, short 0, byte 0, long 0, float 0.0,double 0.0, char \u0000,boolean false,String null 

- 使用数组的步骤

  - 1.声明数组并开辟空间  

  - 2 给数组各个元素赋值 
  - 3 使用数组 

- 数组下标是从0开始的

- 数组下标必须在指定范围内使用，否则报：下标越界异常，比如 int [] arr=new int[5]; 则有效下标为0-4

- 数组属引用类型，数组型数据是对象（`object`)

### 数组赋值机制

1.基本数据类型赋值，这个值就是具体的数据，而且相互不影响。int n1 = 2: int n2 = n1；

2.数组在默认情况下是引用传递，赋的值是地址.

赋值方式为引用赋值，所以`arr2`的变化会影响到 `arr1`

代码arr1 = (1,2,3);

int【】arr2 = arr1;

### 数组添加

> import java.util.Scanner;
> public class demo3 {
>     public static void main(String[] args) {
>         Scanner myScanner=new Scanner(System.*in*);
>         int[] arr = {1, 2, 3};
>         do {
>             int[] arrnew = new int[arr.length + 1];
>             for (int i = 0; i < arr.length; i++) {
>                 arrnew[i] = arr[i];
>             }
>             System.*out*.println("请输入你要添加的元素");
>            int addNum=myScanner.nextInt();
>             arrnew[arrnew.length - 1] = addNum;//把要添加的值赋值给arrnew
>             arr = arrnew;//让arr指向arrnew
>             System.*out*.println("arr扩容后的元素情况");
>             for (int i = 0; i < arr.length; i++) {
>                 System.*out*.println(arr[i] + "\t");
>             }
>             System.*out*.println("是否继续添加 y/n");
>             char key=myScanner.next().charAt(0);
>             if(key=='n'){
>                 break;
>             }
>         }while(true);
>         System.*out*.println("你退出了添加");
>     }
> }

## 排序

### 排序的介绍

排序是将多个数据，依指定的顺序进行排列的过程
排序的分类: 

1.内部排序:指将需要处理的所有数据都加载到内部存储器中进行排序。包括(交换式排序法、选择式排序法和插入式排序法);
        2.外部排序法:数据量过大，无法全部加载到内存中，需要借助外部存储进行排序。包括(合并排序法和直接合并排序法)。

### 冒泡排序法

从下标冒泡排序 (Bubble Sorting) 的基本思想是: 通过对待排序序列从后向前较大的元素开始)，依次比较相邻元素的值，若发现逆序则交换，使值较大的元素逐渐从前移向后部，就象水底下的气泡一样逐渐向上冒。

### 案例

按从小到大的顺序排列

```java
public class bubbleSort {
 public static void main(String[] args) {
     int arr[] = {23, 56, 41, 67, 21};
     int temp = 0;
     for (int i = 0; i < 4; i++) {
         for (int j = 0; j < 4 - i; j++) {
             if (arr[j] > arr[j + 1]) {
                 temp = arr[j];
                 arr[j] = arr[j + 1];
                 arr[j + 1] = temp;
             }
         }
         System.*out*.println("\n第" + (i + 1) + "轮");
         for (int j = 0; j < arr.length; j++) {
             System.*out*.print(arr[j] + "\t");

​            }
​        }
​    }
}
```



## 查找

### 介绍:

在java中，我们常用的查找有两种:

1顺序查找  

2.二分查找[二分法，我们放在算法讲解]
31410
案例演示:有一个数列:白眉鹰王、金毛狮王、紫衫龙王、青翼蝠王猜数游戏:从键盘中任意输入一个名称，判断数列中是否包含此名称[顺序查找] 要求: 如果找到了，就提示找到，并给出下标值。
请对一个有序数组进行二分查找{1.8.10.89.1000,1234》，输入一个数看看该数组是否存在此数，并且求出下标，如果没有就提示"没有这个数”

## 二维数组

如果要访问第（i+1)个一维数组的第j+1个值arr[i][j]

### 二维数组的使用

#### 使用方式1: 动态初始化

语法: 类型[][] [] []数组名=new 类型[大小] [大小]

比如: int a[] []=new int[2] [3]使用演示 



二维数组在内存的存在形式

![image-20230522172148540](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230522172148540.png)

#### 使用方式2: 动态初始化 

先声明: 类型 数组名[] [];

再定义(开辟空间)数组名 = new 类型[大小] [大小]

赋值(有默认值，比如int 类型的就是0)

#### 使用方式3: 动态初始化-列数不确定

![image-20230522173719259](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230522173719259.png)

给每个一维数组开辟空间：

![image-20230522173804429](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230522173804429.png)

使用方式4: 静态初始化
定义 类型 数组名[] [] ={{值1,值2...},{值1,值2..},{值1,值2..}} 

使用即可[ 固定方式访问]

比如：

int[] [] arr={{1,1,1},{2,5,9},{100}};.

### 二维数组的遍历

![image-20230523193217779](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230523193217779.png)

# 面向对象编程（基础部分）

## 类与对象（object）



#### 类和对象的区别和联系

通过上面的案例和讲解我们可以看出：

1)类是抽象的，概念的，代表一类事物，比如人类，猫类..,即它是数据类型.

2)对象是具体的，实际的，代表一个具体事物，即是实例。

3)类是对象的模板，对象是类的一个个体，对应一个实例、

#### 分配机制

![image-20230523171031518](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230523171031518.png)

#### 属性/成员变量

基本介绍

- 从概念或叫法上看：***成员变量=属性=field(字段***）(即或员变量是用来表示属性的，授课中，统一叫属性）
- 属性是类的一个组成部分，一般是基本数据类型，**也可是引用类型**（对象，数组）。比如我们前面定义猫类的int age就是属性



![image-20230523170329765](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230523170329765.png)

**<u>注意事项</u>**

.1)属性的定义语法同变量，示例：**访问修饰符 属性类型属性名；**

2)属性（properties)的定义类型可以为任意类型，包含基本类型或引用类型

3)属性如果不赋值，有默认值，规则和数组一致。

#### 如何创建对象

- 1.先声明再创建

Cat cat;//声明对象 cat

cat=new Cat();//创建

- 2.直接创建

  Cat cat = new Cat();



#### 如何访问属性

√基本语法

**对象名.属性名；**

案例演示赋值和输出

cat.name;

cat.age;

cat.color;

#### 类和对象的内存分配机制（重要）



![image-20230523172522199](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230523172522199.png)

### 类的定义

![image-20230523202949013](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230523202949013.png)







# 成员方法（method)

## 基本介绍

在某些情况下，我们要需要定义成员方法（简称方法）。比如人类：除了有一些属性外（年龄，姓名..),我们人类还有一些行为比如：可以说话、跑步...通过学习，还可以做算术题。这时就要用成员方法才能完成。现在要求对Person类完善。



### ·成员方法（方法）的定义

访问修饰符 返回数据类型 方法名（形参列表..) //方法体语句；

return 返回值；

1.形参列表：表示成员方法输入cal(int n),getSum(int num1,int num2)

2.返回数据类型：表示成员方法输出，void表示没有返回值

3.方法主体：表示为了实现某一功能代码块

4.return 语句不是必须的。

### **代码演示**

```java
public class Method1 {
    public static void main(String[] args){
//先创建对象，然后调用方法即可
        Person p1 = new Person();
        p1.speak();//调用方法
        p1.cal2(5);
        int returnRes = p1.getSum(10,20);
       System.out.println("getSum方法返回的值=" + returnRes);
    }
}
class Person {
    String name;
    int age;

    //public代表方法是公开的，void代表方法没有返回值，
    //speak（）：speak是方法名，（）形参列表
    //{} 方法体，可以写我们要执行的代码
    public void speak() {
        System.out.println("我是一个好人");

    }

   public void cal2(int n){
    int res = 0;
    for(int i = 1;i<= n;i++){
        res += i;
    }
        System.out.println("cal2方法 计算结果为" + res);

    }
    //int:表示方法执行后，返回一个int值
    public int getSum(int num1,int num2){
        int res = num1 + num2;
        return res;
    }
}
```

### 方法的调用机制

![image-20230523193012529](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230523193012529.png)

### 注意事项和细节

- 访问修饰符（作用是控制 方法使用的范围）

- 如果不写默认访问，[有四种：**<u>public,protected,默认，private</u>**],具体在后面说

- 返回数据类型一个方法最多有一个返回值[思考，如何返回多个结果返回数组]

- 返回类型可以为任意类型，包含**基本类型或引用类型**（数组，对象）

- 如果**方法要求有返回数据类型，则方法体中最后的执行语句必须为return值**；而且要求返回值类型必须和return的值类型一致或兼容，如果方法是void,则方法体中可以没有return语句，或者只写return;方法名

- 遵循驼峰命名法，最好见名知义，表达出该功能的意思即可，比如 得到两个数的和getSum,开发中按照规范

##### **形参列表**

- 1.一个方法可以有0个参数，也可以有多个参数，中间用逗号隔开，比如**getSum(int n1,int n2)**

- 2.参数类型可以为任意类型，包含基本类型或引用类型，比如**printArr(int [] [] map).**

- 3.调用带参数的方法时，一定对应着参数列表传入相同类型或兼容类型的参数！【getSum】 

- 4.方法定义时的参数称为形式参数，简称形参；方法调用时的参数称为实际参数，简称实参，**实参和形参的类型要一致或兼容、个数、顺序必须一致！**[演示]
- 方法体里面写完成功能的具体的语句，可以为输入、输出、变量、运算、分支、循环、方法调用，但里面不能再定义方法！即：**方法不能嵌套定义。**



#### 方法调用

方法调用细节说明

- 1.同一个类中的方法调用：直接调用即可。比如print(参数）;案例演示：A类sayOk调用print()

- 2.<u>跨类</u>中的方法A类调用B类方法：需要**通过对象名调用。**比如对象名方法名（参数）;案例演示：B类 sayHello调用print

## 重载（overload）



### **基本介绍**

java中允许同一个类中，多个同名方法的存在，但要求形参列表不一致

比如：System.out.println();out是PrintStream类型

### **重载的好处**

1)减轻了起名的麻烦

2)减轻了记名的麻烦

![image-20230525170143465](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230525170143465.png)



### ·注意事项和使用细节·

- 1)方法名：必须相同

- 2)形参列表：必须不同（参数类型或个数或顺序，至少有一样不同，参数名无要求）

- 3)返回类型：无要求

# 可变参数

## **·基本概念**

java允许将同一个类中多个同名同功能但参数个数不同的方法，封装成一个方法。

## **·基本语法·**

访问修饰符 返回类型 方法名（数据类型...形参名）{    }

## 注意事项和使用细节

1)可变参数的实参可以为0个或任意多个。

2)可变参数的实参可以为数组。

3)可变参数的本质就是数组

.4)可变参数可以和普通类型的参数一起放在形参列表，但必须保证可变参数在最后

5)一个形参列表中只**能出现一个可变参数**

![image-20230525194822435](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230525194822435.png)

## 代码演示



`/*有三个方法，分别实现返回姓名和两巾课成绩（总分）,`

`返回姓名和三巾课成绩（总分）,返回姓名和五门课成绩（总分）。`

`封装成一个可变参数的方法*/`

`public class VarParametercise {`

​    `public static void main(String[] args){`
​        `C t1=new C();`
​        `System.*out*.println( t1.showScore("wang",46,56,78,99));`

​    `}`
`}`

`class C{`
    `public String showScore(String name,double...scores){`
       `double totalScore = 0;`
       `for(int i = 0;i < scores.length;i++){`
           `totalScore += scores[i];`
       `}`
`return name + "有“ + score.length + 门课的成绩总分为=" + totalScore ;`
    `}`
`}`

![image-20230527152930446](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230527152930446.png)

# 作用域（Scope)



## 基本使用

- 在java编程中，主要的变量就是**属性（成员变量）和局部变量**。-

- 2.我们说的局部变量一般是指在成员方法中定义的变量。【举例Cat类：cry】

- 3.java中作用域的分类

  - 全局变量：也就是属性，作用域为整个类体Cat类：cry eat等方法使用属性![image-20230525195510941](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230525195510941.png)

  - 局部变量：也就是除了属性之外的其他变量，作用域为定义它的代码块中！

  - ![image-20230525195419412](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230525195419412.png)

    4.**全局变量可以不赋值，直接使用**，因为有默认值![image-20230525195847786](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230525195847786.png)，**局部变量必须赋值后，才能使用**，因为没有默认值。[举例]

### 注意事项和细节使用

 1.属性和局部变量可以重名，访问时遵循就近原则。

2.在同一个作用域中，比如在同一个成员方法中，两个局部变量，不能重名。[举例]。

3.属性生命周期较长，伴随着对象的创建而创建，伴随着对象的死亡而死亡。局部变量，生命周期较短，伴随着它的代码块的执行而创建，伴随着代码块的结束而死亡。即在一次方法调用过程中。

4.作用域范围不同

全局变量/属性：**可以被本类使用，或其他类使用**（通过对象调用）

局部变量：只能在本类中对应的方法中使用

5.修饰符不同

全局变量/属性可以加修饰符![image-20230525202053292](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230525202053292.png)

 局部变量不可以加修饰符





# 构造方法/构造器

·看一个需求我们来看一个需求：前面我们在创建人类的对象时，是先把一个对象创建好后，再给他的年龄和姓名属性赋值，如果现在我要求，在创建人类的对象时，就**直接指定这个对象的年龄和姓名**，该怎么做？这时就可以使用构造器。

## **基本介绍**

构造方法又叫构造器（constructor),是类的一种特殊的方法，它的主要作用是**<u>完成对新对象的初始化</u>**。

## ·基本语法·

[修饰符]方法名（形参列表）{方法体；}

## 注意事项和使用细节

1.一个类可以定义多个不同的构造器，即**构造器重载**

比如：我们可以再给Person类定义一个构造器，用来创建对象的时候，只指定人名不需要指定年龄·<img src="C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230525204358694.png" alt="image-20230525204358694" style="zoom:33%;" />

2.构造器名和类名要相同

3.构造器没有返回值

4.**构造器是完成对象的初始化**，并不是创建对象

5.在创建对象时，**系统自动的调用**该类的构造方法

6.构造器的修饰符可以默认，也可以是public protected private

7.方法名和类名字必须一样

8..如果程序员没有定义构造器，**系统会自动给类生成一个默认无参构造方法**(也叫默认构造方法

9.一旦**定义了自己的构造器，默认的构造器就覆盖了**，就不能再使用默认的无参构造器，除非显式的定义一下，即：Person（）{}



# this



## **·this的注意事项和使用细节**

1.this关键字可以用来访问本类的属性、方法、构造器

2.this用于区分当前类的属性和局部变量

3.访问成员方法的语法：**this.方法名（参数列表）;**

4.访问构造器语法：this(参数列表）;**注意只能在构造器中使用**

5.this不能在类定义的外部使用，只能在类定义的方法中使用。



**<u>this小结：简单的说，哪个对象调用，this就代表哪个对象</u>**



![image-20230527153203443](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230527153203443.png)

# 面向对象编程（中级部分）



<img src="C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230527153433374.png" alt="image-20230527153433374" style="zoom:33%;" />



## 快捷键

- 显示所有快捷键的快捷键：ctrl + j

- 生成 while ：itit + 回车

- 删除行：<u>ctrl + Y</u>

- 复制当前行： ctrl + d
- 补全代码：Alt + /

- 多行注销：ctrl  + shift + /

- 运行： Alt + A
- 将光标放在一个方法上，输入ctrl+B,可以**定位到方法** [学继承后，非常有用]
- 添加注释：ctrl + /

- 自动的分配变量名，通过在后面加.var
  - ![image-20230527172620283](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230527172620283.png)
  - 就变成![image-20230527172653899](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230527172653899.png)
- 生成**构造器-**快捷键：Alt + insert
- 查看一个类的层级关系： ctrl + H
  - ![image-20230527172029904](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230527172029904.png)
  - 把鼠标停在Person上 输入快捷键，即可显示

### **自动导入：**

**先输入：**

**![image-20230527170231378](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230527170231378.png)**

**鼠标停在红色Scanner出**

**输入快捷键  <u>Alt + enter</u>**

- 快速格式化代码：ctrl + Alt + L

## 包

### 包的三大作用

1.区分相同名字的类

2.当类很多时，可以很好的管理类

3.控制访问范围·

包基本语法**package com.hspedu;**

### 说明：

1. package 关键字，表示打包
2. .2.com.hspedu:表示包名

### ·包的本质分析（原理）![image-20230528162115088](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230528162115088.png)

实际上就是**<u>创建不同的文件夹</u>**来保存类文件，画出示意图。

### 包的命名

![image-20230528163519736](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230528163519736.png)

![image-20230528163712738](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230528163712738.png)



### ·注意事项和使用细节

1. package 的作用是声明当前类所在的包，**需要放在类的最上面**，**一个类中最多只有一句package**

   ![image-20230529171819496](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230529171819496.png)

2. import指令 位置放在package的下面，在类定义前面，可以有多句且没有顺序要求。

## 访问修饰符

### ·基本介绍

java提供四种访问控制修饰符号控制方法和属性（成员变量）的访问权限（范围）: 

1.公开级别：用**public**修饰，对外公

2.受保护级别：用**protected**修饰，对子类和同一个包中的类公开

3.默认级别：没有修饰符号，向同一个包的类公开.

4.私有级别：用**private**修饰，只有类本身可以访问，不对外公开.

### 4种访问修饰符的访问范围

![image-20230529172237242](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230529172237242.png)

### 使用的注意事项

1)修饰符可以用来修饰类中的**属性，成员方法以及类**

2)**只有<u>默认</u>的和<u>public</u>才能修饰<u>类</u>**！,并且遵循上述访问权限的特点。

3)因为没有学习继承，因此关于在子类中的访问权限

4)**成员方法**的访问规则和**属性**完全一样.//com.hspedu.modifier:

## 封装（重点）

### 封装介绍

封装（**encapsulation**)就是把抽象出的数据[**属性**]和对数据的操作[**方法**]封装在一起，数据被保护在内部，程序的其它部分只有通过被授权的操作[方法],才能对数据进行操作。

![image-20230529175427471](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230529175427471.png)

### 封装的理解和好处

1)隐藏实现细节：

方法（连接数据库）&lt;--调用（传入参数.)

2)可以对数据进行验证，保证安全合理

  

### 封装的实现步骤（三步）

1)将属性进行私有化private 【不能直接修改属性】

2)提供一个公共的（public)set方法，用于对属性判断并赋值public void setXxx(类型 参数名）///Xxx 表示某个属性//加入数据验证的业务逻辑属性=参数名；

3)提供一个公共的get方法，用于获取属性的值public XX getXxx0{//权限判断return XX;

## 继承

### 继承基本介绍

继承可以解决代码复用，当多个类存在相同的属性（变量）和方法时，可以从这些类中抽出父类，在父类中定义这些相同的属性和方法，所有的子类不需要重新定义这些属性和方法，只需要通过extends来声明继承父类即可。

### 继承的基本语法

class 子类 extends 父类{}

- 子类会自动拥有父类定义的属性和方法
- 父类又叫 超类，基类。
- 子类又叫派生类。



### 原理图 

![image-20230530173355044](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230530173355044.png)

### 继承给编程带来的便利

- 代码的复用性提高了

- 代码的扩展性和维护性提高了

  ### 细节

  - 1.子类继承了所有的属性和方法，非私有的属性和方法可以直接访问，但是私有属性和方不能在子类直接访问，要通过公共的方法去访问

  ![image-20230530192413886](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230530192413886.png)

![image-20230530192506683](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230530192506683.png)

- 2.子类必须调用父类的构造器，完成父类的初始化

- 3.当创建子类对象时，不管使用子类的哪个构造器，默认情况下总会调用父类的无参构造去，**如果父类没有提供无参构造器，则必须在子类的构造器中用super去指定使用父类的哪个构造器完成对父类的初始化工作**，否则，编译不会通过

![image-20230530201513385](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230530201513385.png)

- 4.如果希望指定调用父类的某个构造器，则显示的调用一下：super（参数列表）

![image-20230530202930259](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230530202930259.png)

- 5.super在使用时，需要放在构造器的第一行。
- 6.super()和this() 都只能放在构造器第一行，因此这两个方法不能共存在一个构造器。
- 7.java所有类都是Object类的子类，Object是![image-20230530205753202](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230530205753202.png)
- 8.父类构造器的调用不限于直接父类，将一直往上追溯到Object类（顶级父类）
- 9.子类最多继承一个父类（指直接继承），即java中是单继承机制。
- 10.不能滥用继承，子类和父类之间必须满足is-a的逻辑关系![image-20230530210426996](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230530210426996.png)



继承的本质分析（重要）

![image-20230531155832684](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230531155832684.png)

## super关键字

### 基本介绍

super代表父类的引用，用于访问父类的属性，方法，构造器

### 基本语法



- 访问父类的<u>属性</u>，但不能访问父类的Private属性
  - **super.属性名；**![image-20230531173750295](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230531173750295.png)

- 访问父类的<u>方法</u>，不能访问父类的private方法
  - **super.方法名（参数列表）;**

- 访问父类的<u>构造器</u>：
  - **super（参数列表）**；只能放在构造器第一句，只能出现一句。

![image-20230531173807219](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230531173842732.png)



### super给编程带来的便利

1.调用父类构造器的好处（分工明确，父类属性由父类初始化，子类属性由子类初始化）。

2.当子类中有和父类中的成员（属性和方法）重名时，为了访问父类的成员，必须通过super。如果没有重名，使用super，this，直接访问是一样的效果。

![image-20230531191203702](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230531191203702.png)

3.super的访问不限于直接父类，如果爷爷类和本类中有同名的成员，也可以使用super去访问爷爷类的成员；如果多个基类中都有同名的成员，使用super访问遵循就近原则。A->B->C

![image-20230531191819235](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230531191819235.png)

### super和this的比较

![image-20230531192406879](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230531192406879.png)

## 方法重写/覆盖（override)

### 基本介绍

方法重写（覆盖）就是子类有一个方法和父类的某个方法的名称，返回类型，参数一样，那么我们就说子类的这个方法覆盖了父类的那个方法

### 注意事项和使用细节

1.子类的方法的**形参列表，方法名称**，要和父类方法的参数，方法名称完全一样。

2.子类方法的返回类型和父类方法返回类型一样，或者是**父类返回类型的子类**

比如 父类 返回类型是Object，子类方法返回类型是String

![image-20230531200421842](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230531200421842.png)

3.子类方法不能缩小父类方法的访问权限

public —>protected —>默认 —>private

![image-20230531200633814](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230531200633814.png)

### **方法重载**和**方法重写**的比较

![image-20230531201007615](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230531201007615.png)

## 多态

### 多【多种】态【状态】基本介绍

方法或对象具有多种形态。是面向对象的第三大特征，多肽建立在封装和继承基础上的。

多态的具体表现

1.**方法**的多态

重写和重载体现多态

![image-20230531210842493](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230531210842493.png)

![image-20230531210906932](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230531210906932.png)

![image-20230531210916613](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230531210916613.png)

2.**对象**的多态

- 一个对象的编译类型和运行类型可以不一致

- 编译类型在定义对象时，就确定了，不能改变

- 运行类型是可以改变的

- 编译类型看定义时 = 号的左边，运行类型看 = 号右边

  ### 多态的注意事项

  多态的前提是：两个对象（类）存在继承关系

  #### 多态的向上转型

  1.本质：父类的引用指向了子类的对象

  2.语法：父类类型   引用名 = new 子类类型（）；

  3.特点：编译类型看左边，运行类型看右边。

  可以调用父类中的所有成员（需遵守访问权限），**不能调用子类**中的特有成员。

![image-20230601170927116](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230601170927116.png)



####  多态的向下转型

1.语法：子类类型    引用名 = （子类类型）父类引用；

2.只能强转父类的引用，不能强转父类的对象

3.要求父类的引用必须指向的是当前目标类型的对象

4.可以调用子类类型中的所有成员

 

![image-20230601192507143](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230601192507143.png)



### 细节

- 属性没有重写之说，属性的值看编译类型

![image-20230601200252863](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230601200252863.png)

- **instanceOf**比较操作符，用于判断对象的类型是否为某某类型或某某类型的子类型

![image-20230601201237493](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230601201237493.png)![image-20230601201335743](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230601201335743.png)

### java的动态绑定机制（重点）

- 当调用**对象方法**时，该方法会和**该对象的内存地址/运行类型**绑定
- 当调用**对象属性**时，**没有动态绑定机制**，哪里声明哪里使用

### 多态的应用

1.多态数组

> `public class Main {`
>     `public static void main(String[] args) {`
>         `Person[] persons = new Person[5];`
>         `persons[0] = new Person("jack",18);`
>         `persons[1] = new Student("jack",18,100);`
>         `persons[2] = new Student("jk",18,93);`
>         `persons[3] = new Teacher("king",43,30000);`
>         `persons[4] = new Teacher("sasf",73,25000);`
>         `for(int i = 0;i<persons.length;i++) {`
>             `System.*out*.println(persons[i].say());`
>             `if (persons[i] instanceof Student) {`
>                 `((Student) persons[i]).Study();`
>             `} else if (persons[i] instanceof Teacher) {`
>                 `((Teacher) persons[i]).Teach();`
>             `} else if (persons[i] instanceof Person) {`
>             `} else {`
>                 `System.*out*.println("你的输出有误");`
>             `}`
>         `}`
>
> ​    `}`
> `}`

2.多态参数

方法定义的形参类型为父类类型,实参类型允许为子类类型

![image-20230602160011769](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230602160011769.png)

## Object



![image-20230602160246334](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230602160246334.png)

![image-20230602160526309](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230602160526309.png)

### equals方法

==是一个比较运算符

- ==：既可以判断基本类型，又可以判断引用类型

- ==：如果判断基本类型，判断的是值是否相等。

- ==：如果判断引用类型，判断的是地址是否相等，即判定是不是同一个对象

  equals：是Object类中的方法，只能判断引用类型

  默认判断的是地址否是否相等，子类中往往重写该方法，用于判断内容是否相等。

![image-20230602165901129](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230602165901129.png)

### hashCode方法

- 提高具有哈希结构的容器的效率
- 两个引用，如果指向的是同一个对象，则哈希值肯定是一样的
- 两个引用，如果指向的是不同对象，则哈希值是不一样的
- 哈希值主要根据地址号来的，不能完全将哈希值等价于地址

![image-20230602175017311](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230602175017311.png)

![image-20230602174946286](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230602174946286.png)

### toString方法

#### 基本介绍

- 默认返回：全类名 + @ + 哈希值的十六进制，

​      子类往往重写toString方法，用于返回对象的属性信息

![image-20230602193052586](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230602193052586.png)

- 重写toString方法，打印对象或拼接对象时，都会自动调用该对象的toString形式

![image-20230602191845554](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230602191845554.png)

![image-20230602191925784](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230602191925784.png)

- 当直接输出一个对象时，toString方法会被默认的调用，

- 比如 System.out.println(monster);  就会默认调用monster.toString()

  ![image-20230602192821084](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230602192821084.png)

### finalize方法

- 当对象被回收时，系统自动调用该对象的finalize方法，子类可以重写该方法，做一些释放资源的操作、
- 什么时候被回收：当某个对象没有任何引用时，则jvm就认为这个对象是个垃圾对象，就会使用垃圾回收机制来销毁对象，在销毁对象前，会调用finalize方法
- 垃圾回收机制的调用，是由系统来决定，也可以通过System.gc()主动触发垃圾回收机制

![image-20230602195850675](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230602195850675.png)

## 断点调试（debug)

### 一个实际需求

1.在开发中，新手程序员在查找错误时，这时老程序员就会温馨提示，可以**用断点调试一步一步的看源码执行的过程，从而发现错误所在**。 

2.重要提示：在断点调试过程中，是**运行状态**，是以对象的运行类型来执行的。

### 断点调试介绍

- 断点调试是指程序的某一行设置一个断点，调试时，程序运行到这一步就会停住，然后你可以一步步往下调试，调试过程中可以看各个变量当前的值，出错的话，调试到出错的代码行就显示错误，停下。进行分析从而找到这个bug
- 断点调试是程序员必须掌握的技能。
- 断点调试也能帮助我们查看java底层源代码的执行过程，提高程序员的java水平

### 断点调试的快捷键

F7（跳入）

F8（跳过）

shift + F8(跳出)

F9(resume, 执行到下一个断点)

shift + F8（跳出方法）

![image-20230602200353709](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230602200353709.png)

# 面向对象（高级部分）

## 类变量和类方法

### 什么是类变量

类变量也叫静态变量/静态属性，是该类的所有对象共享的变量，任何一个该类的对象去访问它时，取到的都是相同的值，同样任何一个该类的对象去修改它时，修改的也是同一个变量。

### 如何定义类变量

定义语法：

访问修饰符 static 数据类型 变量名；【推荐】

static 访问修饰符 数据类型 变量名；

![image-20230703093500805](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230703093500805.png)

### 如何访问类变量

类名.类变量名

或者  对象名.类变量名

### 细节

1.什么时候需要用类变量

当我们需要让某个类的所有对象都共享一个变量时，就可以考虑使用类变量（静态变量）：比如：定义学生类，统计所有学生共交多少钱时。

2.类变量与实例变量（普通属性）区别

类变量是该类所有对象共享的，而实例变量是每个对象独享的。

3.加上static称为类变量或者静态变量，否则称为实例变量/普通变量/非静态变量

4.实例变量不能通过 类名.类变量名 方式访问。

5.类变量是在类加载时就初始化了，也就是说，即使你没有创造对象，只要类加载了，就可以使用类变量了。

6.

### 代码示例引入

![image-20230703091147351](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230703091147351.png)

![image-20230703091238083](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230703091238083.png)

此时child1.count，child2.count，child3.count指向同一个数据空间，因此和Child.count相同，都是3.

### 类方法基本介绍

类方法也叫静态方法。

形式如下：

访问修饰符 static 数据返回类型 方法名（）{}【推荐】

static 访问修饰符 数据返回类型 方法名（）{}

### 类方法调用

**使用方式**：

类名.类方法名   

或者  对象名.类方法名

（前提是 满足访问修饰符的访问权限和范围）

![image-20230703101340838](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230703101340838.png)

### 类方法的经典使用场景

当方法中不涉及任何和对象相关的成员，则可以将方法设计成静态方法，提高开发效率。

在程序员实际开发，往往会将一些通用的方法，设计成静态方法，这样我们不需要创建对象就可以使用了，比如打印一维数组，冒泡排序，完成某个计算任务。

### 细节

1.类方法和普通方法都是随着类的加载而加载，将结构信息存储在方法区：

类方法中无this的参数

普通方法隐含this的参数

2.类方法可以通过类名调用，也可以通过对象名调用。

3.普通方法和对象有关，需要通过对象名调用，比如对象名.方法名（参数），不能通过类名调用。

4.类方法中不允许使用和对象有关的关键字，比如this和super。普通方法（成员方法）可以。

5.**类方法（静态方法）中只能访问静态变量或静态方法**

6.**普通成员方法，既可以访问普通方法（变量），也可以访问静态方法（变量)**



### 小结

- 静态方法，只能访问静态成员
- 非静态方法，可以访问所有成员
- 在编写代码时，仍然要遵守访问权限规则

## 理解main方法语法

### 深入理解main方法

解释main方法的形式：public static void main（String【】 args){}

- java虚拟机需要调用类main（）方法，所以该方法的访问权限必须是public

- java虚拟机在执行main（）方法时不必创建对象，所以该方法必须是static

- 该方法接收String类型的数组参数，该数组保存执行java命令时传递给所运行的类的参数

  ![image-20230703151240596](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230703151240596.png)

![image-20230703151344435](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230703151344435.png)

### 特别提醒

1.在main（）方法中，我们可以直接调用main方法所在类的静态方法或静态属性。

2.但是，不能直接访问该类中的非静态成员，必须创建该类的一个实例对象后，才能通过这个对象去访问类中的非静态成员。

## 代码块

### 基本介绍

代码块又称为初始化块，属于类中的成员【即 是类的一部分】，类似于方法，将逻辑语句封装在方法体中，通过{}包围起来。

但和方法不同，**没有方法名，没有返回，没有参数，只有方法体**，而且不用通过对象或类显示调用，而是加载类时，或创建对象时隐式调用。

### 基本语法

[修饰符]{

代码

}；

### 注意

1.修饰符 可写可不写，要写的话，也只能是**static**

2.代码块分为两类，使用static修饰符的叫**静态代码块**，没有static修饰的，叫**普通代码块**。

3.逻辑语句可以为任何逻辑语句（输入，输出，方法调用，循环，判断等）

4.**；**号可以写上，也可以省略。

### 代码块的好处

1.相当于另一种形式的构造器（对构造器的补充机制），可以做初始化的操作

2.如果多个构造器中都有重复的语句，可以抽取到初始化块中，提高代码的重用性

### 细节

1.static代码块也叫静态代码块，作用就是对类进行初始化，而且它随着**类的加载**而执行，并且只执行一次。如果是普通代码块，每创建一个对象，就执行。

2.类什么时候被加载【重点背下来】

- 创建对象实例时（new）

  ![image-20230703154314096](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230703154314096.png)

- 创建子类对象实例，父类也会被加载

  ![image-20230703154932089](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230703154932089.png)

  ![image-20230703154542465](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230703154542465.png)

- 使用类的静态成员时（静态属性 静态方法）

![image-20230703155134784](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230703155134784.png)

![image-20230703155057700](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230703155057700.png)

3.**普通代码块**，在创建对象示例时，会被隐式调用。

被创建一次，就会调用一次。

如果只是使用类的静态成员时，普通代码块并不会执行。

**4**.创建一个对象时，在一个类调用顺序是：(重点，难点）：

（1）调用静态代码块和静态属性初始化（注意：静态代码块和静态属性初始化调用的优先级一样，如果有多个静态代码块和多个静态变量初始化，则按他们定义的顺序调用）![image-20230703164220411](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230703164220411.png)

（2）调用普通代码块和普通属性的初始化（注意：普通代码块和普通属性初始化调用的优先级一样，如果有多个普通代码块和多个普通属性初始化，则按定义顺序调用）![image-20230703164449946](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230703164449946.png)

（3）调用构造方法。

小结：

1.static代码块是类加载时，执行，只会执行一次

2.普通代码块是在创建对象时调用的，创建一次，调用一次

3.类加载的3种情况，需要记住.

**5.**构造器的最前面其实隐含了super（）和 调用普通代码块。

![image-20230703165905708](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230703165905708.png)

**6.**我们看一下创建一个子类时（继承关系）,他们的静态代码块，静态属性初始普通代码块，普通属性初始化，构造方法的调用顺序如下：

①父类的静态代码块和静态属性（优先级一样，按定义顺序执行）

②子类的静态代码块和静态属性（优先级一样，按定义顺序执行）

③父类的普通代码块和普通属性初始化（优先级一样，按定义顺序执行）

④父类的构造方法

⑤子类的普通代码块和普通属性初始化（优先级一样，按定义顺序执行）

⑥子类的构造方法//面试题

![image-20230703204939433](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230703204939433.png)

## Final

### 基本介绍

final 中文意思：最后的。最终的。

final 可以修饰类，属性，方法和局部变量。

在某些情况下，程序员可以有以下需求，就会用到final：

1.当不希望类被继承时，可以用final修饰

![image-20230704084534140](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230704084534140.png)

2.当不希望父类的某个方法被子类覆盖/重写（override）时，可以用final关键字修饰

![image-20230704084752950](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230704084752950.png)

3.当不希望类的某个属性的值被修改，可以用final修饰。

![image-20230704085346662](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230704085346662.png)

![image-20230704085301468](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230704085301468.png)

4.当不希望某个局部变量被修改。可以使用final修饰

###  ![image-20230704085200541](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230704085200541.png)final细节

1.final修饰的属性又叫常量，一般用xx_xx_xx来命名

2.final修饰的属性在定义时，必须赋初值，并且以后不再修改，复制可以在如下位置之一：

（1）定义时：如public final double TAX_RATE = 0.08;

（2）在构造器中

（3）在代码块中

![image-20230704101508035](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230704101508035.png)

3.如果final修饰的属性是**静态**的，则初始化的位置只能是：

（1）定义时

（2）在静态代码块，不能再构造器中赋值。



4.final类不能继承，但是可以实例化对象。

5.如果类不是final类，但是含有final方法，则该方法虽然不能重写，但是可以被继承。

6.一般来说，如果一个类已经是final类了，就没必要再将方法修饰成final方法。

7.final不能修饰构造方法（即构造器）

8.final和static往往搭配使用，效率更高，底层编译器做了优化处理

9.包装类（Integer，Double，float,Boolean等都是final），String也是final类。

## 抽象类

### 抽象类介绍

(1)用abstract关键字来修饰一个**类**时，这个类就叫抽象类

**访问修饰符 abstract 类名{**

**}**

(2)用abstract 关键字来修饰一个**方法**时，这个方法就是抽象方法

访问修饰符 abstract 返回类型 方法名（参数列表）；//没有方法体

(3)抽象类的价值更多作用是在于设计，是设计者设计好后，让子类继承并实现抽象类（）

### 抽象类细节

(1)抽象类不能实例化

(2)**抽象类不一定要包含abstract方法，也就是说，抽象类可以没有abstract方法。**

(3)**一旦包含了abstract方法，则这个类必须声明为abstra**ct。

(4)abstract只能修饰类和方法，不能修饰属性和其他的。

(5)抽象类可以有任意成员【抽象类本质还是类】，比如：非抽象方法，构造器，静态属性等等

(6)抽象方法不能有主体，即不能实现。如图所示![image-20230704152452801](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230704152452801.png)

(7)如果一个类继承了抽象类，则它必须实现抽象类的所有抽象方法，除非它自己也声明为abstract类

(8)抽象方法不能使用**private，final，和static**来修饰，因为这些关键字都是和重写相违背的。

## 接口

### 基本介绍

接口就是给出一些没有实现的方法，封装到一起，到某个类要使用的时候，再根据具体情况把这些方法写出来。

语法：

<u>interface 接口名{</u>

<u>//属性</u>

<u>//方法（**1.抽象方法 2.默认实现方法 3.静态方法**）</u>

<u>}</u>

<u>class 类名 implements 接口{</u>

<u>自己属性；</u>

<u>自己方法；</u>

<u>必须实现的接口的抽象方法</u>

<u>}</u>

### 接口细节

1.接口不能被实例化

2.接口中所有的**方法**是public方法，接口中抽象方法，可以不用abstract 修饰

![image-20230704165546973](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230704165546973.png)

3.一个普通类实现接口，就必须将该接口的所有方法都实现

4.抽象类实现接口，可以不用实现接口的方法

5.一个类同时可以实现多个接口

![image-20230704163913042](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230704163913042.png)

6.接口中的属性，只能是final的，而且是 public static final修饰符。

比如：**int a = 1；实际上是public static final int a = 1**；（必须初始化）

7.接口中属性的访问形式：**接口名.属性名**

8.接中不能继承其他的类，但是可以继承多个别的接口![image-20230704190520589](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230704190520589.png)

![image-20230704161959446](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230704161959446.png)

## 内部类

### 基本介绍

一个类的内部又完整的嵌套了另一个类结构。被嵌套的类称为内部类（inner class），嵌套其他类的类称为外部类（outer class）。

是类的五大成员之一（**属性，方法，构造器，代码块，内部类**）。

### 基本语法

**class Outer{//外部类**

​     **class Inner{//内部类**

​       **}**

**}**

**class Other{//外部其他类**

**}**

### 内部类的分类

**定义在外部类局部位置上（比如方法内）：**

1.局部内部类（有类名）

2<u>.匿名内部类（没有类名，重点）</u>

**定义在外部类的成员位置上：**

1.成员内部类（没有static修饰）

2.静态内部类（使用static修饰）

### 局部内部类的使用

说明：局部内部类是定义在外部类的局部位置，比如方法体中，并且有类名。

1.可以直接访问外部类的所有成员，包括私有的

2.不能添加访问修饰符，因为它的地位就是一个局部变量。局部变量是不能使用修饰符的。但是**可以使用final修饰**，因为局部变量也可以使用final![image-20230704203510840](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230704203510840.png)

3**.作用域**：仅仅在定义它的方法或代码块中。

4.局部内部类--访问--->外部类的成员【访问方式：直接访问】

5.外部类--访问--->局部内部类成员【访问方式：创建对象，再访问（注意：必须在作用域内）】

6.外部其它类--不能访问---->局部内部类（因为 局部内部类地位是一个局部变量）

7.如果外部类和局部内部类的成员重名时，默认遵循**就近原则**，如果想访问外部类的成员，则可以使用（外部类名.this.成员）去访问

**System.out.println("外部类的n2 = " + 外部类名.this.n2);**

**记住：**

**（1)局部内部类定义在方法中/代码块中**

**（2）作用域在方法体或者代码块中**

**（3）本质仍然是一个类**

### 匿名内部类的使用（重要！！！）

- 本质是类
- 内部类
- 该类没有名字
- 同时还是一个对象

说明：匿名内部类是定义在外部类的局部位置，比如方法体中，并且没有类名

#### 基本语法

**new 类或接口 （参数列表）{**

**类体**

**}；**

#### 细节

1.可以直接访问外部类的所有成员，包括私有的

2.不能添加访问修饰符，因为它的地位就是一个局部变量

3.作用域：仅仅在定义它的方法或代码块中

4.匿名内部类--访问-->外部类成员【访问方式：直接访问】

5.外部其它类--不能访问--->匿名内部类（因为匿名内部类地位是一个局部变量）

6.如果外部类和匿名内部类的成员重名时，匿名内部类访问的话，默认遵循就近原则，如果想访问外部类的成员，则可以使用（外部 类名.this.成员）去访问

### 成员内部类

**说明：成员内部类是定义在外部类的成员位置，并且没有static修饰。**

1.可以直接访问外部类的所有成员，包括私有的

2.可以添加任意访问修饰符（public，protected，默认，private），因为它的地位就是一个成员。

3.作用域：和外部类的其他成员一样，为整个类体

4.成员内部类---访问---->外部类（比如：属性）[访问方式：直接访问](说明）

5.外部类---访问----->内部类（说明）访问方式：创建对象，再访问

6.外部其他类---访问---->成员内部类

7.如果外部类和内部类的成员重名时，内部类访问的话，默认遵循**就近原则**，如果想访问外部类成员，则可以使用**（外部类名.this.成员）**去访问。

### 静态内部类

#### 静态内部类的使用

**说明：静态内部类是定义在外部类的成员位置，并且有static修饰**

1.可以直接访问外部类的所有静态成员，包含私有的，但不能直接访问非静态成员

2.可以添加任意访问修饰符（public、protected、默认、private),因为它的地位就一个成员。

3.作用域：同其他的成员，为整个类体

4.静态内部类--访问-->外部类（比如静态属性）【访问方式：直接访问所有静态成员】

5.外部类--访问-->静态内部类【访问方式：创建对象，再访问】

6.外部其它类--访问-->静态内部类

7.如果外部类和静态内部类的成员重名时，静态内部类访问时，默认遵循就近原则，如果想访问外部类的成员，则可以使用（外部类名.成员）去访问。







# 枚举和注解

## 基本介绍

1.枚举对应英文（enumeration，简写enum）

2.枚举是一组常量的集合

3.枚举属于一种特殊的类，里面只含有一组有限的特定的对象。

## 枚举的两种实现方式

- 自定义类实现枚举
- 使用enum关键字实现枚举

### *自定义类实现枚举

1.不需要提供setXXX方法，因为枚举对象值通常为只读

2.对枚举对象/属性使用**final + static**共同修饰，实现底层优化。

3.枚举对象名通常使用**全部大写**，常量的命名规范

4.枚举对象根据需要，也可以有多个属性

![image-20230705160440738](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230705160440738.png)

#### 代码演示

```java
public class Enumtest1 {
    public static void main(String[] args) {
        System.out.println(Season.AUTUMU);
    }
}
class Season{
    private String name;
    private String des;//描述
    public static final Season SPRING = new Season("春天","温暖");
    public static final Season SUMMER = new Season("夏天","炎热");
    public static final Season AUTUMU = new Season("秋天","凉爽");
    public static final Season WINTER = new Season("冬天","寒冷");

    private Season(String name,String des) {
        this.name = name;
        this.des = des;

    }

    public String getName() {
        return name;
    }

    public String getDes() {
        return des;
    }

    @Override
    public String toString() {
        return "Season{" +
                "name='" + name + '\'' +
                ", des='" + des + '\'' +
                '}';
    }
}
```



#### 小结：

进行自定义类实现枚举，有如下特点：

1)构造器私有化

2)本类内部创建一组对象门

3)对外暴露对象（通过为对象添加public final static修饰符）

4)可以提供get方法，但是不要提供set

### *使用enum关键字实现枚举

#### 代码演示

```java
public class Enumtest1 {
    public static void main(String[] args) {
        System.out.println(Season.AUTUMN);
    }
}
enum Season{

    SPRING("春天","温暖"),SUMMER ("夏天","炎热"),AUTUMN("秋天","凉爽"),WINTER("冬天","寒冷");
    private String name;
    private String des;//描述
    /*public static final Season SPRING = new Season("春天","温暖");
    public static final Season SUMMER = new Season("夏天","炎热");
    public static final Season AUTUMU = new Season("秋天","凉爽");
    public static final Season WINTER = new Season("冬天","寒冷");
*/
    private Season(String name,String des) {
        this.name = name;
        this.des = des;

    }

    public String getName() {
        return name;
    }

    public String getDes() {
        return des;
    }

    @Override
    public String toString() {
        return "Season{" +
                "name='" + name + '\'' +
                ", des='" + des + '\'' +
                '}';
    }
}
```

![image-20230705163014428](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230705163014428.png)

## enum关键字实现枚举注意事项 

1.当我们使用enum关键字开发一个枚举类时，默认会继承Enum类

2.传统的public static final Season2 SPRING=new Season2("春天","温暖");简化成SPRING("春天","温暖")

3.如果使用无参构造器 创建 枚举对象，则**实参列表和小括号**都可以省略·

4.当有多个枚举对象时，使用，间隔，最后有一个分号结尾

5.枚举对象必须放在枚举类的行首.

## enum常用方法应用实例

1.**toString**：Enum类已经重写过了，返回的是当前对象名，子类可以重写该方法，用于返回对象的属性信息

2.**name**：返回当前对象名（常量名），子类中不能重写

3.**ordinal**：返回当前对象的位置号，默认从0开始

4.**values**：返回当前枚举类中所有的常量

5.**valueOf**：将字符串装换成枚举对象，要求字符串必须为已有的常量名，否则或报错。

6.**compareTo**：比较两个枚举常量，比较的就是编号。

## enum实现接口

- 使用enum关键字后，就不能再继承其它类了，因为enum会隐式继承Enum，而java是单继承机制

- 枚举类很普通类一样，可以实现接口，如下形式：

  **enum 类名 implements 接口1，接口2 {}**

  

# Annotation(注解)

## 注解的理解

1.注解（Annotation）也被称为元数据（Metadate），用于修饰解释 包，类，方法，属性，构造器，局部变量等数据信息。

2.和注释一样，注解不影响程序逻辑，但注解可以被编译或运行，相当于嵌入在代码中的补充信息。

3.在JavaSE中，注解的使用目的比较简单，例如标记过时的功能，忽略警告等。

   在JavaEE中注解占据了更重要的角色，例如用来配置应用程序的任何切面，代替java EE旧版中所遗留的繁穴代码和XML配置等。

## 三个基本的Annotation

- @Override ：限定某个方法，是重写父类方法，该注解只能用于方法
- @Deprecated： 用于表达某个程序元素（类，方法等）已过时
- @SuppressWarning：抑制编译器警告

## 基本的Annotation介绍

使用Annotation时要在其前面增加@ 符号，并把该Annotation 当成一个修饰符使用，用于修饰它支持的程序元素

### Override使用说明

1.@override 表示指定重写父类的方法（从编译层面验证），如果父类没有fiy方法，则会报错

2.如果不写@Override注解，而父类仍有public void fly(){},仍然构成重写

3.@Override 只能修饰方法，不能修饰其它类，包，属性等等

4.查看@Override注解源码为@Target（ElementType.METHOD），说明只能修饰方法

5.@Target 是修饰注解的注解，称为元注解

### @Deprecated的说明

1.用于表示某个程度元素（类，方法等）已过时

2.可以修饰方法，类，字段，包，参数 等等

3.@Deprecated的作用可以做到新旧版本的兼容和过度

### @SuppressWarnings注解的案例

说明各种值

1)unchecked 是忽略没有检查的警告

2)rawtypes是忽略没有指定泛型的警告（传参时没有指定泛型的警告错误）

3)unused 是忽略没有使用某个变量的警告错误

4)@SuppressWarnings可以修饰的程序元素为，查看@Target

5)生成@SupperssWarnings时，不用背，直接点击左侧的黄色提示，就可以选择（注意可以指定生成的位置）

## JDK的元Annotation（元注解)

### 元注解的基本介绍

JDK的元Annotation 用于修饰其他Annotation

### 元注解的种类（使用不多，了解，不用深入研究）

1)R**etention**//指定注解的作用范围，三种 SOURCE,CLASS,RUNTIME

2)**Target**//指定注解可以在哪些地方使用

3)**Documented**//指定该注解是否会在javadoc体现)Inherited//子米会继承父类注解

### @retention注解

> 说明：只能用于修饰一个 Annotation 定义，用于指定该 Annotation 可以保留多长时间，@Rentention 包含一个 RetentionPolicy类型的成员变量，使用@Rentention时必须为该value成员变量指定值：
>
> >@Retention的三种值
> >
> >1)**RetentionPolicy.SOURCE**:编译器使用后，直接丢弃这种策略的注释
> >
> >2)**RetentionPolicy.CLASS**:编译器将把注解记录在class文件中.当运行Java程序时，JVM不会保留注解。这是默认值
> >
> >3)**RetentionPolicy.RUNTIME**:编译器将把注解记录在class文件中.当运行韩顺Java程序时，JVM会保留注解，程序可以通过反射获取该注解

### @Documentd注解

@Documented基本说明

@Documented:用于指定被该元 Annotation 修饰的 Annotation 类将被javadoc 工具提取成文档，即在生成文档时，可以看到该注释。

说明：定义为Documented的注解必须设置Retention值为RUNTIME。

### @Traget

#### 基本说明

用于修饰Annotation定义，用于指定被修饰Annotation能用于修饰哪些程序元素，@Traget也包含一个名为value的成员变量

### @Inherited注解

被它修饰的 Annotation 将具有继承性.如果某个类使用了被 @lnherited 修饰的Annotation,则其子类将自动具有该注解

# 异常

## 基本概念

Java语言中，将程序执行中发生的不正常情况称为“异常”。（开发过程中的语法错误和逻辑错误不是异常）

**执行过程中所发生的异常事件可分为两类**

1.Error（错误）：Java虚拟机无法解决的严重错误。如：JVM系统内部错误，资源耗尽等严重错误。

比如：StackOverflowError[栈溢出]和	OOM（out of memeory),Error是严重错误，程序会本崩溃。

2.Exception：其他因编程错误或偶然的外在因素导致的一般性问题，可以使用针对性的代码进行处理，例如空指针访问，试图读取不存在的文件，网络连接中断等等，Exception分文两大类：运行时异常【】和编译时异常【】。

## 注意

- 异常分为两大类，运行时异常和编译时异常。
- 运行异常时，编译器检查不出来。一般是指编译时的逻辑错误，是程序员应该避免其出现的异常。
- 对于运行时异常，可以不做处理，因为这类异常很普遍，若全处理可能会对程序可读性和运行效率产生影响。

## 常见的运行时异常包括

- NullPointerException空指针异常（当应用程序试图在需要对象的地方使用null时，抛出该异常）
- ArithmeticException数字运算异常（当出现异常的运算条件时，抛出此异常）
- ArrayIndexOutOfBoundsException数字下标越界异常（用非法索引访问数组时抛出的异常）
- ClassCastException类型转换异常（当试图将对象强制转换为不是实例的子类时，抛出该异常）
- NumberFromatException数字格式不正确异常（当应用程序试图将字符串转换成一种数值类型，但该字符串不能转换为适当格式时，抛出该异常）

## ·编译异常介绍

编译异常是指在编译期间，就必须处理的异常，否则代码不能通过编译。

## 常见的编译异常 

- SQLException//操作数据库时，查询表可能发生异常

- IOException//操作文件时，发生的异常

- FileNotFoundException//当操作一个不存在的文件时，发生异常

- ClassNotFoundException//加载类，而该类不存在时，异常

- EOFException//操作文件，到文件未尾，发生异常

- lllegalArguementException//参数异常

## 异常处理

### 基本介绍

异常处理就是当异常发生时，对异常处理的方式。

### 异常处理方式

**1.try-catch-finally**

程序在代码块中捕获发生的异常，自行处理

![image-20230707095852779](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230707095852779.png)

**2.throws**

将发生的异常抛出，交给调用者（方法）来处理，最顶级的处理者就是JVM

t<u>hrows 处理机制图</u>

<u>1.try-catch-finally和throws二选一</u>

<u>2.如果程序员，没有显示是处理异常，默认throws</u>

![image-20230707100313879](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230707100313879.png)

## try-catch异常处理

1.java提供try和catch块来处理异常。try块用于包含可能出错的代码。catch块用于处理try块中发生的异常。可以根据需要在程序中有多个数量的try。。catch块。

2.**基本语法**

try{

//可疑代码

//将异常生成对应的异常对象，传递给catch块

}catch（异常）{

//对异常的处理

}

### 注意事项

- 如果异常发生了，则异常后面的代码不会执行，直接进入到catch块。

- 如果异常没有发生，则顺序执行try的代码块，不会进入到catch。

- 如果希望不管是否发生异常，都执行某段代码（比如关闭连接，释放资源等），则使用如下代码

  **try{**

  **//可疑代码**

  **}catch（异常）{**

  **//...**

  **}finally{**

  **//释放资源等。。**

  **}**

- 可以进行try-finally配合使用，这种用法相当于没有捕获异常，因此程序会直接崩溃。

  **try{**

  **//代码...**

  **}finally{//总是执行**

  **}**

- 可以有多个catch语句，捕获不同的异常（进行不同的业务处理），要求**父类异常在后，子类异常在前**，比如（exception 在后，NullPointerException在前），如果发现异常，只会匹配一个catch，案例演示：

  **try{**

  **}catch（NullPointerException e){**

  **}catch(Exception e){**

  **}finally{**

  **}**

  ## 体系图

  ![image-20230707163141811](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230707163141811.png)

  

### try-catch-finally执行顺序小结

1)如果没有出现异常，则执行try块中所有语句，不执行catch块中语句，如果有finally,最后还需要执行finally里面的语句

2)如果出现异常，则try块中异常发生后，try块剩下的语句不再执行。将执行catch块中的语句，如果有finally,最后还需要执行finally里面的语句！

## 自定义异常

当程序中出现了某些“错误”，但该错误信息并没有在Throwable子类中描述处理，这个时候可以自己设计异常类，用于描述该错误信息。

### 基本步骤

1.定义类：自定义异常类名（程序员自己写）继承Exception或RuntimeException

2.如果继承Exception，属于编译异常。

3.如果继承RuntimeException,属于运行异常（一般来说，继承RuntimeException）

### 代码演示

```java
public class CustomException {
    public static void main(String[] args) {
        int age = 148;
        if(!(age > 18 && age < 120)){
           throw new AgeException("你的年龄不在18--120之间");
        }
        System.out.println("你的年龄范围正常");

    }
}
class AgeException extends RuntimeException{
    public AgeException(String message) {
        super(message);
    }
}
```



## throws

### 基本介绍

1.如果一个方法（中的语句执行时）可能生成某种异常，但是并不能确定如何处理这种异常，则此方法应显示声明抛出异常，表面此方法将不对这些异常进行处理，而由该方法的调用者负责处理。

2.在方法声明中用throws 语句可以声明抛出异常的列表，throws后面的异常类型可以是方法中产生的数据类型，也可以说是它的父类。

### 细节

1)对于**编译**异常，程序中必须处理，比如try-catch或者throws

2)对于**运行**时异常，程序中如果没有处理，默认就是throws的方式处理

3)子类重写父类的方法时，对抛出异常的规定：子类重写的方法，**所抛出的异常类型要么和父类抛出的异常一致，要么为父类抛出的异常的类型的子类型**

4)在throws过程中，如果有方法try-catch,就相当于处理异常，就可以不必throws

### throws与throw对比

![image-20230707153703826](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230707153703826.png)

# 常用类

## 包装类

### 包装类和基本数据类型的装换

- jdk5前的手动装箱和拆箱方式，装箱：基本类型->包装类型，反之，拆箱
- jdk5以后（含jdk5）的自动装箱和拆箱方式
- 自动装箱底层调用的是valueOf方法，比如Integer.valueOf()

### 包装类的分类

1.针对八种数据类型相应的引用类型---包装类

2.有了类的特点，就可以调用类中的方法

![image-20230708084344956](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230708084344956.png)

### 包装类和基本数据类型的相互转换案例

> //手动装箱
>
> int n1 = 100;
>
> Integer integer = new Integer(n1);//方法一
>
> Integer integer2 = new Integer(n1);//方法二
>
> //手动拆箱
>
> int i = integer.intValue();
>
> //jdk5以后，就可以自动装箱和自动装箱
>
> //自动装箱
>
> int n2 = 200;
>
> Integer integer = n2;
>
> //自动拆箱
>
> int n3 = integer;

## String类

### String类的理解和创建对象

1.String对象用于保存字符串，也是一组字符序列

2.字符串常量对象是用双引号括起来的字符序列。例如：“你好”，“12.97”。“boy"等

3.字符串的字符使用UnIcode字符编码，一个字符（不区分字母还是汉字）占两个字节。

4.String类较常用类构造方法（其它看手册）：

- String s1 = new String();
- String s2 = new String(String original);
- String s3 = new String(char[] a);
- String s4 = new String(char[] a,int startindex,int count)

两种创建String对象的区别

方式一：直接赋值 String s = "hsp";

方式二：调用构造器 String s2 = new String（“hsp");

- 方式一：先从常量池查看是否有“hsp"数据空间，如果有，直接指向；如果没有则重新创建，然后指向。s最终指向的是常量池的空间地址
- 方式二：先在堆中创建空间，里面维护了value属性，指向常量池的hsp空间。如果常量池没有“hsp",重新创建，如果有，直接通过value指向。最终指向的是堆中的空间地址。

![image-20230708110459916](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230708110459916.png)

### 字符串特性

1.String是一个final类，代表不可变的字符序列

2.字符串是不可变的。一个字符串对象一旦被分配，其内容是不可变的

### String类的常见方法应用实例

- equals：区分大小写，判断内容是否相等
- equalslgnoreCase:忽略大小写的判断内容是否相等
- length：获取字符的个数，字符串的长度
- indexOf：获取字符在字符串中第一次出现的索引，索引从0开始，如果找不到，返回-1
- lastIndexOf：获取字符在字符串中最后一次出现的索引，索引从0开始，如果找不到，返回-1
- substring:截取指定范围的字串
- trim：去前后空格
- CharAt:获取某索引处的字符，注意不能使用Str[index]这种方式

- toUpperCase
- toLowerCase
- concat
- replace 替换字符串中的字符

- split分割字符串，对于某些分割字符，我们需要转义比如| \\等

- compareTo//比较两个字符串的大小

- toCharArray//转换成字符数组

- format//格式字符串，%s字符串%c字符%d整型%.2f浮点型.

## StringBuffer类

### 基本介绍

- java.lang.StringBuffer代表可变的字符序列，可以对字符串内容进行增删
- 很多方法和String相同，但StringBuffer是可变长度的。
- StringBuffer是一个容器

- StringBuffer的直接父类是AbstractStringBuilder
- StringBuffer实现了Serializable,即StringBuffer的对象可以串行化
- 在父类中 AbstractStringBuilder 有属性 char[] value,不是final，该value数组存放 字符串内容，引出存放在堆中
- StringBuffer是一个final类，不能被继承

## String VS StringBuffer

1.String保存的是字符串常量，里面的值不能更改，每次String类的更新实际上就是更改地址，效率较低

2.StringBuffer 保存的是字符串变量，里面的值可以更改，每次StringBuffer 的更改实际上可以更新内容，不用每次更新地址，效率较高//char[] value;//这个放在堆

### StringBuffer的构造器

- StringBufffer()   构造一个其中不带字符的字符串缓冲区，其初始化容量为16个字符
- StringBuffer（CharSequence seq)   public java.lang.StringBuilder(CharSequence seq) 构造一个字符串缓冲区，它包含与指定的CharSequence相同字符
- StringBuffer（int capacity） 构造一个不带字符，但具有指定初始化容量的字符串缓冲区，即对char[]大小进行指定
- StringBuffer（String str） 构造一个字符串缓冲区，并将其内容初始化为指定的字符串内容

## StringBuilder类

### 基本介绍

1.一个可变的字符序列。此类提供一个与StringBuffer兼容是ApL，但不保证同步（StringBuilder不是线程安全）。此类被设计用作StringBuffer的一个简单替换，用在字符串缓冲区被单个线程使用的时候，如果可能，建议优先采取该类，因为在大多数实现中，它比StringBuffer要快。

2.在StringBuilder上是主要操作是append 和insert 方法，可重载这些方法，以接收任意类型的数据。

### 细节

1.StringBuilder 继承 AbstractStringBuilder 类

2.实现了Serializable,说明StringBuilder 对象是可以串行化（对象可以网络传输，可以保存到文件）

3.StringBuilder 是final类，不能继承

4.StringBuilder 对象字符序列仍然存放在其父类AbstractStringBuilder的char[] value;因此，字符序列是堆中

5.StringBuilder 的方法，没有做互斥的处理，即没有sycnchronized关键字

## String，StringBuilder，StringBuilder的比较

- StringBuilder 和StringBuffer非常相似，均代表可变的字符序列，而且方法也一样

- String：不可变字符序列，效率低，但是复用率高。

- StringBuffer：可变字符序列，效率较高（增删），线程安全

- StringBuilder ：可变字符序列，效率最高，线程不安全

- String使用注意说明：string s="a";//创建了一个字符串

  s+="b";//实际上原来的"a"字符串对象已经丢弃了，现在又产生了一个字符串s+"b"(也就是"ab")。如果多次执行这些改变串内容的操作，会导致大量副本字符串对象存留在内存中，降低效率。如果这样的操作放到循环中，会极大影响程序的性能=>结论：如果我们对String做大量修改，不要使用String

## String，StringBuilder，StringBuilder的选择

使用的原则，结论：

1.如果字符串存在大量的修改操作，一般使用StringBuffer或StringBuilder

2.如果字符串存在大量的修改操作，并在单线程的情况，使用 StringBuilder

3.如果字符串存在大量的修改操作，并在多线程的情况，使用 StringBuffer

4.如果我们字符串很少修改，被多个对象引用，使用String,比如配置信息等

 5.String Builder 的方法使用和 StringBuffer 一样

## Math类

### 基本介绍

Math类包含用于执行基本数学运算的方法，如初等指数，对数，平方根和三角函数。



### Math常见方法

- abs 绝对值

- pow 求幂

- ceil 向上取整

- floor 向下取整

- round 四舍五入

- sqrt 求开方

- random 求随机数 范围：0-1

  获取a-b之间的一个随机整数a,b 均为整数 

  int num = （int）（a + Math.random()*（b-a+1))

- max求两个数的最大值

- min求两个数的最小值

  # Arrays类

  ## Arrays类常见方法

  Arrays里面包含了一系列静态方法，用于管理或操作数组（比如排序和搜索）

  1.toString 返回数组的字符串形式

  2.sort排序 （自然排序和定制排序）

  ```java
  //冒泡 + 定制排序
  import java.util.Arrays;
  import java.util.Comparator;
  
  public class StringBuffer {
      public static void main(String[] args) {
          int[] arr = {1, 43, 22, 76, 21, 5, 98, 43};
              bubble(arr, new Comparator() {
                  @Override
                  public int compare(Object o1, Object o2) {
                  int i1 =  (Integer)o1;
                  int i2 =  (Integer)o2;
                  return  i1 - i2;
                  }
              });
      }
      public static void bubble(int arr[], Comparator c) {
          int tep = 0;
          for (int i = 0;i < arr.length - 1;i++){
              for (int j = 0;j < arr.length - 1 - i;j++){
                  if(c.compare(arr[j],arr[j + 1] ) > 0){
                      tep = arr[j];
                      arr[j] = arr[j+1];
                      arr[j + 1] = tep;
                  }
  
              }
          }
      }
  }
  ```

  3.binarySearch 通过二分搜索法进行查找，要求必须排好序

  int index = Arrays.binarySearch(arr,3);

  4.copyOf 数组元素的复制

  > System.out.println(Arrays.toString(arr));
  >             int[] integer = Arrays.copyOf(arr,4);
  >             System.out.println(Arrays.toString(integer));

  5.fill数组元素的填充

  ![image-20230710153416041](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230710153416041.png)

![image-20230710153522900](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230710153522900.png)

6.equals比较两个数组元素内容是否完全一致

> boolean equals = Arrays.equals(arr,arr2);

7.asList将一组值，转换成list

List<Integer> asList = Arrays.asList(2,3,4,5,6,1);

System.out.println("asList="+asList);

## System类

System类常见方法

1.exit 退出当前程序

2.arraycopy：复制数组元素，比较适合底层调用，一般使用Arrays.copyOf完成复制数组

int[] src = {1,2,3};

int[] dest = new int[3];

System.array.copy(src,0,dest,0,3);

3.currentTimeMilens:返回当前时间距离1970-1-1的毫秒数

4.gc：运行垃圾回收机制System.gc();

## BigInter类和BigDecimal类

### BigInteger和BigDecimal常见方法

1.add 加

2.subtract 减

3.multiply 乘

4.divide 除

### BigInteger和BigDecimal介绍

应用场景

1.BigInteger适合保存比较大的整型

2.BigDecimal适合保存精度更高的浮点型（小数）

- ![image-20230710192138111](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230710192138111.png)

1.在对 BigInteger进行加减乘除的时候，需要使用对应的方法，不能直接进行+-*

2.BigInteger add = bigInteger.add(bigInteger2);

System.out.printLn(add);

- ![image-20230710192221027](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230710192221027.png)

## 日期类

### 第一代日期类

1.Date：精确到毫秒，代表特定瞬间

2.SimpleDateFormat：格式化和解析日期的类

SimpleDateFormat 格式化和解析日期的具体类。它允许进行格式化（日期->文本），解析（文本->日期）和规范化。

3.表格

![image-20230710194257526](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230710194257526.png)

### 注意

1.创建SimpleDateFormat对象，可以指定相应的格式

2.这里的格式使用的字母是规定好，不能乱改

![image-20230710194926540](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230710194926540.png)

![image-20230710194906046](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230710194906046.png)

### 第二代日期

1.第二代日期类，主要是Calendar类（日历）

2.Calendar类是一个抽象类，它为特定瞬间与一组诸如YEAR ,MONTH,DAY_OF_MONTH,HOUR等日历字段之间的转换提供了一些方法，并为操作日历字段（；例如获得下星期的日期）提供了一些方法。

![image-20230710204602938](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230710204602938.png)

### 示例

![image-20230710202137379](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230710202137379.png)

## 第三代日期类

前面两代日期类的不足分析

JDK 1.0中包含了一个java.util.Date类，但是它的大多数方法已经在JDK 1.1引入Calendar类之后被弃用了。而Calendar也存在问题是：

1)可变性：像日期和时间这样的类应该是不可变的。

2)偏移性：Date中的年份是从1900开始的，而月份都从0开始。

3)格式化：格式化只对Date有用，Calendar则不行。

4)此外，它们也不是线程安全的；不能处理闫秒等（每隔2天，多出1s)。

> //使用now(),返回表示当前日期时间时创建对象
>
> LocalDateTime ldt = LoccalDateTime.now();
>
> System.out.println(ldt);

第三代日期类的更多方法

- LocalDateTime类
- MonthDay类：检查重复事件
- 是否是闰年
- 增加日期的某个部分
- 使用plus方法测试增加时间的某个部分
- 使用minus方法测试查看一年前和一年后的日期

![image-20230710203907406](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230710203907406.png)

# 集合

## 集合的好处

1.可以动态保存任意多个对象，使用比较方便

2.提供了一系列方便的操作对象的方法：add，remove，set，get等

3.使用集合添加，删除新元素的示意代码更加简洁

## collection图

![image-20230711104222733](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230711104222733.png)

## Map图

![image-20230711104616223](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230711104616223.png)

## 注意：

1.集合主要是两组（单列集合，双列集合）

2**.Collection** 接口有两个重要的子接口**List  set**，它们的实现子类都是**单列集合**

3.**Map** 接口的实现子类 是**双列集合**，存放的**K-V**

## Collection接口实现类的特点

1.collection实现子类可以存放多个元素，每个元素可以是Object

2.有些Collection是实现类，可以存放重复的元素，有些不可以

3.有些Collection的实现类，有些是有序的（List），有些不是有序（Set)

4.Collection接口没有直接的实现子类，是通过它的子接口Set和List来实现的

## Collection接口和常用方法

- Iterator对象称为迭代器，主要用于遍历Collection集合中的元素。

- 所有实现了Collection接口的集合类都有一个iterator()方法，用以返回一个实现了Interator接口的对象，即可以返回一个迭代器。

- Iterator仅用于遍历集合，Iterator本身并不存放对象。

- Iterator的结构图：

  ![image-20230711153524935](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230711153524935.png)

提示：在调用Iterator.next()方法之前必须要调用Iterator.hasNext()进行检测。若不调用，且下一条记录无效，直接调用it.next()会抛出NoSuchElementException异常。

### 方法：

1)add:添加单个元素

2)remove:删除指定元素

3)contains:查找元素是否存在

4)size:获取元素个数

5)isEmpty:判断是否为空

6)clear:清空

7)addAll:添加多个元素

8)containsAll:查找多个元素是否都存在

9)removeAll:删除多个元素

10)说明：以ArrayList实现类来演示.

### ·Collection接口遍历对象方式2-for循环增强.

增强for循环，可以代替iterator迭代器，

特点：增强for就是简化版的iterator,本质一样。只能用于遍历集合或数组。

**基本语法：**

for(元素类型元素名：集合名或数组名）{访问元素}

![image-20230711161711383](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230711161711383.png)

## 代码演示

```java
import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;

public class Collection1 {
    public static void main(String[] args) {
        List List = new ArrayList();
        List.add("jack");//添加
        List.add("10");
        List.add(true);
        System.out.println(List);
       // List.remove(0);//删除
      //  System.out.println(List);
        System.out.println(List.contains("jack"));//查找元素10
        System.out.println(List.size());//返回元素个数
        System.out.println(List.isEmpty());//判断是否为空
        List.clear();//清空
        ArrayList List2 = new ArrayList();
        List2.add("红楼梦");
        List2.add("三国演义");
        List.add(List2);//添加多个元素
        List.add("聊斋");
        System.out.println(List.containsAll(List2));//查找多个元素是否存在
        System.out.println(List.removeAll(List2));//删除多个元素
    }
}
```

如果想再次遍历，需要重置我们的迭代器

> iterator = col.iterator();

## List

### List接口基本介绍

List接口是Collection接口的子接口

1.List集合类中元素有序（即添加顺序和取出顺序一致），且可重复

2.List集合中的每个元素都有其对应的顺序序列，即支持索引。

3.List容器中每个元素都对应一个整数的序号记载其在容器中的位置，可以根据序号存取容器中的元素。

### ·List接口的常用方法

ListMethod.javaList 集合里添加了一些根据索引来操作集合元素的方法

  1.void add(int index,Object ele):在index位置插入ele元素

2) boolean addAll(int index, Collection eles):从index位置开始将eles中的所有元素添加进来
3) Object get(int index):获取指定index位置的元素
4) int indexOf(Object obj):返回obj在集合中首次出现的位置
5) int lastlndexOf(Object obj):返回obj在当前集合中未次出现的位置
6) Object remove(int index):移除指定index位置的元素，并返回此元素
7) Object set(int index,Object ele):设置指定index位置的元素为ele,相当于是替换
8) List subList(int fromlndex,int tolndex):返回从fromlndex到tolndex位置的子集合

```java
import java.util.ArrayList;
import java.util.List;

public class ListTest {
    public static void main(String[] args) {
        List list = new ArrayList();
        list.add("jack");
        list.add("mary");
        list.add("tom");
        list.add("jack");
        System.out.println(list);
        list.add(1,"dwsd");//在索引为一的位置插入
        List list2 = new ArrayList();
        list2.add("张三");
        list2.add("李四");
        list2.add("王五");
        list.addAll(list2);//将list2 中所有元素加进来
        System.out.println(list);
        System.out.println(list.indexOf("tom"));//返回集合中首次出现的位置
        list.add("han");
        System.out.println(list.lastIndexOf("han"));//返回在集合中最后出现的位置
        list.remove(0);//移除指定位置的元素
        list.set(1,"玛丽");//将索引位置替换
        System.out.println(list);
    }
}
```

### List的三种遍历方式

1)**方式一**：使用iterator

Iterator iter = col.iterator();

while(iter.hasNext(){

Object o = iter.next();}

2)**方式二**：使用增强for

for(Object o:col){

}

3)**方式三**：使用普通for

for(int i=0;i&lt;list.size();i++){

Object object = list.get(i);

System.out.println(object);}

说明：使用LinkedList完成使用方式和ArrayList一样

### Array List

#### Array List的底层操作机制源码分析

1)ArrayList中维护了一个Object类型的数组elementData.

transient Object[] elementData;

2)当创建对象时，如果使用的是无参构造器，则初始elementData容量为0(jdk7是10)

3)当添加元素时：先判断是否需要扩容，如果需要扩容，则调用grow方法，否则直接添加元素到合适位置

4)如果使用的是无参构造器，如果第一次添加，需要扩容的话，则扩容elementData为10,如果需要再次扩容的话，则扩容elementData为1.5倍。

5)如果使用的是指定容量capacity的构造器，则初始elementData容量为capacity

6)如果使用的是指定容量capacity的构造器，如果需要扩容，则直接扩容elementData为1.5倍。

#### 注意事项

- permits all elements,including null,ArrayList 可以加入null,并且多个
- Array List是由数组来实现数据存储的
- Array List基本等同于Vector，除了Array List是线程不安全（执行率高），在多线程情况下，不建议使用Array List

### Vector

#### Vector的基本介绍

1.Vector类的定义说明

![image-20230712105347935](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230712105347935.png)

2.Vector底层也是一个对象数组，protected Object[] elementData;

3.Vector是线程同步的，即线程安全，Vector类的操作方法带有synchronized

4.在开发中，需要线程同步安全时，考虑使用Vector

#### ArrayList  VS Vector

![image-20230712091451864](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230712091451864.png)

### LinkedList

#### LinkList的底层操作机制

1.LinkedList底层维护了一个双向链表

2.LinkedList中维护了两个属性first和last分别指向 首节点和尾结点

3.每个节点（Node对象），里面维护了prev，next，item三个属性，其中通过prev指向前一个，通过next指向后一个节点。最终实现双向链表。

4.所以LinkedList的元素的添加和删除，不是通过数组完成的，相对来说效率较高。

5.模拟一个简单的双向链表

![image-20230712140818340](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230712140818340.png)

#### LinkedList的全面说明

1.LinkedList实现了双向链表和双端队列特点

2.可以添加任何元素（元素可以重复）。包括null

3.线程不安全，没有实现同步

#### ArrayList和LinkedList的比较

![image-20230712151103233](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230712151103233.png)

#### 如何选择ArrayList和LinkedList：

1.如果我们改查的操作多，选择ArrayList

2.如果我们增删的操作多，选择LinkedList

3.一般来说，在程序中，80%-90%都是查询，因此大部分情况下会选择ArrayList

## Set

### Set接口基本介绍

1.无序（添加和取出的顺序不一致），没有索引

2.不允许重复元素，所以最多包含一个null

### Set接口和常用方法

和List接口一样，Set接口也是Collection的子接口，因此，常用方法和Collection接口一样

### Set接口的遍历方式

同Collection的遍历方式一样，因为Set接口是Collection接口的子接口

1.可以使用迭代器

2.增强for

3.**不能使用索引的方式来获取**

### Set接口实现类-HashSet

#### HashSet的全面说明

1.HashSet实现了Set接口

2.HashSet实际上是HashMap

![image-20230712152420378](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230712152420378.png)

3.可以存放null值，但是只能有一个null

4.HashSet不保证元素是有序的，取决于hash后，在确定索引的结果

5.不能有重复元素/对象。

#### HashSet底层机制说明

HashSet底层是HashMap，HashMap底层是（数组 + 链表 + 红黑树）

![image-20230712165134099](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230712165134099.png)

- 添加一个元素时，先得到hash值-会转成->索引值
- 找到存储数据表table，看到这个索引位置是否已经存放的有元素
- 如果没有，直接加入
- 如果有，调用equals比较，如果相同，就放弃添加，如果不相同，则添加到最后
- 在java8中，如果一条链表的元素个数达到TREEIFY_THRESHOLD（默认是 8），并且table的大小 >= MIN_TREEIFY_CAPACITY(默认64)，就会进行树化（红黑树）

### Set接口实现类-LinkedHashSet

1.LinkedHashSet是HashSet的子类

2.LinkedHashSet底层是一个LinkedHashMap，底层维护了一个数组 + 双向链表

3.LinkedHashSet根据元素的hashCode值来决定元素的存储位置，同时使用链表维护元素的次序，这使得元素看起来是插入顺序保存的

4.LinkedHashSet不允许添重复元素

#### 说明

- 在LinkedHashSet中维护了一个hash表和双向链表（LinkedHashSet有head和tail)
- 每一个节点有before和after属性，这样可以形成双向链表
- 再添加一个元素时，先求hash值，再求索引，确定该元素在table的位置，然后将添加的元素加入到双向链表（如果已经存在，不添加【原则和HashSet一样】）
- 

![image-20230713095807732](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230713095807732.png)

## Map

### 特点

（这里是JDK8的Map接口特点）

1.Map与Collection并列存在。用于保存具有映射关系的数据：key--Value

2.Map中key和Value可以是任何引用类型的数据，会封装到HashMap￥Node对象中

3.Map中Key不允许重复，原因和HashSet一样

4.Map中Value可以重复

5.Map的key可以为null，value可以为null，注意key为null，只能有一个。Value为null，可以多个

6.常用String类作为Map的key

7.key和value之间存在单向一对一关系，即通过指定的key总能找到对应的value

8.Map存放数据的Key-Value示意图，一对k-v是放在一个HashMap￥Node中的，因为Node实现了Entry接口

![image-20230713143127032](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230713143127032.png)

### Map接口常用方法

1)put:添加

2)remove:根据键删除映射关系

3)get:根据键获取值4)size:获取元素个数

5)isEmpty:判断个数是否为0

6)clear:清除

7)containsKey:查找键是否存在

### Map接口的实现类-HashMap

- （k,v)是一个Node实现了Map.Entry<K,V>,查看HashMap的源码可以看到。
- jdk7.0的hashmap底层实现[数组 + 链表]，jdk8.0底层[数组 + 链表 + 红黑树]

![image-20230713155607438](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230713155607438.png)

#### 扩容机制

1.HashMap底层维护了Node类型的数组，默认为null

2.当创建对象时，将加载因子（loadfactor）初始化为0.75

3.当添加key-val 时，通过key的哈希值得到在table的索引。然后判断该索引处是否有元素，如果没有元素直接添加。如果该索引处有元素，继续判断该元素的key和准备加入的key是否相等，如果相等，则直接替换val；如果不相等需要判断是树结构还是链表结构，做出相应处理。如果添加时发现容量不够，则需要扩容

4.第1次添加，则需要扩容table容量为16,临界值（threshold)为12(16*0.75)

5.以后再扩容，则需要扩容table容量为原来的2倍（32),临界值为原来的2倍，即24,依次类

6.在Java8中，如果一条链表的元素个数超过TREEIFY_THRESHOLD(默认是&),并且table的大小>=MIN_TREEIFY CAPACITY(默认64),就会进行树化（红黑树）

### HashTable

#### 基本介绍

- 存放的元素是键值对：即K-V
- hashtable的键和值都不能为null
- hashTable使用方法基本上和HashMap一样
- hashTable是线程安全的，hashMap是线程不安全的

### HashTable  VSHashMap

![image-20230713190853167](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230713190853167.png)



### Map接口实现类-Properties

#### 基本介绍

  1.Properties类继承自Hashtable类并且实现了Map接口，也是使用一种键值对的形式来保存数据。

  2.他的使用特点和Hashtable类似

3. Properties 还可以用于 从 xxx.properties 文件中，加载数据到Properties类对象，并进行读取和修改
4. 说明：工作后xxx.properties文件通常作为配置文件，这个知识点在IO流举例，有兴趣可先看文章

## 总结-开发中如何选择集合实现类

1.先判断存储类型（一组对象或一组键值对）

2.一组对象：Collection接口

​    允许重复：List 

​                   增删多：LinkList[底层维护了一个双向链表]

​                   改查多：ArrayList [底层维护了一个双向链表]

​    不允许重复：Set

​                    无序：HashSet[底层是HashMap，维护了一个哈希表  即（数组 + 链表 + 红黑树）]

​                    排序：TreeSet

​                    插入和取出顺序一致：LinkedHashSet，维护数组 + 双向链表

3.一组键值对：Map

​       键无序：HashMap[底层是 ：哈希表  jdk7：数组 + 链表， jdk8：数组 + 链表 + 红黑树]

​       键排序：TreeMap

​       键插入和取出顺序一致：LinkedHashMap

​       读取文件：Properties

## Collections类

## Collection工具类介绍

  1.Collections是一个操作Set、List和Map等集合的工具类

2. Collections 中提供了一系列静态的方法对集合元素进行排序、查询和修改等操作

   ## 排序操作

   1)reverse(List):反转List中元素的顺序

   2)shuffle(List):对List集合元素进行随机排序

   3)sort(List):根据元素的自然顺序对指定List集合元素按升序排序

   4)sort(List,Comparator):根据指定的Comparator产生的顺序对List集合元素进行排序

   5)swap(List,int,int):将指定list集合中的i处元素和j处元素进行交换

   6)应用案例演示

```java
import java.util.ArrayList;
import java.util.Comparator;
import java.util.List;

public class Collections {

​    public static void main(String[] args) {
​        List list = new ArrayList();
​        list.add("jack");
​        list.add("tom");
​        list.add("king");
​       list.add("milan");
​       System.*out*.println(list);
​        java.util.Collections.*reverse*(list);//反转list中元素顺序
​        System.*out*.println(list);
​        java.util.Collections.*shuffle*(list);//随机排序
​        System.*out*.println(list);
​        java.util.Collections.*sort*(list);//升序排列
​        //按照字符串长度大小排序
​        java.util.Collections.*sort*(list, new Comparator() {
​            @Override
​            public int compare(Object o1,Object o2) {
​                return ((String)o1).length() - ((String)o2).length();
​            }
​        });
​        System.*out*.println("按字符串长度大小排序=" + list);
         java.util.Collections.swap(list,0,1);//交换元素位置

​    }


}
```

# 泛型

## 泛型介绍

**泛（广泛）型（类型）=>Integer,String,Dog**

1)泛型又称参数化类型，是Jdk5.0出现的新特性，解决数据类型的安全性问题

2)在类声明或实例化时只要指定好需要的具体的类型即可。

3)Java泛型可以保证如果程序在编译时没有发出警告，运行时就不会产生ClassCastException异常。同时，代码更加简洁、健壮

4)泛型的作用是：可以在类声明时通过一个标识表示类中某个属性的类型，或者是某个方法的返回值的类型，或者是参数类型。

## 泛型的好处

1.编译时，检查添加元素的类型。提高了安全性

2.减少了类型转换的次数

- 不使用泛型Dog-加入->Object-取出->Dog//放入到ArrayList会先转成Object,在取出时，还需要转换成Dog
- 使用泛型Dog->Dog->Dog//放入时，和取出时，不需要类型转换，提高效率

3.不再提示编译警告

泛型介绍

泛（广泛）型（类型）=>Integer,String,Dog

1)泛型又称参数化类型，是Jdk5.0出现的新特性，解决数据类型的安全性问题

2)在类声明或实例化时只要指定好需要的具体的类型即可。

3)Java泛型可以保证如果程序在编译时没有发出警告，运行时就不会产生ClassCastException异常。同时，代码更加简洁、健壮

4)泛型的作用是：可以在类声明时通过一个标识表示类中某个属性的类型，或者是某个方法的返回值的类型，或者是参数类型。

## 泛型的声明

interface 接口< T >{} 和class 类< K,V>{}

说明：

1.其中，T,K,V不代表值，而是代表类型

2.任意字母都可以。常用T表示，是Type的缩写

## 泛型的实例化

要在类名后面指定类型参数的值（类型）。如：

1.List< String  >strList = new ArrayList< String >();

2.Iterator< Customer >iterator = customers.iterator();

泛型的使用细节

1. interface List  < T >{};, public class HashSet < E >{}.....等等

2. 说明：T,E只能是引用类型

   看看下面语句是否正确？:

   List<Integer> list = new ArrayList<Integer>0;

   List&lt;int&gt;list2=new ArrayList&lt;int&gt;0;

   3.在指定泛型具体类型后，可以传入该类型或者其子类类型

   4.泛型使用形式List&lt;Integer&gt;list1=new ArrayList&lt;Integer>{};0;List&lt;lnteger&gt;list2=new ArrayList<>;

   5.如果我们这样写 List list3=new ArrayList();默认给它的泛型是[<E>E就是Object

## 自定义泛型

### 自定义泛型类

#### 基本语法

class 类名 < T,R....>{

成员

}

### 注意细节

1.普通成员可以使用泛型（属性，方法）

2.使用泛型的数组，不能初始化

3.静态方法中不能使用类的泛型

4.泛型类的类型，是在创建对象时确定的（因为创建对象时，需要指定确定类型）

5.如果在创建对象时，没有指定类型，默认为Object

### 自定义泛型方法

#### 基本语法

修饰符 < T,R...> 返回类型 方法名（参数列表）{}

注意细节

1.泛型方法，可以定义在普通类中，也可以定义在泛型类中

2.当泛型方法被调用时，类型会确定

3. public void eat(E e) {},修饰符后没有&lt;T,R.&gt;eat方法不是泛型方法，而是使用了泛型

   ### 自定义泛型接口

   #### 基本语法

   interface 接口名 <T，R...>{}

   注意细节

   1)接口中，静态成员也不能使用泛型（这个和泛型类规定一样）

   2)泛型接口的类型，在继承接口或者实现接口时确定

   3)没有指定类型，默认为Object

   ## 泛型的继承和通配符

   ### ·泛型的继承和通配符说明

   1)泛型不具备继承性List<Object>list=new ArrayList<String>0;//不对

   2)&lt;?&gt;:支持任意泛型类型

   3)&lt;?extends A&gt;:支持A类以及A类的子类，规定了泛型的上限

   4)&lt;? super A&gt;:支持A类以及A类的父类，不限于直接父类，规定了泛型的下限

# java绘图坐标体系坐标体系

## 介绍

下图说明了Java坐标系。坐标原点位于左上角，以像素为单位。在Java坐标系中，第一个是x坐标，表示当前位置为水平方向，距离坐标原点×个像素；第二个是y坐标，表示当前位置为垂直方向，距离坐标原点y个像素。

![image-20230715104100804](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230715104100804.png)

## ·坐标体系-像素

1.绘图还必须要搞清一个非常重要的概念-像素一个像素等于多少厘米？

2.计算机在屏幕上显示的内容都是由屏幕上的每一个像素组成的。例如，计算机显示器的分辨率是800×600,表示计算机屏幕上的每一行由800个点组成，共有600行，整个计算机屏幕共有480000个像素。**像素是一个密度单位，而厘米是长度单位，两者无法比较**

## 绘图原理

 **Component类提供了两个和绘图相关最重要的方法：**

1.paint(Graphicsg)绘制组件的外观

2.repaint()刷新组件的外观。当组件第一次在屏幕显示的时候，程序会自动的调用paint()方法来绘制组件。

**在以下情况paint()将会被调用：**

1.窗口最小化，再最大化

2.窗口的大小发生变化

3.repaint函数被调用

### 代码演示

```java
import javax.swing.*;
import java.awt.*;

public class DrawCricle extends JFrame{//JFrame对应窗口，可以理解成一个画板
    private MyPanel mp = null;//定义一个画板

    public static void main(String[] args) {
        new DrawCricle();

    }
    public DrawCricle(){//构造器
        mp = new MyPanel();
        //把面板放入画框
        this.add(mp);
        //设置窗口大小
        this.setSize(400,300);
        this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        this.setVisible(true);//可以显示
    }
}
class MyPanel extends JPanel{
    @Override
    public void paint(Graphics g) {//g相当于一个画笔,Graphics提供了很多绘画方式
        super.paint(g);
        g.drawOval(10,10,100,100);
    }
}
```

## Graphics类

Graphics类你可以理解就是画笔，为我们提供了各种绘制图形的方法：

1.画直线 drawLine(int x1,int y1,int x2,int y2)

2.画矩形边框 drawRect(int x,int y,int width,int height)

3.画桐圆边框 drawOval(int x,int y,int width,int height)

4.填充矩形 fillRect(int x,int y,int width,int height)

5.填充隋圆 fillOval(int x,int y,int width,int height)

6.画图片 drawlmage(lmage img,int x,int y,..)

7.画字符串 drawString(String str,int x,int y)

8.设置画笔的字体 setFont(Font font)

9.设置画笔的颜色 setColor(Color c)

![image-20230717092638160](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230717092638160.png)



![image-20230717093001567](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230717093001567.png)

## 小球移动代码

```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.KeyEvent;
import java.awt.event.KeyListener;

public class BellMove extends JFrame {
    MyPanel mp = null;

    public BellMove() {
        mp = new MyPanel();
        this.add(mp);
        this.setSize(400,300);
        this.addKeyListener(mp);
        this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        this.setVisible(true);
    }
    public static void main(String[] args) {
        BellMove bellMove = new BellMove();
    }
}
class MyPanel extends JPanel implements KeyListener {
    int x = 10;
    int y = 10;
    @Override
    public void paint(Graphics g) {
        super.paint(g);
        g.fillOval(x,y,20,20);
    }

    //keyListener是监听键盘移动的监听器
    @Override//当有字符输出，该方法会触发
    public void keyTyped(KeyEvent e) {
        System.out.println((char)e.getKeyCode() + "被按下...");
    }

    @Override//当某个键按下，该方法会触发
    public void keyPressed(KeyEvent e) {
        if(e.getKeyCode() == KeyEvent.VK_DOWN){
            y++;
        }else if(e.getKeyCode() == KeyEvent.VK_UP){
            y--;
        }else if(e.getKeyCode() == KeyEvent.VK_RIGHT){
            x++;
        }else if (e.getKeyCode() == KeyEvent.VK_LEFT){
            x--;
        }
        this.repaint();//重绘,很重要

    }
    @Override//当某个键释放（松开），该方法会触发
    public void keyReleased(KeyEvent e) {

    }
}

```

# 线程

## 线程相关概念

**程序（program)**

是为完成特定任务用某种语言编写的一组指令的集合。

简单的说：就是我们写的代码

**进程**

1.进程是指运行中的程序，比如我们使用QQ,就启动了一个进程，操作系统就会为该进程分配内存空间。当我们使用迅雷，又启动了一个进程，操作系统将为迅雷分配新的内存空间。

2.进程是程序的一次执行过程，或是正在运行的一个程序。是**动态过程**：有它自身的产生、存在和消亡的过程

**线程**

1.线程由进程创建的，是进程的一个实体

2.一个进程可以拥有多个线程，如下图

![image-20230717161632383](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230717161632383.png)

其他相关概念

1.单线程：同一个时刻，只允许执行一个线程

2.多线程：同一个时刻，可以执行多个线程，比如：一个qq进程，可以同时打开多个聊天窗口，一个迅雷进程，可以同时下载多个文件

3.并发：同一个时刻，多个任务交替执行，造成一种“貌似同时”的错觉，简单的说，单核cpu实现的多任务就是并发。

![image-20230717162252750](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230717162252750.png)

4.并行：同一个时刻，多个任务同时执行。多核cpu可以实现并行。

![image-20230717162336121](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230717162336121.png)

## 线程基本使用

**创造线程的两种方式**

在Java中线程使用有两种方式

1.继承Thread类，重写run方法

2.实现Runnable接口，重写run方法

继承Thread vs实现Runnable的区别

1.从java的设计来看，通过继承Thread或者实现Runnable接口来创建线程本质上没有区别，从jdk帮助文档我们可以看到Thread类本身就实现了Runnable接口

2.实现Runnable接口方式更加适合多个线程共享一个资源的情况，并且避免了单继承的限制

## 实现多线程案例

```java
public class thread1 {
    public static void main(String[] args) {
        T1 t1 = new T1();
        T2 t2 = new T2();
        Thread thread1 = new Thread(t1);
        Thread thread2 = new Thread(t2);
        thread1.start();
        thread2.start();
    }
}
class T1 implements Runnable{
    int count = 0;

    @Override
    public void run() {
        while (true){
        System.out.println("hello,word!" + (++count));
        try {
            Thread.sleep(1000);
        } catch (InterruptedException e) {
            throw new RuntimeException(e);
        }
            if(count == 10){
                break;
            }
    }
    }
}
class T2 implements Runnable{
    int count = 0;

    @Override
    public void run() {
        while (true){
        System.out.println("hi!" + (++count));
        try {
            Thread.sleep(1000);
        } catch (InterruptedException e) {
            throw new RuntimeException(e);
        }
        if(count == 5){
            break;
        }
    }
    }
}
```

## 线程终止基本说明·

1.当线程完成任务后，会自动退出。

2.还可以通过使用变量来控制run方法退出的方式停止线程，即通知方式

## 线程常用方法

**常用方法第一组**

1.setName//设置线程名称，使之与参数name相同

![image-20230717205647410](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230717205647410.png)

2.getName//返回该线程的名称·

3.start//使该线程开始执行；Java虚拟机底层调用该线程的start0方法

4.run//调用线程对象run方法；

5.setPriority//更改线程的优先级

6.getPriority//获取线程的优先级

7.sleep//在指定的毫秒数内让当前正在执行的线程休眠（暂停执行）

**常用方法第二组**

1.yield:线程的礼让。让出cpu,让其他线程执行，但礼让的时间不确定，所以也不一定礼让成功

2.join:线程的插队。插队的线程一旦插队成功，则肯定先执行完插入的线程所有的任务案例：创建一个子线程，每隔1s输出hello,输出20次，主线程每隔1秒，输出hi,输出20次要求：两个线程同时执行，当主线程输出5次后，就让子线程运行完毕，主线程再继续。

**用户线程和守护线程**

1.用户线程：也叫工作线程，当线程的任务执行完或通知方式结束

2.守护线程：一般是为工作线程服务的，当所有的用户线程结束，守护线程自动结束

3.常见的守护线程：垃圾回收机制

### ·注意事项和细节

1.start 底层会创建新的线程，调用run,run就是一个简单的方法调用，不会启动新线程·

2.线程优先级的范围

3.interrupt,中断线程，但并没有真正的结束线程。所以一般用于中断正在休眠线程

4.sleep:线程的静态方法，使当前线程休眠

## 线程的生命周期·线程状态转换图

![image-20230718095945863](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230718095945863.png)

## Synchronized

### 线程同步机制

1.在多线程编程，一些敏感数据不允许被多个线程同时访问，此时就使用同步访问术，保证数据在任何同一时刻，最多有一个线程访问，以保证数据的完整性。N也可以这里理解：线程同步，即当有一个线程在对内存进行操作时，其他线程都不可以对这个内存地址进行操作，直到该线程完成操作，其他线程才能对该内存地址进行操作.

### 同步具体方法-Synchronized

1.同步代码块synchronized(对象）{//得到对象的锁，才能操作同步代码//需要被同步代码；~

2.synchronized还可以放在方法声明中，表示整个方法-为同步方法

public synchronized void m (String name){//需要被同步的代码

3.如何**理解：**就好像 某小伙伴上厕所前先把门关上（上锁）,完事后再出来(解锁）,那么其它小伙伴就可在使田厕所了 

## 互斥锁

·基本介绍

1.Java语言中，引入了对象互斥锁的概念，来保证共享数据操作的完整性。

2.每个对象都对应于一个可称为“互斥锁”的标记，这个标记用来保证在任一时刻，只能有一个线程访问该对象。

3.关键字synchronized来与对象的互斥锁联系。当某个对象用synchronized修饰时，表明该对象在任一时刻只能由一个线程访问

4.同步的局限性：导致程序的执行效率要降低

5.同步方法（非静态的）的锁可以是this,也可以是其他对象（要求是同一个对象）

6.同步方法（静态的）的锁为当前类本身。

### ·注意事项和细节

1.同步方法如果没有使用static修饰：默认锁对象为this

2.如果方法使用static修饰，默认锁对象：当前类.class

3.实现的落地步骤：·需要先分析上锁的代码·选择同步代码块或同步方法·要求多个线程的锁对象为同一个即可！

释放锁

### 下面操作会释放锁

1.当前线程的同步方法、同步代码块执行结束

案例：上厕所，完事出来

2.当前线程在同步代码块、同步方法中遇到break、return。

案例：没有正常的完事，经理叫他修改bug,不得已出来

3.当前线程在同步代码块、同步方法中出现了未处理的Error或Exception,导致异常结束

案例：没有正常的完事，发现忘带纸，不得已出来

4.当前线程在同步代码块、同步方法中执行了线程对象的wait()方法，当前线程暂停，并释放锁。

### 下面操作不会释放锁

1.线程执行同步代码块或同步方法时，程序调用Thread.sleep0、Thread.yield()方法暂停当前线程的执行，不会释放锁

案例：上厕所，太困了，在坑位上眯了一会

2.线程执行同步代码块时，其他线程调用了该线程的suspend()方法将该线程挂起，该线程不会释放锁。提示：应尽量避免使用suspend()和resume()来控制线程，方法不再推荐使用

# IO流

## 文件·

什么是文件

文件，对我们并不陌生，文件是保存数据的地方，比如大家经常使用的word文档，txt件，excel文件...都是文件。它既可以保存一张图片，也可以保持视频，声音...

### 文件流

文件在程序中是以流的形式来操作的

![image-20230718210041605](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230718210041605.png)

![image-20230718203806291](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230718203806291.png)

流：数据在数据源（文件）和程序（内存）之间经历的路径

输入流：数据从数据源（文件）到程序（内存）的路径

输出流：数据从程序（内存）到数据源（文件）的路径

## 常用的文件操作

创建文件对象相关构造器和方法>

相关方法

new File(String pathname)//根据路径构建一个File对象

new File(File parent,String child)//根据父目录文件+子路径构建

new File(String parent,String child)//根据父目录+子路径构建

### 第三个方法代码演示

```java
import org.junit.jupiter.api.Test;

import java.io.File;
import java.io.IOException;

public class file1 {
    public static void main(String[] args) {
    }
    @Test
    public void create(){
        String parentPath = "d:\\";
        String filePath = "news1.txt";
        File file = new File(parentPath,filePath);
        try {
            file.createNewFile();
            System.out.println("创建成功");
        } catch (IOException e) {
            throw new RuntimeException(e);
        }
    }
}
```

### 目录的操作和文件的删除

mkdir创建一级目录

mkdirs创建多级目录

delete删除空目录或文件

#### 创建多级目录代码演示

```
import org.junit.jupiter.api.Test;

import java.io.File;

public class Directory1 {
    public static void main(String[] args) {

    }
    @Test
    public void m1(){
        String direvtoryPath = "d\\demo\\a\\b";
        File file = new File(direvtoryPath);
        if (file.exists()){
            System.out.println(direvtoryPath + "存在");
        }else {
            if (file.mkdirs()){
                System.out.println("创建成功");
            }else {
                System.out.println("创建失败");
            }
        }
    }
}

```

## IO流原理及流的分类

### Java IO流原理

1.  I/0是Input/Output的缩写，I/O技术是非常实用的技术，用于处理数据传输。如读/写文件，网络通讯等。
2. 2.Java程序中，对于数据的输入/输出操作以”流（stream)”的方式进行。
3. java.io包下提供了各种“流”类和接口，用以获取不同种类的数据，并通过方法输入或输出数据

   4.输入input：读取外部数据（磁盘，光盘等存储设备的数据）到程序（内存）中。

   5.输出output：将程序（内存）数据输出到磁盘，光盘等存储设备中。

![image-20230719092021185](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230719092021185.png)

### 流的分类

按操作数据单位不同分为：字节流（8bt),字节流（按字节）

按数据流的流向不同分为：输入流，输出流

按流的角色的不同分为：节点流，处理流/包装流

![image-20230719092404806](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230719092404806.png)

1.java的Io流共涉及40多个类，实际上非常规则，都是从如上四个抽象基类派生的。

2.由这四个类派生出来的子类名称都是以其父类名作为子类名后缀。

10流体系图-常用的类·InputStream:字节输入流√ InputStream抽象类是所有类字节输入流的超类√ InputStream 常用的子类1.FilelnputStream:文件输入流2.BufferedlnputStream:缓冲字节输入流3.ObjectlnputStream:对象字节输入流

![image-20230719093149268](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230719093149268.png)

### 拷贝文件代码演示

```java
import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.FileOutputStream;
import java.io.IOException;

public class FileCopy {
    public static void main(String[] args) {
        String filrPath ="d:\\news1.txt";
        String desPath ="d:\\news2.txt";
        FileInputStream fileInputStream = null;
        FileOutputStream fileOutputStream = null;

        try {
            fileInputStream = new FileInputStream(filrPath);
            fileOutputStream = new FileOutputStream(desPath);
            byte[] buf = new byte[1024];
            int readLen = 0;
            while ((readLen = fileInputStream.read(buf)) != -1){
                fileOutputStream.write(buf);
            }
            System.out.println("拷贝成功");
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if(fileInputStream != null){
                try {
                    fileInputStream.close();
                } catch (IOException e) {
                    throw new RuntimeException(e);
                }
            }
            if(fileOutputStream != null){
                try {
                    fileOutputStream.close();
                } catch (IOException e) {
                    throw new RuntimeException(e);
                }
            }
        }
    }
}

```

## Io体系图-常用的类

### FileReader 和 FileWriter 介绍

FileReader 和 FileWriter 是字符流，即按照字符来操作io



### FileReader相关方法：

1)new FileReader(File/String)

2)read:每次读取单个字符，返回该字符，如果到文件未尾返回-1

3)read(char[]):批量读取多个字符到数组，返回读取到的字符数，如果到文件末尾返回-1

![image-20230719105733747](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230719105733747.png)

**相关API:**

1)new String(char[]):将char[]转换成String

2)new String(char[],off,len):将char[]的指定部分转换成String

### FileWriter常用方法

1)new FileWriter(File/String):覆盖模式，相当于流的指针在首端

2)new FileWriter(File/String,true):追加模式，相当于流的指针在尾端

3)write(int):写入单个字符4)write(char[]):写入指定数组

5)write(char[],off,len):写入指定数组的指定部分

6)write(string):写入整个字符串

7)write(string,off,len):写入字符串的指定部分相关API:String类：toCharArray:将String转换成char[]

**注意：FileWriter使用后，必须要关闭（close)或刷新（flush),否则写入不到指定的文件**

![image-20230719105703476](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230719105703476.png)

介绍BufferedOutputStream

BufferedOutputStream是字节流，实现缓冲的输出流，可以将多个字节写入底层输出流中，而不必对每次字节写入调用底层系统

![image-20230719154306654](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230719154306654.png)

## 节点流和处理流

### 基本结束

1.节点流可以从一个特定的数据源读写数据，如File Reader，File Writer

![image-20230719170336808](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230719170336808.png)

2.处理流（也叫包装流）是“连接”在已保存的流（节点流或处理流）之上，为程序提供更为强大的读写功能，如BufferedReader,BufferedReader

![image-20230719170636172](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230719170636172.png)

### 节点流和处理流的区别和联系

1.节点流是**底层流/低级流**，直接跟数据源相接。

2.处理流（包装流）包装节点流，既可以消除不同节点流的实现差异，也可以提供更方便的方法来完成输入输出

3.处理流（也叫包装流）对节点流进行包装，使用了修饰器设计模式，不会直接与数据源相连[模拟修饰器设计模式

处理流的功能主要体现在以下两个方面：

1.性能的提高：主要以增加缓冲的方式来提高输入输出的效率。

2.操作的便捷：处理流可能提供了一系列便捷的方法来一次输入输出大批量的数据，使用更加灵活方便

![image-20230719154201101](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230719154201101.png)

## 对象流-ObjectlnputStream和ObjectOutputStream>

看一个需求

1.将int num=100这个int数据保存到文件中，注意不是100数字，而是int100,并且，能够从文件中直接恢复int 100

2.将Dog dog=new Dog("小黄",3)这个dog对象保存到文件中，并且能够从文件恢复.

3.上面的要求，就是能够将基本数据类型或者对象进行序列化和反序列化操作

### 序列化和反序列化

1.序列化就是在保存数据时，保存数据的值和数据类型.

2.反序列化就是在恢复数据时，恢复数据的值和数据类型

3.需要让某个对象支持序列化机制，则必须让其类是可序列化的，为了让某个类是可序列化的，该类必须实现如下两个接口之一：>Serializable//这是一个标记接口>Externalizable

### 序列化形式保存演示

```java
public class ObjectTest {
    public static void main(String[] args) throws Exception {
        String filePath = "d:\\news2.txt";
        ObjectOutputStream oos = new ObjectOutputStream(new FileOutputStream(filePath));
        oos.write(100);
        oos.writeBoolean(true);
        oos.writeDouble(12.4);
        oos.writeObject(new Dog("大黄",3));
        oos.close();
        System.out.println("保存成功（序列化形式）");

    }
}
class  Dog implements Serializable {
    private String name;
    private int age;

    public Dog(String name,int age) {
        this.age = age;
        this.name = name;
    }
}
```

