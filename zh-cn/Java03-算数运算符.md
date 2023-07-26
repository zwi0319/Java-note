# Java03-算数运算符

## 1. 算术运算符

![image-20230726144616890](.\assets\image-20230726144616890.png)

```java
public static void main(String[] args) {
    System.out.println(8 + 2);//10
    System.out.println(8 - 2);//6
    System.out.println(8 * 2);//16
    System.out.println(8 / 2);//4
    System.out.println(8 % 2);//0
    System.out.println(8 % 3);//2

    /*
        作为表达式使用
        前++：++i 先自增后赋值
        后++：i++先赋值后自增
    */
    int a1 = 1;
    int a2 = 1;
    int b1 = a1++;
    int b2 = ++a2;
    System.out.println(b1);//1
    System.out.println(a1);//2
    System.out.println(b2);//2
    System.out.println(a2);//2
}
```

**细节说明：**

1. 对于除号`"/"`，它的整数除和小数除是有区别的：整数之间做除法时，只保留整数部分而舍弃小数部分。例如：`int x = 10 / 3`,结果是3 
2. 当对一个数取模时，可以等价`a % b = a - a / b * b`，这样我们可以看到取模的一个本质运算。 
3. 当自增当做一个独立语言使用时，不管是`++i`;还是`i++`;都是一样的，等价 
4. 当自增当做一个表达式使用时`j = ++i`等价[?] 
5. 当自增当做一个表达式使用时`j = i++`等价[?]

## 2. 关系运算符

![image-20230726144818955](.\assets\image-20230726144818955.png)

```java
int a = 9; //老韩提示: 开发中，不可以使用 a, b
int b = 8;
System.out.println(a > b); //T
System.out.println(a >= b); //T
System.out.println(a <= b); //F
System.out.println(a < b);//F
System.out.println(a == b); //F
System.out.println(a != b); //T
boolean flag = a > b; //T
System.out.println("flag=" + flag);
```

**细节说明：**

1. 关系运算符的结果都是 boolean 型，也就是要么是 true，要么是 false。 
2. 关系运算符组成的表达式，我们称为关系表达式。 a > b 
3. 比较运算符"`==`"不能误写成"`=`"

## 3. 逻辑运算符*

分为两组学习 

1. 短路**与**`&&`，短路**或**`||`，**取反**`!` 
2. 逻辑**与**`&`，逻辑**或**`|`，逻辑**异或**`^`

![image-20230726144846291](.\assets\image-20230726144846291.png)

**说明逻辑运算规则：** 

1. `a&b`:&叫**逻辑与**：规则：当 a 和 b 同时为true,则结果为true,否则为false 
2. `a&&b`:&&叫**短路与**：规则：当 a 和 b 同时为true,则结果为true,否则为false 
3. `a|b`:叫**逻辑或**，规则：当 a 和 b,有一个为true,则结果为true,否则为false 
4. `a||b`:叫**短路或**，规则：当 a 和 b,有一个为true,则结果为true,否则为false 
5. `!a`:叫**取反**，或者非运算。当 a 为true,则结果为false,当a为false是，结果为true 
6. `a^b`:叫**逻辑异或**，当 a 和 b 不同时，则结果为true,否则为false

------

`&&` **和** `&` **使用区别：**

1. `&&`短路与：如果第一个条件为 false，则第二个条件不会判断，最终结果为 false，**效率高** 
2. `&`逻辑与：不管第一个条件是否为 false，第二个条件都要判断，效率低
3. 开发中， 我们使用的基本是使用短路与`&&`, 效率高

------

`||` **和**`|` **使用区别：**

1.  `||`短路或：如果第一个条件为 true，则第二个条件不会判断，最终结果为 true，**效率高** 
2.  `|` 逻辑或：不管第一个条件是否为 true，第二个条件都要判断，效率低 
3.  **开发中，我们基本使用**`||`

![image-20230726144951910](.\assets\image-20230726144951910.png)

![image-20230726144959672](.\assets\image-20230726144959672.png)

![image-20230726145011655](.\assets\image-20230726145011655.png)

## 4. 赋值运算符

### 4.1. 介绍 

> **赋值运算符就是将某个运算后的值，赋给指定的变量。**

### 4.2. 赋值运算符的分类 

- 基本赋值运算符 `=` 

> int a = 10; 	

- 复合赋值运算符 

> `+=` ，`-=` ，`*=` ， `/=` ，`%=` 等 , 重点讲解一个 `+=` ，其它的使用是一个道理 
>
> a += b	[等价 a = a + b; ] 
>
> a -= b 	[等价 a = a - b; ]

------

**赋值运算符细节：**

1. 运算顺序**从右往左** 

> int num = a + b + c; 

2. 赋值运算符的左边只能是**变量**,右边 可以是**变量**、**表达式**、**常量值** 

> int num = 20; int num2= 78 * 34 - 10; int num3 = a; 

3. 复合赋值运算符等价于下面的效果 

> 比如：a += 3;等价于 a = a + 3; 其他类推 

4. 复合赋值运算符会进行类型转换。 

> byte b = 2; b += 3; b++;

```java
public static void main(String[] args) {
    int a = 10;
    a += 4;//a = a + 4;
    System.out.println(a);//14
}
```

## 5. 三元运算符*

### 5.1. 基本语法：

> **条件表达式 ? 表达式 1: 表达式 2;** 

### 5.2. 运算规则： 

1. 如果条件表达式为 true，运算后的结果是表达式 1； 
2. 如果条件表达式为 false，运算后的结果是表达式 2； 

**口诀**: [一灯大师：**一真大师**]

### 5.3. 使用细节：

1. 表达式 1 和表达式 2 要为可以赋给接收变量的类型(或可以自动转换) 
2. 三元运算符可以转成 `if--else` 语句

> int res = a > b ? a++ : --b; 
>
> if ( a > b) res = a++; 
>
> else res = --b;

```java
int a = 10;
int b = 20;
int c = 30;
int temp = a > b ? a : b;
int result = temp > c ? temp : c;
System.out.println(result);
//代码优化
int result1 = (a > b ? a : b) > c ? (a > b ? a : b) : c;
System.out.println(result1);
```

## 6. 优先级

**运算符优先级：**

1. 运算符有不同的优先级，所谓优先级就是表达式运算中的运算顺序。如表，上一行运算符总优先于下一行。 

![image-20230726145426794](.\assets\image-20230726145426794.png)

2. 只有单目运算符、赋值运算符是从右向左运算的。 

3. 一览表, 不要背，使用多了，就熟悉了

## 7. 标识符命名规则与规范

### 7.1. 标识符概念

1. Java对各种变量、方法和类等命名时使用的字符序列称为标识符 
2. 凡是自己可以起名字的地方都叫标识符`int num1 = 90`

### 7.2. 标识符的命名规则（必须遵守） 

1. 由26个英文字母大小写，`0~9``_`或`$`组成 
2. 数字不可以开头。int 3ab = 1;//错误 
3. 不可以使用**关键字**和**保留字**，但能包含关键字和保留字。
4. Java中严格区分大小写，长度无限制。`int totalNum = 10``int n = 90`
5. 标识符**不能包含空格**，`int a b=90`

### 7.3. 标识符命名规范[更加专业]

1. **包名**：**多单词组成时所有字母都小写**：`aaa.bbb.ccc` 比如`com.hsp.crm`
2. **类名**、**接口名**：多单词组成时，**所有单词的首字母大写**：`XxxYyyZzz` [大驼峰] 

比如： `TankShotGame` 

1. **变量名**、**方法名**：多单词组成时，**第一个单词首字母小写**，第二个单词开始每个单词首字母大写：`xxxYyyZzz` [小驼峰， 简称:驼峰法] 比如： `tankShotGame` 

1. **常量名**：**所有字母都大写**。多单词时每个单词用**下划线连接**：`XXX_YYY_ZZZ` 比如 ：定义一个所得税率 `TAX_RATE` 

1. 后面我们学习到 **类**，**包**，**接口**，等时，我们的命名规范要这样遵守,更加详细的看文档

## 8. 关键字和保留字

### 8.1. 关键字的定义和特点 (不用背) 

定义：被 Java 语言赋予了特殊含义，用做**专门用途的字符串**（单词） 

特点：关键字中所有字母都为小写

![image-20230726145700594](.\assets\image-20230726145700594.png)

![image-20230726145714512](.\assets\image-20230726145714512.png)

### 8.2. 保留字

Java 保留字：现有 Java 版本**尚未使用**，但**以后版本可能会作为关键字使用**。自己命名标识符时要避免使用这些保留 字 `byValue`、`cast`、`future`、 `generic`、 `inner`、 `operator`、 `outer`、 `rest`、 `var` 、 `goto` 、`const`

## 9. 键盘输入语句

### 9.1. 介绍 

在编程中，需要接收用户输入的数据，就可以使用键盘输入语句来获取。`Input.java` , 需要一个 扫描器(对象), 就是 `Scanner`

### 9.2. 步骤 ： 

1. 导入该类的所在包`java.util.*` 
2. 创建该类对象（声明变量） `new Scanner(System.in)`
3. 调用里面的功能`next()`

```java
import java.util.Scanner;//表示把 java.util 下的 Scanner 类导入

/**
 * java 12 键盘输入
 *
 * @author 22175
 * @date 2023/05/09
 */
public class Java_12_KeyboardInput {
    public static void main(String[] args) {
        //演示接受用户的输入
        //步骤
        //Scanner 类 表示 简单文本扫描器，在 java.util 包
        //1. 引入/导入 Scanner 类所在的包
        //2. 创建 Scanner 对象 , new 创建一个对象,体会
        // myScanner 就是 Scanner 类的对象
        Scanner myScanner = new Scanner(System.in);
        //3. 接收用户输入了， 使用 相关的方法
        System.out.println("请输入名字");
        //当程序执行到 next 方法时，会等待用户输入~~~
        String name = myScanner.next(); //接收用户输入字符串
        System.out.println("请输入年龄");
        int age = myScanner.nextInt(); //接收用户输入 int
        System.out.println("请输入薪水");
        double sal = myScanner.nextDouble(); //接收用户输入 double
        System.out.println("人的信息如下:");
        System.out.println("名字=" + name + " 年龄=" + age + " 薪水=" + sal);
    }
}
```