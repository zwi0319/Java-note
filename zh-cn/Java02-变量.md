# Java02-变量

## 1. 变量介绍

### 1.1. 为什么需要变量

**变量->是程序的->基本组成单位**

> 不论是使用哪种高级程序语言编写程序，变量都是其程序的基本组成单位
>
> 变量有三个甚本要素（类型+名称+值）

### 1.2. 变量的介绍

**概念：**

变量相当于内存中一个数据存储空间的表示，你可以把变量看做是一个房间的牌号，通过门牌号我们可以找到房间，而通过变量名可以访问到变量（值）

**变量使用的基本步骤** ：

1. 声明变量

> int a; 

1. 赋值

> a=60; 

1. 使用`System.out.println(a);`

也可以一步到位`[int a = 60]`通常我们是一步完成

### 1.3. **变量的注意事项**

![image-20230726143129848](.\assets\image-20230726143129848.png)

1. 只能存**一个值**
2. 变量名**不允许重复定义**
3. 一条语句**可以定义多个变量**
4. 变量在**使用之前一定要进行赋值**
5. 变量的**作用域范围**

## 2. `+`的使用

![image-20230726143256907](.\assets\image-20230726143256907.png)

```java
System.out.println(100 + 98);//198
System.out.println("100" + 98);//10098
System.out.println(100 + 3 + "hello");//103hello
System.out.println("hello" + 100 + 3);//hello1003
```

## 3. 数据类型*

### 3.1. 概述

**每一种数据都定义了明确的数据类型，在内存中分配了不同大小的内存空间（字节）**

![image-20230726143344274](.\assets\image-20230726143344274.png)

上图说明 ：

1. java数据类型分为两大类**基本数据类型**，**引用数据类型** 
2. 基本数据类型有8中数值型[`byte`,`short`,`int`,`long`,`float`,`double`][`char`,`boolean`]
3. 引用类型：[`类`,`接口`,`数组`]

### 3.2. 整数类型

![image-20230726143416897](.\assets\image-20230726143416897.png)

**整形的使用细节：**

1. Java各整数类型有固定的范围和字段长度，不受具体OS`[操作系统]`的影响，以保证java程序的可移植性。
2. Java的整型常量默认为int型，声明long型常量须后加`"l"`或`"L"`
3. java程序中变量常声明为int型，除非不足以表示大数，才使用long 
4. bit：计算机中的最小存储单位。byte:计算机中基本存储单元，`1 byte=8 bit`<u>[二进制再详细说，简单举例一个byte 3和short 3]</u>

### 3.3. 浮点类型

![image-20230726143514988](.\assets\image-20230726143514988.png)

**说明一下** ：

1. 关于浮点数在机器中存放形式的简单说明,`浮点数=符号位+指数位+尾数位`
2. 尾数部分可能丢失，**造成精度损失**(小数都是近似值)。

------

**浮点型使用细节：**

1. 与整数类型类似，Java浮点类型也有固定的范围和字段长度，不受具体OS的影响。

- - [float4个字节]
  - [double是8个字节] 

2. Java的浮点型常量默认为double型，声明float型常量，须后加`'f'`或`'F'`浮点型常量有两种表示形式

- - 十进制数形式：如：5.12	512.0f	.512(必须有小数点)
  - 科学计数法形式：如：5.12e2 [ ]	5.12E-2 [ ]

3. 通常情况下，应该使用double型，因为它比float型更精确。[举例说明]

- - double num9=2.1234567851;
  - float num10=2.1234567851F;

4. 浮点数使用陷阱：`2.7` 和 `8.1 / 3`比较

### 3.4. 字符类型

**基本介绍：**

字符类型可以表示**单个字符**,字符类型是 char，char 是**两个字节**(可以存放汉字)，多个字符我们用字符串 String(我们 后面详细讲解 String)

> \#代码 
>
> char c1 = 'a'; 
>
> char c2 = '\t'; 
>
> char c3 = '韩'; 
>
> char c4 = 97;

------

**字符类型使用细节：**

1. 字符常量是用单引号`''`括起来的单个字符。例如： `char c1='a'`,`char c2='中'`,`char c3='9'`
2. Java中还允许使用转义字符`'\'`来将其后的字符转变为特殊字符型常量。例如：`char c3='\n'`;`'\n'`表示换行符 
3. 在java中，char的本质是一个整数，在输出时，是 unicode码对应的字符。http://tool.chinaz.com/Tools/Unicode.aspx 
4. 可以直接给char赋一个整数，然后输出时，会按照对应的unicode字符输出`97 -> a` 
5. char类型是可以进行运算的，相当于一个整数，因为它都对应有Unicode码

**字符类型本质：**

![image-20230726143732977](.\assets\image-20230726143732977.png)

### 3.5. 布尔类型

**基本介绍** ：

1. 布尔类型也叫booolean类型，booolean类型数据只允许取值true和false,无 null 
2. boolean类型**占1个字节**。 
3. boolean类型适于逻辑运算，一般用于程序流程控制：

- f条件控制语句;
- while循环控制语句;
- do-while循环控制语句;
- for循环控制语句;

------

**使用细节：**

- **不可以0或非0的整数替代false和true**,这点和C语言不同

## 4. 编码

### 4.1. ASCII 码介绍(了解)

![image-20230726143811118](.\assets\image-20230726143811118.png)

### 4.2. Unicode 编码介绍(了解)

![image-20230726143833495](.\assets\image-20230726143833495.png)

### 4.3. UTF-8 编码介绍(了解)

![image-20230726143853988](.\assets\image-20230726143853988.png)

## 5. 数据类型转换*

### 5.1. 自动类型转换

![image-20230726143911661](.\assets\image-20230726143911661.png)

### 5.2. 自动类型转换注意和细节

1. 有多种类型的数据混合运算时，系统首先自动将所有数据转换成容量最大的那种数据类型，然后再进行计算。 
2. 当我们把`精度(容量)大`的数据类型赋值给`精度(容量)小`的数据类型时，就会报错，反之就会进行自动类型转换。 
3. (`byte`,`short`)和`char`之间不会相互自动转换。 
4. `byte`,`short`,`char`他们三者可以计算，**在计算时首先转换为int类型**。 
5. boolean不参与转换 
6. 自动提升原则：表达式结果的类型自动提升为操作数中最大的类型

![image-20230726144004111](.\assets\image-20230726144004111.png)

```java
public static void main(String[] args) {
    // 1.有多种类型的数据混合运算时，系统首先自动将所有数据转换成容量最大的那种数据类型，然后再进行计算。
    int n1 = 10;//ok
    // f1oat d1=n1+1.1;// 错误n1+1.1=>结果类型是double
    // double d1=n1+1.1;// 对n1+1.1=>结果类型是double
    float d1 = n1 + 1.1F;//对n1+1.1=>结果类型是f1oat

    // 2.当我们把精度（容量）大的数据类型赋值给精度（容量）小的数据类型时，就会报错，反之就会进行自动类型转换。
    //int n2 = 1.1;//错误 double -> int

    // 3.(byte,short)和char之间不会相互自动转换。
    //当把具体数赋给 byte 时，(1)先判断该数是否在 byte 范围内，如果是就可以
    byte b1 = 10; //对 , -128-127
    // int n2 = 1; //n2 是 int
    // byte b2 = n2; //错误，原因： 如果是变量赋值，判断类型
    // char c1 = b1; //错误， 原因 byte 不能自动转成 char

    // 4.byte,short,char他们三者可以计算，在计算时首先转换为int类型。
    byte b2 = 1;
    byte b3 = 2;
    short s1 = 1;
    //short s2 = b2 + s1;//错, b2 + s1 => int
    int s2 = b2 + s1;//对, b2 + s1 => int
    //byte b4 = b2 + b3; //错误: b2 + b3 => int

    // boolean 不参与转换
    boolean pass = true;
    //int num100 = pass;// boolean 不参与类型的自动转换

    // 6.自动提升原则：表达式结果的类型自动提升为操作数中最大的类型
    //看一道题
    byte b4 = 1;
    short s3 = 100;
    int num200 = 1;
    float num300 = 1.1F;
    double num500 = b4 + s3 + num200 + num300; //float -> double
}
```

## 6. 数据类型强制转换

自动类型转换的逆过程，**将容量大的数据类型转换为容量小的数据类型**。使用时要加上强制转换符 `()`，但可能造成 **精度降低或溢出**,格外要注意。

> **int a = (int) 1.99;
> System.out.println(a);//造成精度丢失
> int b = 2000;
> byte c = (byte) b;
> System.out.println(c);//造成数据溢出**


---

**强制转换细节：**

1. 当进行数据的大小从`大->小`，就需要使用到强制转换 
2. 强转符号只针对于最近的操作数有效，往往会使用**小括号**`()`提升优先级

> **int x = (int) 10 * 3.5 + 6 * 1.5;//编译错误： double -> int
> int x = (int) (10 * 3.5 + 6 * 1.5);// (int)44.0 -> 44
> System.out.println(x);//44**

3. `char`类型可以保存`int`的常量值，但不能保存`int`的变量值，需要强转

> **char c1 = 100; //ok
> int m = 100; //ok
> char c2 = m; //错误
> char c3 = (char) m; //ok
> System.out.println(c3);//100 对应的字符, d 字符**

4. `byte`和`short`,`char`类型在进行运算时，当做`int`类型处理。

## 7. 基本数据类型和string类型的转换*

![image-20230726144247580](.\assets\image-20230726144247580.png)

```java
//基本数据类型->String
int n1 = 100;
float f1 = 1.1F;
double d1 = 4.5;
boolean b1 = true;
String s1 = n1 + " ";
String s2 = f1 + " ";
String s3 = d1 + " ";
String s4 = b1 + " ";
System.out.println(s1 + " " + s2 + " " + s3 + " " + s4);

//String->对应的基本数据类型
String s5 = "123";
//会在 OOP 讲对象和方法的时候回详细
//解读 使用 基本数据类型对应的包装类，的相应方法，得到基本数据类型
int num1 = Integer.parseInt(s5);
double num2 = Double.parseDouble(s5);
float num3 = Float.parseFloat(s5);
long num4 = Long.parseLong(s5);
byte num5 = Byte.parseByte(s5);
boolean b = Boolean.parseBoolean("true");
short num6 = Short.parseShort(s5);
System.out.println("===================");
System.out.println(num1);//123
System.out.println(num2);//123.0
System.out.println(num3);//123.0
System.out.println(num4);//123
System.out.println(num5);//123
System.out.println(num6);//123
System.out.println(b);//true

//怎么把字符串转成字符 char -> 含义是指 把字符串的第一个字符得到
//解读 s5.charAt(0) 得到 s5 字符串的第一个字符 '1'
System.out.println(s5.charAt(0));
```

怎么把字符串转成字符 char -> 含义是指 把字符串的第一个字符得到

> **System.out.println(s5.charAt(0));	//解读 s5.charAt(0) 得到 s5 字符串的第一个字符 '1'**

**注意事项：**

1. 在将String类型转成基本数据类型时，要确保String类型能够转成有效的数据，比如我们可以把"123"，转成一个整数，但是不能把"hello"转成一个整数
2. 如果格式不正确，就会抛出异常，程序就会终止，这个问题在**异常处理**章节中，会处理

## 8. API的使用

1. API (Application Programming Interface）用程序编程接口)是Java提供的基本编程接口(java提供的类还有相关的方法)。中文在线文档： https://www.matools.com 
2. Java语言提供了大量的基础类，因此Oracle公司也为这些基础类提供了相应的AP文档，用于告诉开发者如何使用这些类，以及这些类里包含的方法。
3. Java类的组织形式[图]
4. 举例说明如何使用ArrayLista类有哪些方法.安：包->类->方法

直接索引。Math

![image-20230726144421638](.\assets\image-20230726144421638.png)