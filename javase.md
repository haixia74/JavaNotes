

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

3.当不希望类的某个属性的值被修改

![image-20230704085346662](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230704085346662.png)

![image-20230704085301468](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230704085301468.png)

![image-20230704085200541](C:\Users\86177\AppData\Roaming\Typora\typora-user-images\image-20230704085200541.png)
