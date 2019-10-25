**Exercise 2.1-1**  
略  

**Exercise 2.1-2**  
```c++
insertion_sort(A)
for j = 2 to A.length
	key = A[j]
	i = j - 1
	while i > 0 and A[i] < key
		A[i + 1] = A[i]
		i = i + 1
	A[i + 1] = key
```

**Exercise 2.1-3**
```c++
LINEAR_SEARCHING(A, V)
	for (i = 1 to A.length)
		if A[i] == v
			return i
	return nil
```
循环不变式：A[1……i - 1]中没有V
初始化：i = 1时，A为空数组，无需证明
保持：对于A[i]之前的所有元素，如若相等，就已经返回了，所以A[1……i - 1]中没有V
终止：当i = A.length + 1时，退出循环，表示数组没有元素V，既返回nil

**Exercise 2.1-4**
```c++
binary_adding(A, B)
C是一个新数组，大小为A.size + 1
carry = 0
for i = A.length downto 1
	C[i + 1] = (A[i] + B[i] + carry) % 2
	carry = (A[i] + B[i] + carry) / 2
C[0] = carry
return C
```

**Exercise 2.2-1**  
$\theta$($n^3$)  

**Exercise 2.2-2**
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
  
**Exercise 2.2-3**  
暂时不答  
  
**Exercise 2.2-4**  
不会  