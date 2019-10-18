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