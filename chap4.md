**Exercise 4.1-1**
返回最大的负数

**Exercise 4.1-2**
```c++
find-max-sub-array(A)
max-sum = 0
for i = 1 to A.length
    sum = 0
    for (j = i to A.length)
        sum = sum + A[j];
        if sum > max-sum
            max-left = i
            max-right = j
            max-sum = sum
return (max-left, max-right, max-sum)
```

**Exercise 4.1-3**
暂时不答

**Exercise 4.1-4**
设置一个初始最大数组和为0，左右标为0

**Exercise 4.1-5**
不会