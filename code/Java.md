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

2.System.out.print**ln**()打印完会**换行**，System.out.print()打印完不换行

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

4.



