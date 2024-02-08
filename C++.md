# long long int

```C++

#include<bits/stdc++.h>
#define int long long
const int maxn=1e5+10;
int arr[maxn],d[maxn];
signed main(){
    int n,num=0,sum=0;
    cin>>n;
    for(int i=1;i<=n;i++)
    {
        cin>>arr[i];
        d[i]=arr[i]-arr[i-1];
    }
    for(int i=2;i<=n;i++)
    {
        if(d[i]>0) num+=d[i];
        else sum+=-d[i];
    }
    cout<<max(num,sum)<<endl;
    return 0;
}
```

此处#define int long long是将 int 类型定义为 long long 类型，是为了使 int 类型的变量能够存储更大的数值范围。

这段代码中的 `signed` 是指定 `main` 函数的返回类型为 `signed int`。

# 判断质数的两种方法

```C++
#include <bits/stdc++.h>
using namespace std;
int main()
{
  int m,i;
  cin>>m;
  for(i=2;i*i<=m;i++)
    if(m%i==0) break;
  if(i*i>m) cout<<"YES"<<endl;//说明不是因为break退出循环的，而是自然退出循环，即为素数
  else cout<<"NO"<<endl;
}
```

```C++
#include <bits/stdc++.h>
using namespace std;
int main()
{
  int m,i,flag=0;
  cin>>m;
  for(i=2;i<=m/2;i++)
    if(m%i==0) 
    {
      flag++;
      break;
    }
  if(flag==0) cout<<"YES"<<endl;//说明不是因为break退出循环的，而是自然退出循环，即为素数
  else cout<<"NO"<<endl;
}
```

# !变量

```C++
#include "bits/stdc++.h"
using namespace std;
int main()
{
	int i = 1, m = 0;
		if (!m)
		{
			m = m + 10;
		}
	printf("m=%d", m);
	return 0;
}
//结果为m=10
```

若m为非0或者为真，那么!m为假，所以不执行if里的语句。

若m为0或者为假，那么!m为真，所以执行if里的语句。

# break和continue

break可以用在switch和循环语句（for while和 do while)中，它的作用是跳出当前的结构（距离最近的那个），终止该结构内的语句执行。continue只能用在循环语句中，它的作用是跳过当前循环结构的剩余语句，直接进入下一次循环的判断，如果条件成立，就继续循环

```C++
#include "stdio.h"
void main()
{
	char c;
	while ((c = getchar()) != '\n')
	{
		switch (c)
		{
		case  'I':  break;
		case  'L':  continue;
		default:   putchar(c);  continue;
		}
		putchar('1');
	}
	putchar('2');
}
```

上例中，break用于跳出当前最近的switch结构，而不是while结构，而continue只能作用与循环结构，所以它跳出的是while语句，直接进入下一次循环的判断。

# 函数

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

如果将fun函数的定义放在main函数前面，就不需要声明一个fun函数，即void fun(void);这行代码可以删去。

fun函数中if的条件成立，使得a被赋值为2，但是只在if的{}内起作用，在{}外a仍然为1。



# 关于scanf

```C
#include<stdio.h>

int main() {

	char str[6];

	scanf("%5s", str);//读取五个字符到str中

	printf("%s", str);//输出str中所有内容

	return 0;

}

/*

使用%5s可以读取完整的字符串，

但是s前的数值不超过数组大小6，即最大5;

若scanf中不用%5s而用%s则str存储的是字符串首元素

*/
```

# n++与++n

```C++
int x=100+(n++);//x先等于100加n，n再加1
int x=100+(++n);//n先加1，x再等于100加n
```

# 四舍五入

```C++
int x;
cin>>x;
int n=(int)(x+0.5);
```

# 调用函数比大小

方法一（在自定义函数里输出结果）

```C++
#include <bits/stdc++.h>
using namespace std;
void max(int a, int b)
{
	int ret;
	if (a > b) ret = a;
	else ret = b;
	cout << ret << endl;
}
int main() {
	max(5, 6);
	max(8, 9);
}
```

方法二（在main函数里输出结果）

```C++
#include <bits/stdc++.h>
using namespace std;
int max(int a, int b)
{
	int ret;
	if (a > b) ret = a;//不使用return a；
	else ret = b;//不使用return b；原因是不方便维护，应单一return
	return ret;
}
int main() {
	cout << max(5, 6) << endl;
	cout << max(8, 9) << endl;
}
```

# 字符串

```C++
#include <bits/stdc++.h>
using namespace std;
string a, b;//重点
int ans = 1, num = 1;
int main() {
	cin >> a >> b;
	for (int i = 0; i < a.length(); i++)
		ans *= a[i] - '@';
	for (int i = 0; i < b.length(); i++)
		num *= b[i] - '@';
	ans %= 47;
	num %= 47;
	if (ans==num) {
		cout << "GO";
	}
	else cout << "STAY";
	return 0;
}

```

**a.length()**表示字符串a的长度；**a[i]**表示字符串中第i个字符

# sort函数

```C++
#include<bits/stdc++.h>
using namespace std;
int arr[9] = { 1,2,3,6,5,4,7,8,9 };
int main()
{
    sort(arr, arr+9);//sort函数不取最后一位地址对应的数！
    for (int i = 0; i <= 8; i++)
    {
        printf("%d", arr[i]);
    }
}
```

#include "bits/stdc++.h"
using namespace std;

