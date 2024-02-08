# 1.

```C++
#include<bits/stdc++.h>
using namespace std;
	void fun(void);//声明一个fun函数
	int main(void){
		fun();
		return 0;
	}
	void fun(void) {
		int a = 1;
		if (a == 1) {
			int a = 2;
		}
		cout << a << endl;
	}
```

如果将fun函数的定义放在main函数前面，就不需要声明一个fun函数，即void fun(void);一行代码可以删去。

fun函数中if的条件成立，使得a被赋值为2，但是只在if的{}内起作用，在{}外a仍然为1。

# 2.实现程序的反复输入

```C++
#include "stdio.h"
int main()
{
	int n, sum;
	while (1)
	{
		scanf("%d", &n);
		if (n == 0) break;
		sum = 0;
		for (int i = 2; i <= n / 2; i++)
		{
			if (n % i == 0) sum++;
		}
		if (sum == 0) printf("%d是素数\n", n);
		else printf("%d不是素数，其有%d个约数\n", n, 2 * sum);
	}
	return 0;
}
```

例如该代码，通过while(1){ }实现的反复输入

# 3.输出菱形

```C++
#include<bits/stdc++.h>
using namespace std;
int main() {
	int k = 5;//2k-1层菱形
	for (int i = 1; i <= k; i++)//控制上半截层数
	{
		for (int j = 1; j <= k - i; j++)//控制空格数
			cout << " ";
		for (int j = 1; j <= 2 * i - 1; j++)//控制*数
			cout << "*";
		cout << endl;
	}
	for (int i = 1; i <= k - 1; i++)//下半截层数
	{
		for (int j = 1; j <= i; j++)//控制空格数
			cout << " ";
		for (int j = 1; j <= 2*(k-i)-1; j++)//控制*数
			cout << "*";
		cout << endl;
	}
	return 0;
}
```





