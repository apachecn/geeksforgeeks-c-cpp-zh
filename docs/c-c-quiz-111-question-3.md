# C 小测验–111 |问题 3

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-111-question-3/](https://www.geeksforgeeks.org/c-c-quiz-111-question-3/)

为以下内容选择最佳陈述:

```cpp
int arr[50] = {0,1,2,[47]=47,48,49};
```

**(A)** 这在 C 语言中是不允许的，会产生编译错误
**(B)** 按照标准这在 C 语言中是允许的。基本上，它会将 arr[0]、arr[1]、arr[2]、arr[47]、arr[48]和 arr[49]分别初始化为 0、1、2、47、48 和 49。数组的剩余元素将被初始化为 0。

**回答:** **(B)**

**说明:**在 C 语言中，对选中的元素也可以进行数组初始化。默认情况下，初始值设定项从第 0 个元素开始。数组中的特定元素可以由[]指定。应该注意的是，剩余的元素(即数组初始化中没有提到的元素)将被初始化为 0。例如，“int arr[10] = {100，[5]=100，[9]=100}”在 c 语言中也是合法的。这将 arr[0]，arr[5]和 arr[9]初始化为 100。所有剩余的元素都是 0。

[本题小考](https://www.geeksforgeeks.org/c-quiz-111-gq/)