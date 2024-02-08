# 快速注释

先用方向键将光标调到某一行， 然后按shift键加方向键选中多行。再接着按ctrl键和/键快速注释

# 输出

1.

```Java
System.out.println("2+3"+2+3);//输出2+3=23
System.out.println("2+3"+(2+3));//输出2+3=5
System.out.println(2+3+"="+(2+3));//输出5=5
System.out.println(2+3+"=2+3");//输出5=2+3
```

2.System.out.printf**ln**()打印完会**换行**，System.out.printf()打印完不换行

# 变量

变量名是一种标识符，只能由英文字母、数字、下划线组成，且数字不能放在首位

# 常量

java定义整型常量,例如：final int a=100;

# 数据类型

```Java
package demo;
import java.util.Scanner;
public class demo{
  public static void main(String[] args){
    Scanner in=new Scanner(System.in);
    double a=in.nextInt();
    System.out.print(a);
  }
}
```

运行这段代码输入1，会得到1.0，整数会被转化成浮点数

# 比较

1.

```Java
package demo;
import java.util.Scanner;
public class Main{
  public static void main(String[] args){
    Scanner in=new Scanner(System.in);
    int a=in.nextInt();
    System.out.println(a>10);
  }
}
```

若输入的数大于10，输出ture，否则输出false

2.对于**`System.out.println(5>3==6>4);`**Java会先计算5>3和6>4，两式都为ture，ture==ture，所以打印输出ture

3.对于**`System.out.println(6>5>4);`**Java会先计算6>5，结果为ture，然后比较ture和4的大小，无法比较，Java会报错

# 数组

## 1.基本的数组声明方式

Java中数组大小可以用**常量**或**赋值的变量**表示，如

```Java
package demo;
import java.util.*;
public class Main{
	public static void main(String[] args)
	{
		Scanner in=new Scanner(System.in);
		int n=in.nextInt();
		int[] arr=new int[n];//最基本的声明,使用变量
		Arrays.fill(arr,-2);
		for(int i=0;i<n;i++)
		{
			System.out.print(arr[i]+" ");
		}
	}
}
```

但是C++中数组大小只能用**常量**或**常量表达式**表示。

## 2.其他数组声明方式

```Java
int[] arr=new int[] {0,1,2,3};//不显式的声明数组的容量
int[] arr={0,1,2,3};//不用new的方法
```

## 3.初始化数组

用`Arrays.fill(数组名,初始化数值);`，需使用`java.util.Arrays`类,或者`import java.util.*;`

## 4.数组长度

数组变量名.length,如`arr.length`

## 5.数组变量

### (1).数组变量的赋值

```Java
int[] a=new int[10];
a[0]=5;
int[] b=a;//数组变量之间的赋值是管理权限的赋予
b[0]=16;
System.out.print(a[0]);//输出结果16
```

      第一行int[] a=new int[10];是声明一个变量名为a的数组变量和一个长度为10的数组，变量a是数组的管理者。

      第二行是通过管理者a让数组编号为0的单元变成5。

      第三行将数组a在内存中的地址赋值给数组变量b，这样b和a就指向了同一数组，所以b就是该数组另一管理者了。

      第四行通过b将数组编号为0的单元变成16。

      第五行通过a读取输出了数组编号为0的单元中的16。

### (2).数组变量的比较

数组变量的比较即判断是否管理同一数组

```Java
package demo;
import java.util.*;
public class Main{
public static void main(String[] args){
int[] a=new int[10];
  int[] b=a;
  System.out.print(a==b);//输出ture
}
}
```

另一例：

```Java
package demo;
import java.util.*;
public class Main{
public static void main(String[] args){
int[] a={0，1，2};
  int[] b={0，1，2};
  System.out.print(a==b);//输出false
}
}
```

尽管两数组内容相同，但并非同一数组

### (3).复制数组

如果想将一数组的元素赋值给二数组，只能用循环遍历一数组，将每一元素复制给二数组

