2.1-1  
略  

2.1-2  
```c++
#include <iostream>
using namespace std;
void insertion_sort(int* a, int size)
{
	for (int i = 1; i < size; ++i)
	{
		int key = a[i];
		int j = i - 1;
		while (j >= 0 && a[j] < key)
		{
			a[j + 1] = a[j];
			j = j - 1;
		}
		a[j + 1] = key;
	}
}
int main()
{
	int a[5] = { 5, 34, 234, 12, 4 };
	insertion_sort(a, 5);
	for (int i = 0; i < 5; ++i)
		cout << a[i] << " ";
	cout << endl;
	return 0;
}
```

2.1-3
```c++
const int nil = -1;
int linear_finding(int* a, int size, int v)
{
	for (int i = 0; i < size; ++i)
		if (a[i] == v)
			return i;
	return nil;
}
```

2.1-4
```c++
int* binary_adding(int* a, int* b, int size)
{
	int* c = new int[size + 1];
	int carry = 0;
	for (int i = size - 1; i >= 0; --i)
	{
		c[i + 1] = (a[i] + b[i] + carry) % 2;
		carry = (a[i] + b[i] + carry) / 2;
	}
	c[0] = carry;
	return c;
}
```

2.2-1  
$\theta$($n^3$)  

2.2-2
```c++
void selection_sort(int* a, int size)
{
	for (int j = 0; j < size - 1; ++j)
	{
		int min = j;
		for (int i = j + 1; i < size; ++i)
			if (a[min] > a[i])
				min = i;
		int temp = a[min];
		a[min] = a[j];
		a[j] = temp;
	}
}
```
初始化：初始化时数组为空，无需证明  
保持：遍历A[j……A.length]寻找到最小的数，与A[j]互换，此时，A[1……j]为有序  
终止：当j=A.length时，循环退出，因为最后一次比较确定了最后两个元素的顺序，所以此时整个数组有序
    
Q:为什么它只需要对前n-1个元素运行?  
A:因为第n-1次时，比较了最后两个元素的大小，确定n-1处的元素，自然整个数组已经有序  
  
最坏和最好情况都是$\theta$($n^2$)  
  
2.2-3  
暂时不答  
  
2.2-4  
不会  