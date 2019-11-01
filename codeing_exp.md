堆排序的下标处理
```c++
#include <iostream>
using namespace std;
int parent(int* a, int index)
{
	return a[(index - 1) / 2];
}
int Lchild(int* a, int index)
{
	return a[(index + 1) * 2 - 1];
}
int Rchild(int* a, int index)
{
	return a[(index + 1) * 2];
}
int main()
{
	int a[7];
	for (int i = 0; i < 7; ++i)
		a[i] = i;
	cout << parent(a, 5) << " " << parent(a, 6) << endl;
	cout << Lchild(a, 1) << " " << Rchild(a, 1) << endl;
	system("pause");
	return 0;
}
```