---
tags:
- Binary Search
---

#### Binary Search 常用技巧总结

##### 注意事项

- 溢出： 取值时候需要防止溢出
- 边界错误：需要注意的是，循环体外的初始化条件，循环体内部的迭代步骤，都必须遵循一致的区间规则
- 死循环：错误的边界，使得不能从循环中正确退出。

##### 第一类：需要查找的值和目标值完全相同

- 写法一： 左闭右开区间: 注意right取值始终是在范围之外的值

```python
def find(arr, target):
  left, right = 0, len(arr)
  while left < right:
    mid = left + (right - left)//2
    if arr[mid] == target: 
      return mid
    elif arr[mid] < target:
      left = mid + 1
    else:
      right = mid
  return -1
```

- 写法二： 全部闭区间：注意right取值在范围之内

```python
def find(arr, target):
  left, right = 0, len(arr) - 1
  while left <= right:
    mid = left + (right - left)//2
    if arr[mid] == target:
      return mid
    elif arr[mid] < target:
      left = mid + 1
    else:
      right = mid - 1
  return -1
```

##### 第二类：查找第一个不小于目标值的位置，或者查找最后一个小于目标值的位置

> 需要查找的数值在数组中并不一定出现，或者出现但是并不一定唯一。

```python
def binarysearch(arr, target):
  left, right = 0, len(arr)
  while left < right:
    mid = left + (right - left) // 2
    if arr[mid] < target:
      left = mid + 1
    else:
      right = mid
  return right
```

> 变形只需要修改返回值，返回right-1 即可

##### 第三类：查找第一个大于目标值的数，可以变形为查找最后一个不大于目标值的数

```python
def binarysearch(arr, target):
  left, right = 0, len(arr)
  while left < right:
    mid = left + (right - left) // 2
    if arr[mid] <= target:
      left = mid + 1
    else:
      right = mid
  return right
```

##### Reference

- https://www.cnblogs.com/grandyang/p/6854825.html
- https://blog.csdn.net/yefengzhichen/article/details/52372407
- https://segmentfault.com/a/1190000016825704
- https://www.1point3acres.com/bbs/thread-432793-1-1.html