**Exercise 2.1-1**  
<31, 41, 59, 26, 41, 58>
<31, 41, 59, 26, 41, 58>
<31, 41, 59, 26, 41, 58>
<26, 31, 41, 59, 41, 58>
<26, 31, 41, 41, 59, 58>
<26, 31, 41, 41, 58, 59>

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
循环不变式：在for循环迭代之前，数组A[1···i - 1]是由A中最小的i-1个元素组成的一个有序数组
    
Q:为什么它只需要对前n-1个元素运行?  
A:因为第n-1次时，比较了最后两个元素的大小，确定n-1处的元素，自然整个数组已经有序  
  
最坏和最好情况都是$\theta$($n^2$)  
  
**Exercise 2.2-3**  
平均、最坏情况为$\theta$($n$)  
  
**Exercise 2.2-4**  
不会  
  
**Exercise 2.3-1**  
![sloution](pic/2.3-1.png)
  
**Exercise 2.3-2**  
```c++
merge(A, p, q, r)
n1 = q - p + 1
n2 = r - q
let L[1..n1 + 1] and R[1..n2 + 1] be new arrays
for i = 1 to n1
	L[i] = A[p + i - 1]
for j = 1 to n2
	R[j] = A[q + j]
L[n1 + 1] = INF
R[n1 + 1] = INF
i = 1
j = 1
for k = p to r
	if (L[i] == INF)
		A[k] = R[j]
		j = j + 1
	else if (R[j] == INF)
		A[k] = L[i]	
		i = i + 1
	else if (L[i] < R[j])
		A[k] = L[i]
		i = i + 1
	else
		A[k] = R[j]
		j = j + 1
```
  
**Exercise 2.3-3**  
不会  
  
**Exercise 2.3-4**
```c++
insertion_sort(A, length)
if length == 1
	return
insertion_sort(A, length - 1)
key = A[length]
i = length - 1
while i > 0 and A[i] > key
	a[i + 1] = A[i]
	i = i + 1
A[i + 1] = key
```  
$$
T(n)=\begin{cases}
	\theta(1),\quad n\leq1 \\\\
	T(n - 1) + \theta(n),\quad n > 1
\end{cases}
$$
  
**Exercise 2.3-5**
```c++
binary_search(A, V, left, right)
while left <= right
	mid = (left + right) / 2
	if (A[mid] == V)
		return mid
	else if (A[mid] > v)
		left = mid + 1
	else
		right = mid - 1
return nil
```
  
**Exercise 2.3-6**  
不行，寻找到适合的位置，还要循环右移数组，需要n的时间复杂度，并不会优化插入排序 
  
**Exercise 2.3-7**
暂时8会