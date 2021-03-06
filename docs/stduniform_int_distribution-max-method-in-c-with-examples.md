# STD::uniform _ int _ distribution max()方法在 C++ 中有示例

> 原文:[https://www . geesforgeks . org/stduniform _ int _ distribution-max-method-in-c-with-examples/](https://www.geeksforgeeks.org/stduniform_int_distribution-max-method-in-c-with-examples/)

C++ 中 **uniform_int_distribution 类**的 **max()** 方法用来得到这个 uniform_int_distribution 可以生成的最大可能值。

**语法:**

```cpp
result_type max() const;

```

**参数:**该方法不接受任何参数。

**返回值:**这个方法返回这个 uniform_int_distribution 中可能产生的最大值。

**例:**

```cpp
// C++ code to demonstrate
// the working of max() function

#include <iostream>

// for uniform_int_distribution function
#include <random>

using namespace std;

int main()
{
    int a = 10, b = 100;

    // Initializing of uniform_int_distribution class
    uniform_int_distribution<int> distribution(a, b);

    // Using max()
    cout << "Max value that can be generated"
         << " by this uniform_int_distribution: "
         << distribution.max() << endl;

    return 0;
}
```

**输出:**

```cpp
Max value that can be generated by this uniform_int_distribution: 100

```

**参考:**[https://en . cppreference . com/w/CPP/numeric/random/uniform _ int _ distribution/max](https://en.cppreference.com/w/cpp/numeric/random/uniform_int_distribution/max)