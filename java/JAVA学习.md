## JAVA学习

### 一、基础知识！

#### 1.1安装

##### 1、JDK、JRE和JVM的关系

JDK（Java Development Kit）

开发工具：编译工具（javac.exe）和运行工具（java.exe）

<img src="C:\Users\17487\AppData\Roaming\Typora\typora-user-images\image-20220703165148782.png" alt="image-20220703165148782" style="zoom:67%;" />

##### 2、常用DOS命令

<img src="C:\Users\17487\AppData\Roaming\Typora\typora-user-images\image-20220703170115996.png" alt="image-20220703170115996" style="zoom:50%;" />

#### 1.2 基础语法

##### 1、注释

+ 单行注释：//注释信息
+ 多行注释：/ * 注释信息 *  /
+ 文档注释：/**注释信息 * /

##### 2、关键字

+ 被Java语言赋予特定含义的单词
+ 关键字字母全部小写

##### 3、常量

+ 常量：在程序运行过程中，其值不可以发生改变的量
+ 空常量是不能被输出的
+ <img src="C:\Users\17487\AppData\Roaming\Typora\typora-user-images\image-20220703184611082.png" alt="image-20220703184611082" style="zoom:67%;" />

##### 4、数据类型

+ <img src="C:\Users\17487\AppData\Roaming\Typora\typora-user-images\image-20220703185102130.png" alt="image-20220703185102130" style="zoom: 67%;" />

<img src="C:\Users\17487\AppData\Roaming\Typora\typora-user-images\image-20220703185304134.png" alt="image-20220703185304134" style="zoom:67%;" />

##### 5、变量

+ 在程序运行过程中其值可以发生改变的量

+ 格式：数据类型 变量名=变量值
+ 注意事项：
  + 1、名字不能重复；
  + 2、变量未赋值，不能使用；
  + 3、long类型的变量定义时，为防止证书过大，后面要加L；
  + 4、float类型的变量定义时，为防止类型不兼容，后面要加F。

##### 6、标识符

+  定义：给类、方法、变量等起名字的符号
+ 规则
  + 由数字、字母、下划线和美元符组成
  + 不能以数字开头
  + 不能是关键字
  + 区分大小写
+ **常见命名约定**
  + 小驼峰命名法
    + 1、标识符是一个单词时，首字母小写；
    + 2、标识符有多个单词组成的时候，第一个单词首字母小写，其他单词首字母大写；
  + 大驼峰命名法
    + 1、标识符是一个单词时，首字母大写；
    + 2、标识符由多个单词组成的时候，每个单词的首字母大写；

##### 7、类型转换

+ 自动类型转换

  + 整型、实型（常量）、字符型数据可以混合运算。运算中，不同类型的数据先转化为同一类型，然后进行运算。

  + 转换由低级到高级：**byte,short,char—> int —> long—> float —> double** 

  + 数据类型转换必须满足如下规则：

  + 1. **不能对boolean类型进行类型转换**。

  + 2. 不能把对象类型转换成不相关类的对象。

  + 3. 在把容量大的类型转换为容量小的类型时必须使用强制类型转换。

  + 4. 转换过程中可能导致溢出或损失精度浮点数到整数的转换是通过舍弃小数得到，而不是四舍五入

    + 5. 浮点数到整数的转换是通过**舍弃小数**得到，而不是四舍五入

+ 强制类型转换

  + 把一个表示***数据范围大的数值***或者变量赋值给另一个**表示数据范围小**的变量
  + 格式：**目标数据类型 变量名 = （目标数据类型）指或者变量**

#### 1.3 运算符

##### 1、算数运算符

+ **前缀自增自减法(++a,--a)**：先进行自增或者自减运算，再进行表达式运算

+ **后缀自增自减法(a++,a--)**：先进行表达式运算，再进行自增或者自减运算

##### 2、关系运算符

+ ==、!=、>、<、>=、<=

##### 3、位运算符

```java
A = 0011 1100 //60
B = 0000 1101 //13
-----------------
A&B = 0000 1100
A | B = 0011 1101
A ^ B = 0011 0001
~A= 1100 0011
```

<img src="C:\Users\17487\AppData\Roaming\Typora\typora-user-images\image-20220703200843223.png" alt="image-20220703200843223" style="zoom:67%;" />

##### 4、逻辑运算符

##### 5、赋值运算符

##### 6、其他运算符

条件运算符：**三元运算符（?:）**，该运算符有3个操作数，并且需要判断布尔表达式的值。该运算符的主要是决定哪个值应该赋值给变量

```java
variable x = (expression) ? value if true : value if false
```

##### 7、运算符优先级

运算符等级由高到低依次为：

<img src="C:\Users\17487\AppData\Roaming\Typora\typora-user-images\image-20220703201620693.png" alt="image-20220703201620693" style="zoom: 80%;" />

#### 1.4 循环结构

##### **1、while** 循环

只要布尔表达式为 true，循环就会一直执行下去。

```java
while( 布尔表达式 ) {
  //循环内容
}
```

##### **2、do…while** 循环

对于 while 语句而言，如果不满足条件，则不能进入循环。但有时候我们需要即使不满足条件，也至少执行一次。

```java
do {
       //代码语句
}while(布尔表达式);
```

##### **3、for** 循环

for循环执行的次数是在执行前就确定的

```java
for(初始化; 布尔表达式; 更新) {
    //代码语句
}
```

**for-each循环**

JDK 1.5 引进了一种新的循环类型，被称为 For-Each 循环或者加强型循环，它**能在不使用下标的情况下遍历数组**。

```
for(type element: array)
{
    System.out.println(element);
}
```



##### 4、break

break 主要用在循环语句或者 switch 语句中，用来跳出整个语句块。

break 跳出最里层的循环，并且继续执行该循环下面的语句。

##### 5、continue

continue 适用于任何循环控制结构中。作用是让程序立刻跳转到下一次循环的迭代。

在 for 循环中，continue 语句使程序立即跳转到更新语句。

在 while 或者 do…while 循环中，程序立即跳转到布尔表达式的判断语句。

#### 1.5 条件语句

##### 1、if语句

```
if(布尔表达式)
{
   //如果布尔表达式为true将执行的语句
}
```

```
if(布尔表达式){
   //如果布尔表达式的值为true
}else{
   //如果布尔表达式的值为false
}
```

```
if(布尔表达式 1){
   //如果布尔表达式 1的值为true执行代码
}else if(布尔表达式 2){
   //如果布尔表达式 2的值为true执行代码
}else if(布尔表达式 3){
   //如果布尔表达式 3的值为true执行代码
}else {
   //如果以上布尔表达式都不为true执行代码
}
```

##### 2、switch语句

**switch case 执行时，一定会先进行匹配，匹配成功返回当前 case 的值，再根据是否有 break，判断是否继续输出，或是跳出判断。**

```java
switch(expression){
    case value :
       //语句
       break; //可选
    case value :
       //语句
       break; //可选
    //你可以有任意数量的case语句
    default : //可选
       //语句
}
```

+ switch 语句中的变量类型可以是： byte、short、int 或者 char。case 标签必须为字符串常量或字面量
+ 当变量的值与 case 语句的值相等时，那么 case 语句之后的语句开始执行，直到 break 语句出现才会跳出 switch 语句。case 语句不必须要包含 break 语句。如果没有 break 语句出现，程序会继续执行下一条 case 语句，直到出现 break 语句。
+ switch 语句可以包含一个 **default 分支**，default 在没有 case 语句的值和变量值相等的时候执行。default 分支不需要 break 语句。

#### 1.6 数组

##### 1、一维数组

声明数组变量+创建数组：java使用new操作符来创建数组

```java
dataType[] arrayRefVar = new dataType[arraySize];   //首选
dataType[] arrayRefVar = {value0, value1, ..., valuek};
```

数组作为返回值参数

```java
public static void printArray(int[] array) {
  for (int i = 0; i < array.length; i++) {
    System.out.print(array[i] + " ");
  }
}
//调用
printArray(new int[]{3, 1, 2, 6, 4, 2});
```

数组作为函数的返回值

```java
public static int[] reverse(int[] list) {
  int[] result = new int[list.length];
 
  for (int i = 0, j = result.length - 1; i < list.length; i++, j--) {
    result[j] = list[i];
  }
  return result;
}
```

##### 2、多维数组

即数组的数组

初始化

```java
type[][] typeName = new type[typeLength1][typeLength2];
```

##### 3、Arrays类

java.util.Arrays 类能方便地操作数组，它提供的所有方法都是静态的。具有以下功能：

- 给数组赋值：通过 fill 方法。
- 对数组排序：通过 sort 方法,按升序。
- 比较数组：通过 equals 方法比较数组中元素值是否相等。
- 查找数组元素：通过 binarySearch 方法能对排序好的数组进行二分查找法操作。

#### 1.7 正则表达式

定义了字符串的模式，可以用来搜索、编辑或处理文本

#### 1.8 Java方法

```java
修饰符 返回值类型 方法名(参数类型 参数名){
    ...
    方法体
    ...
    return 返回值;
}
```

<img src="C:\Users\17487\AppData\Roaming\Typora\typora-user-images\image-20220704221616666.png" alt="image-20220704221616666" style="zoom:80%;" />

**方法的重载**：一个类的两个方法拥有相同的名字，但是有不同的参数列表

#### 1.9 Stream、File、IO

java包：Java.io



### 二、面向对象

#### 2.1类

##### 1、Number&Math类

##### 2、string类

```
//创建字符串
String s1 = "Runoob";              // String 直接创建
String s2 = "Runoob";              // String 直接创建
String s3 = s1;                    // 相同引用
String s4 = new String("Runoob");   // String 对象创建
String s5 = new String("Runoob");   // String 对象创建
```

+ 字符串长度： length() 方法，它返回字符串对象包含的字符数。

+ 连接字符串：concat()或“+”

#### 2.2 继承

+ 继承就是子类继承父类的特征和行为，使得子类对象（实例）具有父类的实例域和方法，
+ 或子类从父类继承方法，使得子类具有父类相同的行为。

```java
class 父类 {
}
 
class 子类 extends 父类 {
}
```

继承的特性

- 子类拥有父类非 private 的属性、方法。
- 子类可以拥有自己的属性和方法，即子类可以对父类进行扩展。
- 子类可以用自己的方式实现父类的方法。
- Java 的继承是单继承（一个子类只能有一个父类），但是可以多重继承

+ 提高了类之间的耦合性

关键字

+ extends：只能继承一个类

+ implements：

+ **super**：通过super关键字来实现对父类成员的访问，用来引用当前对象的父类

+ **this**：指向自己的引用

+ final：修饰变量（包括类属性、对象属性、局部变量和形参）、方法（包括类方法和对象方法）和类。

  + 使用 final 关键字声明类，就是把类定义定义为最终类，不能被继承，
  + 或者用于修饰方法，该方法不能被子类重写
  + **注：** final 定义的类，其中的属性、方法不是 final 的。


```java
//声明类
final class 类名 {//类体}
//声明方法
修饰符(public/private/default/protected) final 返回值类型 方法名(){//方法体}
```

#### 2.3 重写(Override)与重载(Overload)

+ 重写是**子类对父类**的允许访问的方法的实现过程进行重新编写, 返回值和形参都不能改变。**即外壳不变，核心重写！**

+ 重载是在**一个类**里面，方法名字相同，而参数不同。返回类型可以相同也可以不同。每个重载的方法（或者构造函数）都必须有一个独一无二的参数类型列表。

+ 方法重载是一个类的多态性表现,而方法重写是子类与父类的一种多态性表现。

+ 重写与重载之间的区别


|  区别点  | 重载方法 |                    重写方法                    |
| :------: | :------: | :--------------------------------------------: |
| 参数列表 | 必须修改 |                  一定不能修改                  |
| 返回类型 | 可以修改 |                  一定不能修改                  |
|   异常   | 可以修改 | 可以减少或删除，一定不能抛出新的或者更广的异常 |
|   访问   | 可以修改 |     一定不能做更严格的限制（可以降低限制）     |

#### 2.4 多态

+ 同一个行为具有多个不同表现形式或形态的能力
+ 多态的优点：消除类型之间的耦合关系、可替换性、可扩充性、接口性、灵活性、简化性
+ 注意事项
  + 多态是方法的多态，属性没有多态
  + 父类和子类之间，类型转换ClassCastException
  + 多态存在的三个必要条件：继承、方法重写、**父类引用指向子类对象：Parent p = new Child();**


#### 2.5 抽象类

+ 在 Java 中抽象类表示的是**一种继承关系**，一个类只能继承一个抽象类，而一个类却可以实现多个接口
+  abstract class 来定义抽象类
+ 抽象类中不一定包含抽象方法，但是有抽象方法的类必定是抽象类。
+ 抽象类中的抽象方法只是声明，不包含方法体，就是不给出方法的具体实现也就是方法的具体功能。
+ 构造方法，类方法（用 static 修饰的方法）不能声明为 抽象方法。
+ **抽象类的子类必须给出抽象类中的抽象方法的具体实现，除非该子类也是抽象类。**
+ 特点：
  + **抽象类不能被实例化new**，如果被实例化，就会报错，编译无法通过。只有**抽象类的非抽象子类可以创建对象**。
  + 抽象类中可以写普通方法
  + 抽象方法必须在抽象类中


#### 2.6 封装

+ 修改属性的可见性来限制对属性的访问（一般限制为private）
+ 对每个值属性提供对外的公共方法访问，也就是创建一对赋取值方法，用于对私有属性的访问

#### 2.7 接口

+ **约束**
+ 定义一些方法，让不同的人实现
+ 接口通常以**interface来声明**
+ 接口无法被实例化，但是可以被实现。一个实现接口的类，**必须实现接口内所描述的所有方法**，否则就必须声明为抽象类。
+ 接口有以下特性：
  - 接口是隐式抽象的，当声明一个接口的时候，不必使用**abstract**关键字。
  - 接口中每一个方法也是隐式抽象的，声明时同样不需要**abstract**关键字。
  - 接口中的方法都是公有的。

```java
//接口的声明
[可见度] interface 接口名称 [extends 其他的接口名] {
        // 声明变量 
        // 抽象方法
}
```

+ 类使用**implements关键字**实现接口
+ 一个类可以同时实现多个接口。
+ 一个类只能继承一个类，但是能实现多个接口。
+ 一个接口能继承另一个接口，这和类之间的继承比较相似。

```java
...implements 接口名称[, 其他接口名称, 其他接口名称..., ...] ...
```

+ 在Java中，类的多继承是不合法，但接口允许多继承。

#### 2.8 枚举

+ Java 枚举类使用 enum 关键字来定义，各个常量使用逗号 **,** 来分割。
+ values() 返回枚举类中所有的值。
+ ordinal()方法可以找到每个枚举常量的索引，就像数组索引一样。
+ valueOf()方法返回指定字符串值的枚举常量。

#### 2.9 java包

+ 为了防止命名冲突，访问控制，提供搜索和定位类（class）、接口、枚举（enumerations）和注释（annotation）等

+ 作用
  + 1、把**功能相似或相关的类或接口**组织在同一个包中，方便类的查找和使用。
  + 2、如同文件夹一样，包也采用了**树形目录**的存储方式。同一个包中的类名字是不同的，不同的包中的类的名字是可以相同的，当同时调用两个不同包中相同类名的类时，应该加上包名加以区别。因此，包可以避免名字冲突。
  + 3、包也**限定了访问权限**，拥有包访问权限的类才能访问某个包中的类。
+ 语法格式

```java
package pkg1[．pkg2[．pkg3…]];

package net.java.util;
public class Something{
   ...
}
```

- **java.lang**-打包基础的类
- **java.io**-包含输入输出功能的函数

#### 2.10 异常

异常的分类

+ 检查性异常

+ 运行时异常
+ 错误error

Error和Exception的区别

+ Error通常是灾难性的致命的错误，是程序无法控制和处理的，当出现这些异常时，java虚拟机一般会选择终止线程
+ Exception通常情况下是可以被程序处理的，并且在程序中应该尽可能的去处理这些异常

异常处理机制

+ 抛出异常

+ 捕获异常

+ 关键字：try、catch、finally、throw、throws

### 三、java高级编程

#### 3.1数据结构

- 枚举（Enumeration）
  
- 位集合（BitSet）
- 向量（Vector）
  - 动态数组
- 栈（Stack）
- 字典（Dictionary）
- 哈希表（Hashtable）
- 属性（Properties）

#### 3.2 注解

概念：

+ JDK5的新特性
+ 说明程序的
+ 使用注解：@注解名称

作用分类

+ 编写文档：生成doc文档
+ 代码分析：使用反射
+ 编译检查：Override

注解的分类

+ 基本内置注解

  + **@Override**：检测该注解标注的方法是否继承自父类（接口）

  + **@Deprecated**：该注解标注的内容，表示已过时

  + **@SuppressWarnings**：压制警告，一般传递参数all


+ 元注解

  + 用于描述注解的注解
  + public @interface 注解名称{}

  - **@Target**：描述注解能够作用的位置
    - ElementType取值
      - TYPE：可以作用于类上
      - METHOD：可以作用于方法上
      - FIELD：可以作用于成员变量上

  - **@Retention**：描述注解被保留的阶段
    - @Retention(Retention.RUNTIME)

  - **@Documented**：描述注解是否被抽取到API文档中

  - **@Inherited**：描述注解是否被子类继承

+ 自定义注解

  + 本质：一个接口，该接口默认继承Annotation接口

    + 属性：在接口中可以定义的成员方法

      + 属性的返回值类型（基本数据类型、String、枚举类型、注解、以上类型的数组）；
      + 定义了属性，需要在使用时给其赋值
        + 如果定义属性时，使用default关键字给属性默认初始化值，则使用注解时，可以不进行属性的赋值；
        + 如果只有一个属性需要赋值，并且属性的名称是value，则value可以省略，直接定义值即可
        + 数组赋值时，值使用{}包裹。如果数组中只有一个值，则{}可以省略


##### 解析注解







